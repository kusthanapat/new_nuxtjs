<script setup>
    import SmartFarm from '~/assets/images/Smart_Farm.png';
    import iconPath from '~/assets/images/icon_durian.png';
    import iconPath1 from '~/assets/images/กรมส่งเสริมการเกษตร.png';
    import iconPath2 from '~/assets/images/AIC-nontaburi.png';
    import iconPath3 from '~/assets/images/KMUTNB.png';
    import iconPath4 from '~/assets/images/วทอ.png';
    import iconPath5 from '~/assets/images/mechatronics.png';
    import iconPath6 from '~/assets/images/IoT.png';
    import iconPath7 from '~/assets/images/SmartFarmer.png';
    import iconPath8 from '~/assets/images/smart_pic_use3.png';

// definePageMeta({
//     layout: "index-layout"
// })

    import { ref, onMounted, onUnmounted } from 'vue';

    const currentSlide = ref(0); // ตั้งค่า slide เริ่มต้นเป็น slide 1
    const totalSlides = 2; // จำนวนสไลด์ทั้งหมด

    // ฟังก์ชันเปลี่ยนสไลด์
    const changeSlide = () => {
    currentSlide.value = (currentSlide.value + 1) % totalSlides;
    };

    // เริ่มการทำงานของสไลด์อัตโนมัติเมื่อ mounted
    onMounted(() => {
    const interval = setInterval(changeSlide, 5000); // เปลี่ยนสไลด์ทุก ๆ 5 วินาที
    onUnmounted(() => {
        clearInterval(interval); // ล้าง interval เมื่อ component ถูกถอดออก
    });
    });
</script>

<template>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.6.0/css/all.min.css" integrity="sha512-Kc323vGBEqzTmouAECnVceyQqyqdsSiqLQISBL29aUW4U/M7pSPA/gEUZQqv1cwx4OnYxTxve5UMg5GT6L4JJg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <nav class="bg-gray-900 p-1 w-full fixed z-10">
        <div class="container mx-auto flex items-center">
        <div class="flex items-center space-x-3 ml-36">
            <img :src="iconPath" class="w-10 h-10 mx-auto" />
            <a href="/" class="text-white font-bold text-xl">MyDurian</a>
        </div>
        <div class="flex space-x-6 ml-14">
            <NuxtLink  class="nav-link" to="/home">
            <!-- <i class="fa fa-home"></i> -->
            Home
            </NuxtLink>
            <NuxtLink class="nav-link" to="/dashboard">
            <!-- <i class="fa fa-file-alt"></i> -->
            Dashboard
            </NuxtLink>
            <NuxtLink class="nav-link" to="/chart">
            <!-- <i class="fa fa-file-alt"></i> -->
            Chart
            </NuxtLink>
            <NuxtLink class="nav-link" to="/contact">
            <!-- <i class="fa fa-file-alt"></i> -->
            Contact
            </NuxtLink>
        </div>
        <div class="flex space-x-6 ml-96"> 
            <NuxtLink class="nav-link" to="/login">
            <i class="fa fa-file-alt"></i>
            Login
            </NuxtLink>
            <NuxtLink class="nav-link" to="/signup">
            <i class="fa fa-file-alt"></i>
            Sign up
            </NuxtLink>
        </div>
    </div>
</nav>
    <div class="h-full pb-5">
        <div class="carousel-container">
            <!-- Slide 1 -->
            <div v-if="currentSlide === 0" class="slide slide-active h-screen w-full justify-between flex  pl-52 bg-black">
                <div class="flex-col mt-20 w-full">
                    <div class="flex flex-col">
                        <span class="text-span text-6xl text-white">SMART FARM KMUTNB</span>
                        <span class="text-span text-5xl text-white mt-4">for Nontaburi farmers</span>
                        <span class="text-span text-xl text-gray-400 mt-4">โครงการสมาร์ทฟาร์มพัฒนาการเกษตร</span>
                        <span class="text-span text-xl text-gray-400 mt-4">ภายใต้ความร่วมมือระหว่าง กระทรวงเกษตรนนทบุรีและ</span>
                        <span class="text-span text-xl text-gray-400 mt-4">มหาวิทยาลัยเทคโนโลยีพระจอมเกล้าพระนครเหนือ</span>
                    </div>
                    <div class="flex justify-between items-center w-44 mt-6">
                        <img :src="iconPath1" class="size-28">
                        <img :src="iconPath2" class="size-32 ml-3">
                        <img :src="iconPath3" class="size-28 ml-3">
                        <img :src="iconPath4" class="size-32">
                        <img :src="iconPath5" class="size-32">
                    </div>
                </div>
                <div class="mt-12 flex-col">
                    <div class="flex pt-28 pr-36">
                        <img :src="iconPath" class="mx-auto scale-150" />
                    </div>
                </div>
            </div>

            <!-- Slide 2 -->
            <div v-if="currentSlide === 1" class="slide slide-active h-screen w-full justify-between flex  pl-52 bg-gradient-to-r from-black to-fuchsia-800">
                <div class="flex-col mt-20 w-full">
                    <div class="flex flex-col">
                        <span class="text-span text-6xl text-white">SMART FARM KMUTNB</span>
                        <span class="text-span text-5xl text-white mt-4">for Nontaburi farmers</span>
                        <span class="text-span text-xl text-gray-400 mt-4">โครงการสมาร์ทฟาร์มพัฒนาการเกษตร</span>
                        <span class="text-span text-xl text-gray-400 mt-4">ภายใต้ความร่วมมือระหว่าง กระทรวงเกษตรนนทบุรีและ</span>
                        <span class="text-span text-xl text-gray-400 mt-4">มหาวิทยาลัยเทคโนโลยีพระจอมเกล้าพระนครเหนือ</span>
                    </div>
                    <div class="flex justify-between items-center w-44 mt-6">
                        <img :src="iconPath1" class="size-28">
                        <img :src="iconPath2" class="size-32 ml-3">
                        <img :src="iconPath3" class="size-28 ml-3">
                        <img :src="iconPath4" class="size-32">
                        <img :src="iconPath5" class="size-32">
                    </div>
                </div>
                <div class="mt-12 flex-col">
                    <div class="flex pt-28 pr-36">
                        <img :src="iconPath8" class="mx-auto scale-150" />
                    </div>
                </div>
            </div>

            <!-- Navigation Dots -->
            <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex space-x-4">
                <div 
                    @click="currentSlide = 0" 
                    :class="['w-20 h-2 border rounded-md cursor-pointer', currentSlide === 0 ? 'bg-lime-500 border-lime-500' : 'bg-white border-gray-300']">
                </div>
                <div 
                    @click="currentSlide = 1" 
                    :class="['w-20 h-2 border rounded-md cursor-pointer', currentSlide === 1 ? 'bg-lime-500 border-lime-500' : 'bg-white border-gray-300']">
                </div>
            </div>
        </div>

    <!-- <div class="h-screen w-full justify-between flex  pl-52 bg-black">
        <div class="flex-col mt-20 w-full">
            <div class="flex flex-col">
                <span class="text-span text-6xl text-white">SMART FARM KMUTNB</span>
                <span class="text-span text-5xl text-white mt-4">for Nontaburi farmers</span>
                <span class="text-span text-xl text-gray-400 mt-4">โครงการสมาร์ทฟาร์มพัฒนาการเกษตร</span>
                <span class="text-span text-xl text-gray-400 mt-4">ภายใต้ความร่วมมือระหว่าง กระทรวงเกษตรนนทบุรีและ</span>
                <span class="text-span text-xl text-gray-400 mt-4">มหาวิทยาลัยเทคโนโลยีพระจอมเกล้าพระนครเหนือ</span>
            </div>
            <div class="flex justify-between items-center w-44 mt-6">
                <img :src="iconPath1" class="size-28">
                <img :src="iconPath2" class="size-32 ml-3">
                <img :src="iconPath3" class="size-28 ml-3">
                <img :src="iconPath4" class="size-32">
                <img :src="iconPath5" class="size-32">
            </div>
        </div>
        <div class="mt-12 flex-col">
            <div class="flex pt-28 pr-36">
                <img :src="iconPath" class="mx-auto scale-150" />
            </div>
        </div>
    </div> -->

    <!-- <div class="h-screen w-full justify-between flex  pl-52 bg-violet-900">
        <div class="flex-col mt-20 w-full">
            <div class="flex flex-col">
                <span class="text-span text-6xl text-white">SMART FARM KMUTNB</span>
                <span class="text-span text-5xl text-white mt-4">for Nontaburi farmers</span>
                <span class="text-span text-xl text-gray-400 mt-4">โครงการสมาร์ทฟาร์มพัฒนาการเกษตร</span>
                <span class="text-span text-xl text-gray-400 mt-4">ภายใต้ความร่วมมือระหว่าง กระทรวงเกษตรนนทบุรีและ</span>
                <span class="text-span text-xl text-gray-400 mt-4">มหาวิทยาลัยเทคโนโลยีพระจอมเกล้าพระนครเหนือ</span>
            </div>
            <div class="flex justify-between items-center w-44 mt-6">
                <img :src="iconPath1" class="size-28">
                <img :src="iconPath2" class="size-32 ml-3">
                <img :src="iconPath3" class="size-28 ml-3">
                <img :src="iconPath4" class="size-32">
                <img :src="iconPath5" class="size-32">
            </div>
        </div>
        <div class="mt-12 flex-col">
            <div class="flex pt-28 pr-36">
                <img :src="iconPath" class="mx-auto scale-150" />
            </div>
        </div>
    </div> -->

    <div class="bg-neutral-900 flex flex-col w-full h-[60vh] pt-16 pr-28 pl-28">
        <div>
            <span class="text-span text-5xl text-white">Example</span>
        </div>
        <div class="flex mt-9 shadow-lg w-full justify-between">
            <div class="flex flex-col h-72 w-80 shadow-lg"> 
                <div>
                    <img src="https://img.thingsboard.io/iot-articles/iot-solutions-1_1090x710.png" class="w-full h-50">
                </div>
                <div class="pl-4 pt-4 bg-white h-20">
                    <span class="text-span text-xl text-black">Dashboard</span>
                </div>
            </div>
            <div class="flex flex-col h-72 w-80 shadow-lg"> 
                <div>
                    <img src="https://img.thingsboard.io/iot-articles/iot-solutions-1_1090x710.png" class="w-full h-50">
                </div>
                <div class="pl-4 pt-4 bg-white h-20">
                    <span class="text-span text-xl text-black">Dashboard</span>
                </div>
            </div>
            <div class="flex flex-col h-72 w-80 shadow-lg"> 
                <div>
                    <img src="https://img.thingsboard.io/iot-articles/iot-solutions-1_1090x710.png" class="w-full h-50">
                </div>
                <div class="pl-4 pt-4 bg-white h-20">
                    <span class="text-span text-xl text-black">Dashboard</span>
                </div>
            </div>
        </div>
    </div>
    <div class="bg-black flex justify-between items-start w-full h-[40vh] pt-16 pr-28 pl-28">
        <div class="w-[60vw] flex flex-col">
            <span class="text-span text-4xl text-white">Smart farm IoT system for durian orchards</span>
            <span class="text-span text-2xl text-white mt-4">fully integrated with hardware and software to enhance</span>
            <span class="text-span text-2xl text-white my-1">and improve efficiency for farmers</span>
        </div>
        <div class="w-[40vw] flex">
            <img :src="iconPath6" class="size-52 pb-6">
            <img :src="iconPath7" class="size-52 pb-6 ml-6">
        </div>
        
    </div>
    <div class="bg-white flex justify-between items-start w-full h-screen pt-16 pr-20 pl-28">
        <div class="w-[50vw] flex flex-col">
            <span class="text-span text-4xl text-black">Benefits</span>
            <span class="text-span text-2xl text-black mt-4">Users, after registering as members can view real-time data</span>
            <span class="text-span text-2xl text-black mt-1">from sensors installed in the durian farm through the website</span>
            <span class="text-span text-2xl text-black mt-1">which includes both dashboards and graphs</span>
            <span class="text-span text-2xl text-black mt-3">Users can also download the data as CSV files</span>
            <span class="text-span text-2xl text-black mt-1">for further use and view historical data</span>
            <span class="text-span text-2xl text-black mt-1">along with receiving notifications through Line Notify</span>
            <button class="btn btn-primary mt-10 w-40 h-10">
                Charts Example
            </button>
            <button class="btn btn-primary mt-3 w-40 h-10">
                Dashboards Example
            </button>
        </div>
        <div class="w-[50vw] flex justify-between">
            <div class="flex flex-col h-96 w-80 border shadow-lg mt-52"> 
                <div>
                    <img src="https://img.thingsboard.io/iot-articles/iot-solutions-1_1090x710.png" class="w-full h-50">
                </div>
                <div class="pl-4 pt-4">
                    <span class="text-span text-xl text-black">Dashboard</span>
                </div>
            </div>

            <div class="flex flex-col h-96 w-80 border shadow-lg mt-52"> 
                <div>
                    <img src="https://img.thingsboard.io/iot-articles/iot-solutions-1_1090x710.png" class="w-full h-50">
                </div>
                <div class="pl-4 pt-4">
                    <span class="text-span text-xl text-black">Chart</span>
                </div>
            </div>
        </div>
    </div>
    <div class="bg-black flex justify-between items-start w-full h-[60vh] pt-20 pr-80 pl-80">
        <div class="flex flex-col">
            <span class="text-span text-xl text-white">Contact</span>
            <hr class="mt-4 mb-4 bg-gray-200">
            <span class="text-span text-xl text-lime-500">Aj Ko</span>
            <span class="text-span text-xl text-lime-500">Aj Min</span>
            <span class="text-span text-xl text-lime-500">Kus</span>
        </div>
        <div class="flex flex-col">
            <span class="text-span text-xl text-white">Relevant agencies</span>
            <hr class="mt-4 mb-4 bg-gray-200">
            <span class="text-span text-xl text-lime-500">Aj Ko</span>
            <span class="text-span text-xl text-lime-500">Aj Min</span>
            <span class="text-span text-xl text-lime-500">Kus</span>
        </div>
        <div class="flex flex-col">
            <span class="text-span text-xl text-white">Location</span>
            <hr class="mt-4 mb-4 bg-gray-200">
            <span class="text-span text-xl text-lime-500">Aj Ko</span>
            <span class="text-span text-xl text-lime-500">Aj Min</span>
            <span class="text-span text-xl text-lime-500">Kus</span>
        </div>
    </div>
    <div class="bg-white flex flex-col w-full h-[20vh] pt-16 pr-28 pl-28">
        <div>
            <span>MyDurian</span>
        </div>
        <div>
            <span>King Mongkut's University of technology north Bangkok</span>
        </div>
    </div>
  </div>
</template>
