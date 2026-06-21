<template>
    <section id="certificates" class="text-white py-20">
        <div class="max-w-7xl mx-auto px-6 lg:px-16">
            <div class="mb-16">
                <p class="text-primary text-sm uppercase mb-2 tracking-widest font-semibold">Achievements</p>
                <h2 class="text-4xl md:text-5xl font-extrabold text-white">Certifications</h2>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div v-for="cert in certificates" :key="cert.id" data-aos="zoom-in"
                    class="group relative bg-[#111a3e] border border-[#1f1641] p-6 rounded-2xl transition-all duration-300 hover:border-primary/50 hover:shadow-[0_0_20px_-5px_rgba(6,162,194,0.2)]">
                    <CertificateCard :cert="cert" />
                </div>
            </div>
        </div>
    </section>
</template>

<script setup>
import CertificateCard from './CertificateCard.vue';

const certificates = [
    {
        id: 1,
        title: 'Basic Kotlin Programming',
        issuer: 'Dicoding Indonesia',
        date: 'February 2021',
        link: 'https://www.dicoding.com/certificates/JMZVM480NZN9',
        desc: 'Basic knowledge of Kotlin programming, including syntax, data types, control flow, and object-oriented programming concepts. This certification demonstrates proficiency in using Kotlin for Android development and other applications.',
    },
    {
        id: 2,
        title: 'Android Application Fundamental',
        issuer: 'Dicoding Indonesia',
        date: 'April 2021',
        link: 'https://www.dicoding.com/certificates/1RXY43Q3MPVM',
        desc: 'Fundamental knowledge of Android application development, including UI design, application lifecycle, navigation, networking, and design pattern. This certification demonstrates the ability to create functional Android applications using best practices and industry standards.',
    },
    {
        id: 3,
        title: 'Android Developer Expert',
        issuer: 'Dicoding Indonesia',
        date: 'May 2021',
        link: 'https://www.dicoding.com/certificates/QLZ985N2EX5D',
        desc: 'Broad knowledge of Android application development with an expert development standard. Focusing more on the implementation of clean architecture, reactive programming, dependency injection, and performance optimization. This certification demonstrates the ability to create high-quality Android applications that are maintainable, scalable, and efficient.',
    },
    {
        id: 7,
        title: 'SOLID Principles in Object-Oriented Programming',
        issuer: 'Dicoding Indonesia',
        date: 'February 2024',
        link: 'https://www.dicoding.com/certificates/EYX40EO25PDL',
        desc: 'Understanding of SOLID principles in object-oriented programming, including single responsibility, open-closed, Liskov substitution, interface segregation, and dependency inversion. This certification demonstrates the ability to apply SOLID principles to create maintainable and scalable software solutions.',
    },
    {
        id: 8,
        title: 'Spec-Driven Development (SDD) with Kiro AI',
        issuer: 'Dicoding Indonesia',
        date: 'April 2026',
        link: 'https://www.dicoding.com/certificates/2VX30RR33XYQ',
        desc: 'Fresh knowledge of Spec-Driven Development (SDD) using Kiro AI as an AI Agent, including understanding the principles of SDD, utilizing Kiro AI for generating specifications, and applying SDD practices in software development. This certification demonstrates proficiency in leveraging Kiro AI to enhance the software development process through effective specification-driven approaches.',
    },
    {
        id: 4,
        title: 'React Programming Course',
        issuer: 'Progate',
        date: 'March 2022',
        link: 'https://progate.com/course_certificate/a7d786e1r9gn86',
        desc: 'Basic knowledge of React programming, including components, state management, hooks, and routing. This certification demonstrates proficiency in building dynamic and interactive web applications using React.',
    },
    {
        id: 5,
        title: 'Javascript Programming Course',
        issuer: 'Progate',
        date: 'March 2022',
        link: 'https://progate.com/course_certificate/d3273294r9envy',
        desc: 'Basic knowledge of JavaScript programming, including syntax, data types, control flow, functions, and object-oriented programming concepts. This certification demonstrates proficiency in using JavaScript for web development and other applications.',
    },
    {
        id: 6,
        title: 'HTML & CSS Programming Course',
        issuer: 'Progate',
        date: 'March 2022',
        link: 'https://progate.com/course_certificate/ebcfb395r93rgp',
        desc: 'Basic knowledge of HTML and CSS programming, including syntax, selectors, layout, and responsive design. This certification demonstrates proficiency in creating visually appealing and user-friendly web pages.',
    },
]
</script>