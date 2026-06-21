<template>
    <section id="education" class="text-white py-20 overflow-hidden">
        <div class="max-w-7xl mx-auto px-6 lg:px-16">
            <div class="mb-16">
                <p class="text-primary text-sm uppercase mb-2 tracking-widest font-semibold">Learning Path</p>
                <h2 class="text-4xl md:text-5xl font-extrabold text-white">Education</h2>
            </div>
            <div class="flex flex-col lg:flex-row items-center gap-16">
                <div class="w-full lg:w-5/12 flex justify-center lg:justify-start" data-aos="fade-right">
                    <div class="relative">
                        <div
                            class="absolute h-full w-full z-0 p-2 translate-x-4 translate-y-4 rounded-2xl shadow-lg border border-primary">
                        </div>
                        <div class="relative z-10 bg-[#111a2e] rounded-2xl overflow-hidden border border-[#1f1641]">
                            <img :src="educ" alt="education"
                                class="w-64 h-64 md:w-96 md:h-120 object-cover transform transition-transform duration-500 hover:scale-110" />
                        </div>
                    </div>
                </div>
                <!-- Content -->
                <div class="w-full lg:w-7/12 space-y-6" data-aos="fade-left">
                    <div v-for="edu in educationData" :key="edu.id"
                        class="group relative p-6 rounded-2xl bg-[#1f1641] transition-all duration-300 hover:border-primary/50">
                        <div class="flex flex-col sm:flex-row sm:items-center justify-between gap-4 mb-4">
                            <div class="flex gap-3 items-center">
                                <div
                                    class="bg-[#050816] p-2 rounded-lg border border-primary/20 group-hover:border-primary transition-colors">
                                    <GraduationCap class="text-primary" :size="24" />
                                </div>
                                <div>
                                    <h3 class="text-lg font-bold text-white group-hover:text-primary transition-colors">
                                        {{ edu.degree }}
                                    </h3>
                                    <p class="text-gray-400 text-sm">
                                        {{ edu.institution }}
                                    </p>
                                </div>
                            </div>
                            <div
                                class=" flex items-center gap-2 text-xs font-medium bg-[#050816] px-3 py-1 rounded-full border border-gray-700 w-fit">
                                <Calendar :size="12" class="text-primary" />
                                {{ edu.duration }}
                            </div>
                        </div>
                        <p class="text-gray-400 text-sm leading-relaxed my-4">
                            {{ edu.details }}
                        </p>
                        <div class="flex items-center gap-2 text-[10px] tracking-wider text-primary font-bold">
                            <CheckCircle2 :size="12" />
                            Academic Excellence
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import educ from '@/assets/educ.jpg';
import { Calendar, CheckCircle2, GraduationCap } from 'lucide-vue-next';

const educationData = [
    {
        id: 1,
        degree: 'Bachelor of Information Techonology',
        institution: 'Universitas Udayana',
        duration: '2018 - 2022',
        details: 'I started my Mobile Development journey from Google Bangkit-Android Development Bootcamp, while doing Internet Network project as my final task. Besides my academic activity, I also take part as Teaching Assistant for Algorithm, Networking, and Android Development subjects. I also active in organization during college, was once a head division of internal public relation. I finish my bachelor degree with GPA score of 3.69.'
    },
    {
        id: 2,
        degree: 'Master of Engineering in IT',
        institution: 'Universitas Gadjah Mada',
        duration: '2024 - 2026',
        details: '2 years after becoming a Mobile Application Developer, I decided to pursue my master degree in Universitas Gadjah Mada. For 2 years, I research a lot about Machine Learning and Deep Learning, especially about Federated Learning as my main research topic. Trying to combine the AI Technology with Mobile Application in order to create a more efficient and effective mobile application.'
    },
]
</script>