<template>
    <section class="py-14 overflow-hidden bg-gradient-to-r from-pink-100 to-purple-100" id="about">
        <div class="container mx-auto px-4">
            <article data-aos="fade-up" data-aos-delay="500" class="flex flex-col lg:flex-row items-center gap-12">

                <!--- Image column  ---->
                <figure class="lg:w-5/12 relative">
                    <div class="relative z-10 rounded-2xl overflow-hidden shadow-2xl w-full max-w-md mx-auto">
                        <img src="@assets/aboutImage.png" alt="About Glamour Clinic" loading="lazy"
                            class="w-full h-auto object-cover aspect-[4/5]">
                        <div class="absolute inset-0 bg-gradient-to-t from-black/40 to-transparent" aria-hidden="true">
                        </div>
                    </div>

                    <!----- Decorative Elements  --->

                    <span class="hidden lg:block absolute -bottom-8 -left-8 w-32 h-32 rounded-full bg-pink-500 
            opacity-20 z-0" aria-hidden="true"></span>

                    <span class="hidden lg:block absolute -top-8 -right-8 w-40 h-40 rounded-full bg-pink-600 
            opacity-20 z-0" aria-hidden="true"></span>

                </figure>

                <!----- content Column ----->

                <div data-aos="fade-up" data-aos-delay="600" class="lg:w-7/12">
                    <header>
                        <h2 id="about-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-6">
                            About <span class="text-pink-600">Glamor Clinic</span>
                        </h2>
                        <p class="mb-6 text-lg text-gray-600">
                            Glamor Clinic is dedicated to helping you look and feel your
                            best through a range of advanced aesthetic and wellness treatments.
                            Our expert team combines medical expertise with a passion for beauty,
                            offering personalized care in a welcoming environment. </p>
                    </header>

                    <section class="mb-6">
                        <h3 class="text-xl font-semibold text-gray-800 mb-4">Our Approach</h3>
                        <ul class="space-y-3">
                            <li v-for="(item, index) in approchItems" :key="index" class="flex items-start">
                                <figure class="bg-pink-100 p-1 rounded-full mr-3">
                                    <Icon :icon="item.icon" class="text-pink-600" aria-hidden="true" />
                                </figure>
                                <p class="text-gray-700">{{ item.text }}</p>
                            </li>
                        </ul>
                    </section>

                    <!----- stats section  ----->

                    <section class="grid grid-cols-2 gap-4 mb-8">
                        <article v-for="(item, index) in stats" :key="index"
                            class="bg-white p-4 rounded-lg shadow-sm flex items-center">
                            <figure class="mr-3">
                                <Icon :icon="item.icon" class="text-pink-500" aria-hidden="true" />
                            </figure>
                            <div>
                                <strong class="text-xl font-bold text-gray-800">{{ item.Value }}</strong>
                                <p class="text-sm text-gray-600">{{ item.label }}</p>
                            </div>
                        </article>
                    </section>
                    <nav>
                        <a href="#appointment" class="bg-pink-600 hover:bg-pink-700 text-white text-center px-8 py-3 
                rounded-full inline-block transistion shadow-lg focus:outline-none focus:ring-2 
                focus:ring-pink-800 focus:ring-offset-2">
                            Meet Our Specialists
                        </a>
                    </nav>
                </div>

            </article>

            <!----- Mission Statement ---->

            <aside class="mt-20 bg-white roundex-2xl p-8 md:p-12 shadow-lg relative overflow-hidden">
                <span class="absolute -top-20 -right-20 w-64 h-64 rounded-full bg-pink-500 opacity-40"
                    aria-hidden="true"></span>
                <div class="relative z-10">
                    <h3 class="font-bold text-pink-800 text-2xl mb-6">Our Mission</h3>
                    <blockquote class="text-lg text-gray-700 mb-6">
                        At Glamor Clinic, our mission is to empower individuals to embrace their unique
                        beauty and enhance their confidence through personalized, state-of-the-art aesthetic
                        treatments. We are committed to providing exceptional care in a welcoming and professional
                        environment, where every client feels valued and understood. Our goal is to help you look
                        and feel your best, naturally.
                    </blockquote>
                    <figure class="flex items-center">
                        <div class="w-12 h-12 rounded-full bg-pink-100 flex items-center justify-center mr-4">
                            <Icon icon="fa-solid:user-md" class="text-pink-600" aria-hidden="true" />
                        </div>
                        <figcaption>
                            <cite class="font-semibold not-italic text-gray-800">Dr. Sarah Johnson</cite>
                            <p class="text-sm text-gray-600">Medical Director & Founder</p>
                        </figcaption>
                    </figure>
                </div>
            </aside>

        </div>
    </section>
</template>

<script setup>
import { ref, toValue } from 'vue';

const approchItems = ref([
    {
        icon: 'fa-solid:heart',
        text: 'Personalized treatment plans tailored to your unique needs and goals.'
    },
    {
        icon: 'fa-solid:user-md',
        text: 'Personalized treatment plans tailored to your unique needs and goals.'
    },
    {
        icon: 'fa-solid:clinic-medical',
        text: 'Personalized treatment plans tailored to your unique needs and goals.'
    }
])

const stats = ref([
    { Value: '10+', label: 'Years of Experience', icon: 'fa-solid:award' },
    { Value: '2.5k+', label: 'Happy Clients', icon: 'fa-solid:heart' },
    { Value: '15+', label: 'Expert Doctors', icon: 'fa-solid:user-md' },
    { Value: '100+', label: 'Treatments ', icon: 'fa-solid:clinic-medical' }
])        
</script>
