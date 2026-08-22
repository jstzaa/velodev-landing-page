<script setup>
// Props or reactive state can be added if needed for customization
</script>

<template>
  <header id="home" class="scroll-mt-24 mx-5 my-5 md:mx-10 md:my-5 rounded-4xl bg-primary text-light border border-secondary/20 shadow-2xl relative overflow-hidden">
    <!-- Subtle Background Glows inside the Card -->
    <div class="absolute -top-24 -left-24 w-96 h-96 bg-light/30 rounded-full blur-3xl pointer-events-none" />
    <div class="absolute -bottom-24 -right-24 w-96 h-96 bg-light/30 rounded-full blur-3xl pointer-events-none" />

    <div class="flex items-center px-6 sm:px-10 md:px-16 lg:px-20 py-10 md:py-30 relative z-10">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-12 lg:gap-8 items-center w-full max-w-7xl mx-auto">
        
        <!-- Left Content: Headline, Tagline, CTA -->
        <div class="lg:col-span-7 flex flex-col items-start gap-6 text-left">
          <!-- Headline -->
          <h1 class="text-4xl sm:text-5xl lg:text-6xl font-bold tracking-tight leading-[1.15] text-light">
            Scale-up Bisnis Anda <br> Bersama Velodev
          </h1>

          <!-- Tagline -->
          <p class="text-base sm:text-lg text-tertiary max-w-xl leading-relaxed">
            Velodev merancang landing page modern dengan kecepatan tinggi, arsitektur yang skalabel, dan pengalaman visual yang memukau.
          </p>

          <!-- CTA Buttons -->
          <div class="flex flex-wrap items-center gap-4 pt-2">
            <a
              href="#contact"
              class="inline-flex items-center justify-center gap-2.5 px-7 py-3.5 rounded-full bg-light hover:bg-cream text-primary font-bold shadow-lg shadow-black/20 transition-all duration-200 hover:scale-[1.02] active:scale-[0.98]"
            >
              <span>Mulai Proyek</span>
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
              </svg>
            </a>

            <a
              href="#services"
              class="inline-flex items-center justify-center px-6 py-3.5 rounded-full bg-secondary/25 hover:bg-secondary/40 text-light border border-tertiary/40 font-medium transition-all duration-200 hover:scale-[1.02] active:scale-[0.98]"
            >
              Lihat Layanan
            </a>
          </div>
        </div>

        <!-- Right Content: Photo with card styling & floating badge -->
        <div class="order-first lg:order-2 lg:col-span-5 flex justify-center items-center relative">
          <div class="relative w-full max-w-md lg:max-w-none">
            <!-- Decorative Border Gradient Glow -->
            <div class="absolute -inset-1 rounded-3xl bg-gradient-to-tr from-secondary/40 via-tertiary/25 to-secondary/30 blur-lg opacity-70" />

            <!-- Main Photo Container -->
            <div class="relative rounded-2xl overflow-hidden border border-secondary/40 bg-primary shadow-2xl aspect-[4/3] sm:aspect-[16/11]">
              <img
                src="https://images.unsplash.com/photo-1522071820081-009f0129c71c?auto=format&fit=crop&w=1200&q=80"
                alt="Velodev Development Team Collaboration"
                class="w-full h-full object-cover object-center transform hover:scale-105 transition-transform duration-700"
                loading="eager"
              />
              <div class="absolute inset-0 bg-gradient-to-t from-primary/80 via-transparent to-transparent pointer-events-none" />
            </div>

            <!-- Floating Feature Tag -->
            <div class="absolute -bottom-4 -left-4 sm:bottom-4 sm:-left-6 bg-tertiary/95 backdrop-blur-md border border-secondary/40 rounded-xl p-3.5 shadow-xl flex items-center gap-3">
              <div class="w-10 h-10 rounded-lg bg-secondary/30 flex items-center justify-center text-primary">
                <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" d="m3.75 13.5 10.5-11.25L12 10.5h8.25L9.75 21.75 12 13.5H3.75Z" />
                </svg>
              </div>
              <div>
                <p class="text-xs font-semibold text-primary">Modern Architecture</p>
                <p class="text-[11px] text-primary">Fast & Scalable Stack</p>
              </div>
            </div>

          </div>
        </div>

      </div>
    </div>
  </header>
</template>
