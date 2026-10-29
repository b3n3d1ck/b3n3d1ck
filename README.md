<!-- b3n3d1ck -->

<p align="center">
  <img width="100%" src="https://raw.githubusercontent.com/b3n3d1ck/b3n3d1ck/main/assets/banner.svg" alt="Abraham — security and web developer" />
</p>

<p align="center">
  <code>recon</code> &nbsp;·&nbsp; <code>webshell hunting</code> &nbsp;·&nbsp; <code>upload &amp; sqli assessment</code> &nbsp;·&nbsp; <code>the web apps around them</code>
</p>

<br>

## Baca, jangan tebak

Dua tool terakhir saya berangkat dari keluhan yang sama: scanner itu menebak.

Dir scanner menembakkan puluhan ribu nama ke server dan berharap yang dicari kebetulan ada di wordlist. Webshell scanner menyapu direktori dari luar dan hanya menemukan yang namanya kebetulan cocok. Hasilnya cuma sebagus tebakan itu — dan sebagian besar tebakan salah, karena endpoint aslinya bernama `/api/v1/invoices`, bukan `/admin`.

Padahal aplikasi web menyebutkan rutenya sendiri. Berkas JavaScript di frontend penuh dengan `fetch("/api/v1/users")`. `robots.txt` justru sering mencantumkan `/admin/` yang ingin disembunyikan. Dan webshell yang sudah ditanam tidak menghilang ke mana-mana — ia berbaring di disk, isinya terbaca, hanya namanya yang acak.

Jadi dua-duanya saya balik: baca sumbernya, jangan tebak dari luar.

<br>

## Yang sedang jalan

<table>
<tr>
<td width="50%"><a href="https://github.com/b3n3d1ck/ghostmap"><img width="100%" src="https://raw.githubusercontent.com/b3n3d1ck/b3n3d1ck/main/assets/card-ghostmap.svg" alt="ghostmap" /></a></td>
<td width="50%"><a href="https://github.com/b3n3d1ck/shellhound"><img width="100%" src="https://raw.githubusercontent.com/b3n3d1ck/b3n3d1ck/main/assets/card-shellhound.svg" alt="shellhound" /></a></td>
</tr>
</table>

**ghostmap** memetakan halaman dan endpoint sebuah situs tanpa wordlist sama sekali. Path dikumpulkan dari berkas JavaScript, `robots.txt`, `sitemap.xml`, dan tautan halaman, lalu ditelusuri secara rekursif — setiap temuan ditandai dari mana asalnya. Ia juga melaporkan berkas sensitif yang terbuka (nilai mirip kata sandi disensor sebelum ditampilkan), teknologi yang dipakai, serta kelemahan header, cookie, dan TLS berikut cara menambalnya. Semuanya lewat GET biasa: tidak ada payload, tidak ada brute-force, tidak ada yang ditulis ke server.

**shellhound** memburu webshell dengan membaca filesystem, bukan memindai dari luar. Dijalankan di server yang Anda kelola, ia menilai isi setiap berkas PHP di web root dan memberi skor berdasarkan keluarga shell yang dikenal, fungsi eksekusi berbahaya, obfuscation, kemampuan upload, dan ekstensi menyamar. Nama berkas berhenti jadi penentu — `avatar.jpg` yang ternyata berisi `<?php system(...)` tetap ketahuan, karena yang diperiksa kodenya.

<br>

## Indeks

| Repositori | Bahasa | Isi |
|---|---|---|
| [web-security-auditor](https://github.com/b3n3d1ck/web-security-auditor) | `PHP` | Masukkan URL, keluar rapor A–F berisi celah dan cara memperbaikinya. Tanpa dependency. |
| [murs](https://github.com/b3n3d1ck/murs) | `Python` | Suite riset keamanan upload dan SQL injection. Punya lab rentan sendiri, bisa ekspor laporan PDF dan retest sebelum/sesudah perbaikan. |
| [nightjar](https://github.com/b3n3d1ck/nightjar) | `TypeScript` | Meja kerja untuk membaca temuan: apa yang bocor, kenapa itu penting, bagaimana menambalnya. Lapisan "baca hasil" di atas tool command-line. |
| [ai-scam-detector](https://github.com/b3n3d1ck/ai-scam-detector) | `HTML` | Cek pesan penipuan WA/SMS dari screenshot atau teks. Membaca pola modus berbahasa Indonesia, jalan sepenuhnya di browser, tidak ada data yang dikirim. |
| [orbitdrop](https://github.com/b3n3d1ck/orbitdrop) | `C#` | Utilitas berkas Windows dengan menu aksi radial. Satu irisan vertikal yang benar-benar jalan, lengkap dengan test dan CI. |
| [scam-detector](https://github.com/b3n3d1ck/scam-detector) | `Python` | Eksperimen klasifikasi teks Naive Bayes di balik pendeteksi penipuan versi awal. |
| [cps-call](https://github.com/b3n3d1ck/cps-call) | `JavaScript` | Antarmuka panggilan suara dan video berbasis web. Alur dan tampilannya lengkap, signaling-nya belum disambung. |

<a href="https://github.com/b3n3d1ck?tab=repositories">Seluruh repositori</a>

<br>

## Angka

<table>
<tr>
<td width="50%"><img width="100%" src="https://github-readme-stats.vercel.app/api?username=b3n3d1ck&show_icons=true&count_private=true&hide_border=true&bg_color=0c1216&title_color=6cc3b0&text_color=93a2a6&icon_color=6cc3b0" alt="GitHub stats" /></td>
<td width="50%"><img width="100%" src="https://github-readme-stats.vercel.app/api/top-langs/?username=b3n3d1ck&layout=compact&langs_count=8&hide_border=true&bg_color=0c1216&title_color=6cc3b0&text_color=93a2a6" alt="Most used languages" /></td>
</tr>
</table>

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/b3n3d1ck/b3n3d1ck/output/snake-dark.svg" />
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/b3n3d1ck/b3n3d1ck/output/snake.svg" />
  <img width="100%" alt="contribution graph" src="https://raw.githubusercontent.com/b3n3d1ck/b3n3d1ck/output/snake-dark.svg" />
</picture>

<br>

<p align="center"><sub><a href="https://apasih.com">apasih.com</a></sub></p>
