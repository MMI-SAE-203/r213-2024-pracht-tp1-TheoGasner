<script setup lang="ts">
import {ref} from 'vue'
const sectionOpen = ref(1)
</script>

<template>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen=1">bouton 1</button>
        <p v-show="sectionOpen==1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Officia mollitia cupiditate,
            deserunt recusandae quae nisi, architecto est aspernatur odio molestiae exercitationem sit dignissimos, 
            adipisci eligendi esse sunt id rem. Eveniet!</p>
    </section>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen=2">bouton 2</button>
        <p v-show="sectionOpen==2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur amet ab corrupti
            ! Laboriosam consectetur, iure voluptates nobis soluta expedita est modi dolorem, totam quidem fugiat ipsa excepturi
            voluptas tenetur numquam!</p>
    </section>
    <section>
        <button class="text-xl" @pointerdown="sectionOpen=3">bouton 3</button>
        <p v-show="sectionOpen==3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Facilis, velit excepturi deserunt distinctio
            explicabo placeat harum animi laudantium quaerat, reiciendis officiis iure quod unde magni quisquam, possimus reprehenderit
            facere error!</p>
    </section>
</template>