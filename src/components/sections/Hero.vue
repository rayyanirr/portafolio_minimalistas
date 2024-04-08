<script setup>
import { basics } from '@cv'
import Section from '@/components/Section.vue'
import IconMail from '@/components/Icons/Mail.vue'
import IconPhone from '@/components/Icons/Phone.vue'
import X from '@/components/Icons/X.vue'
import GitHub from '@/components/Icons/Github.vue'
import LinkedIn from '@/components/Icons/LinkedIn.vue'
import WorldMap from '@/components/Icons/WorldMap.vue'

const { name, label, image, location, profiles, phone, email } = basics;
const { city, region } = location;

const LinkedInfo = profiles.find(({ network }) => network === 'LinkedIn');
const LinkedUrl = LinkedInfo?.url

const SOCIAL_ICONS = {
    LinkedIn,
    GitHub,
    X,
}

</script>

<template>
    <Section>
        <div class="container">
            <div class="info">
                <h1>{{ name }}</h1>
                <h2>{{ label }}</h2>
                <span>
                    <WorldMap />
                    {{ city }}, {{ region }}
                </span>
                <footer>

                    <div class="print">
                        {{ email }} | {{ phone }} | {{ LinkedUrl }} |
                    </div>

                    <div class="no-print">
                        <a v-if="email !== null" :href="`mailto:${email}`"
                            :title="`Enviar un correo electronico a ${name} al correo ${email} `" target="_blank"
                            rel="noopener noreferrer">
                            <IconMail />
                        </a>

                        <a v-if="phone !== null" :href="`tel:${phone}`"
                            :title="`Llamar por telefono a  ${name} al numero ${phone} `" target="_blank"
                            rel="noopener noreferrer">
                            <IconPhone />
                        </a>



                        <a v-for="({ url, network }, index) in profiles" :key="index" :href="url"
                            :title="`Visitar el perfil de  ${name} en ${network} `" target="_blank"
                            rel="noopener noreferrer">
                            <component :is="SOCIAL_ICONS[network]" />
                        </a>
                    </div>



                </footer>
            </div>

            <figure>
                <img :src="image" :alt="name">
            </figure>

        </div>
    </Section>

</template>

<style scoped>
.container {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    gap: 1rem;
}

.info {

    display: flex;
    flex-direction: column;
    gap: 0.5rem;
    padding-right: 32px;

}

h1 {
    font-size: 2rem;
}

h2 {
    color: #444;
    font-weight: 500;
    font-size: 1.1rem;
    text-wrap: balance;
}

span {
    color: #666;
    display: flex;
    align-items: center;
    gap: .25rem;
    font-size: .85rem;
    letter-spacing: -0.05rem;


}

img {
    aspect-ratio: 1 / 1;
    object-fit: cover;
    width: 129px;
    border-radius: 6px;
}

footer {
    color: #555;
    font-size: 0.65rem;
    display: flex;
    gap: 4px;
    margin-top: 8px;

}

footer a {
    color: #777;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    border: 1px solid #eee;
    padding: 4px;
    height: 32px;
    width: 32px;
    border-radius: 6px;
    transition: all .3s ease;
}

footer a:hover {
    background-color: #eee;
}
</style>