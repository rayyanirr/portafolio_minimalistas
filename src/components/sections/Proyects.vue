<script setup>
import Section from '@/components/Section.vue'

import { projects } from '@cv';

</script>

<template>

    <Section title="Proyects">

        <ul>
            <li v-for="({ url, description, highlights, isActive, name }, index) in projects" :key="index">
                <article>
                    <header>
                        <h3>
                            <a :href="url" :title="`Ver el proyecto ${name}`">
                                {{ name }}
                            </a>
                            <span v-if="isActive"> &bull; </span>
                        </h3>
                        <p>{{ description }}</p>
                    </header>
                    <footer>

                        <span v-for="(highlight, index) of highlights" :key="index">
                            {{ highlight }}
                        </span>

                    </footer>

                </article>
            </li>

        </ul>
    </Section>

</template>


<style scoped>
ul {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1rem;
}

article {
    border-radius: 8px;
    border: 1px solid #f2f2f2;
    gap: 16px;
    display: flex;
    flex-direction: column;
    padding: 16px;
    height: 100%;
}

article header {
    flex: 1;
}

article h3 {
    margin-bottom: 4px;

}

article h3 span {
    color: rgb(16, 173, 110);

}

article a {
    color: #111;
}

article a:hover {
    text-decoration: underline;
}

article p {
    font-size: 0.7rem;
    line-height: 1.2rem;
    margin-bottom: 8px;

}



footer {
    display: inline-flex;
    flex-wrap: wrap;
    gap: 4px;
    font-size: 0.6rem;
}

footer span {
    border-radius: 6px;
    background-color: #eee;
    color: black;
    font-size: 0.6rem;
    font-weight: 500;
    padding: 0.2rem 0.6rem;
}
</style>