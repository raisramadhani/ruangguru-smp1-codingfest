# Tutorial Membuat Aplikasi KELOMPOK 2 (SMP 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor, membuat project baru, dan berada di tampilan **Designer** (tombol di pojok kanan atas).

---

## TAHAP 0: Membuat Halaman Login (Screen1)

Kita akan membuat halaman Login terlebih dahulu di **Screen1** (Screen bawaan saat pertama kali membuat project).

### A. Desain (Designer)

1. **Input Username:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke layar.
   - Di panel **Properties** (sebelah kanan), ubah **Hint** menjadi: `Masukkan Username`.
   - Di panel **Components**, klik **Rename Component** dan ubah namanya menjadi: `InputUsername`.
2. **Input Password:** Dari panel **Palette** > **User Interface**, tarik komponen **PasswordTextBox** ke layar.
   - Di panel **Properties**, ubah **Hint** menjadi: `Masukkan Password`.
   - Klik **Rename Component**, ubah menjadi: `InputPassword`.
3. **Tombol Login:** Dari **Palette**, tarik komponen **Button** ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Masuk / Login`.
   - Klik **Rename Component**, ubah menjadi: `Tombol_Masuk`.
4. **Pesan Notifikasi:** Dari panel **Palette**, tarik komponen **Notifier** ke layar (komponen ini akan muncul di bawah layar). Biarkan namanya tetap `Notifier1`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** (pojok kanan atas).

1. Di panel kiri, klik `Tombol_Masuk`, tarik blok kuning paling atas: `when Tombol_Masuk.Click do`.
2. Dari kategori **Control** (warna oranye), tarik blok `if then else` ke dalam blok kuning.
3. **Mengatur Syarat Login (Bagian if):**
   - Dari kategori **Logic** (hijau terang), tarik blok `and` pasangkan ke sebelah `if`.
   - Di lubang kiri `and`: Tarik blok sama dengan `=` dari kategori **Logic**. Sisi kirinya isi dengan blok hijau tua `InputUsername.Text`, sisi kanannya isi dengan teks pink `" "` dan ketik `123`.
   - Di lubang kanan `and`: Tarik blok `=` lagi. Sisi kirinya isi dengan blok hijau tua `InputPassword.Text`, sisi kanannya isi dengan teks pink `" "` dan ketik `123`.
4. **Jika Login Benar (Bagian then):**
   - Klik `Notifier1`, tarik blok ungu `call Notifier1.ShowAlert notice`. Pasangkan ke dalam `then`. Isi dengan teks pink `" "` dan ketik: `Selamat datang kembali!`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`. Isi dengan teks pink `" "` dan ketik: `HalamanUtama`.
5. **Jika Login Salah (Bagian else):**
   - Tarik lagi blok ungu `call Notifier1.ShowAlert notice` ke dalam `else`. Isi dengan teks pink `" "` dan ketik: `Password Salah kak`.

---

## TAHAP 1: Membuat Screen Baru

Kita perlu membuat 3 Screen baru sesuai dengan konsep aplikasi pengelolaan tabungan Anda.

1. Di bagian atas layar, klik tombol **Add Screen**.
2. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, ketik nama: `CatatanMasuk` lalu klik OK.
4. Ulangi langkah 1, ketik nama: `CatatanKeluar` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi)._

> **PENTING:** Silakan coba Run program di HP Anda untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama**. Di sini kita membuat menu utama dan sistem penentuan batas (limit) pengeluaran agar muncul notifikasi jika boros.

### A. Desain (Designer)

1. **Info Limit:** Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Batas Pengeluaran Bulanan: Rp 0`. Centang **FontBold**.
   - Klik **Rename Component**, ubah menjadi: `Teks_Limit`.
2. **Form Set Limit:** - Tarik komponen **TextBox** ke bawahnya. Ubah **Hint** menjadi: `Tentukan Batas (Misal: 50000)`. Centang kotak **NumbersOnly**. Rename menjadi: `Input_Limit`.
   - Tarik komponen **Button** ke bawah TextBox. Ubah **Text** menjadi: `Set Batas`. Rename menjadi: `Tombol_SetLimit`.
3. **Menu Masuk & Keluar:**
   - Tarik **Button** baru ke layar. Ubah **Text** menjadi: `Catat Pemasukan`. Rename menjadi: `Menu_Masuk`.
   - Tarik **Button** lagi ke layar. Ubah **Text** menjadi: `Catat Pengeluaran`. Rename menjadi: `Menu_Keluar`.
4. **Alat Tambahan:** - Tarik komponen **TinyDB** dari kategori **Storage** (Rename: `DB_Kel2`).
   - Tarik komponen **Notifier** dari kategori **User Interface** (Rename: `Peringatan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Navigasi Menu:**
   - Di panel kiri, klik `Menu_Masuk`, tarik blok kuning `when Menu_Masuk.Click do`. Dari kategori **Control**, tarik blok `open another screen screenName`. Isi dengan teks pink `"CatatanMasuk"`.
   - Lakukan cara yang sama untuk `Menu_Keluar`, arahkan ke screenName `"CatatanKeluar"`.
2. **Menampilkan Limit (Saat Layar Dibuka):**
   - Tarik blok kuning `when HalamanUtama.Initialize do`.
   - Klik `Teks_Limit`, tarik blok hijau muda `set Teks_Limit.Text to`.
   - Pasangkan blok `join` (dari kategori **Text**). Lubang pertama isi dengan teks pink `"Batas Pengeluaran Bulanan: Rp "`. Lubang kedua isi dengan blok ungu `call DB_Kel2.GetValue` (Isi tag dengan teks pink `"BatasUang"`, default `0`).
3. **Menyimpan Limit Baru:**
   - Tarik blok kuning `when Tombol_SetLimit.Click do`.
   - Klik `DB_Kel2`, tarik blok ungu `call DB_Kel2.StoreValue`. Isi tag dengan teks pink `"BatasUang"`, dan `valueToStore` dengan blok hijau tua `Input_Limit.Text`.
   - _Update Layar:_ Tarik lagi `set Teks_Limit.Text to` dan gunakan blok `join` yang persis sama dengan langkah 2 di atas agar angkanya langsung berubah di layar.

---

## TAHAP 3: Desain & Blocks - CatatanMasuk

Ganti screen aktif ke **CatatanMasuk**.

### A. Desain (Designer)

1. **Input Keterangan:** Tarik **TextBox**. Ubah **Hint** menjadi: `Keterangan (Contoh: Dikasih Ibu)`. Rename menjadi: `Input_Keterangan`.
2. **Input Nominal:** Tarik **TextBox** ke bawahnya. Centang **NumbersOnly**. Ubah **Hint** menjadi: `Nominal Uang`. Rename menjadi: `Input_Nominal`.
3. **Tombol Simpan:** Tarik **Button**. Ubah **Text** menjadi: `Simpan Pemasukan`. Rename menjadi: `Tombol_Simpan`.
4. **Alat Tambahan:** Tarik **TinyDB** (Rename: `DB_Kel2`) dan **Notifier** (Rename: `Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Simpan Pemasukan:**
   - Tarik blok kuning `when Tombol_Simpan.Click do`.
   - Klik `DB_Kel2`, tarik blok ungu `call DB_Kel2.StoreValue`.
   - Isi `tag` dengan teks pink `"TotalMasuk"`.
   - Isi `valueToStore` dengan blok Math tambah `+` (biru muda). Sisi kirinya isi dengan `call DB_Kel2.GetValue` tag `"TotalMasuk"` (default `0`). Sisi kanannya isi dengan blok hijau tua `Input_Nominal.Text`.
2. **Notifikasi:**
   - Di bawah blok StoreValue, tarik blok ungu `call Pesan.ShowAlert notice`.
   - Isi dengan teks pink `"Pemasukan Tersimpan!"`.

---

## TAHAP 4: Desain & Blocks - CatatanKeluar

Ganti screen aktif ke **CatatanKeluar**. Di sini sistem akan mengecek apakah pengeluaran Anda melebihi limit yang sudah dibuat di Halaman Utama.

### A. Desain (Designer)

1. **Input Keterangan:** Tarik **TextBox**. Ubah **Hint** menjadi: `Keterangan (Contoh: Beli Jajan)`. Rename menjadi: `Input_Keterangan`.
2. **Input Nominal:** Tarik **TextBox**. Centang **NumbersOnly**. Ubah **Hint** menjadi: `Nominal Pengeluaran`. Rename menjadi: `Input_Nominal`.
3. **Tombol Simpan:** Tarik **Button**. Ubah **Text** menjadi: `Simpan Pengeluaran`. Rename menjadi: `Tombol_Simpan`.
4. **Alat Tambahan:** Tarik **TinyDB** (Rename: `DB_Kel2`) dan **Notifier** (Rename: `PeringatanLimit`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Simpan Pengeluaran:**
   - Tarik blok kuning `when Tombol_Simpan.Click do`.
   - Klik `DB_Kel2`, tarik blok ungu `call DB_Kel2.StoreValue`.
   - Isi `tag` dengan teks pink `"TotalKeluar"`.
   - Isi `valueToStore` dengan blok Math tambah `+`. Sisi kirinya isi dengan `call DB_Kel2.GetValue` tag `"TotalKeluar"` (default `0`). Sisi kanannya isi dengan blok hijau tua `Input_Nominal.Text`.
2. **Cek Notifikasi Over-Limit (Boros):**
   - Dari kategori **Control**, tarik blok `if then` dan letakkan di bawah susunan `StoreValue` tadi.
   - **Kondisi (Bagian if):** Dari kategori **Math**, tarik blok lebih besar `>`.
     - Sisi kiri `>`: Tarik `call DB_Kel2.GetValue` isi tag dengan teks pink `"TotalKeluar"`.
     - Sisi kanan `>`: Tarik `call DB_Kel2.GetValue` isi tag dengan teks pink `"BatasUang"`.
   - **Peringatan (Bagian then):** - Jika Total Pengeluaran ternyata lebih besar dari Batas Uang, maka panggil `call PeringatanLimit.ShowAlert notice`.
     - Isi `notice` dengan teks pink `" "` dan ketik: `AWAS! Pengeluaran Anda sudah melebihi batas yang ditentukan!`.

> **PENTING:** Silakan Save project Anda. Coba jalankan secara penuh mulai dari login, atur batas uang 50.000, lalu catat pengeluaran sebesar 60.000. Periksa apakah notifikasi peringatan borosnya muncul!
