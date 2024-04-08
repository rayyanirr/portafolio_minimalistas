<script setup>
import Section from '@/components/Section.vue'

import { skills } from '@cv'

</script>

<template>

    <Section title="Skills">
        <ul v-for="({ name }, index) in skills" :key="index">

            <li>
                <span>{{ name }}</span>
            </li>

        </ul>
    </Section>

</template>

<style scoped>
ul {
    display: inline-flex;
    gap: 8;
    flex-wrap: wrap;
}

li {
    border-radius: 6px;
    background-color: #eee;
    color: black;
    font-size: .8rem;
    font-weight: 500;
    padding: 0.2rem 0.6rem;
}
</style>