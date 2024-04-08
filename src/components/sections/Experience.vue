<script setup>
import Section from '@/components/Section.vue'
import { work } from "@cv"

const obtenerAno = (fecha) => {
    return fecha !== null ? new Date(fecha).getFullYear() : 'Actual';
};

</script>

<template>

    <Section title="Work Experience">

        <ul v-for="({ name, position, url, startDate, endDate, summary, highlights }, index) in work" :key="index">

            <li>
                <article>
                    <header>
                        <div>

                            <h3>{{ name }}</h3>
                            <h4>{{ position }}</h4>
                        </div>

                        <time>
                            {{ obtenerAno(startDate) }} - {{ obtenerAno(endDate) }}
                        </time>
                    </header>

                    <footer>
                        <p>{{ summary }}</p>

                    </footer>


                </article>

            </li>
        </ul>

    </Section>

</template>

<style scoped>
ul {
    display: flex;
    flex-direction: column;
    gap: 32px;
}

li {
    margin-top: 1rem;
}

article h3 {
    font-weight: 500;
    color: #111;
}

article h4 {
    font-weight: 400;
    color: #222;
}

header {
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    margin-bottom: 4px;
}

time {
    font-size: 0.85rem;
    color: #555;
}
</style>