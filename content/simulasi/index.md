---
title: Angsa Hitam
description: Alat simulasi pajak untuk wajib pajak orang pribadi di Indonesia.
enableToc: false
tags:
  - simulasi
---

**Angsa Hitam** membangun alat simulasi pajak untuk karyawan dan wajib pajak orang pribadi di Indonesia.

## Masalahnya

Setiap tahun pemberi kerja menyerahkan bukti potong 1721-A1, dan hampir tidak ada karyawan yang bisa membacanya. Aturannya padat, istilahnya asing, dan kalkulator pajak yang ada di pasaran meminta angka yang justru tidak dimiliki pengguna.

Yang lebih sulit lagi adalah pertanyaan "bagaimana kalau". Bagaimana kalau status PTKP saya berubah? Bagaimana kalau ada penghasilan tambahan di tengah tahun? Bagaimana kalau saya pindah kerja? Tidak ada cara untuk mencoba jawabannya tanpa menghitung ulang dari nol.

## Yang kami bangun

Alat simulasi yang bekerja dari dokumen yang sudah Anda pegang.

1. Unggah slip gaji atau bukti potong 1721-A1.
2. Komponen penghasilan dibaca dari dokumen itu dan menjadi data simulasi Anda.
3. Jalankan skenario: ubah status PTKP, tambahkan penghasilan, ubah periode kerja.
4. Setiap skenario menghasilkan angka PPh 21, penjelasan bahasa awam, dan dasar aturan di balik setiap langkah.

Tidak perlu menghitung manual, tidak perlu paham istilah teknis lebih dulu.

## Cara kerjanya

Dua lapisan yang sengaja kami pisahkan:

**Mesin hitung deterministik.** Seluruh aritmatika dan penerapan tarif dijalankan oleh mesin aturan milik kami sendiri. Skenario yang sama selalu menghasilkan output yang sama, dan setiap baris perhitungan bisa diperiksa.

**Claude untuk kerja bahasa.** Kami membangun di atas Claude API dari Anthropic untuk bagian yang memang persoalan bahasa: membaca komponen penghasilan dari slip gaji yang formatnya berbeda-beda antar pemberi kerja, menormalkannya ke bentuk terstruktur, dan menyusun penjelasan bahasa awam beserta dasar aturannya.

**Model tidak pernah mengerjakan perhitungannya.** Untuk alat pajak ini syarat kebenaran, bukan preferensi: angka simulasi yang tidak bisa direproduksi atau diaudit tidak ada gunanya.

## Batas simulasi

Hasil simulasi adalah alat bantu pemahaman dan perencanaan. Ini bukan penghitungan resmi, bukan pengganti bukti potong dari pemberi kerja, dan bukan nasihat pajak profesional.

