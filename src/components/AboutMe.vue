<template>
    <section id="about" class="text-white mt-4 md:mt-12 relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 md:grid md:grid-cols-2 gap-12 items-center py-16 xl:px-16 relative z-10">
            <div data-aos="fade-right">
                <h2 class="text-4xl md:text-5xl font-extrabold text-white mb-6">
                    More <span class="text-primary">About</span> Me
                </h2>
                <p class="text-gray-400 text-base lg:text-lg mb-10 leading-relaxed">
                    Besides my passion for programming, I have a deep love for hiking, traveling, and gaming. Exploring
                    new trails and immersing myself in nature allows me to recharge and find inspiration for my coding
                    projects. Traveling has broadened my perspective and exposed me to diverse cultures, which I believe
                    enhances my creativity as a developer. Additionally, gaming has honed my problem-solving skills and
                    taught me the importance of teamwork and strategy. I also enjoy sharing my knowledge by teaching
                    programming to others, which has been a rewarding experience that allows me to give back to the
                    community. I've been teaching programming for over 2 years, and focusing on high school students and
                    early college students. I'm excited to continue this journey and help others learn and grow in the
                    field of information technology.
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
                <div class="relative w-64 h-64 md:w-96 md:h-10/12">
                    <div
                        class="absolute inset-0 z-0 rounded-full shadow-lg border border-primary translate-x-4 translate-y-4" />
                    <div
                        class="relative z-10 w-full h-full bg-[#111a3e] rounded-full overflow-hidden border border-[#1f1641]">
                        <img :src="about" alt="About Me"
                            class="w-full h-full object-cover transition-transform duration-500 hover:scale-110" />
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import about from '../assets/2.jpg';

const stats = [
    { value: '4+', label: 'Clients' },
    { value: '5+', label: 'Projects' },
    { value: '2+', label: 'Years' },
]
</script>
