<script setup lang="ts">
import { onErrorCaptured, ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router/auto'

onErrorCaptured((err, instance, info) => {
  console.error('erreur : ', err, '\ninfo : ', info, '\ncomposant : ', instance)
  return true
})
const menuIsOpen = ref(false)
</script>

<template>
  <header>
    <nav>
    <button @poinerdown="menuIsOpen = !menuIsOpen"
      aria-controls="mainNav"
      aria-expanded="true"
      class="rounded-full border-2 border-red-600 bg-red-300 px-2"
    >
    Menu
    </button>

    <transition
      class="transition-all duration-1000"
      enter-from-class="translate-x-full"
      enter-to-class="translate-x-0"
      leave-active-class="translate-x-full"
    >
    <nav id="mainNav " v-show="menuIsOpen">
      <ul>
        <li><a href="#">item 1</a></li>
        <li><a href="#">item 2</a></li>
        <li><a href="#">item 3</a></li>
      </ul>
    </nav>
    </transition>
  </nav>
      <ul>
        <li>
          <RouterLink to="/" class="text-red-500 underline"> Accueil </RouterLink>
        </li>
      </ul>
    </nav>
  </header>
  <RouterView v-slot="{ Component }">
    <Suspense>
      <component :is="Component" />
    </Suspense>
  </RouterView>
</template>

function ref(arg0: boolean) {
  throw new Error('Function not implemented.')
}
