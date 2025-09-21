<template>
    <header class="relative overflow-hidden bg-gradient-to-r from-blue-100 to-purple-100" id="home">
        <article class="max-w-screen-xl mx-auto px-4 sm:px-8 py-16 md:py-28 
        flex flex-col-reverse lg:flex-row items-center gap-10 lg:gap-20">
        <!----- Hero Content ---->
            <section class="w-full lg:w-1/2 text-center lg:text-left">
                <hgroup data-aos="fade-up" data-aos-delay="500" >
                    <h1 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold text-gray-800 mb-4">
                        Enhance Your Natural
                        <mark class="text-pink-600 bg-transparent">Beauty</mark>
                    </h1>
                    <p class="text-base sm:text-lg text-gray-600 mb-8 max-w-xl mx-auto lg:mx-0">
                        Discover simple ways to highlight your best features with minimal effort. From skincare tips to everyday makeup hacks, our goal is to help you feel confident and radiant in your natural look. Embrace your individuality and let your true beauty shine through with gentle care and mindful practices.
                    </p>
                </hgroup>
                <!----- CTA Button-->
                <nav data-aos="fade-up" data-aos-delay="400" 
                class="flex flex-col sm:flex-row justify-center lg:justify-start gap-4 mb-12">
                         <a href="#appointment" class="bg-pink-600 text-white text-center px-8 py-3 rounded-full hover:bg-pink-700
      transition shadow-lg ">
      Book a Consultation
    </a>
    <a href="#services" 
    class="border border-pink-600 text-pink-600 hover:bg-pink-50
     text-center px-8 py-3 rounded-full transition" aria-label="Explore Our Services">Explore Services</a>
                </nav>
                <!------ stats section --->
                <aside data-aos="fade-up" data-aos-delay="600" class="py-4">
                    <ul class="flex flex-wrap justify-center lg:justify-start gap-x-6 gap-y-4 text-center">
                        <li v-for="(stat , index) in stats" :key="index" class="w-1/2 sm:w-auto">
                            <strong class="text-2xl text-pink-600 font-bold">{{ stat.value }}</strong>
                             <small class="block text-sm text-gray-600">{{ stat.label }}</small>
                        </li>
                    </ul>
                </aside>
            </section>

                     <!---- Hero Image  --->
                <figure  data-aos="fade-up" data-aos-delay="400" class="w-full lg:w-1/2 flex justify-center relative">
                    <div class="relative w-full max-w-xs sm:max-w-xs md:max-w-md">
                        <span class="bg-pink-500 rounded-full w-64 h-64  md:w-70 md:h-70 lg:w-80 lg:h-80 absolute -top-10 -left-10 
                        opacity-20" aria-hidden="true">
                    </span>
                      <span class="bg-purple-500 rounded-full  w-45 h-45 lg:w-65 lg:h-65 absolute -bottom-10 -right-0 md:right-15 lg:-right-5 
                        opacity-20">
                    </span>
                    <img src="@assets/hero.png" alt="woman smiling after cosmetic treatment" 
                    class="relative z-10 rounded-full shadow-2xl object-cover  w-[300px] h-[290px] sm:w-[300px] sm:h-[300px] lg:w-[400px] lg:h-[392px]"  loading="eager">
                    </div>
                </figure>

        </article>

    </header>
</template>

<script setup>
  import { ref } from 'vue';
  const stats = ref([
    { label: 'Happy Clients', value:"2500+"},
    { label: 'Sepecialits' , value:"15+" },
    { label: 'Treatments', value:"10+" },
    { label: 'Years of Experience', value:"20+" }
  ])

</script>
