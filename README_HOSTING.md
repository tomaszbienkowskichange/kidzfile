# KidzFile Pro — Deployment Guide

## Struktura plików
```
kidzfile_pro_2026.html   ← Główna aplikacja (PWA + AES-256)
manifest.json            ← PWA manifest
sw.js                    ← Service Worker (offline + cache)
icon-192.png             ← Ikona PWA (ekran główny)
icon-512.png             ← Ikona PWA (splash screen)
icon.svg                 ← Źródło SVG ikony
```

## Hostowanie — opcje od najbezpieczniejszej

### 1. GITHUB PAGES (ZALECANE — darmowe + HTTPS)
**Bezpieczeństwo:** ★★★★★
- Idź na github.com → New repository → nazwa: `kidzfile`
- Wgraj wszystkie pliki
- Settings → Pages → Source: main branch
- Adres: `https://TWOJLOGIN.github.io/kidzfile/`
- HTTPS automatyczny, CDN Cloudflare, 100% darmowe

### 2. NETLIFY DROP (najszybsze — drag & drop)
**Bezpieczeństwo:** ★★★★★
- Idź na netlify.com/drop
- Przeciągnij folder z plikami
- Gotowe w 10 sekund
- HTTPS automatyczny, własna domena możliwa

### 3. CLOUDFLARE PAGES
**Bezpieczeństwo:** ★★★★★
- pages.cloudflare.com
- DDoS protection wbudowane
- HTTPS, WAF, najszybsze CDN na świecie

### 4. VERCEL
**Bezpieczeństwo:** ★★★★☆
- vercel.com → drag & drop lub git
- HTTPS automatyczny

---

## Co NIE jest bezpieczne
- ❌ Zwykły hosting HTTP (bez HTTPS) — PWA nie działa!
- ❌ Dropbox/Google Drive public link — brak HTTPS dla HTML
- ❌ FileZilla na shared hosting bez SSL

## Szyfrowanie danych
Aplikacja używa AES-256-GCM (Web Crypto API — standard bankowy).
Klucz pochodzi z Twojego hasła przez PBKDF2 (310,000 iteracji).
Dane nigdy nie opuszczają urządzenia bez zaszyfrowania.

