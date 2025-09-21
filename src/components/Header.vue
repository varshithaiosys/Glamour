<template>
  <header class="bg-gradient-to-r from-pink-100 to-purple-100 sticky top-0 z-50">
    <div class="max-w-screen-xl mx-auto px-4 py-4 flex justify-between items-center">

      <!----- logo ----->
      <a href="/" class="flex items-center focus:outline-none focus:ring-2 focus:ring-pink-600 rounded">
        <h1 class="text-2xl font-bold text-pink-600">Glamour Clinic</h1>
    </a>

    <!----- Desktop Navigation-->

    <nav class="hidden md:flex space-x-6" aria-label="Primary navigation">
      <a v-for="(link, index) in navlinks"
       :key="index" 
       :href="link.href"
       class="text-gray-700 hover:text-pink-600 transition-colors duration-200 
       focus:outline-none focus:ring-2 focus:ring-pink-600 rounded">{{ link.label }}</a>
    </nav>

    <!----- Appointment button { desktop} ----->

    <div class="hidden md:block">
      <a href="#appointment" class="bg-pink-600 text-white px-5 py-2
       rounded-full hover:bg-pink-700 
      focus:outline-none focus:ring-2 focus:ring-pink-800 
      transition-colors duration-200 shadow-md focus:ring-offset-2">
      Book Appointemnt
    </a>
    </div>

    <!----- Mobile menu Button -->

    <button class="md:hidden p-2 focus:outline-none focus:ring-2 focus:ring-pink-600 
    rounded" @click="toggleMenu" aria-label="Toggle menu" :aria-expanded="isMenuOpen.toString()" aria-controls="mobile-menu">
      <Icon :icon="isMenuOpen ? 'mdi:close' : 'mdi:menu' " class="w-6 h-6" />
    </button>

    <!----- Mobile Menu ----->

    <aside v-if="isMenuOpen" id="mobile-menu" class="md:hidden bg-white shadow-lg py-4 px-4 absolute top-full 
    left-0 right-0 z-50"  aria-label="Mobile menu">
     <nav aria-label="Mobile Navigation">
        <ul class="flex flex-col space-y-4">
          <li v-for="(link, index) in navlinks" :key="index">
            <a :href="link.href" 
            class="block text-gray-700 :hover:text-pink-600 transition-colors 
            duration-200 px-2 py-2 focus:outline-none focus:ring-2 focus:ring-pink-600" @click="toggleMenu">
             {{ link.label }}
          </a>
          </li>
          <li>
              <a href="#appointment" class="block text-center bg-pink-600 text-white px-4 py-2
       rounded-full hover:bg-pink-700 
      focus:outline-none focus:ring-2 focus:ring-pink-800 
      transition-colors duration-200 shadow-md focus:ring-offset-2"  @click="toggleMenu">
      Book Appointemnt
    </a>
          </li>
        </ul>
     </nav>
  </aside>
   </div>
  </header>
</template>

<script setup>
import { Icon } from '@iconify/vue';
import { ref } from 'vue';
 const navlinks = ref([
   { label: 'Home', href: '#home' },
    { label: 'Services', href: '#services' },
   { label: 'About Us', href: '#about' },
   { label: 'Our Specialists', href: '#specialists' },
   { label: 'Contact', href: '#contact' },
 ]);
  const isMenuOpen = ref(false);
  const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value;
  };
 
</script>
