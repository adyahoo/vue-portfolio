<template>
    <section id="projects" class="py-16 bg-gray-900">
        <div class="container mx-auto px-4 max-w-7xl">
            <div class="text-center mb-10">
                <h2 class="text-4xl md:text-5xl font-extrabold text-white">
                    Projects
                </h2>
                <div class="w-28 h-1 bg-primary mx-auto mt-2 rounded-2xl"></div>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-5">
                <div v-for="proj in projects" :key="proj.id"
                    class="bg-gray-800 rounded-lg overflow-hidden shadow-sm hover:shadow-lg hover:scale-105 transition-all duration-300">
                    <img :src="proj.image" :alt="proj.title"
                        class="w-full h-44 object-cover hover:opacity-90 transition-opacity duration-300" />
                    <div class="p-4">
                        <h3 class="text-lg font-semibold text-white group-hover:primary transition-colors">
                            {{ proj.title }}
                        </h3>
                        <p class="text-gray-400 text-sm mt-1 text-justify">
                            {{ proj.desc }}
                        </p>
                        <div class="flex flex-wrap gap-1.5 mt-3">
                            <div v-for="(tech, idx) in proj.techg" :key="idx"
                                class="text-xs px-2 py-0.5 bg-gray-700 text-gray-300 rounded hover:bg-primary hover:text-white transition-colors duration-300">
                                {{ tech }}
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import blanjablanja from '@/assets/projects/blanjablanja.jpg';
import digitirta from '@/assets/projects/digitirta.jpg';
import gunabangsa from '@/assets/projects/gunabangsa.png';
import hino from '@/assets/projects/hino_connect.png';
import senyumku from '@/assets/projects/senyumku.png';

const projects = [
    {
        id: 1,
        image: blanjablanja,
        title: 'Blanjablanja.id',
        desc: 'Marketplace platform that provides a wide range of products to technician services in one application.',
        techg: ['Kotlin', 'Android']
    },
    {
        id: 2,
        image: digitirta,
        title: 'Digitirta',
        desc: 'DigiTirta facilitates meter recording and daily financial bookkeeping for groups managing rural water supply and sanitation systems so that they can be used as a basis for determining future steps.',
        techg: ['Kotlin', 'Android']
    },
    {
        id: 3,
        image: gunabangsa,
        title: 'GunaBangsa',
        desc: 'GunaBangsa is a digital platform to pick-up recyclable waste and exchange it for rewards, aiming to promote sustainable waste management practices.',
        techg: ['Flutter', 'Dart', 'Android']
    },
    {
        id: 4,
        image: hino,
        title: 'Hino Connect Driver',
        desc: 'Hino-Connect Driver is a report and analysis application for truck drivers while on the road. Show how the delivery process and give warning for driving violations.',
        techg: ['Flutter', 'Dart', 'Android']
    },
    {
        id: 5,
        image: senyumku,
        title: 'SenyumKu',
        desc: 'A therapy application for expression rehabilitation of facial paralysis patients. It provides various exercises and activities to help patients improve their facial muscle strength and coordination.',
        techg: ['Flutter', 'Dart', 'Android']
    }
]
</script>