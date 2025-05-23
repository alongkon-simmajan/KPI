<template>
  <div class="min-h-screen bg-gray-100">
     <!-- <div class ="py-6 px-4">
    <div class="w-full bg-white rounded-lg p-4 shadow-sm">
    <div class="flex flex-wrap -mx-2">
      <a-col class="px-2 mb-4 w-full " :xs="{ span: 24 }" :md="{ span: 4 }" :lg="{ span: 4 }">
        <div class="text-sm text-gray-600 mb-1">ปีงบประมาณ</div>
        <a-select v-model:value="selectedYear" option="" class="w-full">
          <a-select-option value="2567">2567</a-select-option>
          <a-select-option value="2566">2566</a-select-option>
          <a-select-option value="2565">2565</a-select-option>
        </a-select>
    </a-col>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6">
        <div class="text-sm text-gray-600 mb-1">ไตรมาส</div>
        <a-select v-model:value="selectedPeriod" class="w-full">
          <a-select-option value="1">1</a-select-option>
          <a-select-option value="2">2</a-select-option>
          <a-select-option value="3">3</a-select-option>
          <a-select-option value="4">4</a-select-option>
        </a-select>
      </div>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6">
        <div class="text-sm text-gray-600 mb-1">หัวข้อค้นหา</div>
        <a-select v-model:value="selectedCategory" class="w-full">
          <a-select-option value="all">ทั้งหมด</a-select-option>
          <a-select-option value="project">โครงการ</a-select-option>
          <a-select-option value="budget">งบประมาณ</a-select-option>
        </a-select>
      </div>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6">
        <div class="text-sm text-gray-600 mb-1">ค้นหา</div>
        <a-input v-model:value="searchText" placeholder="ค้นหา" class="w-full">
          <template #prefix>
            <search-outlined />
          </template>
        </a-input>
      </div>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6">
        <div class="text-sm text-gray-600 mb-1">บริษัท</div>
        <a-select v-model:value="selectedOrganization" class="w-full">
          <a-select-option value="all">ทั้งหมด</a-select-option>
          <a-select-option value="org1">บริษัท A</a-select-option>
          <a-select-option value="org2">บริษัท B</a-select-option>
        </a-select>
      </div>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6">
        <div class="text-sm text-gray-600 mb-1">ส่วนงาน</div>
        <a-select v-model:value="selectedDepartment" class="w-full">
          <a-select-option value="all">ทั้งหมด</a-select-option>
          <a-select-option value="dept1">ฝ่ายบัญชี</a-select-option>
          <a-select-option value="dept2">ฝ่ายไอที</a-select-option>
        </a-select>
      </div>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6">
        <div class="text-sm text-gray-600 mb-1">แผนงาน</div>
        <a-select v-model:value="selectedPlan" class="w-full">
          <a-select-option value="all">ทั้งหมด</a-select-option>
          <a-select-option value="plan1">แผนงาน A</a-select-option>
          <a-select-option value="plan2">แผนงาน B</a-select-option>
        </a-select>
      </div>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6">
        <div class="text-sm text-gray-600 mb-1">สถานะ</div>
        <a-select v-model:value="selectedStatus" class="w-full">
          <a-select-option value="all">ทั้งหมด</a-select-option>
          <a-select-option value="active">กำลังดำเนินการ</a-select-option>
          <a-select-option value="completed">เสร็จสิ้น</a-select-option>
        </a-select>
      </div>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6 flex items-end">
        <a-button class="mr-2 flex items-center" @click="resetFilters">
          <template #icon><sync-outlined /></template>
          รีเซ็ต
        </a-button>
      </div>

      <div class="px-2 mb-4 w-full sm:w-1/2 md:w-1/4 lg:w-1/6 flex items-end">
        <a-button type="primary" class="w-full bg-red-600 hover:bg-red-700" @click="search">
          <template #icon><search-outlined /></template>
          ค้นหา
        </a-button>
      </div>
    </div>
  </div>
  </div>

    <div class="container mx-auto py-6 px-4 over-flow-auto">
       <a-row :gutter="[10,10]">
      <a-col :xs="{ span: 24 }" :md="{ span: 6 }" :lg="{ span: 6 }">
        <a-card hoverable class="bg-white">
          <template #cover>
            <div class="p-4 flex justify-between items-center">
              <div>
                <p class="text-gray-500">Total Revenue</p>
                <p class="text-2xl font-bold">$24,680</p>
                <p class="text-green-500 text-sm">
                  <ArrowUpOutlined /> 12% from last month
                </p>
              </div>
              <div class="bg-blue-100 p-3 rounded-full">
                <DollarOutlined style="font-size: 24px; color: #1890ff" />
              </div>
            </div>
          </template>
        </a-card>
        </a-col>
         <a-col :xs="{ span: 24 }" :md="{ span: 12 }" :lg="{ span: 12 }">
        <a-card hoverable class="bg-white">
          <template #cover>
            <div class="p-4 flex justify-between items-center">
              <div>
                <p class="text-gray-500">New Users</p>
                <p class="text-2xl font-bold">2,845</p>
                <p class="text-green-500 text-sm">
                  <ArrowUpOutlined /> 18% from last month
                </p>
              </div>
              <div class="bg-green-100 p-3 rounded-full">
                <UserAddOutlined style="font-size: 24px; color: #52c41a" />
              </div>
            </div>
          </template>
        </a-card>
        </a-col>

         <a-col :xs="{ span: 24 }" :md="{ span: 6 }" :lg="{ span: 6 }">
        <a-card hoverable class="bg-white">
          <template #cover>
            <div class="p-4 flex justify-between items-center">
              <div>
                <p class="text-gray-500">Active Sessions</p>
                <p class="text-2xl font-bold">1,257</p>
                <p class="text-red-500 text-sm">
                  <ArrowDownOutlined /> 3% from last month
                </p>
              </div>
              <div class="bg-purple-100 p-3 rounded-full">
                <LineChartOutlined style="font-size: 24px; color: #722ed1" />
              </div>
            </div>
          </template>
        </a-card>
      </a-col>
</a-row>
    </div> -->
  </div>
</template>

<script setup>
// import { ref, onMounted } from 'vue';
// import {
//   UserOutlined,
//   DownOutlined,
//   DollarOutlined,
//   UserAddOutlined,
//   LineChartOutlined,
//   BarChartOutlined,
//   ArrowUpOutlined,
//   ArrowDownOutlined
// } from '@ant-design/icons-vue';
// import ApexCharts from 'apexcharts';
// onMounted(() => {
 
// });
</script>