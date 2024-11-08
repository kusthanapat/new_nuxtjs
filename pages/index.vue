<script setup>
    import SmartFarm from '~/assets/images/Smart_Farm.png';
    import iconPath from '~/assets/images/icon_durian.png';
    import iconPath1 from '~/assets/images/กรมส่งเสริมการเกษตร.png';
    import iconPath2 from '~/assets/images/AIC-nontaburi.png';
    import iconPath3 from '~/assets/images/KMUTNB.png';
    import iconPath4 from '~/assets/images/วทอ.png';
    import iconPath5 from '~/assets/images/mechatronics.png';

// definePageMeta({
//     layout: "index-layout"
// })
</script>

<template>
    <nav class="bg-gray-900 p-4">
        <div class="container mx-auto flex justify-between items-center">
        <div class="flex items-center space-x-3">
            <img :src="iconPath" class="w-10 h-10 mx-auto" />
            <a href="/" class="text-white font-bold text-xl">MyDurian</a>
        </div>
        <div class="flex space-x-6 pr-20">
            <NuxtLink  class="nav-link" to="/home">
            <i class="fa fa-home"></i>
            Home
            </NuxtLink>
            <NuxtLink class="nav-link" to="/dashboard">
            <i class="fa fa-file-alt"></i>
            Dashboard
            </NuxtLink>
            <NuxtLink class="nav-link" to="/chart">
            <i class="fa fa-file-alt"></i>
            Chart
            </NuxtLink>
            <NuxtLink class="nav-link" to="/contact">
            <i class="fa fa-file-alt"></i>
            Contact
            </NuxtLink>
            <NuxtLink class="nav-link" to="/login">
            <i class="fa fa-file-alt"></i>
            Login
            </NuxtLink>
        </div>
    </div>
</nav>
  <div class="h-full bg-gradient-to-b from-[#00001a] to-cyan-950 pb-5">
    <div class="w-full justify-between h-full flex pr-64 pl-64">
        <div class="flex-col mt-20">
            <div class="flex justify-between items-center w-auto">
                <img :src="iconPath1" class="size-32">
                <img :src="iconPath2" class="size-32 ml-3">
                <img :src="iconPath3" class="size-32 ml-3">
                <img :src="iconPath4" class="size-32">
                <img :src="iconPath5" class="size-32">
            </div>
            <div class="flex flex-col pt-28">
                <span class="text-4xl text-[#e52802] text-">SMART FARM KMUTNB</span>
                <span class="text-4xl text-green-600 mt-4">โครงการสมาร์ทฟาร์มพัฒนาการเกษตร</span>
            </div>
        </div>
        <div>
            <img src="@/assets/images/sao.png" alt="Smart Farm" class="poster-index ml-12" />
        </div>
    </div>
    <div class="border-t border-gray-700 mt-10 flex justify-between items-start w-screen pl-20 pr-20 pt-16">
        <img src="@/assets/images/post_pic3.jpg" class="show-pic-index ml-28" />
        <span class="text-white text-lg mr-96">KMUTNB</span>
    </div>
  </div>
</template>
