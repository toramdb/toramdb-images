# ToramDB Images (CDN Repository)

Repositori ini difungsikan murni sebagai **"Gudang Gambar" (CDN Asset Pool)** untuk mensuplai ribuan aset statis tingkat tinggi (seperti icon item, monster, pet, map, equipment) ke aplikasi web utama [ToramDB](https://toramcodex.github.io).

## Mengapa dipisah?
Game *Toram Online* memiliki ribuan item. Menyimpan 100,000+ gambar di dalam repositori source code utama akan membebani Github Pages dan merusak performa *version control* (Git). Repositori terpisah memastikan:
1. Repositori web app utama tetap sangat kecil, bersih, dan memuat (*load*) secepat kilat.
2. Gambar dapat di-*serve* menggunakan **server CDN Global** (Content Delivery Network) secara paralel.

## Struktur Direktori
- `/items/` — Gambar *Weapon, Armor, Crysta, Material*
- `/monsters/` — Gambar *Boss, Mini-Boss, Mobs*
- `/pets/` — Aset *Companion Pets*
- `/icons/` — Aset kecil UI, Badge, tipe serangan.

## Cara Menggunakan (via Google Sheets)

Ketika menambahkan referensi gambar baru di Google Sheet ToramDB (pada kolom `ImageURL`), gunakan URL dari **jsDelivr CDN** dengan pola berikut:

```text
https://cdn.jsdelivr.net/gh/toramdb/toramdb-images@main/FOLDER/NAMA_FILE.png
```

**Contoh Kasus:**
Jika Anda baru saja meng-upload gambar Minotaur ke `monsters/minotaur.png` dan mem-pushnya ke Github:
1. *Push* repositori ini agar tersimpan di Github.
2. Link jsDelivr-nya adalah: `https://cdn.jsdelivr.net/gh/toramdb/toramdb-images@main/monsters/minotaur.png`
3. Tempelkan link tersebut ke kolom `ImageURL` di lembar kerja Monstermu.

Sistem *ToramDB* akan secara ajaib memuat gambar ini menggunakan cache berlapis jsDelivr.
