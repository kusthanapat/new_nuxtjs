<script setup>
    import iconPath from '~/assets/images/icon_durian.png';
</script>

<template>
    <div class="w-full h-full">
        <!-- Navigation -->
        <nav class="bg-gray-900/95 backdrop-blur-md p-4 w-full fixed z-50 shadow-lg">
        <div class="container mx-auto">
            <div class="flex items-center justify-between">
            <div class="flex items-center space-x-4">
                <img :src="iconPath" class="w-12 h-12 hover:scale-110 transition-transform" />
                <NuxtLink to="/" class="text-white font-bold text-2xl hover:text-lime-400 transition-all font-kanit">
                MyDurian
                </NuxtLink>
            </div>
            
            <!-- Desktop Navigation -->
            <div class="hidden md:flex space-x-8">
                <NuxtLink v-for="link in ['Home', 'Dashboard', 'Chart', 'Contact']" 
                        :key="link"
                        :to="`/${link.toLowerCase()}`"
                        class="text-gray-300 hover:text-lime-400 transition-all relative group font-kanit">
                {{ link }}
                <span class="absolute bottom-0 left-0 w-full h-0.5 bg-lime-400 transform scale-x-0 group-hover:scale-x-100 transition-transform"></span>
                </NuxtLink>
            </div>

            <div class="hidden md:flex space-x-4">
                <NuxtLink to="/login" 
                        class="px-6 py-2 text-gray-300 hover:text-white border border-transparent hover:border-lime-400 rounded-lg transition-all font-kanit">
                Login
                </NuxtLink>
                <NuxtLink to="/signup" 
                        class="px-6 py-2 bg-lime-500 text-white rounded-lg hover:bg-lime-400 transform hover:scale-105 transition-all shadow-lg hover:shadow-lime-500/30 font-kanit">
                Sign up
                </NuxtLink>
            </div>
            </div>
        </div>
        </nav>

        <div class="flex flex-col h-screen w-full mt-40 justify-center items-center">
            <div class="flex flex-col mt-40 ">
                <h2 class="text-5xl font-bold text-black">MyDurian</h2>
                <h3 class="text-5xl font-bold text-black">Login</h3>
            </div>
            <div>
                <p>Username</p>
                <input type="text" class="border border-gray-900">
            </div>
        </div>
    </div>
</template>