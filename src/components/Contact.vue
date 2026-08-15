<script setup>
import { reactive, ref } from 'vue';
import { Linkedin, Mail, MapPin, Phone } from 'lucide-vue-next';

const contactInfo = [
  {
    id: 1,
    icon: Mail,
    title: 'Email',
    value: 'example@example.com',
    link: 'mailto:example@example.com'
  },
  {
    id: 2,
    icon: Phone,
    title: 'Phone',
    value: '+123 4567890',
    link: 'tel:+1234567890'
  },
  {
    id: 3,
    icon: Linkedin,
    title: 'LinkedIn',
    value: 'linkedin.com/in/username',
    link: '#'
  },
  {
    id: 4,
    icon: MapPin,
    title: 'Location',
    value: 'New York, USA',
    link: null
  },
]

const formData = reactive({
  email: '',
  subject: '',
  message: ''
})

const isSubmitting = ref(false)

const handleSubmit = async () => {
  isSubmitting.value = true

  try {
    formData.email = ''
    formData.subject = ''
    formData.message = ''
  } catch (error) {
    alert('Failed to send message. Please try again')
  } finally {
    isSubmitting.value = false
  }
}
</script>

<template>
  <section class="py-20 bg-gray-900" id="contact">
    <div class="container mx-auto px-4 max-w-6xl" data-aos="zoom-out">
      <div class="text-center mb-12">
        <h2 class="text-3xl md:text-5xl font-extrabold text-white mb-2">
          Let's Connect
        </h2>
        <div class="w-28 h-1 bg-primary mx-auto mt-2 rounded-2xl"></div>
      </div>
      <div class="grid md:grid-cols-2 gap-8">
        <div>
          <p class="text-gray-400 mb-8 leading-relaxed">
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Ipsa laudantium, nisi eaque eos ipsam
            perspiciatis illo dignissimos quasi nemo modi impedit dolor beatae esse. Dolorem minus tenetur atque illo
            quae!
          </p>
          <div class="space-x-6">
            <div v-for="info in contactInfo" :key="info.id" class="flex items-center gap-4 group">
              <div
                class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center group-hover:bg-primary/20 transition-colors">
                <component :is="info.icon" :size="18" class="text-primary" />
              </div>
              <div>
                <h4 class="text-white font-medium text-sm mt-2">
                  {{ info.title }}
                </h4>
                <a v-if="info.link" :href="info.link" class="text-gray-400 text-sm hover:text-primary transition-colors"
                  :target="info.title === 'Location' ? '_self' : '_blank'"
                  :ref="info.title === 'Location' ? '' : 'noopener noreferrer'">
                  {{ info.value }}
                </a>
                <p v-else class="text-gray-400 text-sm mt-2">
                  {{ info.value }}
                </p>
              </div>
            </div>
          </div>
        </div>
        <!-- Form -->
        <div class="bg-gray-800 rounded-lg p-6">
          <form @submit.prevent="handleSubmit">
            <!-- Email -->
            <div class="mb-4">
              <label for="email" class="text-white block mb-4 text-sm font-medium">
                Email
              </label>
              <input type="email" id="email" v-model="formData.email"
                class="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white text-sm focus:outline-none focus:border-primary transition-colors"
                placeholder="your@email.com" required />
            </div>
            <!-- Message -->
            <div class="mb-4">
              <label for="message" class="text-white block mb-4 text-sm font-medium">
                Message
              </label>
              <textarea id="message" v-model="formData.message"
                class="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white text-sm focus:outline-none focus:border-primary transition-colors"
                placeholder="Your Message ..." rows="4" required />
            </div>
            <button
              class="w-full px-6 py-2.5 bg-primary text-white rounded-xl font-medium hover:bg-primary/80 transition-colors disabled:opacity-50 disabled:cursor-not-allowed">
              {{ isSubmitting ? 'Sending...' : 'Send Message' }}
            </button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>