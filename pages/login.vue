<template>
  <div
    class="min-h-screen flex flex-col justify-center py-12 sm:px-6 lg:px-8"
    :style="bgStyle"
  >
    <div class="absolute inset-0">
      <div
        class="w-full h-full"
      ></div>
    </div>

    <div class="relative mt-32 sm:mx-auto sm:w-full sm:max-w-md padMobile">
        
      <div class="bg-white py-8 px-4 shadow sm:rounded-lg sm:px-10 borderR">
        <a-alert
          v-if="loginError"
          type="error"
          :message="loginError"
          class="mb-4"
          showIcon
        />
            <div>
            <p class="text-center font-bold text-lg">เข้าสู่ระบบประเมินผลการปฏิบัติงาน</p>
        </div>
        <a-form
          :model="formState"
          @finish="handleSubmit"
          layout="vertical"
          class="space-y-6"
          requiredMark="optional"
        >
          <a-form-item
            label="รหัสพนักงาน"
            Placeholder="รหัสพนักงาน"
            name="username"
            :rules="[{ required: true, message: 'กรุณากรอกชื่อผู้ใช้' }]"
          >
            <a-input v-model:value="formState.username" size="large" />
          </a-form-item>
          <a-form-item
            label="รหัสผ่าน"
            Placeholder="รหัสผ่าน"
            name="password"
            :rules="[{ required: true, message: 'กรุณากรอกรหัสผ่าน' }]"
          >
            <a-input-password v-model:value="formState.password" size="large" />
          </a-form-item>

          <a-form-item>
            <a-button
              
              html-type="submit"
              class="w-full bg-red-600 hover:bg-red-700 text-white border-none"
              size="large"
              color="red"
              :loading="loading"
            >
              เข้าสู่ระบบ
            </a-button>
          </a-form-item>

          
        </a-form>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, reactive, computed } from 'vue'
import { useRouter } from 'vue-router'
import axios from 'axios'
import bgImage from '../asset/images/login-bg.png'
definePageMeta({
  layout: 'blank'
})
const router = useRouter()
const loading = ref(false)
const loginError = ref('')

const formState = reactive({
  username: '',
  password: '',
})

const bgStyle = computed(() => ({
  backgroundImage: `url(${bgImage})`,
  backgroundSize: 'cover',
  backgroundPosition: 'center',
}))

const handleSubmit = async () => {
  loading.value = true
  loginError.value = ''

  try {
    // ส่งข้อมูลไปยัง API
    const response = await axios.post('https://your-api-endpoint/login', {
      username: formState.username,
      password: formState.password,
    })
    
    // ตรวจสอบผลลัพธ์จาก API
    if (response.data.success) {
      // หากเข้าสู่ระบบสำเร็จ
      const userPermission = response.data.permission // สมมุติว่า API ส่งค่าผลลัพธ์ permission มา

      // เช็ค permission และไปยังหน้าตามที่กำหนด
      if (userPermission === 'staff') {
        router.push('/self_performance')
      } else {
        router.push('/')
      }
    } else {
      // หากข้อมูลการล็อกอินผิดพลาด
      loginError.value = 'เกิดข้อผิดพลาดในการเข้าสู่ระบบ'
    }
  } catch (error) {
    loginError.value = 'เกิดข้อผิดพลาดในการเข้าสู่ระบบ'
    console.error('Login error:', error)
  } finally {
    loading.value = false
  }
}
</script>
<style scoped>
@media (max-width: 480px) {
.padMobile{
  padding: 30px;
}
}
.borderR{
    border-radius: 3%;
}
</style>
