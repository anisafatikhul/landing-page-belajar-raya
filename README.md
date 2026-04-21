# Landing Page Donasi — Sakola Kembara

Single-page donation landing untuk event Sakola Kembara. Built sesuai [PRD](../sakem-donation-landing-prd.md).

## Preview

Buka `index.html` langsung di browser — tidak perlu build step.

```bash
# Opsi 1: buka langsung
open index.html

# Opsi 2: serve dengan Python (rekomendasi biar asset path aman)
python3 -m http.server 8000
# lalu buka http://localhost:8000
```

## Stack

- HTML5 semantic
- Tailwind CSS via CDN (`<script src="https://cdn.tailwindcss.com">`)
- Vanilla JS untuk copy-to-clipboard
- Google Fonts: Plus Jakarta Sans (sans) + Lora (serif)

## Placeholders — ganti sebelum event

Semua ditandai dengan HTML comment `<!-- TAG -->`. Cari di `index.html`:

| Tag | Lokasi | Ganti dengan |
|---|---|---|
| `<!-- VIDEO_PLACEHOLDER -->` | Hero section | Uncomment `<iframe>` YouTube dan paste VIDEO_ID |
| `<!-- QRIS_IMAGE_PLACEHOLDER -->` | Donation Card A | Ganti div dashed dengan `<img src="assets/qris.png">` |
| `<!-- BANK_NAME -->` | Donation Card B | Ganti `[NAMA BANK]` di `<p id="bank-name">` |
| `<!-- ACCOUNT_NUMBER -->` | Donation Card B | Ganti `0000-0000-0000` di `<p id="account-number">` |
| `<!-- ACCOUNT_HOLDER -->` | Donation Card B | Sudah terisi default "Yayasan Sakola Kembara Indonesia" — ganti kalau perlu |
| `<!-- WHATSAPP_NUMBER -->` | Konfirmasi block | Ganti `6281234567890` di URL `wa.me/...` (format 62xxx, tanpa +) |
| `<!-- FINANCIAL_REPORT_LINK -->` | Trust indicator | Ganti `href="#"` dengan URL laporan keuangan |

## Assets

Folder `assets/`:
- `hero-team.jpg` — foto tim (dari situs referensi)
- `favicon.ico` — favicon
- `qris.png` — **belum ada**, tambahkan file QRIS di sini lalu update HTML

## Struktur page

```
[1] Hero        → Greeting + video placeholder + CTA
[2] Story       → Tentang Sakem + 3 mini stats
[3] Programs    → 3 tahap pembinaan
[4] Donation    → QRIS + Transfer Bank + WhatsApp
[5] Footer      → Kontak + social + copyright
```

## Deploy

Single static file — cocok untuk Vercel, Netlify, GitHub Pages.

```bash
# Contoh: GitHub Pages → push ke branch main, enable Pages di Settings
# Contoh: Vercel → import repo, deploy (auto-detect static)
```
