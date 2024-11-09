<template>
  <div class="min-h-screen bg-gradient-to-b from-gray-900 to-black font-noto">
    <!-- Navigation -->
    <nav class="bg-gray-900/95 backdrop-blur-md p-4 w-full fixed z-50 shadow-lg">
      <div class="container mx-auto">
        <div class="flex items-center justify-between">
          <div class="flex items-center space-x-4">
            <img :src="iconPath" class="w-12 h-12 hover:scale-110 transition-transform" alt="MyDurian Logo" />
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

    <!-- Hero Section -->
    <div class="relative">
      <div class="carousel-container">
        <TransitionGroup name="slide" class="flex justify-between">
          <div v-for="index in 2" 
               v-show="currentSlide === index - 1"
               :key="index"
               class="min-h-screen w-full flex items-center justify-between px-8 md:px-20"
               :class="index === 1 ? 'bg-black/90' : 'bg-gradient-to-r from-black/90 to-fuchsia-900/90'">
            
            <div class="flex-1 space-y-8 mt-20 max-w-2xl">
              <div class="space-y-4">
                <h1 class="text-4xl md:text-7xl text-white font-bold tracking-tight font-prompt">
                  SMART FARM <div class="text-lime-400">KMUTNB</div>
                </h1>
                <h2 class="text-3xl md:text-5xl text-white/90 font-light font-prompt">
                  for Nontaburi farmers
                </h2>
              </div>
              
              <div class="space-y-3 text-gray-400">
                <p class="text-xl font-light font-prompt">โครงการสมาร์ทฟาร์มพัฒนาการเกษตร</p>
                <p class="text-xl font-light font-prompt">ภายใต้ความร่วมมือระหว่าง กระทรวงเกษตรนนทบุรีและ</p>
                <p class="text-xl font-light font-prompt">มหาวิทยาลัยเทคโนโลยีพระจอมเกล้าพระนครเหนือ</p>
              </div>
            </div>

            <div class="hidden md:block">
              <img :src="index === 1 ? iconPath : iconPath8"
                   class="w-full max-w-xl transform scale-80 hover:scale-155 transition-transform"
                   :alt="index === 1 ? 'Durian' : 'Smart Farm'" />
            </div>
          </div>
        </TransitionGroup>

        <!-- Enhanced Navigation Dots -->
        <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 flex space-x-4">
          <button v-for="index in 2"
                  :key="index"
                  @click="currentSlide = index - 1"
                  class="w-20 h-2 rounded-full transition-all"
                  :class="currentSlide === index - 1 ? 'bg-lime-400 scale-110' : 'bg-white/30 hover:bg-white/50'">
          </button>
        </div>
      </div>
    </div>

    <!-- Enhanced Example Section -->
    <section class="bg-neutral-900/50 py-24 px-8 md:px-20">
      <h2 class="text-4xl text-white font-bold mb-16 text-center">Example Solutions</h2>
      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <div v-for="i in 3" 
             :key="i"
             class="bg-white/5 backdrop-blur-lg rounded-xl overflow-hidden shadow-xl hover:shadow-lime-500/20 transform hover:scale-105 transition-all duration-300">
          <img src="https://img.thingsboard.io/iot-articles/iot-solutions-1_1090x710.png"
               class="w-full h-48 object-cover hover:opacity-90 transition-opacity"
               alt="Dashboard example" />
          <div class="p-6">
            <h3 class="text-xl font-semibold text-white">Dashboard {{ i }}</h3>
            <p class="mt-2 text-gray-400">Interactive and real-time monitoring dashboard for your smart farm.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Enhanced Features Section -->
    <section class="bg-black/80 py-24 px-8 md:px-20">
      <div class="flex flex-col md:flex-row justify-between items-center gap-12">
        <div class="md:w-7/12">
          <h2 class="text-3xl md:text-5xl text-white font-bold mb-8">
            Smart farm IoT system for
            <span class="text-lime-400">durian orchards</span>
          </h2>
          <p class="text-xl text-gray-300 leading-relaxed">
            Fully integrated with hardware and software to enhance
            and improve efficiency for farmers through advanced IoT technology
            and real-time monitoring systems.
          </p>
        </div>
        <div class="flex space-x-10">
          <img :src="iconPath6" class="h-32 hover:scale-110 transition-transform" alt="IoT" />
          <img :src="iconPath7" class="h-32 hover:scale-110 transition-transform" alt="Smart Farmer" />
        </div>
      </div>
    </section>

    <!-- Enhanced Benefits Section -->
    <section class="py-24 px-8 md:px-20 bg-gradient-to-b from-black/50 to-gray-900/50">
      <div class="flex flex-col md:flex-row justify-between gap-16">
        <div class="md:w-1/2 space-y-8">
          <h2 class="text-5xl font-bold text-white">Benefits</h2>
          <div class="space-y-6">
            <p class="text-xl text-gray-300 leading-relaxed">
              Users, after registering as members can view real-time data
              from sensors installed in the durian farm through the website
              which includes both dashboards and graphs.
            </p>
            <p class="text-xl text-gray-300 leading-relaxed">
              Users can also download the data as CSV files
              for further use and view historical data
              along with receiving notifications through Line Notify.
            </p>
          </div>
          <div class="flex flex-col sm:flex-row gap-4 pt-8">
            <button class="px-8 py-4 bg-lime-500 text-white rounded-lg hover:bg-lime-400 transform hover:scale-105 transition-all shadow-lg hover:shadow-lime-500/30">
              Charts Example
            </button>
            <button class="px-8 py-4 bg-lime-500 text-white rounded-lg hover:bg-lime-400 transform hover:scale-105 transition-all shadow-lg hover:shadow-lime-500/30">
              Dashboards Example
            </button>
          </div>
        </div>

        <div class="md:w-1/2 grid grid-cols-1 md:grid-cols-2 gap-8">
          <div v-for="(type, index) in ['Dashboard', 'Chart']"
               :key="index"
               class="bg-white/5 backdrop-blur-lg rounded-xl overflow-hidden shadow-xl hover:shadow-lime-500/20 transform hover:scale-105 transition-all duration-300">
            <img src="https://img.thingsboard.io/iot-articles/iot-solutions-1_1090x710.png"
                 class="w-full h-48 object-cover hover:opacity-90 transition-opacity"
                 :alt="type" />
            <div class="p-6">
              <h3 class="text-xl font-semibold text-white">{{ type }}</h3>
              <p class="mt-2 text-gray-400">Interactive and customizable {{ type.toLowerCase() }} for data visualization.</p>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Enhanced Footer -->
    <footer class="bg-black/90 text-white">
      <div class="container mx-auto px-8 py-16">
        <div class="grid grid-cols-1 md:grid-cols-3 gap-16">
          <div class="space-y-6">
            <h3 class="text-2xl font-bold">Contact</h3>
            <hr class="border-lime-500/30 w-24" />
            <ul class="space-y-4">
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Aj Ko</li>
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Aj Min</li>
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Kus</li>
            </ul>
          </div>
          
          <div class="space-y-6">
            <h3 class="text-2xl font-bold">Relevant agencies</h3>
            <hr class="border-lime-500/30 w-24" />
            <ul class="space-y-4">
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Aj Ko</li>
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Aj Min</li>
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Kus</li>
            </ul>
          </div>

          <div class="space-y-6">
            <h3 class="text-2xl font-bold">Location</h3>
            <hr class="border-lime-500/30 w-24" />
            <ul class="space-y-4">
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Aj Ko</li>
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Aj Min</li>
              <li class="text-gray-300 hover:text-lime-400 transition-colors cursor-pointer">Kus</li>
            </ul>
          </div>

        </div>
      </div>
      
      <div class="border-t border-gray-800">
        <div class="container mx-auto px-8 py-6">
          <p class="text-sm text-gray-400">
            MyDurian - King Mongkut's University of Technology North Bangkok
          </p>
        </div>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';

// Import images (keep your existing imports)
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

const currentSlide = ref(0);
const totalSlides = 2;
const isMenuOpen = ref(false);

const changeSlide = () => {
  currentSlide.value = (currentSlide.value + 1) % totalSlides;
};

onMounted(() => {
  const interval = setInterval(changeSlide, 5000);
  onUnmounted(() => {
    clearInterval(interval);
  });
});
</script>

<style>
/* Import Google Fonts */
@import url('https://fonts.googleapis.com/css2?family=Prompt:wght@300;400;500;600;700&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;500;600&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+Thai:wght@300;400;500;600;700&display=swap');

/* Define custom font classes */
.font-prompt {
  font-family: 'Prompt', 'Noto Sans Thai', sans-serif;
}

.font-kanit {
  font-family: 'Kanit', 'Noto Sans Thai', sans-serif;
}

.font-noto {
  font-family: 'Noto Sans Thai', sans-serif;
}

/* Transition animations */
.slide-enter-active,
.slide-leave-active {
  transition: all 0.5s ease-out;
}

.slide-enter-from,
.slide-leave-to {
  opacity: 0;
  transform: translateX(30px);
}

.carousel-container {
  position: relative;
  overflow: hidden;
  width: 100%;
}
</style>