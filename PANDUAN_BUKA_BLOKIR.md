# 📖 PANDUAN CARA MEMBUKA BLOKIRAN & PROTEKSI APLIKASI (MANUAL & SELEKTIF)

Panduan ini menjelaskan langkah demi langkah untuk membuka kembali proteksi Master Password, proteksi berkas Windows, proteksi klik kanan/F12, maupun proteksi PIN apabila Anda/Panitia ingin melakukan penyesuaian kodingan atau sistem secara manual di kemudian hari.

---

## 🔑 1. Membuka / Menonaktifkan Proteksi Master Password (Password Utama)

Saat pertama kali membuka file `index.html` di browser, aplikasi dilindungi oleh **Master Password Gate** untuk mencegah orang luar membuka aplikasi tanpa izin.

- **Password Default**: `UNDIAN2026`

### **Cara A: Membuka Aplikasi di Browser**
1. Buka `index.html` di browser.
2. Masukkan Password: **`UNDIAN2026`** (atau kata sandi yang telah Anda ubah).
3. Klik tombol **Masuk Aplikasi** atau tekan **Enter**.
4. Setelah terbuka, sesi akan tersimpan selama tab browser tidak ditutup (tidak akan meminta password lagi saat reload live stream).

### **Cara B: Menonaktifkan Master Password Permanen**
1. Masuk ke halaman **Setup Aplikasi** (Tekan tombol **Setup / Esc**).
2. Masuk ke **Section 4: Pengaturan Mesin & Tampilan**.
3. Hapus centang pada pilihan **`🔒 Aktifkan Master Password saat Buka Aplikasi`**.
4. Klik **Buka Undian Pemenang**. Kini aplikasi langsung terbuka tanpa meminta password.

---

## 🛠️ 2. Membuka Blokir Atribut Berkas (Read-Only) pada Windows OS

Jika file `index.html` dikunci oleh sistem Windows (Read-Only) sehingga tidak bisa disimpan saat diedit di editor:

### **Metode A: Melalui Windows Explorer (Paling Mudah)**
1. Buka folder lokasi project: `C:\Users\LENOVO\Documents\undian-akbar\`.
2. Klik kanan pada file **`index.html`** &rarr; pilih **Properties**.
3. Di bagian bawah tab **General**, **HAPUS CENTANG** pada opsi **`Read-only`**.
4. Klik **Apply** lalu **OK**.

### **Metode B: Melalui Terminal / Command Prompt / PowerShell**
1. Buka Terminal / CMD di folder project.
2. Jalankan perintah berikut:
   ```cmd
   attrib -r "index.html"
   ```
3. Tekan **Enter**. File kini dapat diedit & disimpan kembali secara normal.

---

## 🛠️ 3. Membuka Blokir Klik Kanan & F12 / Inspect Element (Pada Kodingan JavaScript)

Jika Anda ingin mengembalikan akses **Klik Kanan** dan **Tombol F12 / Inspect Element / View Source** di browser:

1. Buka file [`index.html`](file:///c:/Users/LENOVO/Documents/undian-akbar/index.html) di Code Editor Anda (VS Code / Notepad).
2. Cari bagian kode JavaScript di bawah tag `<script>` (sekitar baris 2616):
   ```javascript
   /* ---------- Global Anti-Inspect & Security Protection ---------- */
   ```
3. Hapus atau beri komentar `//` pada blok kode berikut:

```javascript
// --- CARA NONAKTIFKAN BLOKIR KLIK KANAN & F12 ---
// Hapus atau beri tanda // pada baris di bawah ini:

/*
document.addEventListener("contextmenu", e => {
  e.preventDefault();
  return false;
});
*/

// Dan pada listener keydown, hapus bagian pencegahan F12 / Ctrl+Shift+I:
/*
if (
  e.key === "F12" ||
  (e.ctrlKey && e.shiftKey && (e.key === "I" || e.key === "i" || e.key === "J" || e.key === "j")) ||
  (e.ctrlKey && (e.key === "U" || e.key === "u" || e.key === "S" || e.key === "s"))
) {
  e.preventDefault();
  return false;
}
*/
```
4. Simpan file (`Ctrl + S`). Akses Klik Kanan dan F12 di browser akan kembali aktif normal.

---

## 🛠️ 4. Membuka / Menonaktifkan Proteksi PIN Setup

Jika Anda ingin membuka menu Setup tanpa diminta PIN `1234`:

### **Cara A: Dari Layar Setup Aplikasi**
1. Masuk ke Layar **Setup** &rarr; gulung ke **Section 4: Pengaturan Mesin & Tampilan**.
2. **Hapus centang** pada pilihan **`🔒 Proteksi PIN saat Buka Setup`**.
3. Klik **Buka Undian Pemenang**.

### **Cara B: Dari Kode JavaScript (`index.html`)**
1. Cari objek `DEFAULT_STATE` di file [`index.html`](file:///c:/Users/LENOVO/Documents/undian-akbar/index.html) (sekitar baris 1410).
2. Ubah baris `pinProtection: true` menjadi `false`:
   ```javascript
   settings: {
     ...
     pinProtection: false, // Ubah ke false untuk matikan PIN
     setupPin: "1234"
   }
   ```
3. Hapus cache LocalStorage di browser (atau jalankan `localStorage.clear()` di console browser) jika ingin mengosongkan state lama.

---

*Panduan ini disimpan permanen di berkas `PANDUAN_BUKA_BLOKIR.md` dalam folder project Anda.*
