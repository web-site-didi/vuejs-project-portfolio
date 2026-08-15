<script setup>
import About from '../assets/about.jpg';

const stats = [
  { value: '+200', label: 'Clients' },
  { value: '+300', label: 'Projects' },
  { value: '+7', label: 'Years' },
]
</script>

<template>
  <section class="text-white mt-1 md:mt-16 relative overflow-hidden" id="about">
    <div class="max-w-7xl mx-auto px-4 md:grid md:grid-cols-2 gap-12 items-center py-16 xl:px-16 relative z-10">
      <div data-aos="fade-right">
        <h2 class="text-4xl md:text-5xl font-extrabold text-white mb-6">
          More <span class="text-primary">About</span> Me
        </h2>
        <p class="text-gray-400 text-base lg:text-lg mb-10 leading-relaxed">
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Delectus esse corrupti rerum. Sequi earum id
          doloribus quibusdam, quis dolorum, ex labore error dolor suscipit asperiores. Quae incidunt ratione provident
          earum.
          <br><br>
          Lorem ipsum dolor sit, amet consectetur adipisicing elit. Quas blanditiis obcaecati placeat possimus, nihil
          ullam labore odit deserunt, nesciunt nam ab neque dolore tempora aut. Necessitatibus nemo quod enim
          laboriosam!
        </p>
        <div class="grid grid-cols-3 gap-6 max-w-xl">
          <div v-for="item in stats" :key="item.label"
            class="text-center rounded-2xl bg-[#111a3e] border border-[#1f1641] p-5 transition-all duration-300 hover:border-primary/50">
            <h3 class="text-primary font-bold text-2xl md:text-3xl">
              {{ item.value }}
            </h3>
            <p class="text-xs text-gray-400 uppercase tracking-wider mt-1">
              {{ item.label }}
            </p>
          </div>
        </div>
      </div>
      <!-- Image -->
      <div class="mt-16 md:mt-0 flex justify-center lg:justify-end relative" data-aos="fade-left">
        <div class="relative w-64 h-64 md:w-96 md:h-120">
          <div class="absolute inset-0 z-0 rounded-full shadow-lg border border-primary translate-x-4 translate-y-4">
          </div>
          <div class="relative z-10 w-full h-full bg-[#111a3e] rounded-full overflow-hidden border border-[#1f1641]">
            <img :src="About" alt="about Me" class="w-full h-full object-cover transition-transform duration-500">
          </div>
        </div>
      </div>
    </div>
  </section>
</template>