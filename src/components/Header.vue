<template>
    <header class="relative z-50 px-6 py-7">
        <div class="max-w-7xl mx-auto flex justify-between items-center">
            <!-- Logo -->
            <div class="text-white text-3xl font-black cursor-pointer">
                Portfolio <span class="text-primary">.</span>
            </div>
            <!-- Navigation -->
            <nav class="hidden md:flex items-center gap-10">
                <ul class="flex gap-8">
                    <li v-for="items in menuItems" :key="items.name">
                        <button @click="scrollToSection(items.href)"
                            class="text-gray-300 hover:text-white text-base font-medium transition-colors">
                            {{ items.name }}
                        </button>
                    </li>
                </ul>
                <button @click="scrollToSection('#contact')"
                    class="bg-primary hover:bg-primary/90 text-white px-6 py-2.5 rounded-lg text-base font-semibold transition-all">
                    Contact Me
                </button>
            </nav>
            <!-- Menu Button -->
            <button class="md:hidden text-white" @click="isMenuOpen = !isMenuOpen">
                <Menu :size="32" />
            </button>
            <!-- Menu Window on Small Screen -->
            <!-- Gray BG -->
            <div v-if="isMenuOpen" class="fixed bg-black/40 backdrop-blur-sm w-full inset-0 md:hidden"
                @click="isMenuOpen = false"></div>
            <!-- Menu Window -->
            <div class="fixed right-0 top-0 bg-base-blue h-full w-100 z-50 transform transition-transform duration-300 md:hidden p-4"
                :class="isMenuOpen ? 'translate-x-0' : 'translate-x-full'">
                <button class="w-full justify-items-end text-white mb-10" @click="isMenuOpen = false">
                    <X :size="32"></X>
                </button>
                <ul class="flex flex-col gap-8">
                    <li v-for="items in menuItems" :key="items.name">
                        <button @click="scrollToSection(items.href)"
                            class="text-white text-xl font-semibold hover:text-primary transition-colors">
                            {{ items.name }}
                        </button>
                    </li>
                    <li class="mt-6">
                        <button @click="scrollToSection('#contact')"
                            class="bg-primary hover:bg-primary/90 text-white px-6 py-2.5 rounded-xl text-lg font-bold transition-all w-full">
                            Contact Me
                        </button>
                    </li>
                </ul>
            </div>
        </div>
    </header>
</template>

<script setup>
import { Menu, X } from 'lucide-vue-next';
import { ref } from 'vue';


const isMenuOpen = ref(false)

const menuItems = [
    { name: 'Education', href: '#education' },
    { name: 'Certificates', href: '#certificates' },
    { name: 'About', href: '#about' },
    { name: 'Skills', href: '#skills' },
    { name: 'Projects', href: '#projects' },
]
const scrollToSection = (href) => {
    isMenuOpen.value = false
    const element = document.querySelector(href)

    if (element) {
        element.scrollIntoView({ behavior: 'smooth' })
    }
}
</script>
