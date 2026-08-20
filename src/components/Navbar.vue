<script setup>
import { ref } from 'vue'

const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
  <nav class="fixed inset-x-5 md:inset-x-10 bottom-10 md:bottom-auto md:top-5 flex flex-row px-8 md:px-10 py-4 md:py-5 rounded-full justify-between items-center shadow-xl shadow-black/25 z-40 backdrop-blur-md bg-primary/90 border border-secondary/40 text-light">
    <div>
      <h1 class="text-lg font-bold tracking-tight text-cream">Velodev</h1>
    </div>
    <ul class="hidden md:flex flex-row gap-6 text-sm font-medium text-tertiary">
      <li><a href="" class="hover:text-cream transition-colors">Home</a></li>
      <li><a href="" class="hover:text-cream transition-colors">About</a></li>
      <li><a href="" class="hover:text-cream transition-colors">Service</a></li>
      <li><a href="" class="hover:text-cream transition-colors">Pricing</a></li>
      <li><a href="" class="hover:text-cream transition-colors">Contact</a></li>
    </ul>
    <button
      type="button"
      class="md:hidden cursor-pointer focus:outline-none transition-transform duration-200 active:scale-95 text-tertiary hover:text-cream"
      aria-label="Toggle navigation menu"
      @click="toggleMenu"
    >
      <svg
        v-if="!isMenuOpen"
        class="w-6 h-6"
        aria-hidden="true"
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        fill="none"
        viewBox="0 0 24 24"
      >
        <path stroke="currentColor" stroke-linecap="round" stroke-width="2" d="M5 7h14M5 12h14M5 17h14"/>
      </svg>
      <svg
        v-else
        class="w-6 h-6"
        aria-hidden="true"
        xmlns="http://www.w3.org/2000/svg"
        width="24"
        height="24"
        fill="none"
        viewBox="0 0 24 24"
      >
        <path stroke="currentColor" stroke-linecap="round" stroke-width="2" d="M6 18 18 6M6 6l12 12"/>
      </svg>
    </button>

    <Transition
      enter-active-class="transition-all duration-300 ease-out"
      enter-from-class="opacity-0 translate-y-6 scale-95"
      enter-to-class="opacity-100 translate-y-0 scale-100"
      leave-active-class="transition-all duration-200 ease-in"
      leave-from-class="opacity-100 translate-y-0 scale-100"
      leave-to-class="opacity-0 translate-y-6 scale-95"
    >
      <aside
        v-if="isMenuOpen"
        class="md:hidden absolute bottom-24 py-6 inset-x-0 rounded-2xl shadow-2xl shadow-black/40 z-10 backdrop-blur-md bg-primary/95 border border-secondary/40"
      >
        <ul class="flex flex-col items-center justify-center gap-5 text-base text-tertiary">
          <li><a href="" class="hover:text-cream transition-colors">Home</a></li>
          <li><a href="" class="hover:text-cream transition-colors">About</a></li>
          <li><a href="" class="hover:text-cream transition-colors">Service</a></li>
          <li><a href="" class="hover:text-cream transition-colors">Pricing</a></li>
          <li><a href="" class="hover:text-cream transition-colors">Contact</a></li>
        </ul>
      </aside>
    </Transition>
  </nav>
</template>
