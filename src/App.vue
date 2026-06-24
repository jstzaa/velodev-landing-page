<script setup>

</script>

<template>
  <div class="fixed inset-x-5 md:inset-x-10 bottom-10 md:bottom-auto md:top-5 flex flex-row px-10 py-5 rounded-full justify-between items-center shadow-xl shadow-gray/20 z-20 backdrop-blur-md">
    <div>
      <h1 class="text-lg">Velodev</h1>
    </div>
    <ul class="hidden md:flex flex-row gap-5 text-base">
      <li><a href="">Home</a></li>
      <li><a href="">About</a></li>
      <li><a href="">Service</a></li>
      <li><a href="">Pricing</a></li>
      <li><a href="">Contact</a></li>
    </ul>
    <div class="md:hidden">
      <svg class="w-6 h-6" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24"><path stroke="currentColor" stroke-linecap="round" stroke-width="2" d="M5 7h14M5 12h14M5 17h14"/></svg>
    </div>
    <aside class="md:hidden absolute bottom-24 py-5 inset-x-5 rounded-2xl shadow-xl shadow-gray/20 z-10 backdrop-blur-md">
      <ul class="flex flex-col items-center justify-center gap-5 text-base">
        <li><a href="">Home</a></li>
        <li><a href="">About</a></li>
        <li><a href="">Service</a></li>
        <li><a href="">Pricing</a></li>
        <li><a href="">Contact</a></li>
      </ul>
    </aside>
  </div>
</template>