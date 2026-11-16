# Pembaca Komik (Pustaka)

Aplikasi Android untuk membaca komik/dokumen: CBZ, MHTML, PDF, EPUB.

## Cara mendapatkan APK
1. Push ke branch `main` (atau jalankan manual: **Actions → Build APK → Run workflow**).
2. Setelah selesai (± 3–5 menit), buka run-nya lalu unduh artifact **Pembaca-Komik-apk**.
3. Ekstrak zip-nya, pasang `app-debug.apk`.

## Struktur
```
.github/workflows/build.yml   # workflow build (pdf.js diunduh otomatis)
app/                          # kode aplikasi
  src/main/assets/index.html  # antarmuka pembaca
  src/main/java/.../MainActivity.java
  keystore.jks                # kunci tetap agar APK bisa menimpa versi lama
```

## Catatan
- Berjalan sepenuhnya offline; pdf.js hanya diunduh saat build.
- Mengubah versi: edit `versionCode` / `versionName` di `app/build.gradle`.
- `keystore.jks` + sandinya ada di repo agar update APK konsisten. Aman untuk pemakaian pribadi;
  untuk rilis publik, buat kunci baru dan simpan sandinya di GitHub Secrets.
