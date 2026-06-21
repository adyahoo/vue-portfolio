<template>
    <section id="contact" class="pt-20 bg-gray-900">
        <div class="container mx-auto px-4 max-w-6xl">
            <div class="text-center mb-12">
                <h2 class="text-3xl md:text-5xl font-extrabold text-white mb-2">
                    Let's Connect
                </h2>
                <div class="w-28 h-1 bg-primary mx-auto mt-2 rounded-2xl" />
            </div>
            <div class="grid gap-8">
                <!-- Description -->
                <div>
                    <p class="text-gray-400 mb-8 leading-relaxed md:text-center md:text-lg">
                        I'm always open to new opportunities and collaborations. <br>Whether you have a project in mind
                        or
                        just want to chat, feel free to get in touch with me.
                    </p>
                    <div class="space-y-6 md:flex md:flex-row md:justify-between">
                        <div v-for="info in infos" :key="info.id" class="flex items-center gap-4 group">
                            <div
                                class="w-10 h-10 rounded-full bg-primary/10 flex items-center justify-center group-hover:bg-primary/20 transition-colors">
                                <component :is="info.icon" :size="24" class="text-primary" />
                            </div>
                            <div>
                                <h4 class="text-white font-medium text-sm">
                                    {{ info.title }}
                                </h4>
                                <a v-if="info.link" :href="info.link"
                                    class="text-gray-400 text-sm hover:text-primary transition-colors"
                                    :target="info.title === 'Location' ? '_self' : '_blank'"
                                    :ref="info.title === 'Location' ? '' : 'noopener noreferrer'">
                                    {{ info.value }}
                                </a>
                                <p v-else class="text-gray-400 text-sm">
                                    {{ info.value }}
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
                <!-- Form -->
                <!-- <div class="bg-gray-800 rounded-lg p-6">
                    <form @submit.prevent="handleSubmit">
                        <div class="mb-4">
                            <label for="email" class="text-white block mb-2 text-sm font-medium">Email</label>
                            <input type="email" id="email" v-model="formData.email"
                                class="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white text-sm focus:outline-none focus:border-primary transition-colors"
                                placeholder="example@email.com" required />
                        </div>
                        <div class="mb-4">
                            <label for="message" class="text-white block mb-2 text-sm font-medium">Message</label>
                            <textarea id="message" v-model="formData.message"
                                class="w-full px-4 py-2 bg-gray-700 border border-gray-600 rounded-lg text-white text-sm focus:outline-none focus:border-primary transition-colors"
                                placeholder="Leave message for me here.." rows="4" required />
                        </div>
                        <button type="submit" :disabled="isSubmitting"
                            class="w-full px-6 py-2.5 bg-primary text-white rounded-lg font-medium hover:bg-primary/80 transition-colors disabled:opacity-50 disabled:cursor-not-allowed">
                            {{ isSubmitting ? 'Sending...' : 'Send Message' }}
                        </button>
                    </form>
                </div> -->
            </div>
        </div>
    </section>
</template>

<script setup>
import { createLucideIcon, Linkedin, Mail } from 'lucide-vue-next';
import { reactive, ref } from 'vue';

const infos = [
    {
        id: 1,
        icon: Linkedin,
        title: 'LinkedIn',
        value: 'linkedin.com/in/maulidi-adi/',
        link: 'https://www.linkedin.com/in/maulidi-adi/'
    },
    {
        id: 2,
        icon: Mail,
        title: 'Email',
        value: 'maulidi.adiprasetia@gmail.com',
        link: null
    },
    {
        id: 3,
        icon: createLucideIcon("git-hub", [
            ["path", { "d": "M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8", "key": "13rawv" }]
        ]),
        title: 'GitHub',
        value: 'adyahoo (Maulidi Adi Prasetia)',
        link: 'https://github.com/adyahoo/'
    },
    {
        id: 4,
        icon: createLucideIcon("instagram", [
            ["path", { "d": "M12.271 2.77A0.96 0.96 0 1 0 12.271 4.69A0.96 0.96 0 0 0 12.271 2.77", "key": "1m8l3w" }],
            ["path", { "d": "M7.283 1.442H8.001C10.137 1.442 10.39 1.449 11.233 1.488C12.013 1.523 12.437 1.654 12.719 1.763C13.092 1.908 13.359 2.082 13.639 2.362S14.092 2.908 14.237 3.282C14.347 3.563 14.477 3.987 14.512 4.767C14.551 5.61 14.559 5.863 14.559 7.998S14.551 10.387 14.512 11.23C14.477 12.01 14.346 12.433 14.237 12.715A2.5 2.5 0 0 1 13.638 13.634C13.358 13.914 13.092 14.087 12.718 14.232C12.438 14.342 12.014 14.472 11.233 14.508C10.39 14.546 10.137 14.555 8.001 14.555S5.611 14.546 4.768 14.508C3.988 14.472 3.565 14.342 3.283 14.232A2.5 2.5 0 0 1 2.363 13.634A2.5 2.5 0 0 1 1.763 12.714C1.654 12.433 1.523 12.009 1.488 11.229C1.45 10.386 1.442 10.133 1.442 7.996S1.45 5.608 1.488 4.765C1.524 3.985 1.654 3.561 1.764 3.279C1.909 2.906 2.083 2.639 2.363 2.359S2.909 1.906 3.283 1.761C3.565 1.651 3.988 1.521 4.768 1.485C5.506 1.451 5.792 1.441 7.283 1.44Z", "key": "9sywsr" }],
            ["path", { "d": "M8 0C5.829 0 5.556 0.01 4.703 0.048C3.85 0.088 3.269 0.222 2.76 0.42A3.9 3.9 0 0 0 1.343 1.343A3.9 3.9 0 0 0 0.42 2.76C0.222 3.268 0.087 3.85 0.048 4.7C0.01 5.555 0 5.827 0 8.001C0 10.173 0.01 10.445 0.048 11.298C0.088 12.15 0.222 12.731 0.42 13.24C0.625 13.766 0.898 14.212 1.343 14.657C1.787 15.102 2.233 15.376 2.759 15.58C3.269 15.778 3.849 15.913 4.701 15.952C5.555 15.99 5.827 16 8 16S10.444 15.99 11.298 15.952C12.149 15.912 12.732 15.778 13.241 15.58A3.9 3.9 0 0 0 14.657 14.657C15.102 14.212 15.375 13.766 15.58 13.24C15.777 12.731 15.912 12.15 15.952 11.298C15.99 10.445 16 10.173 16 8S15.99 5.555 15.952 4.701C15.912 3.85 15.777 3.268 15.58 2.76A3.9 3.9 0 0 0 14.657 1.343A3.9 3.9 0 0 0 13.24 0.42C12.73 0.222 12.148 0.087 11.297 0.048C10.443 0.01 10.172 0 7.998 0Z", "key": "11qio8" }],
            ["path", { "d": "M8.001 3.892A4.109 4.109 0 1 0 8.001 12.109A4.109 4.109 0 0 0 8.001 3.892", "key": "pjbwp0" }],
            ["path", { "d": "M8.001 5.333A2.667 2.667 0 1 1 8.001 10.667A2.667 2.667 0 0 1 8.001 5.333", "key": "8ac0tl" }]
        ]),
        title: 'Instagram',
        value: 'adyahooo',
        link: 'https://www.instagram.com/adyahooo/'
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
    } catch (error) {
        alert('Failed to send message')
    } finally {
        isSubmitting.value = false
    }
}
</script>
