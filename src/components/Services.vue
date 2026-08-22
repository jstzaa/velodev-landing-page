<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const services = [
  {
    id: '01',
    category: 'UI/UX & Web Design',
    title: 'High-Converting Landing Page Design',
    tagline: 'Desain visual memukau yang dirancang khusus untuk melipatgandakan konversi dan memperkuat citra brand Anda.',
    description: 'Kami tidak sekadar membuat website yang bagus dipandang, tetapi menyusun arsitektur visual berbasis psikologi audiens untuk mengarahkan setiap pengunjung menjadi pelanggan setia.',
    features: [
      'Bespoke Figma Design System & Brand Alignment',
      'Wireframing, UX Journey & Interactive Prototype',
      'Mobile-First Responsive Layout di semua resolusi',
      'Audit UX & Conversion Rate Optimization (CRO)'
    ],
    accentGradient: 'from-secondary/20 via-tertiary/10 to-transparent',
    badgeColor: 'bg-secondary/20 text-tertiary border-secondary/30',
    bgClass: 'bg-[#37472b]',
    previewType: 'design'
  },
  {
    id: '02',
    category: 'Modern Web Development',
    title: 'Ultra-Fast & Scalable Frontend Architecture',
    tagline: 'Pengembangan website modern dengan kecepatan kilat, clean code, dan integrasi ekosistem tanpa batas.',
    description: 'Dibangun di atas fondasi teknologi mutakhir seperti Vue 3, Vite, dan Tailwind CSS untuk menjamin waktu loading instan, keamanan maksimal, serta kemudahan pengembangan fitur masa depan.',
    features: [
      'Vue 3 / Nuxt, React & Modern JavaScript Stack',
      'Arsitektur modular, scalable & maintainable code',
      'Integrasi Headless CMS, CRM, & REST/GraphQL API',
      'TypeScript-ready dengan zero redundant libraries'
    ],
    accentGradient: 'from-tertiary/20 via-secondary/10 to-transparent',
    badgeColor: 'bg-tertiary/20 text-light border-tertiary/30',
    bgClass: 'bg-[#2e3b23]',
    previewType: 'code'
  },
  {
    id: '03',
    category: 'Speed & Technical SEO',
    title: 'Google PageSpeed 95+ & Search Engine Dominance',
    tagline: 'Kecepatan loading di bawah 1 detik untuk pengalaman pengguna terbaik dan peringkat teratas di Google.',
    description: 'Kecepatan adalah kunci konversi. Kami mengoptimasi setiap byte aset gambar, script, dan struktur semantic HTML agar website Anda lulus semua metrik Google Core Web Vitals dengan nilai sempurna.',
    features: [
      'Skor 95–100 pada Google PageSpeed & Core Web Vitals',
      'Optimasi LCP, FID, CLS & Total Blocking Time',
      'Struktur Semantic HTML5, Schema Markup & Open Graph',
      'Smart Image Compression (WebP/AVIF) & Edge Caching'
    ],
    accentGradient: 'from-secondary/25 via-light/10 to-transparent',
    badgeColor: 'bg-secondary/20 text-secondary border-secondary/30',
    bgClass: 'bg-[#334227]',
    previewType: 'speed'
  },
  {
    id: '04',
    category: 'Motion & Micro-Interactions',
    title: 'Immersive Motion & Micro-Interactions',
    tagline: 'Pengalaman interaktif berkelas dunia dengan animasi dinamis dan transisi yang memikat perhatian.',
    description: 'Hadirkan nuansa premium melalui efek scroll-driven, parallax, dan mikro-interaksi halus yang responsif terhadap setiap sentuhan, tanpa mengorbankan fluiditas performa 60 FPS.',
    features: [
      'Scroll-driven stacked cards, parallax & smooth reveal',
      'Micro-interactions responsif pada button & cards',
      'Animasi 60 FPS buttery smooth berbasis CSS GPU & Canvas',
      'Dukungan Accessible Motion (prefers-reduced-motion)'
    ],
    accentGradient: 'from-tertiary/20 via-secondary/15 to-transparent',
    badgeColor: 'bg-tertiary/20 text-cream border-tertiary/30',
    bgClass: 'bg-[#29351e]',
    previewType: 'motion'
  },
  {
    id: '05',
    category: 'Maintenance & Growth',
    title: 'Continuous Maintenance & Conversion Analytics',
    tagline: 'Dukungan teknis berkelanjutan, monitoring 24/7, dan optimalisasi berkala untuk pertumbuhan bisnis Anda.',
    description: 'Kemitraan jangka panjang untuk memastikan landing page Anda selalu dalam performa puncak, aman dari ancaman siber, dan terus diperbarui berdasarkan data perilaku pengunjung nyata.',
    features: [
      '24/7 Uptime Monitoring & Proteksi Keamanan SSL',
      'Pembaruan berkala dependensi & backup otomatis harian',
      'Integrasi Heatmaps & Analisis Interaksi Pengunjung',
      'Dedicated Developer Support via WhatsApp / Slack'
    ],
    accentGradient: 'from-secondary/20 via-tertiary/10 to-transparent',
    badgeColor: 'bg-secondary/25 text-tertiary border-secondary/35',
    bgClass: 'bg-[#232d1a]',
    previewType: 'analytics'
  }
]

const activeIndex = ref(0)
const cardRefs = ref([])
const containerRef = ref(null)

const handleScroll = () => {
  if (!cardRefs.value.length) return
  
  const windowCenter = window.innerHeight * 0.45
  
  cardRefs.value.forEach((cardEl, index) => {
    if (!cardEl) return
    const rect = cardEl.getBoundingClientRect()
    if (rect.top <= windowCenter) {
      activeIndex.value = index
    }
  })
}

const scrollToCard = (index) => {
  const target = cardRefs.value[index]
  if (target) {
    const yOffset = -120
    const y = target.getBoundingClientRect().top + window.pageYOffset + yOffset
    window.scrollTo({ top: y, behavior: 'smooth' })
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <section id="services" class="relative py-16 md:py-28 px-5 md:px-10 scroll-mt-20">
    <!-- Anchor alias for #service -->
    <div id="service" class="absolute -top-24 left-0 pointer-events-none" />

    <!-- Ambient Background Lighting -->
    <div class="absolute top-1/4 left-1/2 -translate-x-1/2 w-3/4 max-w-4xl h-96 bg-secondary/15 rounded-full blur-3xl pointer-events-none" />
    <div class="absolute bottom-1/3 right-10 w-80 h-80 bg-tertiary/10 rounded-full blur-3xl pointer-events-none" />

    <div class="max-w-7xl mx-auto relative z-10">
      
      <!-- Section Header -->
      <div class="flex flex-col items-center text-center max-w-3xl mx-auto mb-14 md:mb-20">
        <!-- Tag Pill -->
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-secondary/20 border border-secondary/35 text-primary text-xs md:text-sm font-semibold tracking-wide uppercase mb-4 shadow-sm backdrop-blur-md">
          <span class="w-2 h-2 rounded-full bg-primary animate-pulse" />
          <span>Layanan Eksklusif</span>
        </div>

        <!-- Main Heading -->
        <h2 class="text-3xl sm:text-4xl md:text-5xl lg:text-6xl font-bold tracking-tight text-primary leading-[1.15] mb-5">
          Solusi Digital Komprehensif <br class="hidden sm:inline">
          <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary via-[#65824e] to-secondary">
            Untuk Skalabilitas Bisnis
          </span>
        </h2>

        <!-- Subtitle -->
        <p class="text-base sm:text-lg text-primary/80 leading-relaxed max-w-2xl">
          Setiap solusi dirancang presisi dengan standar industri tertinggi, menggabungkan estetika desain memikat dan performa komputasi modern.
        </p>

        <!-- Quick Navigation / Active Step Indicator Pills (Desktop & Tablet) -->
        <div class="hidden md:flex flex-wrap items-center justify-center gap-2.5 mt-8 p-1.5 rounded-full bg-primary/10 border border-secondary/30 backdrop-blur-md">
          <button
            v-for="(service, idx) in services"
            :key="service.id"
            type="button"
            class="px-4 py-2 rounded-full text-xs font-semibold transition-all duration-300 cursor-pointer flex items-center gap-1.5"
            :class="activeIndex === idx 
              ? 'bg-primary text-light shadow-md shadow-black/15 scale-105' 
              : 'text-primary/70 hover:text-primary hover:bg-white/50'"
            @click="scrollToCard(idx)"
          >
            <span class="text-[10px] opacity-75 font-mono">{{ service.id }}</span>
            <span>{{ service.category }}</span>
          </button>
        </div>
      </div>

      <!-- Stack Scroll Cards Container -->
      <div ref="containerRef" class="relative flex flex-col gap-8 md:gap-12 pb-12">
        <div
          v-for="(service, index) in services"
          :key="service.id"
          :ref="el => (cardRefs[index] = el)"
          class="stack-card-wrapper sticky transition-all duration-300"
          :style="{
            top: `calc(5.5rem + ${index * 1.25}rem)`,
            zIndex: index + 10,
            marginBottom: index === services.length - 1 ? '0' : '4.5rem'
          }"
        >
          <!-- Stack Card Container -->
          <div
            class="group relative rounded-3xl md:rounded-[2.5rem] p-6 sm:p-8 md:p-12 lg:p-14 scale-85 text-light border border-secondary/30 shadow-[0_25px_60px_-15px_rgba(0,0,0,0.35)] overflow-hidden transition-all duration-500 hover:border-secondary/60 backdrop-blur-xl"
            :class="service.bgClass"
          >
            <!-- Card Background Ambient Glows -->
            <div class="absolute -top-32 -right-32 w-80 h-80 bg-light/10 rounded-full blur-3xl pointer-events-none group-hover:bg-light/15 transition-all duration-500" />
            <div class="absolute -bottom-32 -left-32 w-80 h-80 bg-secondary/15 rounded-full blur-3xl pointer-events-none" />
            <div class="absolute inset-0 bg-gradient-to-br opacity-40 pointer-events-none" :class="service.accentGradient" />

            <!-- Card Content Grid -->
            <div class="relative z-10 grid grid-cols-1 lg:grid-cols-12 gap-8 lg:gap-12 items-center">
              
              <!-- Left Column: Info, Badges, Features, CTA -->
              <div class="lg:col-span-7 flex flex-col items-start text-left">
                
                <!-- Category & ID Header -->
                <div class="flex items-center gap-3 mb-4">
                  <span class="inline-flex items-center justify-center px-3.5 py-1 rounded-full text-xs font-mono font-bold tracking-wider border shadow-inner" :class="service.badgeColor">
                    {{ service.id }}
                  </span>
                  <span class="text-xs uppercase tracking-widest font-semibold text-tertiary">
                    {{ service.category }}
                  </span>
                </div>

                <!-- Card Title -->
                <h3 class="text-2xl sm:text-3xl md:text-4xl font-bold tracking-tight text-light mb-3 leading-snug">
                  {{ service.title }}
                </h3>

                <!-- Tagline -->
                <p class="text-sm sm:text-base text-cream/90 font-medium mb-4 leading-relaxed">
                  {{ service.tagline }}
                </p>

                <!-- Detailed Description -->
                <p class="text-xs sm:text-sm text-tertiary/90 leading-relaxed mb-6">
                  {{ service.description }}
                </p>

                <!-- Features / Deliverables List -->
                <div class="w-full grid grid-cols-1 sm:grid-cols-2 gap-2.5 sm:gap-3 mb-8">
                  <div
                    v-for="(feature, fIdx) in service.features"
                    :key="fIdx"
                    class="flex items-start gap-2.5 p-2.5 rounded-xl bg-black/15 border border-secondary/20 hover:border-secondary/40 transition-colors"
                  >
                    <div class="w-5 h-5 rounded-full bg-secondary/30 text-light flex items-center justify-center shrink-0 mt-0.5">
                      <svg class="w-3 h-3" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" d="m4.5 12.75 6 6 9-13.5" />
                      </svg>
                    </div>
                    <span class="text-xs text-light/90 leading-tight">{{ feature }}</span>
                  </div>
                </div>

                <!-- CTA Action Area -->
                <div class="flex flex-wrap items-center gap-4">
                  <a
                    href="#contact"
                    class="inline-flex items-center justify-center gap-2 px-6 py-3 rounded-full bg-light text-primary font-bold text-xs sm:text-sm shadow-lg shadow-black/25 hover:bg-cream hover:scale-[1.03] active:scale-[0.98] transition-all duration-200"
                  >
                    <span>Konsultasikan Kebutuhan</span>
                    <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
                    </svg>
                  </a>
                  
                  <span class="text-xs text-tertiary flex items-center gap-1.5">
                    <span class="w-1.5 h-1.5 rounded-full bg-secondary animate-ping" />
                    Slot Proyek Tersedia
                  </span>
                </div>

              </div>

              <!-- Right Column: Interactive Mockup Showcase -->
              <div class="lg:col-span-5 flex justify-center w-full">
                
                <!-- 01 DESIGN PREVIEW MOCKUP -->
                <div v-if="service.previewType === 'design'" class="w-full max-w-md rounded-2xl bg-[#1f2918]/80 border border-secondary/30 p-5 shadow-2xl backdrop-blur-md flex flex-col gap-4">
                  <div class="flex items-center justify-between border-b border-secondary/20 pb-3">
                    <div class="flex items-center gap-1.5">
                      <div class="w-2.5 h-2.5 rounded-full bg-red-400/80" />
                      <div class="w-2.5 h-2.5 rounded-full bg-yellow-400/80" />
                      <div class="w-2.5 h-2.5 rounded-full bg-green-400/80" />
                    </div>
                    <span class="text-[11px] font-mono text-tertiary">figma-canvas-v2.fig</span>
                    <span class="text-[10px] px-2 py-0.5 rounded bg-secondary/30 text-light font-semibold">100% Vector</span>
                  </div>

                  <!-- Mockup Content -->
                  <div class="space-y-3">
                    <div class="h-24 rounded-xl bg-gradient-to-br from-primary/60 to-secondary/30 p-3 border border-secondary/30 flex flex-col justify-between">
                      <div class="flex justify-between items-start">
                        <div class="h-3 w-20 bg-light/70 rounded-full" />
                        <span class="text-[10px] px-2 py-0.5 rounded-full bg-light text-primary font-bold shadow">+148% Conv.</span>
                      </div>
                      <div class="space-y-1.5">
                        <div class="h-2.5 w-3/4 bg-light/40 rounded-full" />
                        <div class="h-2 w-1/2 bg-light/30 rounded-full" />
                      </div>
                    </div>

                    <!-- Mini UI Components Grid -->
                    <div class="grid grid-cols-2 gap-2.5">
                      <div class="p-3 rounded-xl bg-black/30 border border-secondary/20 flex flex-col gap-1.5">
                        <span class="text-[10px] text-tertiary">User Flow Rating</span>
                        <div class="flex items-center gap-1 text-light text-xs font-bold">
                          <span>4.95 / 5.0</span>
                          <span class="text-secondary text-[10px]">★★★★★</span>
                        </div>
                      </div>
                      <div class="p-3 rounded-xl bg-black/30 border border-secondary/20 flex flex-col gap-1.5">
                        <span class="text-[10px] text-tertiary">Design Tokens</span>
                        <div class="text-xs font-mono text-cream font-bold">
                          240+ Auto Layout
                        </div>
                      </div>
                    </div>

                    <!-- Interactive status pills -->
                    <div class="flex items-center justify-between text-[11px] px-3 py-2 rounded-lg bg-secondary/15 border border-secondary/30 text-light">
                      <span class="flex items-center gap-1.5">
                        <span class="w-2 h-2 rounded-full bg-secondary" />
                        Figma Ready Hand-off
                      </span>
                      <span class="font-mono text-tertiary">Auto Grid 12-Col</span>
                    </div>
                  </div>
                </div>

                <!-- 02 CODE PREVIEW MOCKUP -->
                <div v-else-if="service.previewType === 'code'" class="w-full max-w-md rounded-2xl bg-[#192213] border border-secondary/30 p-5 shadow-2xl backdrop-blur-md flex flex-col gap-3 font-mono text-xs">
                  <div class="flex items-center justify-between border-b border-secondary/20 pb-3">
                    <div class="flex items-center gap-2">
                      <div class="w-2.5 h-2.5 rounded-full bg-secondary/60" />
                      <span class="text-tertiary text-[11px]">LandingPage.vue</span>
                    </div>
                    <span class="text-[10px] px-2 py-0.5 rounded bg-primary/80 border border-secondary/30 text-cream">Vite 8.1 ⚡</span>
                  </div>

                  <!-- Code lines -->
                  <div class="space-y-1.5 py-1 text-[11px] leading-relaxed select-none">
                    <div class="text-tertiary/60">// Ultra-fast reactive architecture</div>
                    <div>
                      <span class="text-secondary font-bold">const</span>
                      <span class="text-light"> config = </span>
                      <span class="text-tertiary">definePage</span>({
                    </div>
                    <div class="pl-4">
                      <span class="text-light">ssr: </span>
                      <span class="text-cream font-semibold">true</span>,
                    </div>
                    <div class="pl-4">
                      <span class="text-light">hydration: </span>
                      <span class="text-secondary">'progressive'</span>,
                    </div>
                    <div class="pl-4">
                      <span class="text-light">cachePolicy: </span>
                      <span class="text-tertiary">'edge-cached-max'</span>
                    </div>
                    <div>})</div>
                  </div>

                  <!-- Terminal status bar -->
                  <div class="mt-2 p-2.5 rounded-lg bg-black/40 border border-secondary/20 flex items-center justify-between text-[10px]">
                    <span class="text-secondary flex items-center gap-1.5">
                      <span class="inline-block w-1.5 h-1.5 rounded-full bg-secondary animate-pulse" />
                      Build time: 0.28s
                    </span>
                    <span class="text-tertiary font-mono">0 errors • 0 warnings</span>
                  </div>
                </div>

                <!-- 03 SPEED & SEO PREVIEW MOCKUP -->
                <div v-else-if="service.previewType === 'speed'" class="w-full max-w-md rounded-2xl bg-[#1d2617]/90 border border-secondary/30 p-5 shadow-2xl backdrop-blur-md flex flex-col gap-4">
                  <div class="flex items-center justify-between border-b border-secondary/20 pb-3">
                    <div class="flex items-center gap-2">
                      <span class="text-secondary text-sm">⚡</span>
                      <span class="text-light font-bold text-xs">Google Lighthouse Report</span>
                    </div>
                    <span class="text-[10px] px-2 py-0.5 rounded bg-secondary/30 text-light font-bold">PASSED</span>
                  </div>

                  <!-- 4 Circular Score Gauges -->
                  <div class="grid grid-cols-4 gap-2 text-center py-2">
                    <div class="flex flex-col items-center gap-1">
                      <div class="w-12 h-12 rounded-full border-2 border-secondary bg-secondary/20 flex items-center justify-center text-light font-bold text-sm shadow-inner shadow-secondary/40">
                        100
                      </div>
                      <span class="text-[10px] text-tertiary font-medium">Performance</span>
                    </div>
                    <div class="flex flex-col items-center gap-1">
                      <div class="w-12 h-12 rounded-full border-2 border-secondary bg-secondary/20 flex items-center justify-center text-light font-bold text-sm shadow-inner shadow-secondary/40">
                        100
                      </div>
                      <span class="text-[10px] text-tertiary font-medium">Accessibility</span>
                    </div>
                    <div class="flex flex-col items-center gap-1">
                      <div class="w-12 h-12 rounded-full border-2 border-secondary bg-secondary/20 flex items-center justify-center text-light font-bold text-sm shadow-inner shadow-secondary/40">
                        100
                      </div>
                      <span class="text-[10px] text-tertiary font-medium">Best Practice</span>
                    </div>
                    <div class="flex flex-col items-center gap-1">
                      <div class="w-12 h-12 rounded-full border-2 border-secondary bg-secondary/20 flex items-center justify-center text-light font-bold text-sm shadow-inner shadow-secondary/40">
                        100
                      </div>
                      <span class="text-[10px] text-tertiary font-medium">SEO Ready</span>
                    </div>
                  </div>

                  <!-- Metrics bar -->
                  <div class="space-y-2 text-xs">
                    <div class="flex justify-between items-center p-2 rounded-lg bg-black/30 border border-secondary/20">
                      <span class="text-tertiary text-[11px]">Largest Contentful Paint (LCP)</span>
                      <span class="text-secondary font-mono font-bold">0.6s (Fast)</span>
                    </div>
                    <div class="flex justify-between items-center p-2 rounded-lg bg-black/30 border border-secondary/20">
                      <span class="text-tertiary text-[11px]">Cumulative Layout Shift (CLS)</span>
                      <span class="text-secondary font-mono font-bold">0.00 (Zero Shift)</span>
                    </div>
                  </div>
                </div>

                <!-- 04 MOTION PREVIEW MOCKUP -->
                <div v-else-if="service.previewType === 'motion'" class="w-full max-w-md rounded-2xl bg-[#1a2314] border border-secondary/30 p-5 shadow-2xl backdrop-blur-md flex flex-col gap-4">
                  <div class="flex items-center justify-between border-b border-secondary/20 pb-3">
                    <div class="flex items-center gap-2">
                      <span class="text-tertiary text-sm">✦</span>
                      <span class="text-light font-bold text-xs">Motion Engine 60FPS</span>
                    </div>
                    <span class="text-[10px] px-2 py-0.5 rounded bg-secondary/25 text-cream font-mono">GPU Accelerated</span>
                  </div>

                  <!-- Motion Timeline Visualizer -->
                  <div class="p-3.5 rounded-xl bg-black/30 border border-secondary/20 space-y-3">
                    <div class="flex justify-between text-[11px] text-tertiary">
                      <span>Timeline: Scroll Trigger</span>
                      <span class="font-mono text-secondary">0ms → 450ms</span>
                    </div>
                    
                    <!-- Progress Bar Wave -->
                    <div class="h-3 w-full bg-primary/40 rounded-full overflow-hidden relative">
                      <div class="h-full bg-gradient-to-r from-secondary via-light to-tertiary w-3/4 rounded-full animate-pulse" />
                    </div>

                    <div class="grid grid-cols-3 gap-2 pt-1 text-center">
                      <div class="p-1.5 rounded bg-primary/30 border border-secondary/20 text-[10px] text-cream">
                        Ease: Spring
                      </div>
                      <div class="p-1.5 rounded bg-primary/30 border border-secondary/20 text-[10px] text-cream">
                        Damping: 20
                      </div>
                      <div class="p-1.5 rounded bg-primary/30 border border-secondary/20 text-[10px] text-cream">
                        FPS: 60 Lock
                      </div>
                    </div>
                  </div>

                  <!-- Interactive preview box -->
                  <div class="p-3 rounded-xl bg-gradient-to-r from-secondary/20 to-tertiary/20 border border-secondary/30 flex items-center justify-between">
                    <div class="flex items-center gap-2.5">
                      <div class="w-8 h-8 rounded-lg bg-light text-primary flex items-center justify-center font-bold text-xs shadow">
                        ✨
                      </div>
                      <div class="text-left">
                        <p class="text-xs font-bold text-light">Micro-Interactions</p>
                        <p class="text-[10px] text-tertiary">Adaptive haptic feedback feel</p>
                      </div>
                    </div>
                    <span class="text-[10px] font-bold px-2 py-1 rounded-full bg-secondary/40 text-light">Active</span>
                  </div>
                </div>

                <!-- 05 ANALYTICS & SUPPORT MOCKUP -->
                <div v-else-if="service.previewType === 'analytics'" class="w-full max-w-md rounded-2xl bg-[#172012] border border-secondary/30 p-5 shadow-2xl backdrop-blur-md flex flex-col gap-4">
                  <div class="flex items-center justify-between border-b border-secondary/20 pb-3">
                    <div class="flex items-center gap-2">
                      <span class="w-2.5 h-2.5 rounded-full bg-secondary animate-ping" />
                      <span class="text-light font-bold text-xs">Live System Health</span>
                    </div>
                    <span class="text-[10px] px-2 py-0.5 rounded bg-secondary/30 text-light font-bold">ALL SYSTEMS OK</span>
                  </div>

                  <!-- Analytics Stats Grid -->
                  <div class="grid grid-cols-2 gap-2.5">
                    <div class="p-3 rounded-xl bg-black/30 border border-secondary/20 flex flex-col gap-1">
                      <span class="text-[10px] text-tertiary">Server Uptime</span>
                      <span class="text-base font-bold text-secondary font-mono">99.99%</span>
                      <span class="text-[9px] text-light/70">365 Days Guaranteed</span>
                    </div>
                    <div class="p-3 rounded-xl bg-black/30 border border-secondary/20 flex flex-col gap-1">
                      <span class="text-[10px] text-tertiary">Avg Response Time</span>
                      <span class="text-base font-bold text-light font-mono">18ms</span>
                      <span class="text-[9px] text-secondary">Global Edge CDN</span>
                    </div>
                  </div>

                  <!-- Support SLA Box -->
                  <div class="p-3 rounded-xl bg-primary/40 border border-secondary/30 flex items-center justify-between">
                    <div class="flex items-center gap-2.5">
                      <div class="w-8 h-8 rounded-full bg-secondary/30 flex items-center justify-center text-light">
                        <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                          <path stroke-linecap="round" stroke-linejoin="round" d="M9 12.75 11.25 15 15 9.75M21 12c0 1.268-.63 2.39-1.593 3.068a3.745 3.745 0 0 1-1.043 3.296 3.745 3.745 0 0 1-3.296 1.043A3.745 3.745 0 0 1 12 21c-1.268 0-2.39-.63-3.068-1.593a3.746 3.746 0 0 1-3.296-1.043 3.745 3.745 0 0 1-1.043-3.296A3.745 3.745 0 0 1 3 12c0-1.268.63-2.39 1.593-3.068a3.745 3.745 0 0 1 1.043-3.296 3.746 3.746 0 0 1 3.296-1.043A3.746 3.746 0 0 1 12 3c1.268 0 2.39.63 3.068 1.593a3.746 3.746 0 0 1 3.296 1.043 3.746 3.746 0 0 1 1.043 3.296A3.745 3.745 0 0 1 21 12Z" />
                        </svg>
                      </div>
                      <div class="text-left">
                        <p class="text-xs font-bold text-light">Dedicated Support</p>
                        <p class="text-[10px] text-tertiary">Fast SLA response &lt; 15 mins</p>
                      </div>
                    </div>
                    <span class="text-xs font-mono text-secondary font-bold">24/7 Live</span>
                  </div>
                </div>

              </div>

            </div>
          </div>
        </div>
      </div>

      <!-- Bottom Callout after all stacked cards -->
      <div class="mt-12 p-8 md:p-10 rounded-3xl bg-secondary/15 border border-secondary/30 text-center max-w-4xl mx-auto backdrop-blur-md shadow-xl flex flex-col sm:flex-row items-center justify-between gap-6">
        <div class="text-left">
          <h4 class="text-xl md:text-2xl font-bold text-primary mb-1">
            Punya kebutuhan spesifik untuk bisnis Anda?
          </h4>
          <p class="text-sm text-primary/80">
            Kami siap membuat paket kustom yang disesuaikan dengan skala dan target konversi Anda.
          </p>
        </div>
        <a
          href="#contact"
          class="shrink-0 inline-flex items-center justify-center gap-2 px-6 py-3.5 rounded-full bg-primary hover:bg-primary/90 text-light font-bold text-sm shadow-lg shadow-black/20 hover:scale-[1.03] active:scale-[0.98] transition-all"
        >
          <span>Diskusi Sekarang</span>
          <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
          </svg>
        </a>
      </div>

    </div>
  </section>
</template>

<style scoped>
/* Stack scroll card dynamics */
.stack-card-wrapper {
  will-change: transform, top;
}
</style>
