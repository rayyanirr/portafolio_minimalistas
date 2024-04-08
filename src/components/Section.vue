<script setup>

const props = defineProps(['title'])

</script>

<template>
    <section>

        <h2 v-if="props.title !== null"> {{ props.title }}</h2>
        <slot />
    </section>
</template>

<style scoped>
section {
    max-width: 700px;
    margin: 0 auto 48px
}

h2 {
    margin-bottom: 8px;
    font-weight: 700;
    line-height: 1.5;
    font-size: 1.5rem;
}
</style>