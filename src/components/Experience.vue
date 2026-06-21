<template>
    <section id="skills" class="text-white py-20 relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-6 lg:px-16 relative z-10">
            <div class="grid md:grid-cols-2 gap-16 items-start">
                <!-- Skills -->
                <div data-aos="fade-right">
                    <h2 class="text-4xl md:text-5xl font-extrabold mb-12">
                        Technical <span class="text-primary">Skills</span>
                    </h2>
                    <div class="space-y-8">
                        <div v-for="skill in skills" :key="skill.id" class="group">
                            <div class="flex items-center justify-between mb-2">
                                <div class="flex items-center gap-3">
                                    <div
                                        class="p-2 bg-[#111a3e] rounded-lg group-hover:bg-primary transition-colors duration-300">
                                        <component :is="skill.icons" :size="20"
                                            class="text-primary group-hover:text-white" />
                                    </div>
                                    <span class="font-medium tracking-wide">
                                        {{ skill.name }}
                                    </span>
                                </div>
                                <!-- <span class="text-primary font-bold">
                                    {{ skill.width }}
                                </span> -->
                            </div>
                            <div class="h-2 w-full bg-[#131d30] rounded-full p-0.5">
                                <div class="h-full rounded-full bg-linear-to-r from-primary to-green-400 shadow-[0_0_10px_#06a2c2]"
                                    :style="{ width: skill.width }" />
                            </div>
                        </div>
                    </div>
                </div>
                <!-- Experience -->
                <div data-aos="fade-left">
                    <h2 class="text-4xl md:text-5xl font-extrabold mb-12">
                        Work <span class="text-primary">Experience</span>
                    </h2>
                    <div class="space-y-6">
                        <div v-for="exp in exps" :key="exp.id"
                            class="group relative p-6 rounded-2xl bg-[#111a3e] border border-[#1f1641] hover:border-primary/50 transition-all duration-300">
                            <div class="flex gap-4">
                                <div class="shrink-0 mt-1">
                                    <div
                                        class="p-3 bg-[#050816] rounded-xl border border-gray-800 group-hover:border-primary transition-colors">
                                        <Briefcase class="text-primary" :size="24" />
                                    </div>
                                </div>
                                <div class="grow">
                                    <h3
                                        class="text-left font-bold text-white group-hover:text-primary transition-colors">
                                        {{ exp.role }}
                                    </h3>
                                    <div
                                        class="flex flex-col sm:flex-row sm:items-center gap-1 sm:gap-4 text-sm text-gray-400">
                                        <span class="flex items-center gap-1.5">
                                            <Building2 :size="14" class="text-primary" />
                                            {{ exp.company }}
                                        </span>
                                        <span class="flex items-center gap-1.5">
                                            <Calendar :size="14" class="text-primary" />
                                            {{ exp.date }}
                                        </span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import { Atom, Bot, BotMessageSquare, Briefcase, Building2, Calendar, Code, Code2, MonitorCloud, Wind } from 'lucide-vue-next';

const skills = [
    {
        id: 1,
        name: 'Kotlin',
        width: '100%',
        icons: Bot
    },
    {
        id: 2,
        name: 'React Native',
        width: '100%',
        icons: Atom
    },
    {
        id: 3,
        name: 'Flutter',
        width: '100%',
        icons: BotMessageSquare
    },
    {
        id: 4,
        name: 'Javascript',
        width: '100%',
        icons: MonitorCloud
    },
    {
        id: 5,
        name: 'Vue JS',
        width: '100%',
        icons: Code
    },
    {
        id: 6,
        name: 'HTML & CSS',
        width: '100%',
        icons: Code2
    },
    {
        id: 7,
        name: 'Tailwind CSS',
        width: '100%',
        icons: Wind
    },
]
const exps = [
    {
        id: 1,
        role: 'Frontend Developer (Website) - Freelance',
        company: 'PT. Stechoq Robotika Indonesia',
        date: '2026-Present'
    },
    {
        id: 2,
        role: 'Mobile Developer - Fulltime',
        company: 'PT. Timedoor Indonesia',
        date: '2022-2024'
    },
    {
        id: 3,
        role: 'Flutter Mobile Developer - Freelance',
        company: 'TechX',
        date: '2022-2024'
    },
    {
        id: 4,
        role: 'Flutter Mobile Developer - Freelance',
        company: 'Bank Sampah Desa Gunaksa',
        date: '2022'
    },
    {
        id: 5,
        role: 'Frontend Developer (Website) - Internship',
        company: 'PT. Timedoor Indonesia',
        date: '2021-2022'
    },
    {
        id: 6,
        role: 'Coding Teacher - Part-time',
        company: 'PT. Timedoor Indonesia',
        date: '2023-2025'
    },
    {
        id: 7,
        role: 'Frontend Developer Mentor - Freelance',
        company: 'Teach4Hope by KitaBisa',
        date: '2024'
    },
]
</script>
