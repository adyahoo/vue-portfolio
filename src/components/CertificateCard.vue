<template>
    <div>
        <div
            class="absolute -top-4 -right-4 bg-primary p-3 rounded-xl shadow-lg transform group-hover:rotate-12 transition-transform">
            <Award :size="24" class="text-white" />
        </div>
        <div class="flex items-center gap-4 mb-4 text-xs text-gray-400">
            <span class="flex items-center gap-1">
                <ShieldCheck :size="14" class="text-primary" />
                {{ cert.issuer }}
            </span>
        </div>
        <h3 class="text-xl font-bold mb-3 group-hover:text-primary transition-colors">
            {{ cert.title }}
        </h3>
        <p class="text-gray-400 text-sm mb-6 text-justify" :class="{ 'line-clamp-2': !isExpanded }">
            {{ cert.desc }}
        </p>
        <div class="flex justify-between items-center">
            <a :href="cert.link" target="_blank" rel="noopener noreferrer"
                class="inline-flex items-center gap-2 text-sm font-medium text-primary hover:text-white transition-colors border-b border-transparent hover:border-white pb-1">
                View Certificate
                <ExternalLink :size="14" />
            </a>
            <p class="text-gray-400 text-sm hover:text-white hover:cursor-pointer transition-colors"
                @click="toggleExpand">
                {{ isExpanded ? 'See less' : 'See more' }}
            </p>
        </div>
    </div>
</template>

<script setup>
import { Award, ExternalLink, ShieldCheck } from 'lucide-vue-next';
import { ref } from 'vue';

const props = defineProps({
    cert: {
        type: Object,
        required: true,
    },
});

const isExpanded = ref(false);
const toggleExpand = () => {
    isExpanded.value = !isExpanded.value;
};

</script>