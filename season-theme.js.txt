/* Shona Store - JS tema musiman & gaya tampilan (dipindah dari template XML) */
/* [PATCH V1.1.11] TEMA MUSIMAN & GAYA TAMPILAN (15 tema)
     Otomatis menurut tanggal (Hijriah, Imlek, Natal, Kemerdekaan, Hari Ibu & Hari Ayah sedunia). Tema "darkneon" (Midnight Glass) hanya manual.
     Paksa satu tema: isi SS_SEASON_FORCE dengan 'default' | 'ramadan' | 'nuzululquran' | 'idulfitri' | 'iduladha'
     | 'muharram' | 'maulid' | 'isra' | 'harbolnas' | 'hariibu' | 'hariayah' | 'imlek' | 'natal' | 'kemerdekaan' | 'darkneon' (kosongkan '' agar otomatis).
     Uji cepat tanpa edit: tambahkan ?tema=ramadan di alamat blog. */
  (function () {
    var SS_SEASON_FORCE = '';

var SEA_ICO = {
      bag: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M6 2L3 6v14a2 2 0 002 2h14a2 2 0 002-2V6l-3-4z"/><path d="M3 6h18"/><path d="M16 10a4 4 0 01-8 0"/></svg>',
      lantern: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M9 3h6M12 3v2"/><path d="M8 7h8l1 3v5l-1 3H8l-1-3v-5z"/><path d="M12 7v11M9.5 21h5"/></svg>',
      book: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M2 4h7a3 3 0 013 3v13a2 2 0 00-2-2H2z"/><path d="M22 4h-7a3 3 0 00-3 3v13a2 2 0 012-2h8z"/></svg>',
      mosque: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M3 21h18"/><path d="M5 21v-7h14v7"/><path d="M7.5 14a4.5 4.5 0 019 0"/><path d="M12 6v3.5M11 6.5h2"/></svg>',
      kaaba: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M12 3l8 4v10l-8 4-8-4V7z"/><path d="M4 7l8 4 8-4M12 11v10"/></svg>',
      moon: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M21 12.8A9 9 0 1111.2 3a7 7 0 009.8 9.8z"/></svg>',
      envelope: '<svg class="ss-i" viewBox="0 0 24 24"><rect x="5" y="3" width="14" height="18" rx="2"/><path d="M5 9h14"/><circle cx="12" cy="9" r="2.5"/></svg>',
      tree: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M12 3l5 7h-3l4 6H6l4-6H7z"/><path d="M12 16v5"/></svg>',
      flag: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M5 22V3"/><path d="M5 4h14l-3 4 3 4H5"/></svg>',
      sparkle: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M12 3l1.8 5.2L19 10l-5.2 1.8L12 17l-1.8-5.2L5 10l5.2-1.8z"/></svg>',
      zap: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M13 2L4 14h7l-1 8 9-12h-7z"/></svg>',
      heart: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M20.8 4.6a5.5 5.5 0 00-7.8 0L12 5.7l-1-1.1a5.5 5.5 0 00-7.8 7.8l1 1.1L12 21l7.8-7.5 1-1.1a5.5 5.5 0 000-7.8z"/></svg>',
      tie: '<svg class="ss-i" viewBox="0 0 24 24"><path d="M9 3h6l-1.2 4h-3.6z"/><path d="M10.2 7L8.5 18l3.5 3 3.5-3L13.8 7"/></svg>'
    };

var SEASON_THEMES = {
      default: {
        shortName: 'Default',
        icon: SEA_ICO.bag,
        label: 'Default Shona',
        pillText: '',
        greetingShow: false,
        greetingIcon: '',
        greetingText: '',
        greetingSub: '',
        colors: {
          '--desktop-bg-start': '#e2e8f0',
          '--desktop-bg-end': '#cbd5e1',
          '--app-bg-start': '#f4f7fb',
          '--app-bg-end': '#e8eff8',
          '--pattern-color': 'rgba(11, 99, 246, 0.055)',
          '--header-bg-start': '#0b63f6',
          '--header-bg-end': '#1d8cf8',
          '--accent-primary': '#0b63f6',
          '--accent-dark': '#0747b5',
          '--accent-soft': '#eff6ff',
          '--accent-glow': 'rgba(11, 99, 246, 0.18)',
          '--nav-surface': 'rgba(255, 255, 255, 0.96)',
          '--nav-border': 'rgba(226, 232, 240, 0.9)',
          '--nav-text-muted': '#475569',
          '--nav-pill-bg': '#eff6ff',
          '--card-surface': '#ffffff',
          '--card-border': '#f1f5f9',
          '--text-primary': '#1e293b',
          '--text-secondary': '#64748b',
          '--hero-bg-start': '#0a58ca',
          '--hero-bg-end': '#19877b',
        },
        artworkSVG: '',
        bodyWatermarkSVG: '',
        topNavOrnamentSVG: '',
        footerNavOrnamentSVG: '',
      },

      ramadan: {
        shortName: 'Ramadan',
        icon: SEA_ICO.lantern,
        label: 'Ramadan Kareem',
        pillText: 'Ramadan {Y}H',
        greetingShow: true,
        greetingIcon: SEA_ICO.lantern,
        greetingText: 'Marhaban Ya Ramadan • Berkah Belanja',
        greetingSub: 'Diskon Sahur',
        colors: {
          '--desktop-bg-start': '#c7d2fe',
          '--desktop-bg-end': '#a5b4fc',
          '--app-bg-start': '#eef2ff',
          '--app-bg-end': '#e0e7ff',
          '--pattern-color': 'rgba(67, 56, 202, 0.065)',
          '--header-bg-start': '#1e1b4b',
          '--header-bg-end': '#3730a3',
          '--accent-primary': '#4338ca',
          '--accent-dark': '#312e81',
          '--accent-soft': '#e0e7ff',
          '--accent-glow': 'rgba(67, 56, 202, 0.22)',
          '--nav-surface': 'rgba(245, 243, 255, 0.95)',
          '--nav-border': 'rgba(199, 210, 254, 0.9)',
          '--nav-text-muted': '#4338ca',
          '--nav-pill-bg': '#e0e7ff',
          '--card-surface': '#ffffff',
          '--card-border': '#e0e7ff',
          '--text-primary': '#1e1b4b',
          '--text-secondary': '#4f46e5',
          '--hero-bg-start': '#1e1b4b',
          '--hero-bg-end': '#0f766e',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="350" cy="48" r="46" fill="#fde047" fill-opacity="0.14" />
            <path d="M357 24C343 26 333 38 333 52C333 67 345 79 360 79C367 79 373 76 378 72C374 73 370 74 366 74C351 74 339 62 339 47C339 37 346 28 357 24Z" fill="#fde047" fill-opacity="0.9" />
            <circle cx="290" cy="30" r="2" fill="#fef08a" class="ss-sea-twinkle" />
            <circle cx="315" cy="65" r="1.5" fill="#fef08a" class="ss-sea-twinkle2" />
            <circle cx="245" cy="42" r="2.2" fill="#fde047" class="ss-sea-twinkle" />
            <circle cx="195" cy="25" r="1.8" fill="white" class="ss-sea-twinkle2" />
            <g class="ss-sea-sway" style="transform-origin: 48px 0px;">
              <line x1="48" y1="0" x2="48" y2="34" stroke="#fbbf24" stroke-width="1.5" stroke-opacity="0.75" />
              <path d="M41 34H55L58 42L54 58H42L38 42L41 34Z" fill="#f59e0b" fill-opacity="0.5" stroke="#fde047" stroke-width="1.3" />
              <circle cx="48" cy="46" r="3.5" fill="#fef08a" />
            </g>
            <g class="ss-sea-sway2" style="transform-origin: 270px 0px;">
              <line x1="270" y1="0" x2="270" y2="26" stroke="#fbbf24" stroke-width="1.5" stroke-opacity="0.75" />
              <path d="M264 26H276L279 33L275 46H265L261 33L264 26Z" fill="#f59e0b" fill-opacity="0.45" stroke="#fde047" stroke-width="1.2" />
              <circle cx="270" cy="36" r="3" fill="#fef08a" />
            </g>
            <path d="M0 230V182H38V155L44 140L50 155V182H85C85 156 105 142 122 132C139 142 159 156 159 182H215C215 162 230 150 245 142C260 150 275 162 275 182H345V148L351 132L357 148V182H440V230H0Z" fill="#0f172a" fill-opacity="0.4" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <path d="M360 350C330 355 310 380 310 410C310 445 338 472 372 472C388 472 402 466 412 456C404 459 395 460 386 460C352 460 324 432 324 398C324 376 339 358 360 350Z" fill="#4338ca" fill-opacity="0.045" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M385 10C377 12 372 19 372 27C372 36 379 43 388 43C392 43 396 41 399 39C396 40 394 40 391 40C382 40 375 33 375 24C375 18 379 13 385 10Z" fill="#f59e0b" fill-opacity="0.22" />
            <circle cx="362" cy="18" r="2" fill="#f59e0b" fill-opacity="0.35" />
            <circle cx="24" cy="20" r="2.2" fill="#4338ca" fill-opacity="0.2" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Lengkungan Arabesque & Bintang Emas -->
            <path d="M0 64V48C45 48 65 36 95 36C125 36 145 48 190 48H220C265 48 285 36 315 36C345 36 365 48 410 48V64H0Z" fill="#4338ca" fill-opacity="0.08" />
            <!-- Bulan Sabit & Bintang di Sisi Kanan & Kiri -->
            <path d="M382 14C375 16 370 22 370 29C370 37 376 43 384 43C388 43 391 41 394 39C391 40 389 40 387 40C379 40 373 34 373 26C373 21 377 16 382 14Z" fill="#f59e0b" fill-opacity="0.28" />
            <polygon points="362,16 363.5,20 368,20 364.5,22.5 366,27 362,24.5 358,27 359.5,22.5 356,20 360.5,20" fill="#f59e0b" fill-opacity="0.35" />
            <polygon points="34,15 35.5,19 40,19 36.5,21.5 38,26 34,23.5 30,26 31.5,21.5 28,19 32.5,19" fill="#4338ca" fill-opacity="0.22" />
            <circle cx="205" cy="12" r="2" fill="#f59e0b" fill-opacity="0.4" />
          </svg>
        `,
      },

      nuzululquran: {
        shortName: 'Nuzulul Quran',
        icon: SEA_ICO.book,
        label: 'Nuzulul Quran (17–24 Ramadan)',
        pillText: '17–24 Ramadan',
        greetingShow: true,
        greetingIcon: SEA_ICO.book,
        greetingText: 'Peringatan Nuzulul Quran • Malam Penuh Cahaya',
        greetingSub: '17–24 Ramadan',
        colors: {
          '--desktop-bg-start': '#0f2942',
          '--desktop-bg-end': '#164e63',
          '--app-bg-start': '#f0fdfa',
          '--app-bg-end': '#e0f2fe',
          '--pattern-color': 'rgba(13, 148, 136, 0.075)',
          '--header-bg-start': '#082f49',
          '--header-bg-end': '#0f766e',
          '--accent-primary': '#0d9488',
          '--accent-dark': '#115e59',
          '--accent-soft': '#ccfbf1',
          '--accent-glow': 'rgba(217, 119, 6, 0.26)',
          '--nav-surface': 'rgba(240, 253, 250, 0.96)',
          '--nav-border': 'rgba(253, 224, 71, 0.55)',
          '--nav-text-muted': '#115e59',
          '--nav-pill-bg': '#fef3c7',
          '--card-surface': '#ffffff',
          '--card-border': '#99f6e4',
          '--text-primary': '#042f2e',
          '--text-secondary': '#0f766e',
          '--hero-bg-start': '#082f49',
          '--hero-bg-end': '#b45309',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <defs>
              <radialGradient id="nurGlow" cx="350" cy="72" r="85" gradientUnits="userSpaceOnUse">
                <stop offset="0%" stop-color="#fef08a" stop-opacity="0.55" />
                <stop offset="45%" stop-color="#38bdf8" stop-opacity="0.18" />
                <stop offset="100%" stop-color="#082f49" stop-opacity="0" />
              </radialGradient>
            </defs>

            <!-- Pancaran Cahaya Ilahi (Nur) -->
            <circle cx="350" cy="72" r="85" fill="url(#nurGlow)" class="ss-sea-pulse" style="transform-origin: 350px 72px;" />
            <g stroke="#fde047" stroke-opacity="0.32" stroke-width="1.3" stroke-linecap="round">
              <line x1="350" y1="62" x2="350" y2="14" />
              <line x1="335" y1="66" x2="305" y2="26" />
              <line x1="365" y1="66" x2="395" y2="26" />
              <line x1="324" y1="76" x2="282" y2="52" />
              <line x1="376" y1="76" x2="418" y2="52" />
            </g>

            <!-- Bulan Sabit & Bintang Lailatul Qadar -->
            <path d="M62 24C52 26 45 35 45 45C45 56 54 65 65 65C70 65 75 63 79 60C76 61 73 61 70 61C59 61 50 52 50 41C50 33 55 27 62 24Z" fill="#fde047" fill-opacity="0.88" />
            <circle cx="96" cy="30" r="2" fill="#fef08a" class="ss-sea-twinkle" />
            <circle cx="240" cy="26" r="2.2" fill="#bae6fd" class="ss-sea-twinkle2" />
            <circle cx="285" cy="44" r="1.8" fill="#fef08a" class="ss-sea-twinkle" />
            <circle cx="408" cy="34" r="2" fill="#fef08a" class="ss-sea-twinkle2" />

            <!-- Ilustrasi Mushaf Al-Quran Terbuka & Rehal Kayu Emas -->
            <g class="ss-sea-float" transform="translate(314, 54)">
              <!-- Rehal / Penyangga -->
              <path d="M18 46L36 33L54 46" stroke="#f59e0b" stroke-width="2.5" stroke-linecap="round" />
              <!-- Sampul Emas Bawah -->
              <path d="M6 34Q21 30 36 36Q51 30 66 34L63 39Q51 35 36 40Q21 35 9 39Z" fill="#d97706" />
              <!-- Lembaran Kiri & Kanan -->
              <path d="M8 20Q22 16 36 23V36Q22 29 8 33Z" fill="#fefce8" stroke="#fde047" stroke-width="1" />
              <path d="M64 20Q50 16 36 23V36Q50 29 64 33Z" fill="#fef9c3" stroke="#fde047" stroke-width="1" />
              <!-- Garis Ayat Halus -->
              <path d="M13 24Q23 22 32 26M13 28Q23 26 32 30" stroke="#0f766e" stroke-opacity="0.45" stroke-width="1" stroke-linecap="round" />
              <path d="M59 24Q49 22 40 26M59 28Q49 26 40 30" stroke="#0f766e" stroke-opacity="0.45" stroke-width="1" stroke-linecap="round" />
            </g>

            <!-- Siluet Kubah Masjid di Bawah Header -->
            <path d="M0 230V188H82C82 160 105 144 126 132C147 144 170 160 170 188H275C275 166 294 152 314 142C334 152 353 166 353 188H440V230H0Z" fill="#042f2e" fill-opacity="0.4" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <!-- Bintang Rub el Hizb & Cahaya Halus di Background Utama -->
            <g transform="translate(310, 355)" opacity="0.065">
              <rect x="20" y="20" width="68" height="68" stroke="#0d9488" stroke-width="4" />
              <rect x="20" y="20" width="68" height="68" transform="rotate(45 54 54)" stroke="#d97706" stroke-width="4" />
              <circle cx="54" cy="54" r="20" stroke="#0d9488" stroke-width="3" />
            </g>
            <circle cx="40" cy="680" r="145" fill="#0d9488" fill-opacity="0.04" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <!-- Bintang Islami & Cahaya Emas di Navigasi Atas -->
            <g transform="translate(368, 10)" opacity="0.28">
              <rect x="4" y="4" width="16" height="16" stroke="#d97706" stroke-width="1.3" />
              <rect x="4" y="4" width="16" height="16" transform="rotate(45 12 12)" stroke="#0d9488" stroke-width="1.3" />
            </g>
            <path d="M14 54Q24 50 32 55Q40 50 50 54" stroke="#d97706" stroke-opacity="0.32" stroke-width="1.5" fill="none" />
            <path d="M0 64Q205 52 410 64V74H0V64Z" fill="#0d9488" fill-opacity="0.07" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Gelombang Cahaya Nur & Lengkungan Arabesque -->
            <path d="M0 50C95 36 160 54 205 42C250 54 315 36 410 50V64H0V50Z" fill="#0d9488" fill-opacity="0.1" />
            <!-- Siluet Mushaf Terbuka & Pancaran Sinar di Sisi Kanan Footer -->
            <g transform="translate(358, 12)">
              <line x1="18" y1="6" x2="18" y2="0" stroke="#d97706" stroke-opacity="0.45" stroke-width="1.2" stroke-linecap="round" />
              <line x1="11" y1="8" x2="6" y2="3" stroke="#d97706" stroke-opacity="0.35" stroke-width="1.1" stroke-linecap="round" />
              <line x1="25" y1="8" x2="30" y2="3" stroke="#d97706" stroke-opacity="0.35" stroke-width="1.1" stroke-linecap="round" />
              <path d="M4 15Q11 12 18 17Q25 12 32 15V26Q25 23 18 28Q11 23 4 26Z" fill="#f59e0b" fill-opacity="0.26" stroke="#0d9488" stroke-opacity="0.4" stroke-width="1.1" />
            </g>
            <!-- Ornamen Bintang Rub el Hizb di Sisi Kiri Footer -->
            <g transform="translate(20, 14)" opacity="0.3">
              <rect x="5" y="5" width="16" height="16" stroke="#0d9488" stroke-width="1.2" />
              <rect x="5" y="5" width="16" height="16" transform="rotate(45 13 13)" stroke="#d97706" stroke-width="1.2" />
              <circle cx="13" cy="13" r="3" fill="#f59e0b" />
            </g>
          </svg>
        `,
      },

      idulfitri: {
        shortName: 'Idul Fitri',
        icon: SEA_ICO.mosque,
        label: 'Idul Fitri',
        pillText: 'Idul Fitri',
        greetingShow: true,
        greetingIcon: SEA_ICO.mosque,
        greetingText: 'Selamat Hari Raya Idul Fitri {Y}H',
        greetingSub: 'THR Sale',
        colors: {
          '--desktop-bg-start': '#a7f3d0',
          '--desktop-bg-end': '#6ee7b7',
          '--app-bg-start': '#ecfdf5',
          '--app-bg-end': '#d1fae5',
          '--pattern-color': 'rgba(5, 150, 105, 0.065)',
          '--header-bg-start': '#065f46',
          '--header-bg-end': '#10b981',
          '--accent-primary': '#059669',
          '--accent-dark': '#064e3b',
          '--accent-soft': '#d1fae5',
          '--accent-glow': 'rgba(5, 150, 105, 0.22)',
          '--nav-surface': 'rgba(240, 253, 244, 0.95)',
          '--nav-border': 'rgba(167, 243, 208, 0.9)',
          '--nav-text-muted': '#047857',
          '--nav-pill-bg': '#d1fae5',
          '--card-surface': '#ffffff',
          '--card-border': '#d1fae5',
          '--text-primary': '#064e3b',
          '--text-secondary': '#059669',
          '--hero-bg-start': '#065f46',
          '--hero-bg-end': '#b45309',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <g opacity="0.18" transform="translate(340, 10)">
              <rect x="18" y="18" width="44" height="44" stroke="#fde047" stroke-width="2" />
              <rect x="18" y="18" width="44" height="44" stroke="#fde047" stroke-width="2" transform="rotate(45 40 40)" />
              <circle cx="40" cy="40" r="14" stroke="#fde047" stroke-width="1.5" />
            </g>
            <g class="ss-sea-sway" style="transform-origin: 295px 0px;">
              <line x1="295" y1="0" x2="295" y2="28" stroke="#fde047" stroke-width="1.5" />
              <rect x="284" y="28" width="22" height="22" rx="2" transform="rotate(45 295 39)" fill="#fbbf24" fill-opacity="0.6" stroke="#fef08a" stroke-width="1.5" />
              <path d="M288 39L302 39M295 32L295 46" stroke="#065f46" stroke-width="1.2" />
              <path d="M295 54L290 64M295 54L300 64" stroke="#fde047" stroke-width="1.3" stroke-linecap="round" />
            </g>
            <g class="ss-sea-sway2" style="transform-origin: 255px 0px;">
              <line x1="255" y1="0" x2="255" y2="20" stroke="#fde047" stroke-width="1.3" />
              <rect x="247" y="20" width="16" height="16" rx="1.5" transform="rotate(45 255 28)" fill="#34d399" fill-opacity="0.65" stroke="#fef08a" stroke-width="1.3" />
              <path d="M255 39L251 47M255 39L259 47" stroke="#fde047" stroke-width="1.2" stroke-linecap="round" />
            </g>
            <path d="M0 230V188H65C65 162 85 146 105 135C125 146 145 162 145 188H280C280 166 298 152 315 144C332 152 350 166 350 188H440V230H0Z" fill="#022c22" fill-opacity="0.34" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <rect x="330" y="380" width="70" height="70" transform="rotate(45 365 415)" stroke="#059669" stroke-opacity="0.06" stroke-width="4" />
            <rect x="330" y="380" width="70" height="70" stroke="#059669" stroke-opacity="0.06" stroke-width="4" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <rect x="372" y="12" width="16" height="16" transform="rotate(45 380 20)" fill="#f59e0b" fill-opacity="0.2" stroke="#059669" stroke-opacity="0.2" />
            <rect x="18" y="42" width="14" height="14" transform="rotate(45 25 49)" fill="#10b981" fill-opacity="0.18" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Ornamen Ketupat Kembar & Bintang Rub el Hizb -->
            <g transform="translate(366, 12)">
              <rect x="8" y="4" width="14" height="14" rx="1.5" transform="rotate(45 15 11)" fill="#f59e0b" fill-opacity="0.24" stroke="#059669" stroke-opacity="0.3" stroke-width="1" />
              <path d="M10 11H20M15 6V16" stroke="#065f46" stroke-opacity="0.28" stroke-width="0.9" />
            </g>
            <g transform="translate(18, 14)">
              <rect x="6" y="6" width="16" height="16" stroke="#059669" stroke-opacity="0.18" stroke-width="1.2" />
              <rect x="6" y="6" width="16" height="16" transform="rotate(45 14 14)" stroke="#f59e0b" stroke-opacity="0.28" stroke-width="1.2" />
            </g>
            <path d="M0 54Q102 42 205 54T410 54V64H0V54Z" fill="#059669" fill-opacity="0.09" />
          </svg>
        `,
      },

      iduladha: {
        shortName: 'Idul Adha',
        icon: SEA_ICO.kaaba,
        label: 'Idul Adha',
        pillText: 'Idul Adha',
        greetingShow: true,
        greetingIcon: SEA_ICO.kaaba,
        greetingText: 'Selamat Hari Raya Idul Adha • Berkah Qurban',
        greetingSub: 'Promo Qurban',
        colors: {
          '--desktop-bg-start': '#fde68a',
          '--desktop-bg-end': '#fcd34d',
          '--app-bg-start': '#fffbeb',
          '--app-bg-end': '#fef3c7',
          '--pattern-color': 'rgba(180, 83, 9, 0.065)',
          '--header-bg-start': '#78350f',
          '--header-bg-end': '#d97706',
          '--accent-primary': '#b45309',
          '--accent-dark': '#78350f',
          '--accent-soft': '#fef3c7',
          '--accent-glow': 'rgba(180, 83, 9, 0.22)',
          '--nav-surface': 'rgba(255, 251, 235, 0.95)',
          '--nav-border': 'rgba(253, 230, 138, 0.9)',
          '--nav-text-muted': '#92400e',
          '--nav-pill-bg': '#fef3c7',
          '--card-surface': '#ffffff',
          '--card-border': '#fde68a',
          '--text-primary': '#451a03',
          '--text-secondary': '#92400e',
          '--hero-bg-start': '#78350f',
          '--hero-bg-end': '#0f766e',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="360" cy="48" r="34" fill="#fef3c7" fill-opacity="0.2" />
            <path d="M367 28C356 30 348 39 348 50C348 62 358 72 370 72C375 72 380 70 384 67C381 68 378 68 375 68C363 68 353 58 353 46C353 38 359 31 367 28Z" fill="#fef08a" fill-opacity="0.9" />
            <g opacity="0.32" transform="translate(300, 118)">
              <rect x="10" y="15" width="54" height="58" rx="2" fill="#1c1917" />
              <rect x="10" y="25" width="54" height="6" fill="#fbbf24" />
              <rect x="44" y="40" width="10" height="16" fill="#fbbf24" fill-opacity="0.85" />
            </g>
            <path d="M0 185C90 155 185 195 290 168C350 152 395 168 440 178V230H0V185Z" fill="#451a03" fill-opacity="0.35" />
            <path d="M0 202C120 180 240 212 440 190V230H0V202Z" fill="#fef3c7" fill-opacity="0.14" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <path d="M0 700C130 650 280 740 440 680V850H0V700Z" fill="#d97706" fill-opacity="0.045" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M0 60C110 46 260 68 410 52V74H0V60Z" fill="#d97706" fill-opacity="0.09" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Bukit Pasir Emas & Siluet Ka'bah Mini -->
            <path d="M0 48C95 34 210 56 320 40C360 34 390 42 410 46V64H0V48Z" fill="#b45309" fill-opacity="0.11" />
            <g transform="translate(366, 16)" opacity="0.26">
              <rect x="0" y="0" width="22" height="24" rx="1.5" fill="#451a03" />
              <rect x="0" y="5" width="22" height="3" fill="#f59e0b" />
            </g>
            <circle cx="32" cy="22" r="10" fill="#f59e0b" fill-opacity="0.18" />
          </svg>
        `,
      },

      muharram: {
        shortName: 'Muharram',
        icon: SEA_ICO.moon,
        label: '1 Muharram',
        pillText: '1 Muharram',
        greetingShow: true,
        greetingIcon: SEA_ICO.moon,
        greetingText: 'Selamat Tahun Baru Islam 1 Muharram {Y}H',
        greetingSub: 'Tahun Baru',
        colors: {
          '--desktop-bg-start': '#bae6fd',
          '--desktop-bg-end': '#7dd3fc',
          '--app-bg-start': '#f0f9ff',
          '--app-bg-end': '#e0f2fe',
          '--pattern-color': 'rgba(3, 105, 161, 0.06)',
          '--header-bg-start': '#0f172a',
          '--header-bg-end': '#0284c7',
          '--accent-primary': '#0369a1',
          '--accent-dark': '#0f172a',
          '--accent-soft': '#e0f2fe',
          '--accent-glow': 'rgba(3, 105, 161, 0.22)',
          '--nav-surface': 'rgba(240, 249, 255, 0.95)',
          '--nav-border': 'rgba(186, 230, 253, 0.9)',
          '--nav-text-muted': '#0369a1',
          '--nav-pill-bg': '#e0f2fe',
          '--card-surface': '#ffffff',
          '--card-border': '#bae6fd',
          '--text-primary': '#0f172a',
          '--text-secondary': '#0369a1',
          '--hero-bg-start': '#0f172a',
          '--hero-bg-end': '#0369a1',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="260" cy="28" r="2" fill="white" class="ss-sea-twinkle" />
            <circle cx="310" cy="44" r="2.5" fill="#bae6fd" class="ss-sea-twinkle2" />
            <circle cx="385" cy="32" r="2" fill="#fde047" class="ss-sea-twinkle" />
            <circle cx="215" cy="45" r="1.5" fill="white" class="ss-sea-twinkle2" />
            <path d="M405 18L330 56" stroke="url(#cometGrad)" stroke-width="2.2" stroke-linecap="round" />
            <defs>
              <linearGradient id="cometGrad" x1="405" y1="18" x2="330" y2="56" gradientUnits="userSpaceOnUse">
                <stop stop-color="#fde047" stop-opacity="0.95" />
                <stop offset="1" stop-color="#38bdf8" stop-opacity="0" />
              </linearGradient>
            </defs>
            <path d="M357 24C343 26 333 38 333 52C333 67 345 79 360 79C367 79 373 76 378 72C374 73 370 74 366 74C351 74 339 62 339 47C339 37 346 28 357 24Z" fill="#e0f2fe" fill-opacity="0.95" />
            <path d="M0 230V186H110V145L116 128L122 145V186H155C155 154 182 136 215 122C248 136 275 154 275 186H308V145L314 128L320 145V186H440V230H0Z" fill="#020617" fill-opacity="0.45" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <circle cx="380" cy="400" r="110" stroke="#0284c7" stroke-opacity="0.05" stroke-width="12" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M398 10L365 28" stroke="#0284c7" stroke-opacity="0.28" stroke-width="1.5" stroke-linecap="round" />
            <circle cx="362" cy="30" r="2" fill="#0284c7" fill-opacity="0.35" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Konstelasi Bintang & Jejak Komet Hijriah -->
            <path d="M395 12L352 34" stroke="#0284c7" stroke-opacity="0.28" stroke-width="1.8" stroke-linecap="round" />
            <circle cx="350" cy="35" r="2.5" fill="#0369a1" fill-opacity="0.35" />
            <circle cx="28" cy="20" r="2" fill="#0284c7" fill-opacity="0.3" />
            <circle cx="48" cy="42" r="1.8" fill="#0369a1" fill-opacity="0.25" />
            <path d="M28 20L48 42" stroke="#0284c7" stroke-opacity="0.16" stroke-width="1" stroke-dasharray="2 2" />
            <path d="M0 52C120 38 290 38 410 52V64H0V52Z" fill="#0369a1" fill-opacity="0.08" />
          </svg>
        `,
      },

      imlek: {
        shortName: 'Imlek',
        icon: SEA_ICO.envelope,
        label: 'Imlek / Lunar',
        pillText: 'Gong Xi Fa Cai',
        greetingShow: true,
        greetingIcon: SEA_ICO.envelope,
        greetingText: 'Gong Xi Fa Cai • Angpao & Hoki Melimpah',
        greetingSub: 'Hoki Sale',
        colors: {
          '--desktop-bg-start': '#fecaca',
          '--desktop-bg-end': '#fca5a5',
          '--app-bg-start': '#fef2f2',
          '--app-bg-end': '#fee2e2',
          '--pattern-color': 'rgba(220, 38, 38, 0.065)',
          '--header-bg-start': '#7f1d1d',
          '--header-bg-end': '#dc2626',
          '--accent-primary': '#dc2626',
          '--accent-dark': '#991b1b',
          '--accent-soft': '#fee2e2',
          '--accent-glow': 'rgba(220, 38, 38, 0.25)',
          '--nav-surface': 'rgba(255, 247, 237, 0.95)',
          '--nav-border': 'rgba(252, 165, 165, 0.9)',
          '--nav-text-muted': '#991b1b',
          '--nav-pill-bg': '#fee2e2',
          '--card-surface': '#ffffff',
          '--card-border': '#fecaca',
          '--text-primary': '#7f1d1d',
          '--text-secondary': '#b91c1c',
          '--hero-bg-start': '#991b1b',
          '--hero-bg-end': '#d97706',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <path d="M310 70A65 65 0 0 1 420 70L365 70Z" fill="#fbbf24" fill-opacity="0.22" stroke="#fde047" stroke-width="1.5" />
            <g class="ss-sea-sway" style="transform-origin: 355px 0px;">
              <line x1="355" y1="0" x2="355" y2="24" stroke="#fde047" stroke-width="1.5" />
              <rect x="345" y="24" width="20" height="4" rx="1" fill="#fbbf24" />
              <ellipse cx="355" cy="44" rx="18" ry="17" fill="#ef4444" stroke="#fde047" stroke-width="1.5" />
              <ellipse cx="355" cy="44" rx="8" ry="17" stroke="#fde047" stroke-width="1" stroke-opacity="0.7" />
              <rect x="345" y="60" width="20" height="4" rx="1" fill="#fbbf24" />
              <line x1="355" y1="64" x2="355" y2="78" stroke="#fde047" stroke-width="1.5" />
            </g>
            <g class="ss-sea-sway2" style="transform-origin: 55px 0px;">
              <line x1="55" y1="0" x2="55" y2="20" stroke="#fde047" stroke-width="1.3" />
              <ellipse cx="55" cy="35" rx="13" ry="13" fill="#ef4444" stroke="#fde047" stroke-width="1.3" />
              <line x1="55" y1="48" x2="55" y2="60" stroke="#fde047" stroke-width="1.3" />
            </g>
            <path d="M0 195Q60 175 120 195T240 195T360 195T440 195V230H0V195Z" fill="#fbbf24" fill-opacity="0.16" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <circle cx="370" cy="410" r="95" stroke="#dc2626" stroke-opacity="0.05" stroke-width="10" />
            <rect x="345" y="385" width="50" height="50" stroke="#d97706" stroke-opacity="0.06" stroke-width="6" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <circle cx="385" cy="22" r="14" fill="#ef4444" fill-opacity="0.14" stroke="#f59e0b" stroke-opacity="0.3" />
            <circle cx="25" cy="52" r="12" fill="#f59e0b" fill-opacity="0.16" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Lampion Mini & Koin Keberuntungan Emas -->
            <g transform="translate(364, 12)">
              <ellipse cx="14" cy="16" rx="11" ry="10" fill="#ef4444" fill-opacity="0.22" stroke="#d97706" stroke-opacity="0.45" stroke-width="1.2" />
              <line x1="14" y1="26" x2="14" y2="34" stroke="#d97706" stroke-opacity="0.5" stroke-width="1.2" />
            </g>
            <g transform="translate(18, 16)">
              <circle cx="14" cy="14" r="12" fill="#f59e0b" fill-opacity="0.2" stroke="#dc2626" stroke-opacity="0.28" stroke-width="1.2" />
              <rect x="10" y="10" width="8" height="8" stroke="#dc2626" stroke-opacity="0.3" stroke-width="1" />
            </g>
            <path d="M0 54Q50 44 102 54T205 54T308 54T410 54V64H0V54Z" fill="#dc2626" fill-opacity="0.08" />
          </svg>
        `,
      },

      natal: {
        shortName: 'Natal',
        icon: SEA_ICO.tree,
        label: 'Natal & Tahun Baru',
        pillText: 'Merry Christmas',
        greetingShow: true,
        greetingIcon: SEA_ICO.tree,
        greetingText: 'Merry Christmas & Happy New Year!',
        greetingSub: 'Year End',
        colors: {
          '--desktop-bg-start': '#cbd5e1',
          '--desktop-bg-end': '#94a3b8',
          '--app-bg-start': '#f8fafc',
          '--app-bg-end': '#f1f5f9',
          '--pattern-color': 'rgba(22, 101, 52, 0.06)',
          '--header-bg-start': '#14532d',
          '--header-bg-end': '#b91c1c',
          '--accent-primary': '#15803d',
          '--accent-dark': '#14532d',
          '--accent-soft': '#dcfce7',
          '--accent-glow': 'rgba(21, 128, 61, 0.22)',
          '--nav-surface': 'rgba(255, 255, 255, 0.96)',
          '--nav-border': 'rgba(187, 247, 208, 0.9)',
          '--nav-text-muted': '#166534',
          '--nav-pill-bg': '#dcfce7',
          '--card-surface': '#ffffff',
          '--card-border': '#e2e8f0',
          '--text-primary': '#14532d',
          '--text-secondary': '#475569',
          '--hero-bg-start': '#14532d',
          '--hero-bg-end': '#991b1b',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="80" cy="10" r="3" fill="white" class="ss-sea-snow1" />
            <circle cx="170" cy="5" r="2.5" fill="white" class="ss-sea-snow2" />
            <circle cx="260" cy="12" r="3.5" fill="white" class="ss-sea-snow3" />
            <circle cx="330" cy="8" r="2.5" fill="white" class="ss-sea-snow1" />
            <circle cx="400" cy="15" r="3" fill="white" class="ss-sea-snow2" />
            <g opacity="0.35" transform="translate(335, 105)">
              <polygon points="35,0 10,35 24,35 5,65 20,65 0,95 70,95 50,65 65,65 46,35 60,35" fill="#052e16" />
              <circle cx="35" cy="0" r="5" fill="#fde047" />
              <circle cx="28" cy="45" r="3" fill="#ef4444" />
              <circle cx="44" cy="70" r="3" fill="#fde047" />
            </g>
            <path d="M0 195Q110 175 220 195T440 190V230H0V195Z" fill="white" fill-opacity="0.18" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <circle cx="370" cy="390" r="115" fill="#15803d" fill-opacity="0.035" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <polygon points="382,12 372,30 392,30" fill="#15803d" fill-opacity="0.16" />
            <circle cx="382" cy="10" r="2.5" fill="#eab308" fill-opacity="0.5" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Cemara Mini, Bintang Natal & Salju -->
            <g transform="translate(366, 12)">
              <polygon points="12,2 3,18 9,18 1,32 23,32 15,18 21,18" fill="#15803d" fill-opacity="0.22" />
              <circle cx="12" cy="2" r="2.5" fill="#eab308" fill-opacity="0.6" />
            </g>
            <circle cx="30" cy="20" r="3" fill="#dc2626" fill-opacity="0.24" />
            <circle cx="42" cy="34" r="2.5" fill="#15803d" fill-opacity="0.25" />
            <circle cx="205" cy="12" r="2" fill="#94a3b8" fill-opacity="0.35" />
            <path d="M0 52Q102 44 205 52T410 50V64H0V52Z" fill="#15803d" fill-opacity="0.08" />
          </svg>
        `,
      },

      kemerdekaan: {
        shortName: '17 Agustus',
        icon: SEA_ICO.flag,
        label: 'Kemerdekaan RI',
        pillText: 'HUT RI Ke-{N}',
        greetingShow: true,
        greetingIcon: SEA_ICO.flag,
        greetingText: 'Dirgahayu Republik Indonesia • Merdeka!',
        greetingSub: 'Promo 17-an',
        colors: {
          '--desktop-bg-start': '#fecaca',
          '--desktop-bg-end': '#e2e8f0',
          '--app-bg-start': '#fff5f5',
          '--app-bg-end': '#f8fafc',
          '--pattern-color': 'rgba(220, 38, 38, 0.06)',
          '--header-bg-start': '#b91c1c',
          '--header-bg-end': '#ef4444',
          '--accent-primary': '#dc2626',
          '--accent-dark': '#991b1b',
          '--accent-soft': '#fee2e2',
          '--accent-glow': 'rgba(220, 38, 38, 0.24)',
          '--nav-surface': 'rgba(255, 255, 255, 0.97)',
          '--nav-border': 'rgba(254, 202, 202, 0.95)',
          '--nav-text-muted': '#475569',
          '--nav-pill-bg': '#fee2e2',
          '--card-surface': '#ffffff',
          '--card-border': '#fecaca',
          '--text-primary': '#1e293b',
          '--text-secondary': '#64748b',
          '--hero-bg-start': '#b91c1c',
          '--hero-bg-end': '#1e293b',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <g class="ss-sea-pulse" style="transform-origin: 355px 45px;">
              <circle cx="355" cy="45" r="24" stroke="#fde047" stroke-width="1.5" stroke-dasharray="4 4" />
              <circle cx="355" cy="45" r="12" stroke="white" stroke-width="1.5" stroke-dasharray="2 3" />
            </g>
            <path d="M0 175C120 145 260 205 440 165V195C260 235 120 175 0 205V175Z" fill="white" fill-opacity="0.24" />
            <path d="M0 198C120 168 260 228 440 188V230H0V198Z" fill="#7f1d1d" fill-opacity="0.32" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <path d="M0 680C150 630 290 730 440 670V850H0V680Z" fill="#dc2626" fill-opacity="0.04" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M0 58C130 44 280 68 410 52V74H0V58Z" fill="#dc2626" fill-opacity="0.1" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Gelombang Pita Merah Putih & Bintang Garuda -->
            <path d="M0 44C120 30 290 58 410 40V54C290 72 120 44 0 58V44Z" fill="#dc2626" fill-opacity="0.12" />
            <polygon points="378,12 380,18 386,18 381,22 383,28 378,24 373,28 375,22 370,18 376,18" fill="#eab308" fill-opacity="0.45" />
            <polygon points="32,14 33.5,18 38,18 34.5,20.5 36,25 32,22.5 28,25 29.5,20.5 26,18 30.5,18" fill="#dc2626" fill-opacity="0.28" />
          </svg>
        `,
      },

      isra: {
        shortName: 'Isra Mi’raj',
        icon: SEA_ICO.sparkle,
        label: 'Isra Mi’raj',
        pillText: 'Isra Mi’raj',
        greetingShow: true,
        greetingIcon: SEA_ICO.mosque,
        greetingText: 'Selamat Memperingati Isra Mi’raj {Y}H',
        greetingSub: 'Berkah Rajab',
        colors: {
          '--desktop-bg-start': '#ddd6fe',
          '--desktop-bg-end': '#c4b5fd',
          '--app-bg-start': '#faf5ff',
          '--app-bg-end': '#ede9fe',
          '--pattern-color': 'rgba(109, 40, 217, 0.055)',
          '--header-bg-start': '#1e1b4b',
          '--header-bg-end': '#6d28d9',
          '--accent-primary': '#6d28d9',
          '--accent-dark': '#1e1b4b',
          '--accent-soft': '#f5f3ff',
          '--accent-glow': 'rgba(109, 40, 217, 0.22)',
          '--nav-surface': 'rgba(250, 245, 255, 0.95)',
          '--nav-border': 'rgba(221, 214, 254, 0.9)',
          '--nav-text-muted': '#6d28d9',
          '--nav-pill-bg': '#ede9fe',
          '--card-surface': '#ffffff',
          '--card-border': '#ddd6fe',
          '--text-primary': '#1e1b4b',
          '--text-secondary': '#6d28d9',
          '--hero-bg-start': '#1e1b4b',
          '--hero-bg-end': '#6d28d9',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="250" cy="30" r="2" fill="white" class="ss-sea-twinkle" />
            <circle cx="300" cy="52" r="2.5" fill="#fde047" class="ss-sea-twinkle2" />
            <circle cx="345" cy="24" r="1.8" fill="white" class="ss-sea-twinkle" />
            <circle cx="205" cy="48" r="1.5" fill="#ddd6fe" class="ss-sea-twinkle2" />
            <circle cx="395" cy="62" r="2" fill="#fde047" class="ss-sea-twinkle" />
            <path d="M398 34C384 36 374 48 374 62C374 77 386 89 401 89C408 89 414 86 419 82C415 83 411 84 407 84C392 84 380 72 380 57C380 47 387 38 398 34Z" fill="#fef9c3" fill-opacity="0.95" />
            <path d="M62 150C130 70 250 70 330 130" stroke="#fde047" stroke-opacity="0.55" stroke-width="1.6" stroke-dasharray="4 5" stroke-linecap="round" />
            <circle cx="330" cy="130" r="3" fill="#fde047" fill-opacity="0.9" class="ss-sea-pulse" />
            <path d="M0 230V196H48C48 178 62 168 78 168C94 168 108 178 108 196H150V176L155 162L160 176V196H290V186C290 172 304 164 318 164C332 164 346 172 346 186V196H392V176L397 162L402 176V196H440V230H0Z" fill="#020617" fill-opacity="0.42" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <path d="M40 700C140 560 300 560 400 700" stroke="#6d28d9" stroke-opacity="0.05" stroke-width="10" stroke-linecap="round" />
            <circle cx="380" cy="300" r="90" stroke="#6d28d9" stroke-opacity="0.045" stroke-width="10" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M30 56C110 18 250 18 380 52" stroke="#fde047" stroke-opacity="0.35" stroke-width="1.4" stroke-dasharray="3 5" stroke-linecap="round" />
            <circle cx="380" cy="52" r="2.2" fill="#fde047" fill-opacity="0.6" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <path d="M0 50C120 34 290 34 410 50V64H0V50Z" fill="#6d28d9" fill-opacity="0.08" />
            <path d="M30 40C120 12 290 12 380 40" stroke="#6d28d9" stroke-opacity="0.22" stroke-width="1.2" stroke-dasharray="3 5" stroke-linecap="round" />
            <circle cx="30" cy="40" r="2.5" fill="#6d28d9" fill-opacity="0.35" />
            <circle cx="380" cy="40" r="2.5" fill="#6d28d9" fill-opacity="0.35" />
          </svg>
        `,
      },

      maulid: {
        shortName: 'Maulid Nabi',
        icon: SEA_ICO.mosque,
        label: 'Maulid Nabi',
        pillText: 'Maulid Nabi',
        greetingShow: true,
        greetingIcon: SEA_ICO.moon,
        greetingText: 'Peringatan Maulid Nabi Muhammad SAW {Y}H',
        greetingSub: 'Berkah Maulid',
        colors: {
          '--desktop-bg-start': '#bbf7d0',
          '--desktop-bg-end': '#86efac',
          '--app-bg-start': '#f0fdf4',
          '--app-bg-end': '#dcfce7',
          '--pattern-color': 'rgba(4, 120, 87, 0.06)',
          '--header-bg-start': '#064e3b',
          '--header-bg-end': '#059669',
          '--accent-primary': '#047857',
          '--accent-dark': '#064e3b',
          '--accent-soft': '#ecfdf5',
          '--accent-glow': 'rgba(4, 120, 87, 0.22)',
          '--nav-surface': 'rgba(240, 253, 244, 0.95)',
          '--nav-border': 'rgba(187, 247, 208, 0.9)',
          '--nav-text-muted': '#047857',
          '--nav-pill-bg': '#dcfce7',
          '--card-surface': '#ffffff',
          '--card-border': '#bbf7d0',
          '--text-primary': '#064e3b',
          '--text-secondary': '#047857',
          '--hero-bg-start': '#064e3b',
          '--hero-bg-end': '#059669',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="350" cy="70" r="70" fill="#fde047" fill-opacity="0.12" class="ss-sea-pulse" />
            <circle cx="350" cy="70" r="42" fill="#fde047" fill-opacity="0.14" />
            <path d="M350 70L350 0M350 70L420 20M350 70L440 70M350 70L420 120M350 70L280 20M350 70L260 70" stroke="#fde047" stroke-opacity="0.22" stroke-width="1.5" stroke-linecap="round" />
            <path d="M358 44C345 46 336 57 336 69C336 82 347 93 360 93C366 93 371 91 375 88C372 89 369 89 366 89C353 89 342 79 342 66C342 57 348 48 358 44Z" fill="#fef9c3" fill-opacity="0.95" />
            <circle cx="258" cy="34" r="2" fill="white" class="ss-sea-twinkle" />
            <circle cx="215" cy="58" r="2.4" fill="#fde047" class="ss-sea-twinkle2" />
            <circle cx="300" cy="22" r="1.6" fill="white" class="ss-sea-twinkle2" />
            <path d="M0 230V190H70C70 168 90 154 110 154C130 154 150 168 150 190H210V160L216 140L222 160V190H300C300 172 316 162 332 162C348 162 364 172 364 190H440V230H0Z" fill="#022c22" fill-opacity="0.4" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <circle cx="380" cy="380" r="120" stroke="#047857" stroke-opacity="0.05" stroke-width="12" />
            <circle cx="380" cy="380" r="70" stroke="#047857" stroke-opacity="0.04" stroke-width="8" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M370 0L370 74M340 0L390 74M400 0L350 74" stroke="#fde047" stroke-opacity="0.16" stroke-width="1.5" />
            <circle cx="370" cy="30" r="3" fill="#fde047" fill-opacity="0.4" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <path d="M0 52C120 38 290 38 410 52V64H0V52Z" fill="#047857" fill-opacity="0.09" />
            <path d="M30 14L34 24L44 25L36 31L39 41L30 36L21 41L24 31L16 25L26 24Z" fill="#047857" fill-opacity="0.22" />
            <path d="M380 14L384 24L394 25L386 31L389 41L380 36L371 41L374 31L366 25L376 24Z" fill="#047857" fill-opacity="0.22" />
          </svg>
        `,
      },

      harbolnas: {
        shortName: 'Harbolnas',
        icon: SEA_ICO.bag,
        label: 'Harbolnas 11.11 & 12.12',
        pillText: 'Harbolnas',
        greetingShow: true,
        greetingIcon: SEA_ICO.zap,
        greetingText: 'Harbolnas Sale • Diskon Gila-gilaan',
        greetingSub: 'Flash Sale',
        colors: {
          '--desktop-bg-start': '#fecdd3',
          '--desktop-bg-end': '#fda4af',
          '--app-bg-start': '#fff8f5',
          '--app-bg-end': '#ffe4e6',
          '--pattern-color': 'rgba(225, 29, 72, 0.05)',
          '--header-bg-start': '#be123c',
          '--header-bg-end': '#f97316',
          '--accent-primary': '#e11d48',
          '--accent-dark': '#9f1239',
          '--accent-soft': '#fff1f2',
          '--accent-glow': 'rgba(225, 29, 72, 0.22)',
          '--nav-surface': 'rgba(255, 248, 245, 0.96)',
          '--nav-border': 'rgba(254, 205, 211, 0.9)',
          '--nav-text-muted': '#be123c',
          '--nav-pill-bg': '#ffe4e6',
          '--card-surface': '#ffffff',
          '--card-border': '#fecdd3',
          '--text-primary': '#4c0519',
          '--text-secondary': '#9f1239',
          '--hero-bg-start': '#9f1239',
          '--hero-bg-end': '#ea580c',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="360" cy="70" r="52" fill="#fde047" fill-opacity="0.9" class="ss-sea-pulse" />
            <circle cx="360" cy="70" r="40" stroke="#be123c" stroke-opacity="0.35" stroke-width="2" stroke-dasharray="4 4" />
            <text x="360" y="82" text-anchor="middle" font-size="34" font-weight="800" fill="#be123c" font-family="sans-serif">%</text>
            <circle cx="240" cy="40" r="4" fill="#fde047" class="ss-sea-float" />
            <circle cx="290" cy="150" r="5" fill="#ffffff" fill-opacity="0.8" class="ss-sea-twinkle" />
            <circle cx="180" cy="90" r="3" fill="#fb7185" class="ss-sea-twinkle2" />
            <circle cx="120" cy="34" r="4" fill="#fdba74" class="ss-sea-float" />
            <rect x="200" y="120" width="10" height="10" rx="2" fill="#fde047" fill-opacity="0.85" transform="rotate(25 205 125)" class="ss-sea-twinkle2" />
            <rect x="70" y="80" width="9" height="9" rx="2" fill="#ffffff" fill-opacity="0.7" transform="rotate(-20 74 84)" class="ss-sea-twinkle" />
            <path d="M0 230V200C80 184 160 214 240 196C320 178 380 206 440 192V230H0Z" fill="#4c0519" fill-opacity="0.22" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <circle cx="380" cy="360" r="120" stroke="#e11d48" stroke-opacity="0.045" stroke-width="12" stroke-dasharray="10 12" />
            <circle cx="50" cy="680" r="90" stroke="#f97316" stroke-opacity="0.05" stroke-width="10" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <circle cx="360" cy="20" r="3" fill="#fde047" fill-opacity="0.6" />
            <circle cx="330" cy="50" r="2" fill="#ffffff" fill-opacity="0.4" />
            <rect x="385" y="40" width="7" height="7" rx="1.5" fill="#fde047" fill-opacity="0.5" transform="rotate(20 388 43)" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <path d="M0 50C100 36 300 60 410 46V64H0V50Z" fill="#e11d48" fill-opacity="0.08" />
            <circle cx="30" cy="22" r="3" fill="#e11d48" fill-opacity="0.3" />
            <circle cx="380" cy="24" r="3" fill="#f97316" fill-opacity="0.35" />
            <rect x="60" y="30" width="7" height="7" rx="1.5" fill="#f97316" fill-opacity="0.3" transform="rotate(20 63 33)" />
            <rect x="345" y="30" width="7" height="7" rx="1.5" fill="#e11d48" fill-opacity="0.28" transform="rotate(-20 348 33)" />
          </svg>
        `,
      },

      hariibu: {
        shortName: 'Hari Ibu',
        icon: SEA_ICO.heart,
        label: 'Hari Ibu Sedunia',
        pillText: 'Hari Ibu',
        greetingShow: true,
        greetingIcon: SEA_ICO.heart,
        greetingText: 'Selamat Hari Ibu Sedunia',
        greetingSub: 'Untuk Ibu Tercinta',
        colors: {
          '--desktop-bg-start': '#fbcfe8',
          '--desktop-bg-end': '#f9a8d4',
          '--app-bg-start': '#fff7fb',
          '--app-bg-end': '#fce7f3',
          '--pattern-color': 'rgba(219, 39, 119, 0.05)',
          '--header-bg-start': '#9d174d',
          '--header-bg-end': '#ec4899',
          '--accent-primary': '#db2777',
          '--accent-dark': '#9d174d',
          '--accent-soft': '#fdf2f8',
          '--accent-glow': 'rgba(219, 39, 119, 0.22)',
          '--nav-surface': 'rgba(255, 247, 251, 0.95)',
          '--nav-border': 'rgba(251, 207, 232, 0.9)',
          '--nav-text-muted': '#be185d',
          '--nav-pill-bg': '#fce7f3',
          '--card-surface': '#ffffff',
          '--card-border': '#fbcfe8',
          '--text-primary': '#500724',
          '--text-secondary': '#be185d',
          '--hero-bg-start': '#9d174d',
          '--hero-bg-end': '#ec4899',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="215" cy="34" r="2" fill="white" class="ss-sea-twinkle" />
            <circle cx="262" cy="60" r="2.4" fill="#fde68a" class="ss-sea-twinkle2" />
            <circle cx="318" cy="26" r="1.8" fill="white" class="ss-sea-twinkle" />
            <circle cx="420" cy="140" r="2" fill="#fbcfe8" class="ss-sea-twinkle2" />
            <g transform="translate(372 78)">
              <g fill="#fbcfe8" fill-opacity="0.9">
                <ellipse cx="0" cy="-17" rx="9" ry="16" />
                <ellipse cx="0" cy="-17" rx="9" ry="16" transform="rotate(72)" />
                <ellipse cx="0" cy="-17" rx="9" ry="16" transform="rotate(144)" />
                <ellipse cx="0" cy="-17" rx="9" ry="16" transform="rotate(216)" />
                <ellipse cx="0" cy="-17" rx="9" ry="16" transform="rotate(288)" />
              </g>
              <circle cx="0" cy="0" r="7" fill="#fde047" class="ss-sea-pulse" />
            </g>
            <g transform="translate(298 46)">
              <g fill="#fce7f3" fill-opacity="0.8">
                <ellipse cx="0" cy="-10" rx="5.5" ry="10" />
                <ellipse cx="0" cy="-10" rx="5.5" ry="10" transform="rotate(72)" />
                <ellipse cx="0" cy="-10" rx="5.5" ry="10" transform="rotate(144)" />
                <ellipse cx="0" cy="-10" rx="5.5" ry="10" transform="rotate(216)" />
                <ellipse cx="0" cy="-10" rx="5.5" ry="10" transform="rotate(288)" />
              </g>
              <circle cx="0" cy="0" r="4" fill="#fde68a" />
            </g>
            <g transform="translate(240 110) scale(0.9)"><path class="ss-sea-float" d="M0 -4C-6 -12 -18 -4 0 12C18 -4 6 -12 0 -4Z" fill="#fff" fill-opacity="0.75" /></g>
            <g transform="translate(410 34) scale(0.7)"><path class="ss-sea-float" d="M0 -4C-6 -12 -18 -4 0 12C18 -4 6 -12 0 -4Z" fill="#fbcfe8" fill-opacity="0.8" /></g>
            <path d="M0 230V192C80 172 160 202 250 188C330 174 390 192 440 182V230Z" fill="#500724" fill-opacity="0.30" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <circle cx="380" cy="260" r="90" stroke="#db2777" stroke-opacity="0.045" stroke-width="10" />
            <circle cx="60" cy="640" r="70" stroke="#db2777" stroke-opacity="0.04" stroke-width="10" />
            <path d="M40 720C140 600 300 600 400 720" stroke="#db2777" stroke-opacity="0.05" stroke-width="10" stroke-linecap="round" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M30 56C110 20 250 20 380 52" stroke="#db2777" stroke-opacity="0.25" stroke-width="1.4" stroke-dasharray="3 5" stroke-linecap="round" />
            <circle cx="380" cy="52" r="2.2" fill="#db2777" fill-opacity="0.45" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <path d="M0 50C120 34 290 34 410 50V64H0V50Z" fill="#db2777" fill-opacity="0.08" />
            <path d="M30 40C120 12 290 12 380 40" stroke="#db2777" stroke-opacity="0.22" stroke-width="1.2" stroke-dasharray="3 5" stroke-linecap="round" />
            <circle cx="30" cy="40" r="2.5" fill="#db2777" fill-opacity="0.35" />
            <circle cx="380" cy="40" r="2.5" fill="#db2777" fill-opacity="0.35" />
          </svg>
        `,
      },

      hariayah: {
        shortName: 'Hari Ayah',
        icon: SEA_ICO.tie,
        label: 'Hari Ayah Sedunia',
        pillText: 'Hari Ayah',
        greetingShow: true,
        greetingIcon: SEA_ICO.tie,
        greetingText: 'Selamat Hari Ayah Sedunia',
        greetingSub: 'Untuk Ayah Hebat',
        colors: {
          '--desktop-bg-start': '#99f6e4',
          '--desktop-bg-end': '#5eead4',
          '--app-bg-start': '#f0fdfa',
          '--app-bg-end': '#ccfbf1',
          '--pattern-color': 'rgba(13, 148, 136, 0.055)',
          '--header-bg-start': '#0f3b4a',
          '--header-bg-end': '#14b8a6',
          '--accent-primary': '#0d9488',
          '--accent-dark': '#0f3b4a',
          '--accent-soft': '#f0fdfa',
          '--accent-glow': 'rgba(13, 148, 136, 0.22)',
          '--nav-surface': 'rgba(240, 253, 250, 0.95)',
          '--nav-border': 'rgba(153, 246, 228, 0.9)',
          '--nav-text-muted': '#0f766e',
          '--nav-pill-bg': '#ccfbf1',
          '--card-surface': '#ffffff',
          '--card-border': '#99f6e4',
          '--text-primary': '#0f3b4a',
          '--text-secondary': '#0f766e',
          '--hero-bg-start': '#0f3b4a',
          '--hero-bg-end': '#0d9488',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="220" cy="32" r="2" fill="white" class="ss-sea-twinkle" />
            <circle cx="276" cy="58" r="2.4" fill="#fde68a" class="ss-sea-twinkle2" />
            <circle cx="330" cy="24" r="1.8" fill="white" class="ss-sea-twinkle" />
            <circle cx="425" cy="120" r="2" fill="#99f6e4" class="ss-sea-twinkle2" />
            <circle cx="372" cy="70" r="30" fill="#fde68a" fill-opacity="0.9" />
            <circle cx="372" cy="70" r="42" stroke="#fde68a" stroke-opacity="0.35" stroke-width="1.5" stroke-dasharray="3 5" class="ss-sea-pulse" />
            <g transform="translate(300 52)"><path class="ss-sea-float" d="M0 -9L2.6 -2.8L9 -2.2L4.2 2.2L5.6 8.6L0 5.3L-5.6 8.6L-4.2 2.2L-9 -2.2L-2.6 -2.8Z" fill="#fff" fill-opacity="0.85" /></g>
            <g transform="translate(250 112) scale(0.8)"><path class="ss-sea-float" d="M0 -9L2.6 -2.8L9 -2.2L4.2 2.2L5.6 8.6L0 5.3L-5.6 8.6L-4.2 2.2L-9 -2.2L-2.6 -2.8Z" fill="#99f6e4" fill-opacity="0.8" /></g>
            <path d="M0 230V188L70 160L130 190L205 150L280 192L350 164L440 196V230Z" fill="#042f2e" fill-opacity="0.32" />
            <path d="M0 230V206L90 186L170 208L260 190L350 210L440 198V230Z" fill="#042f2e" fill-opacity="0.22" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <circle cx="380" cy="260" r="90" stroke="#0d9488" stroke-opacity="0.045" stroke-width="10" />
            <path d="M0 760L110 650L200 740L300 620L440 760" stroke="#0d9488" stroke-opacity="0.05" stroke-width="10" stroke-linejoin="round" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M30 56C110 20 250 20 380 52" stroke="#0d9488" stroke-opacity="0.25" stroke-width="1.4" stroke-dasharray="3 5" stroke-linecap="round" />
            <circle cx="380" cy="52" r="2.2" fill="#0d9488" fill-opacity="0.45" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <path d="M0 50C120 34 290 34 410 50V64H0V50Z" fill="#0d9488" fill-opacity="0.08" />
            <path d="M30 40C120 12 290 12 380 40" stroke="#0d9488" stroke-opacity="0.22" stroke-width="1.2" stroke-dasharray="3 5" stroke-linecap="round" />
            <circle cx="30" cy="40" r="2.5" fill="#0d9488" fill-opacity="0.35" />
            <circle cx="380" cy="40" r="2.5" fill="#0d9488" fill-opacity="0.35" />
          </svg>
        `,
      },

      darkneon: {
        shortName: 'Dark Glass',
        icon: SEA_ICO.sparkle,
        label: 'Midnight Glass',
        pillText: 'Pro Dark UI',
        greetingShow: true,
        greetingIcon: SEA_ICO.zap,
        greetingText: 'Mode Malam Elegan • Nyaman di Mata',
        greetingSub: 'VIP Access',
        colors: {
          '--desktop-bg-start': '#020617',
          '--desktop-bg-end': '#0f172a',
          '--app-bg-start': '#090d16',
          '--app-bg-end': '#0f172a',
          '--pattern-color': 'rgba(56, 189, 248, 0.08)',
          '--header-bg-start': '#0f172a',
          '--header-bg-end': '#1e1b4b',
          '--accent-primary': '#38bdf8',
          '--accent-dark': '#0284c7',
          '--accent-soft': 'rgba(56, 189, 248, 0.16)',
          '--accent-glow': 'rgba(56, 189, 248, 0.28)',
          '--nav-surface': 'rgba(15, 23, 42, 0.9)',
          '--nav-border': 'rgba(56, 189, 248, 0.3)',
          '--nav-text-muted': '#94a3b8',
          '--nav-pill-bg': 'rgba(56, 189, 248, 0.18)',
          '--card-surface': '#131c31',
          '--card-border': '#1e293b',
          '--text-primary': '#f8fafc',
          '--text-secondary': '#94a3b8',
          '--hero-bg-start': '#1e1b4b',
          '--hero-bg-end': '#0369a1',
        },
        artworkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 230" preserveAspectRatio="xMidYMid slice" fill="none">
            <circle cx="360" cy="40" r="75" fill="#38bdf8" fill-opacity="0.18" />
            <circle cx="80" cy="160" r="90" fill="#818cf8" fill-opacity="0.16" />
            <path d="M0 160L440 120M0 190L440 150M0 220L440 180" stroke="#38bdf8" stroke-opacity="0.16" stroke-width="1" />
            <circle cx="340" cy="35" r="2" fill="#38bdf8" class="ss-sea-twinkle" />
            <circle cx="280" cy="55" r="2" fill="#a855f7" class="ss-sea-twinkle2" />
          </svg>
        `,
        bodyWatermarkSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 440 850" fill="none">
            <circle cx="390" cy="360" r="140" fill="#38bdf8" fill-opacity="0.04" />
            <circle cx="40" cy="680" r="150" fill="#818cf8" fill-opacity="0.04" />
          </svg>
        `,
        topNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 74" preserveAspectRatio="none" fill="none">
            <path d="M20 4H390" stroke="#38bdf8" stroke-opacity="0.35" stroke-width="1.5" />
            <circle cx="385" cy="18" r="22" fill="#38bdf8" fill-opacity="0.08" />
          </svg>
        `,
        footerNavOrnamentSVG: `
          <svg class="ss-sea-svg" viewBox="0 0 410 64" preserveAspectRatio="xMidYMid slice" fill="none">
            <!-- Garis Neon Cyber & Cahaya Aurora -->
            <path d="M40 2H370" stroke="#38bdf8" stroke-opacity="0.45" stroke-width="1.5" />
            <path d="M0 46L110 34L205 46L300 34L410 46V64H0V46Z" fill="#38bdf8" fill-opacity="0.09" />
            <circle cx="378" cy="22" r="2.5" fill="#38bdf8" fill-opacity="0.65" />
            <circle cx="32" cy="22" r="2.5" fill="#818cf8" fill-opacity="0.65" />
          </svg>
        `,
      },
    };

    function cal(tag) {
      try {
        var parts = new Intl.DateTimeFormat('en-u-ca-' + tag + '-nu-latn', { day: 'numeric', month: 'numeric', year: 'numeric' }).formatToParts(new Date());
        var o = {};
        for (var i = 0; i < parts.length; i++) { if (parts[i].type !== 'literal') o[parts[i].type] = parts[i].value; }
        var d = parseInt(o.day, 10), mo = parseInt(o.month, 10), y = parseInt(o.year || o.relatedYear, 10);
        if (d && mo) return { day: d, month: mo, monthRaw: String(o.month), year: y };
      } catch (e) {}
      return null;
    }

    var NOW = new Date();
    var H = cal('islamic-umalqura');
    var C = cal('chinese');
    var YEAR = H && H.year ? String(H.year) : '1448';
    var NUM = String(NOW.getFullYear() - 1945);

    function nthSunday(y, mo, n) {
      var first = (7 - new Date(y, mo, 1).getDay()) % 7 + 1;
      return first + (n - 1) * 7;
    }

    function autoSeason() {
      if (H) {
        if (H.month === 9) return (H.day >= 17 && H.day <= 24) ? 'nuzululquran' : 'ramadan';
        if (H.month === 10 && H.day <= 7) return 'idulfitri';
        if (H.month === 12 && H.day <= 14) return 'iduladha';
        if (H.month === 1 && H.day <= 10) return 'muharram';
        if (H.month === 3 && H.day >= 10 && H.day <= 13) return 'maulid';
        if (H.month === 7 && H.day >= 26 && H.day <= 28) return 'isra';
      }
      if (C && C.monthRaw === '1' && C.day <= 15) return 'imlek';
      var m = NOW.getMonth() + 1, d = NOW.getDate();
      var Y = NOW.getFullYear(), sIbu = nthSunday(Y, 4, 2), sAyah = nthSunday(Y, 5, 3);
      if (m === 5 && d >= sIbu - 6 && d <= sIbu) return 'hariibu';
      if (m === 6 && d >= sAyah - 6 && d <= sAyah) return 'hariayah';
      if (m === 8 && d <= 17) return 'kemerdekaan';
      if ((m === 11 || m === 12) && d >= 9 && d <= 12) return 'harbolnas';
      if ((m === 12 && d >= 15) || (m === 1 && d <= 2)) return 'natal';
      return 'default';
    }

    var VARS = ['--ss-blue', '--ss-blue-dark', '--ss-grad-header', '--ss-grad-main', '--ss-grad-hero-v', '--ss-hero-a', '--ss-hero-b',
      '--ss-bg', '--ss-card', '--ss-border', '--ss-text', '--ss-muted',
      '--ss-sea-bg-a', '--ss-sea-bg-b', '--ss-sea-pattern', '--ss-sea-nav-surface', '--ss-sea-nav-border', '--ss-sea-nav-muted', '--ss-sea-nav-pill', '--ss-sea-glow'];

    function $(id) { return document.getElementById(id); }
    function fill(s) { return (s || '').replace(/\{Y\}/g, YEAR).replace(/\{N\}/g, NUM); }
    function slice(svg) { return (svg || '').replace(/<svg(?![^>]*preserveAspectRatio)/, '<svg preserveAspectRatio="xMidYMid slice"'); }

    var curKey = 'default';
    function isDesk() { return !!(window.matchMedia && window.matchMedia('(min-width: 769px)').matches); }
    function uniq(svg, tag) {
      var ids = {}, m, re = /\sid="([^"]+)"/g, id;
      while ((m = re.exec(svg))) { ids[m[1]] = 1; }
      for (id in ids) {
        svg = svg.split('id="' + id + '"').join('id="' + id + tag + '"')
                 .split('url(#' + id + ')').join('url(#' + id + tag + ')')
                 .split('href="#' + id + '"').join('href="#' + id + tag + '"');
      }
      return svg;
    }
    function layers(svg, tag) {
      return '<div class="ss-sea-layer ss-sea-layer-r">' + uniq(svg, tag + 'r') + '</div>' +
             '<div class="ss-sea-layer ss-sea-layer-l">' + uniq(svg, tag + 'l') + '</div>';
    }
    function measureTop() {
      var h = document.querySelector('.ss-header'), n = document.getElementById('ssTopNavbar');
      if (!h || !n) return;
      var hh = h.offsetHeight, nh = n.offsetHeight, r = document.documentElement.style;
      r.setProperty('--ss-head-h', hh + 'px');
      r.setProperty('--ss-top-h', (hh + nh) + 'px');
    }
    function bindTopEvents() {
      var tm;
      function later() { clearTimeout(tm); tm = setTimeout(measureTop, 60); }
      window.addEventListener('resize', later);
      window.addEventListener('load', measureTop);
      if (document.fonts && document.fonts.ready) { document.fonts.ready.then(measureTop); }
      if (window.ResizeObserver) {
        var ro = new ResizeObserver(later), h = document.querySelector('.ss-header'), n = document.getElementById('ssTopNavbar');
        if (h) ro.observe(h);
        if (n) ro.observe(n);
      }
      var mq = window.matchMedia && window.matchMedia('(min-width: 769px)');
      if (mq) {
        var f = function () { applySeason(curKey); };
        if (mq.addEventListener) { mq.addEventListener('change', f); } else if (mq.addListener) { mq.addListener(f); }
      }
      var sc = function () { document.body.classList.toggle('ss-scrolled', (window.pageYOffset || 0) > 4); };
      window.addEventListener('scroll', sc, { passive: true });
      sc();
    }

    function applySeason(key) {
      if (!SEASON_THEMES[key]) key = 'default';
      var t = SEASON_THEMES[key], c = t.colors, on = key !== 'default';
      var root = document.documentElement, body = document.body;
      if (on) { body.classList.add('ss-season-on'); root.classList.add('ss-sea-root'); } else { body.classList.remove('ss-season-on'); root.classList.remove('ss-sea-root'); }
      if (key === 'darkneon') { body.classList.add('ss-season-dark'); } else { body.classList.remove('ss-season-dark'); }
      body.setAttribute('data-season', key);

      var v = {
        '--ss-blue': c['--accent-primary'],
        '--ss-blue-dark': c['--accent-dark'],
        '--ss-grad-header': 'linear-gradient(155deg, ' + c['--header-bg-start'] + ' 0%, ' + c['--header-bg-end'] + ' 100%)',
        '--ss-grad-main': 'linear-gradient(90deg, ' + c['--accent-dark'] + ' 0%, ' + c['--accent-primary'] + ' 52%, ' + c['--header-bg-end'] + ' 100%)',
        '--ss-grad-hero-v': 'linear-gradient(120deg, ' + c['--hero-bg-start'] + ' 0%, ' + c['--hero-bg-end'] + ' 100%)',
        '--ss-hero-a': c['--hero-bg-start'],
        '--ss-hero-b': c['--hero-bg-end'],
        '--ss-bg': c['--app-bg-start'],
        '--ss-card': c['--card-surface'],
        '--ss-border': c['--card-border'],
        '--ss-text': c['--text-primary'],
        '--ss-muted': c['--text-secondary'],
        '--ss-sea-bg-a': c['--app-bg-start'],
        '--ss-sea-bg-b': c['--app-bg-end'],
        '--ss-sea-pattern': c['--pattern-color'],
        '--ss-sea-nav-surface': c['--nav-surface'],
        '--ss-sea-nav-border': c['--nav-border'],
        '--ss-sea-nav-muted': c['--nav-text-muted'],
        '--ss-sea-nav-pill': c['--nav-pill-bg'],
        '--ss-sea-glow': c['--accent-glow']
      };
      for (var i = 0; i < VARS.length; i++) {
        if (on && v[VARS[i]]) { root.style.setProperty(VARS[i], v[VARS[i]]); } else { root.style.removeProperty(VARS[i]); }
      }

      var set = function (id, html) { var e = $(id); if (e) e.innerHTML = on ? (html || '') : ''; };
      if (on && isDesk() && t.artworkSVG) {
        set('ssSeaArt', layers(t.artworkSVG, '-h'));
        set('ssSeaNavOrn', layers(t.artworkSVG, '-n'));
      } else {
        set('ssSeaArt', t.artworkSVG);
        set('ssSeaNavOrn', t.topNavOrnamentSVG);
      }
      set('ssSeaWm', slice(t.bodyWatermarkSVG));
      set('ssSeaBotOrn', t.footerNavOrnamentSVG);

      var txt = function (id, s) { var e = $(id); if (e) e.textContent = on ? s : ''; };
      txt('ssSeaPill', fill(t.pillText));
      var ic = $('ssSeaIcon'); if (ic) ic.innerHTML = on ? t.greetingIcon : '';
      txt('ssSeaText', fill(t.greetingText));
      txt('ssSeaSub', t.greetingSub);

      var btns = document.querySelectorAll('#ssSeaTester button');
      for (var j = 0; j < btns.length; j++) {
        if (btns[j].getAttribute('data-theme') === key) { btns[j].classList.add('on'); } else { btns[j].classList.remove('on'); }
      }
      curKey = key;
      measureTop();
    }

    function buildTester() {
      if ($('ssSeaTester')) return;
      var box = document.createElement('div');
      box.id = 'ssSeaTester';
      var html = '<div class="ss-sea-t-title">Uji Tema (hanya terlihat dengan ?tema=)</div><div class="ss-sea-t-row">';
      for (var k in SEASON_THEMES) {
        html += '<button type="button" data-theme="' + k + '"><span>' + SEASON_THEMES[k].icon + '</span><span>' + SEASON_THEMES[k].shortName + '</span></button>';
      }
      html += '</div>';
      box.innerHTML = html;
      box.addEventListener('click', function (e) {
        var b = e.target; while (b && b !== box && !b.getAttribute('data-theme')) b = b.parentNode;
        if (b && b !== box) applySeason(b.getAttribute('data-theme'));
      });
      document.body.appendChild(box);
    }

    function init() {
      var q = '';
      try { q = (new URLSearchParams(window.location.search).get('tema') || '').toLowerCase(); } catch (e) {}
      var key = q || SS_SEASON_FORCE || autoSeason();
      if (q) buildTester();
      applySeason(key);
      bindTopEvents();
    }

    if (document.readyState === 'loading') { document.addEventListener('DOMContentLoaded', init); } else { init(); }
  })();
