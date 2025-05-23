<template>
    <div>
        <a-layout-header class="bg-white shadow-md flex items-center justify-between">
            <!-- Header - JMT Style -->
            <div class="bg-red-700 shadow-md text-white w-full">
                <div class="container mx-auto flex items-center justify-between h-16">
                    <!-- Left Side - Logo and Menu -->
                    <div class="flex items-center">
                        <!-- JMT Logo -->
                        <div class="flex items-center mr-6">
                            <div class="bg-white rounded-full p-1 mr-2">
                                <img src="../asset/images/logo_jmt.png" alt="JMT" class="h-8 w-8" onerror="this.src='/api/placeholder/40/40'; this.onerror=null;" />
                            </div>
                            <span class="text-sm">network services</span>
                        </div>
                        
                        <!-- Main Menu -->
                        <div class="flex space-x-4">
                            <a href="#" class="flex items-center px-3 py-2 bg-red-800 rounded-md">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
                                </svg>
                                แดชบอร์ด
                            </a>
                            <a href="#" class="flex items-center px-3 py-2">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                                </svg>
                                ประเมินส่วนตัว
                            </a>
                            <a href="#" class="flex items-center px-3 py-2">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
                                </svg>
                                ประเมินพนักงาน
                            </a>
                            <a href="#" class="flex items-center px-3 py-2">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" />
                                </svg>
                                ฟอร์มประเมิน
                            </a>
                            <a href="#" class="flex items-center px-3 py-2">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                                </svg>
                                จัดการข้อมูลบริษัท
                            </a>
                        </div>
                    </div>
                    
                    <!-- Right Side - Notification and Profile -->
                    <div class="flex items-center">
                        <!-- Notification Icon -->
                        <a href="#" class="text-white mr-4 relative">
                            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9" />
                            </svg>
                            <span class="absolute -top-1 -right-1 bg-white text-red-700 rounded-full w-4 h-4 flex items-center justify-center text-xs font-bold">3</span>
                        </a>
                        
                        <!-- User Profile -->
                        <div class="flex items-center">
                            <div class="bg-white rounded-full p-1 mr-2">
                                <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-red-700" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
                                </svg>
                            </div>
                            <div class="text-sm">
                                <div>สุรพล มาลาทอง</div>
                                <div class="text-xs">Admin</div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </a-layout-header>
        <div class="min-h-screen bg-gray-100">
            <NuxtPage />
        </div>
    </div>
</template>

<script setup>
</script>

<style lang="scss" scoped>
</style>