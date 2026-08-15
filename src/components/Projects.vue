<script setup>
import project1 from '../assets/project1.png'
import project2 from '../assets/project2.png'
import project3 from '../assets/project3.png'
import project4 from '../assets/project4.png'
import project5 from '../assets/project5.png'
import project6 from '../assets/project6.png'

const projects = [
  {
    id: 1,
    image: project1,
    title: 'E-Commerce Platform',
    desc: 'Modern e-commerce solution',
    technology: ['React', 'Node.js', 'MongoDb'],
  },
  {
    id: 2,
    image: project2,
    title: 'E-Commerce Platform',
    desc: 'Modern e-commerce solution',
    technology: ['Vue', 'Node.js', 'MongoDb'],
  },
  {
    id: 3,
    image: project3,
    title: 'E-Commerce Platform',
    desc: 'Modern e-commerce solution',
    technology: ['React', 'Node.js', 'MongoDb'],
  },
  {
    id: 4,
    image: project4,
    title: 'E-Commerce Platform',
    desc: 'Modern e-commerce solution',
    technology: ['Vue', 'Node.js', 'MongoDb'],
  },
  {
    id: 5,
    image: project5,
    title: 'E-Commerce Platform',
    desc: 'Modern e-commerce solution',
    technology: ['React', 'Node.js', 'MongoDb'],
  },
  {
    id: 6,
    image: project6,
    title: 'E-Commerce Platform',
    desc: 'Modern e-commerce solution',
    technology: ['Vue', 'Node.js', 'MongoDb'],
  },
]
</script>

<template>
  <section class="py-16 bg-gray-900" id="projects">
    <div class="container mx-auto px-4 max-w-7xl" data-aos="zoom-in">
      <div class="text-center mb-10">
        <h2 class="text-4xl md:text-5xl font-extrabold text-white">
          Projects.
        </h2>
        <div class="w-28 h-1 bg-primary mx-auto mt-4 rounded-2xl"></div>
      </div>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
        <div v-for="project in projects" :key="project.id"
          class="bg-gray-800 rounded-lg overflow-hidden shadow-sm hover:shadow-lg hover:scale-105 transition-all duration-300">
          <img :src="project.image" :alt="project.title"
            class="w-full h-44 object-cover hover:opacity-90 transition-opacity duration-300">
          <div class="p-4">
            <h3 class="text-lg font-semibold text-white group-hover:primary transition-colors">
              {{ project.title }}
            </h3>
            <p class="text-gray-400 text-sm mt-1">
              {{ project.desc }}
            </p>
            <div class="flex flex-wrap gap-1.5 mt-3">
              <span v-for="(tech, index) in project.technology" :key="index"
                class="text-xs px-2 py-0.5 bg-gray-700 text-gray-300 rounded hover:bg-primary hover:text-white transition-colors duration-300">
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>