<template>
  
    <section class="py-20 overflow-hidden bg-gradient-to-r from-pink-100 to-purple-100" id="contact">
        <div class="container mx-auto px-4">
            <!---- section header  --->
            <header class="relative text-center mb-16" data-aos="fade-up" data-aos-delay="500">
                <span class="absolute -top-10 left-1/2 Transform translate-x-1/2 w-20 h-20 rounded-full 
                        bg-pink-600 opacity-30 z-0" aria-hidden="true"></span>
                <h2 id="specialists-heading" class="text-3xl md:text-4xl font-bold text-gray-800 mb-4 z-10 relative">
                    Contact <span class="text-pink-600">Our Clinic</span>
                </h2>
                <p class="text-lg text-gray-600 max-w-2xl mx-auto relative z-10">
                    OReach out to Glamor Clinic for personalized consultations, appointment bookings, and inquiries about our services.
                  
                </p>
                <span class="absolute -bottom-6 right-1/4 w-16 h-16 rounded-full bg-purple-100 opacity-20 z-0"
                    aria-hidden="true"></span>
            </header>

            <!----- Main content  ---->
            <main class="flex flex-col lg:flex-row gap-12">
                <!----- Contact Info  ---->

                <aside class="lg:w-3/5">
                    <section class="rounded-2xl bg-white h-full p-8 shadow-lxl">
                        <h2 class="text-2xl font-bold text-gray-800 mb-6">Get In Touch</h2>
                        <address class="space-y-6">
                            <article v-for="(item,index) in contactItems" :key="index" class="flex items-start">
                                <figure class="bg-pink-100 p-3 rounded-full mr-4 flex-shrink-0">
                                    <Icon :icon="item.icon" class="text-pink-600 text-xl"/>
                                </figure>
                                <div>
                                    <h3 class="font-semibold text-gray-800 mb-1">{{ item.title }}</h3>
                                    <div v-html="item.content" class="text-gray-600"></div>
                                </div>
                            </article>
                        </address>
                        <figure class="mt-8 rounded-xl overflow-hidden shadow-md">
                            <img src="@assets/contactImg.png" alt="Glamour Clinic Building" 
                            class="w-full h-48 object-cover hover:scale-105 transition-transform duration-500" 
                            width="400" height="200" loading="lazy">
                        </figure>
                    </section>
                </aside>

                <!----- Contact Form  ---->

                <section class="lg:w-3/5">
                    <div class="bg-white rounded-2xl shadow-xl p-8 h-full">
                        <h2 class="text-2xl font-bold text-gray-800 mb-6">Send Us a Message</h2>
                        <form class="space-y-6">
                            <fieldset class="grid grid-cols-1 md:grid-cols-2 gap-6">
                                <div>
                                    <label for="name" class="block text-gray-700 font-medium mb-2">Full Name</label>
                                    <input type="text" id="name" name="name" 
                                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 
                                    focus:ring-pink-500 focus:border-transparent" placeholder="Your Name" required>
                                </div>

                                <div>
                                    <label for="phone" class="block text-gray-700 font-medium mb-2">Phone Number</label>
                                    <input type="tel" id="phone" name="phone" 
                                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 
                                    focus:ring-pink-500 focus:border-transparent" placeholder="+9198786756" required>
                                </div>

                            </fieldset>
                                       <div>
                                    <label for="email" class="block text-gray-700 font-medium mb-2">Email Address</label>
                                    <input type="email" id="email" name="email" 
                                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 
                                    focus:ring-pink-500 focus:border-transparent" placeholder="your@gmail.com" required>
                                </div>

                                  <div>
                                    <label for="name" class="block text-gray-700 font-medium mb-2">service Intrested in</label>
                                    <select  
                                    id="service" 
                                    name="service" 
                                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 
                                    focus:ring-pink-500 focus:border-transparent">
                                    <option value="select">Select</option>
                                    <option v-for="s in services" :key="s.value" :value="s.value">{{ s.label }}</option>
                                </select>
                                </div>

                                 <div>
                                    <label for="name" class="block text-gray-700 font-medium mb-2">Your Message</label>
                                    <textarea  
                                    id="message" 
                                    name="message" 
                                    rows="5"
                                    placeholder="Tell us about your needs or questions"
                                    class="w-full px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 
                                    focus:ring-pink-500 focus:border-transparent">
                                </textarea>
                                </div>
                                
                                <div>
                                    <button type="submit"
                                    class="bg-pink-600 hover:bg-pink-700 text-white rounded-full px-8 py-3 
                                    shadow-lg w-full md:w-auto" aria-label="submit contact form">Send Message</button>
                                </div>
                        </form>
                    </div>
                </section>

            </main>

            <!-------- Google Map  ------>
            <figure class="mt-16 bg-white rounded-2xl shadow-xl overflow-hidden">
                <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3889.113416111726!2d77.56793002539037!3d12.900428037408425!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3bae3ffcaf1d5637%3A0xfe7515248165e4f5!2sYelachenahalli%2C%20Bengaluru%2C%20Karnataka%20560111!5e0!3m2!1sen!2sin!4v1758437194411!5m2!1sen!2sin" 
                width="100%" height="450" style="border:0;" allowfullscreen="" loading="lazy"
                title="Clinic Location Map" class="rounded-2xl" aria-label="Map Showing Clinic location" ></iframe>
            </figure>
            </div>
    </section>
</template>

<script setup>
  import { Icon } from '@iconify/vue';
import { ref } from 'vue';

const contactItems = ref([
    {
        icon:'fa-solid:map-marker-alt',
        title: 'Address',
        content:`
        <p>123 Glamor St, Beauty City, BC 45678</p>`
    },
     {
        icon:'fa-solid:phone-alt',
        title: 'Phone Numbers',
        content:
        `<p>Appointments: <a href="tel:+9193456789" class="hover:text-pink-600">+9193456789</a></br>
           Emergency: <a href="tel:+9193456789" class="hover:text-pink-600">+9193456789</a>
            </p>`,
    },
    {
        icon:'fa-solid:envelope',
        title: 'Email',
        content:
        `<p>
             <a href="mailto:info@gmail.com" class="hover:text-pink-600">info@gmail.com</a></br>
           <a href="mailto:info@gmail.com" class="hover:text-pink-600">info@gmail.com</a>
            </p>`,
    },
      {
        icon:'fa-solid:clock',
        title: 'Working Hours',
        content:
        `<p>
                Monday - Friday: 9:00 AM - 8:00 PM</br>
                Saturday - Sunday: Closed
            </p>`,
    }
])
  const services = ref([
    {value:'botox' , label: 'Botox treatment'},
     {value:'fillers' , label: 'Derma Fillers '},
      {value:'laser' , label: 'laser Therapy'},
       {value:'Facelift' , label: 'Non-surgical Facelift'},
        {value:'other' , label: 'Other'},
])
</script>
