<script setup>
import { basics } from '@cv'
import Section from '@/components/Section.vue'


const { summary } = basics;

</script>

<template>

    <Section title="About">
        <p>{{ summary }}</p>
    </Section>

</template>