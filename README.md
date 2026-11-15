# MandarinVerse

Web belajar Mandarin pemula berbasis HTML, CSS, JavaScript Modules, Firebase Authentication, dan Cloud Firestore.

## Fitur starter
- Register/login/logout Firebase Auth
- Dashboard, greeting dinamis, statistik profil
- Materi Week 1 Day 1–5 dan vocab cards
- Quiz harian, ujian mingguan, passing score 80%
- XP, progres day/week tersimpan di Firestore
- Vocabulary progress dan Review Center
- Responsive untuk mobile/desktop

> Ini starter app untuk pengembangan. Skor, XP, dan pembukaan materi masih dihitung di client; jangan dianggap anti-cheat untuk aplikasi publik tanpa Cloud Functions.

## 1. Buat Firebase project
1. Buka https://console.firebase.google.com/
2. Create project, lalu tambahkan Web App (ikon `</>`).
3. Copy Firebase config dari Project settings → General → Your apps.
4. Ganti placeholder konfigurasi di `public/js/firebase.js`.
5. Ganti `PASTE_PROJECT_ID` di `.firebaserc` dengan Project ID milikmu.

## 2. Aktifkan layanan
- Authentication → Sign-in method → aktifkan Email/Password.
- Firestore Database → Create database.
- Firestore → Rules → paste isi `firestore.rules` lalu Publish.

## 3. Jalankan lokal
Install Node.js LTS dan Firebase CLI:
```bash
npm install -g firebase-tools
firebase login
firebase use --add
firebase emulators:start --only hosting
```
Atau jalankan hosting lokal:
```bash
firebase serve
```
Buka URL lokal yang diberikan Firebase CLI. Jangan membuka `index.html` langsung dari file:// karena memakai ES modules.

## 4. GitHub
Buat repository lalu dari folder project:
```bash
git init
git add .
git commit -m "Initial MandarinVerse app"
git branch -M main
git remote add origin https://github.com/USERNAME/MandarinVerse.git
git push -u origin main
```

## 5. Deploy Firebase Hosting
Dari folder project:
```bash
firebase login
firebase use --add
firebase deploy --only hosting
```
Untuk deploy rules:
```bash
firebase deploy --only firestore:rules
```
Atau deploy hosting dan rules sekaligus:
```bash
firebase deploy
```

## Catatan
- Firebase web config (termasuk apiKey) bukan password server; keamanan utamanya Firebase Auth + Firestore Rules.
- Jangan pernah commit service-account private key.
- Isi kurikulum sekarang sample Week 1. Materi week berikutnya perlu ditambahkan.
- Teks greeting Mandarin seperti “Wǔ ān” dapat terdengar kurang lazim dalam penggunaan sehari-hari; greeting dinamis ini dibuat sesuai permintaan personal dan sebaiknya ditinjau jika kurikulum akan dipakai serius.
