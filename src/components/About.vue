<script setup>
import { ref } from 'vue'

const activeWorkflowStep = ref(0)

const stats = [
  {
    value: '50+',
    label: 'Proyek Selesai',
    description: 'Landing page & web app modern untuk berbagai industri'
  },
  {
    value: '99.8%',
    label: 'Kepuasan Klien',
    description: 'Kemitraan jangka panjang dengan standar delivery tinggi'
  },
  {
    value: '< 0.8s',
    label: 'Kecepatan Loading',
    description: 'Rata-rata LCP super cepat di semua perangkat'
  },
  {
    value: '3.5x',
    label: 'Peningkatan Konversi',
    description: 'Rata-rata lonjakan lead setelah redesign website'
  }
]

const values = [
  {
    icon: '⚡',
    title: 'Performance First',
    description: 'Setiap milidetik berharga. Kami mengoptimasi aset, bundle, dan arsitektur kode agar website memuat seketika tanpa kompromi.',
    badge: 'Core Web Vitals 95+'
  },
  {
    icon: '🎯',
    title: 'Conversion-Driven UX',
    description: 'Bukan sekadar visual cantik. Setiap elemen antarmuka dirancang strategis berdasarkan psikologi pengguna untuk menghasilkan aksi nyata.',
    badge: 'CRO Optimized'
  },
  {
    icon: '🧩',
    title: 'Modern & Clean Stack',
    description: 'Kami menggunakan teknologi terdepan seperti Vue 3, Vite, dan Tailwind CSS untuk menjamin kode modular, aman, dan mudah diekspansi.',
    badge: 'Future-Proof Code'
  },
  {
    icon: '🤝',
    title: 'Transparan & Kolaboratif',
    description: 'Komunikasi langsung tanpa birokrasi berbelit. Anda mendapatkan update berkala dan visibilitas penuh sepanjang proses pengembangan.',
    badge: 'On-Time Guarantee'
  }
]

const workflowSteps = [
  {
    number: '01',
    title: 'Discovery & Strategi',
    desc: 'Memahami tujuan bisnis, target audiens, dan positioning brand Anda untuk menyusun blueprint konversi yang tepat sasaran.',
    tag: 'Riset & Wireframe'
  },
  {
    number: '02',
    title: 'UI/UX & Prototyping',
    desc: 'Merancang desain antarmuka modern di Figma dengan visual identity yang kuat, responsive layout, dan interaksi yang intuitif.',
    tag: 'Design System'
  },
  {
    number: '03',
    title: 'Clean Code Development',
    desc: 'Mengubah desain menjadi kode berkualitas tinggi dengan performa kilat, animasi halus 60 FPS, dan integrasi API yang mulus.',
    tag: 'Vue 3 & Tailwind'
  },
  {
    number: '04',
    title: 'Testing, Launch & Growth',
    desc: 'Audit ketat Google Lighthouse, SEO teknis, deployment ke edge CDN global, dan monitoring performa pasca peluncuran.',
    tag: '99.9% Uptime'
  }
]
</script>

<template>
  <section id="about" class="relative py-16 md:py-28 px-5 md:px-10 scroll-mt-20 overflow-hidden">
    <!-- Ambient Background Glows -->
    <div class="absolute top-10 left-10 w-96 h-96 bg-secondary/15 rounded-full blur-3xl pointer-events-none" />
    <div class="absolute bottom-10 right-10 w-96 h-96 bg-tertiary/20 rounded-full blur-3xl pointer-events-none" />

    <div class="max-w-7xl mx-auto relative z-10">
      
      <!-- Top Section: Header & Narrative Grid -->
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-10 lg:gap-14 items-center mb-16 md:mb-24">
        
        <!-- Left: Tag, Main Headline -->
        <div class="lg:col-span-6 flex flex-col items-start text-left">
          <!-- Tag Pill -->
          <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-secondary/20 border border-secondary/35 text-primary text-xs md:text-sm font-semibold tracking-wide uppercase mb-4 shadow-sm backdrop-blur-md">
            <span class="w-2 h-2 rounded-full bg-primary animate-pulse" />
            <span>Tentang Velodev</span>
          </div>

          <h2 class="text-3xl sm:text-4xl md:text-5xl font-bold tracking-tight text-primary leading-[1.15] mb-6">
            Membangun Landing Page Modern yang <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary via-[#65824e] to-secondary">Mengakselerasi Pertumbuhan</span> Bisnis Anda
          </h2>

          <p class="text-base sm:text-lg text-primary/80 leading-relaxed mb-6">
            Velodev adalah studio pengembangan web yang berfokus pada penciptaan pengalaman digital bernilai tinggi. Kami menjembatani kesenjangan antara desain visual kelas atas dan performa rekayasa perangkat lunak modern.
          </p>

          <div class="flex flex-wrap items-center gap-4">
            <a
              href="#services"
              class="inline-flex items-center gap-2 px-6 py-3 rounded-full bg-primary hover:bg-primary/90 text-light text-sm font-bold shadow-lg shadow-black/15 hover:scale-[1.02] active:scale-[0.98] transition-all"
            >
              <span>Eksplor Layanan Kami</span>
              <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M13.5 4.5 21 12m0 0-7.5 7.5M21 12H3" />
              </svg>
            </a>

            <div class="flex items-center gap-2 text-xs font-semibold text-primary/80 bg-white/60 backdrop-blur-md px-4 py-3 rounded-full border border-secondary/30">
              <span class="w-2 h-2 rounded-full bg-secondary animate-ping" />
              <span>Berbasis di Indonesia • Skala Global</span>
            </div>
          </div>
        </div>

        <!-- Right: Interactive Philosophy / Mission Showcase Box -->
        <div class="lg:col-span-6 relative">
          <div class="relative rounded-3xl md:rounded-[2.5rem] bg-primary text-light p-8 sm:p-10 md:p-12 border border-secondary/30 shadow-2xl overflow-hidden">
            <!-- Background Glows inside box -->
            <div class="absolute -top-20 -right-20 w-72 h-72 bg-light/15 rounded-full blur-3xl pointer-events-none" />
            <div class="absolute -bottom-20 -left-20 w-72 h-72 bg-secondary/20 rounded-full blur-3xl pointer-events-none" />

            <div class="relative z-10 flex flex-col gap-6 text-left">
              <div class="flex items-center justify-between border-b border-secondary/25 pb-4">
                <span class="text-xs font-mono text-tertiary uppercase tracking-widest font-semibold">Filosofi Velodev</span>
                <span class="px-3 py-1 rounded-full bg-secondary/25 text-cream text-[11px] font-bold border border-secondary/30">
                  Est. 2024
                </span>
              </div>

              <blockquote class="text-lg sm:text-xl md:text-2xl font-medium leading-snug text-cream italic">
                &ldquo;Website bukan sekadar brosur online; ini adalah etalase utama dan mesin konversi terpenting bagi bisnis modern.&rdquo;
              </blockquote>

              <div class="space-y-3 pt-2">
                <div class="flex items-center gap-3 text-xs sm:text-sm text-tertiary">
                  <div class="w-5 h-5 rounded-full bg-secondary/30 text-light flex items-center justify-center shrink-0">
                    ✓
                  </div>
                  <span>Zero unnecessary bloatware, murni kode yang efisien & teroptimasi</span>
                </div>
                <div class="flex items-center gap-3 text-xs sm:text-sm text-tertiary">
                  <div class="w-5 h-5 rounded-full bg-secondary/30 text-light flex items-center justify-center shrink-0">
                    ✓
                  </div>
                  <span>Fokus pada Return on Investment (ROI) & pengalaman pengunjung</span>
                </div>
                <div class="flex items-center gap-3 text-xs sm:text-sm text-tertiary">
                  <div class="w-5 h-5 rounded-full bg-secondary/30 text-light flex items-center justify-center shrink-0">
                    ✓
                  </div>
                  <span>Arsitektur modular yang siap bertumbuh bersama bisnis Anda</span>
                </div>
              </div>

              <!-- Founder / Signature pill -->
              <div class="mt-4 pt-4 border-t border-secondary/20 flex items-center justify-between">
                <div>
                  <p class="text-sm font-bold text-light">Velodev Engineering Team</p>
                  <p class="text-xs text-tertiary">Crafting High-Performance Web</p>
                </div>
                <div class="text-xl">✨</div>
              </div>
            </div>
          </div>
        </div>

      </div>

      <!-- Stats Numbers Bar -->
      <div class="grid grid-cols-2 lg:grid-cols-4 gap-4 md:gap-6 mb-16 md:mb-24">
        <div
          v-for="(stat, idx) in stats"
          :key="idx"
          class="p-6 sm:p-8 rounded-2xl md:rounded-3xl bg-white/70 backdrop-blur-md border border-secondary/30 shadow-lg shadow-black/5 hover:border-secondary/60 hover:shadow-xl hover:-translate-y-1 transition-all duration-300 flex flex-col text-left justify-between"
        >
          <div class="text-3xl sm:text-4xl md:text-5xl font-bold font-mono text-primary mb-2 tracking-tight">
            {{ stat.value }}
          </div>
          <div>
            <h3 class="text-sm sm:text-base font-bold text-primary mb-1">
              {{ stat.label }}
            </h3>
            <p class="text-xs text-primary/70 leading-relaxed">
              {{ stat.description }}
            </p>
          </div>
        </div>
      </div>

      <!-- Bento Grid: 4 Core Values -->
      <div class="mb-16 md:mb-24">
        <div class="text-center max-w-2xl mx-auto mb-12">
          <h3 class="text-2xl sm:text-3xl md:text-4xl font-bold text-primary mb-3">
            Mengapa Memilih Velodev?
          </h3>
          <p class="text-sm sm:text-base text-primary/80">
            Kombinasi standar rekayasa modern dan dedikasi penuh pada kesuksesan digital brand Anda.
          </p>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6">
          <div
            v-for="(val, vIdx) in values"
            :key="vIdx"
            class="group p-6 sm:p-8 rounded-3xl bg-[#37472b] text-light border border-secondary/30 shadow-xl relative overflow-hidden flex flex-col justify-between hover:border-secondary/60 hover:-translate-y-1 transition-all duration-300"
          >
            <!-- Card subtle hover glow -->
            <div class="absolute -top-16 -right-16 w-36 h-36 bg-light/10 rounded-full blur-2xl pointer-events-none group-hover:bg-light/20 transition-all" />

            <div class="relative z-10 text-left">
              <div class="w-12 h-12 rounded-2xl bg-secondary/25 border border-secondary/40 flex items-center justify-center text-2xl mb-6 shadow-inner">
                {{ val.icon }}
              </div>
              <span class="inline-block px-2.5 py-0.5 rounded-md bg-black/25 border border-secondary/20 text-[10px] font-mono text-tertiary mb-3">
                {{ val.badge }}
              </span>
              <h4 class="text-lg sm:text-xl font-bold text-light mb-2.5">
                {{ val.title }}
              </h4>
              <p class="text-xs sm:text-sm text-tertiary/90 leading-relaxed">
                {{ val.description }}
              </p>
            </div>
          </div>
        </div>
      </div>

      <!-- How We Work / Interactive 4-Step Process -->
      <div class="rounded-3xl md:rounded-[2.5rem] bg-secondary/15 border border-secondary/35 p-8 sm:p-12 md:p-14 backdrop-blur-md shadow-xl">
        <div class="flex flex-col md:flex-row md:items-end justify-between mb-10 text-left gap-4">
          <div>
            <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-secondary/25 text-primary text-xs font-semibold uppercase tracking-wider mb-2">
              <span>Alur Kerja</span>
            </div>
            <h3 class="text-2xl sm:text-3xl md:text-4xl font-bold text-primary">
              Proses Transparan, Hasil Maksimal
            </h3>
          </div>
          <p class="text-xs sm:text-sm text-primary/80 max-w-md">
            Dari ide awal hingga peluncuran langsung, alur kerja kami terstruktur dan terukur di setiap tahapannya.
          </p>
        </div>

        <!-- Workflow Steps Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
          <div
            v-for="(step, sIdx) in workflowSteps"
            :key="sIdx"
            class="p-6 rounded-2xl bg-white/80 border border-secondary/30 flex flex-col justify-between text-left shadow-sm hover:shadow-md transition-all duration-200"
          >
            <div>
              <div class="flex items-center justify-between mb-4">
                <span class="text-2xl font-bold font-mono text-primary/40">
                  {{ step.number }}
                </span>
                <span class="px-2.5 py-1 rounded-full bg-primary/10 text-primary text-[11px] font-medium border border-primary/20">
                  {{ step.tag }}
                </span>
              </div>
              <h4 class="text-base font-bold text-primary mb-2">
                {{ step.title }}
              </h4>
              <p class="text-xs text-primary/75 leading-relaxed">
                {{ step.desc }}
              </p>
            </div>
          </div>
        </div>
      </div>

    </div>
  </section>
</template>
