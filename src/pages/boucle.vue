<script setup lang="ts">
    import { onErrorCaptured } from 'vue'
    import { RouterLink, RouterView } from 'vue-router/auto'
    import { ref } from 'vue'
    const sectionsData = [
    {
        label: 'bouton 1',
        texte: `texte panneau 1 Lorem ipsum dolor sit ame
        consectetur adipisicing elit. Inventore animi dolore,
        rerum magni laudantium quod excepturi laboriosam, 
        ex modi debitis harum reprehenderit eaque quam ut
        ea molestiae. Id, cum dolor!`
    },
    {
        label: 'bouton 2',
        texte: `texte panneau 2 Lorem ipsum dolor sit amet consectetur
         adipisicing elit. Consectetur amet ab corrupti
        ! Laboriosam consectetur, iure voluptates nobis soluta expedita
        est modi dolorem, totam quidem fugiat ipsa excepturi
        voluptas tenetur numquam!`
    },
    {
        label: 'bouton 3',
        texte: `texte panneau 3 Lorem ipsum dolor sit amet consectetur adipisicing
         elit. Facilis, velit excepturi deserunt distinctio
        explicabo placeat harum animi laudantium quaerat, reiciendis officiis
        iure quod unde magni quisquam, possimus reprehenderit
        facere error!.`
    }
    ]
    const sectionOpen = ref(0)
</script>


<template>
    <section v-for="({ label, texte }, key) of sectionsData" :key="key">
        <pre class="font-mono">key : {{ key }}</pre>
        <pre  @pointerdown="sectionOpen=key+1" class="font-mono">label : {{ label }}</pre>
        <pre v-show="sectionOpen==key+1" class="font-mono">texte : {{ texte }}</pre>
    </section>
</template>