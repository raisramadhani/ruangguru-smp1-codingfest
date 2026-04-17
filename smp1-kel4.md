# Tutorial Membuat Aplikasi KELOMPOK 4 (SMP 1 Surakarta)

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

Sesuai dengan konsep aplikasi Anda, kita perlu membuat 3 Screen baru.

1. Di bagian atas layar, klik tombol **Add Screen**.
2. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, ketik nama: `ProgressTabungan` lalu klik OK.
4. Ulangi langkah 1, ketik nama: `InputUang` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi)._

> **PENTING:** Silakan coba Run program di HP Anda untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama**. Di sini kita membuat Header dengan Logo terlebih dahulu, dilanjutkan daftar menu navigasi.

### A. Desain (Designer)

1. **Membuat Header & Logo (Bisa di-copy ke layar lain nanti):**
   - Dari panel **Palette** > **Layout**, tarik **HorizontalArrangement** ke layar bagian paling atas.
   - Di panel **Properties**, ubah **Width** menjadi `Fill parent`.
   - Dari panel **Palette** > **User Interface**, tarik komponen **Image** ke dalam kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik tombol **Rename Component** pada gambar tersebut, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, cari kotak centang bernama **Clickable** dan **wajib dicentang** (agar logo bisa ditekan untuk me-refresh/kembali ke halaman utama).
   - Tarik komponen **Label** letakkan di sebelah logo jika ingin memberi teks judul aplikasi SMP 1.
2. **Membuat Judul:** Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke layar di bawah header.
   - Di panel **Properties**, ubah **Text** menjadi: `Daftar Menu Aplikasi Menabung`.
   - Centang kotak **FontBold** agar hurufnya tebal.
3. **Menu Input Uang:** Tarik komponen **Button** ke bawah judul.
   - Di panel **Properties**, ubah **Text** menjadi: `Catat Pemasukan / Pengeluaran`.
   - Klik **Rename Component**, ubah menjadi: `Menu_Input`.
4. **Menu Progress:** Tarik komponen **Button** kedua ke bawah tombol pertama.
   - Di panel **Properties**, ubah **Text** menjadi: `Cek Progress Tabungan`.
   - Klik **Rename Component**, ubah menjadi: `Menu_Progress`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**. Kita akan membuat logika logo dan sistem navigasi perpindahan layar.

1. **Logika Logo (Refresh Halaman Utama):**
   - Di panel kiri, temukan dan klik `Logo_Aplikasi`. Tarik blok kuning teratas: `when Logo_Aplikasi.Click do`.
   - Klik kategori **Control** (warna oranye), tarik blok `open another screen screenName`.
   - Klik kategori **Text** (warna pink), tarik blok teks kosong `" "` paling atas. Pasangkan ke blok control tadi, lalu ketik di dalamnya: `HalamanUtama`.
2. **Logika Tombol Input:**
   - Di panel kiri, klik `Menu_Input`. Tarik blok kuning `when Menu_Input.Click do`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`. Pasangkan ke dalam blok kuning.
   - Isi `screenName` dengan teks pink `" "` dan ketik: `InputUang`.
3. **Logika Tombol Progress:**
   - Lakukan hal yang sama: klik `Menu_Progress`, tarik blok kuning `when Menu_Progress.Click do`.
   - Tarik blok `open another screen screenName`, isi dengan teks pink `" "` dan ketik: `ProgressTabungan`.

---

## TAHAP 3: Desain & Blocks - InputUang

Ganti screen aktif ke **InputUang** melalui dropdown Screen di atas. Di sini pengguna akan memasukkan nominal uang.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Ganti screen kembali ke `HalamanUtama` sebentar.
   - Klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard.
   - Ganti screen kembali ke `InputUang`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo otomatis terpasang rapi di bagian atas layar.
2. **Input Nominal:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke layar di bawah header.
   - Di panel **Properties**, ubah **Hint** menjadi: `Nominal Uang (Contoh: 10000)`.
   - Centang kotak **NumbersOnly** (agar keyboard yang muncul hanya angka).
   - Klik **Rename Component**, ubah menjadi: `Input_Nominal`.
3. **Tombol Pemasukan:** Tarik komponen **Button** ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Simpan Sebagai Pemasukan`.
   - Klik **Rename Component**, ubah menjadi: `Tombol_Masuk`.
4. **Tombol Pengeluaran:** Tarik komponen **Button** ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Simpan Sebagai Pengeluaran`.
   - Klik **Rename Component**, ubah menjadi: `Tombol_Keluar`.
5. **Alat Tambahan:**
   - Dari kategori **Storage**, tarik komponen **TinyDB** (Rename menjadi: `DB_Kel4`).
   - Dari kategori **User Interface**, tarik komponen **Notifier** (Rename menjadi: `Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Menyimpan Pemasukan:**
   - Klik `Tombol_Masuk`, tarik blok kuning `when Tombol_Masuk.Click do`.
   - Klik `DB_Kel4`, tarik blok ungu `call DB_Kel4.StoreValue`.
   - Isi `tag` dengan teks pink `"TotalMasuk"`.
   - Di bagian `valueToStore`, pasangkan blok Math tambah `+` (biru muda).
   - Sisi kiri blok `+`: tarik `call DB_Kel4.GetValue`, isi tag dengan teks pink `"TotalMasuk"` dan `valueIfTagNotThere` dengan angka `0`.
   - Sisi kanan blok `+`: tarik blok hijau tua `Input_Nominal.Text`.
   - Tarik blok ungu `call Pesan.ShowAlert notice`. Isi pesan dengan teks pink: `"Pemasukan Berhasil Disimpan!"`.
2. **Menyimpan Pengeluaran:**
   - Lakukan hal yang **sama persis** dengan logika di atas, namun gunakan blok kuning `when Tombol_Keluar.Click do`.
   - Ubah isi `tag` pada `StoreValue` dan `GetValue` menjadi teks pink `"TotalKeluar"`.
   - Ubah pesan Notifier menjadi teks pink: `"Pengeluaran Berhasil Dicatat!"`.

---

## TAHAP 4: Desain & Blocks - ProgressTabungan

Ganti screen aktif ke **ProgressTabungan**. Di sini kita akan membuat target dan membandingkannya dengan saldo otomatis.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Tekan tombol **Ctrl + V** (Paste) di keyboard Anda agar Header dan Logo kembali terpasang rapi di bagian paling atas layar.
2. **Input Target:** Tarik **TextBox** ke bawah header. Ubah **Hint** menjadi: `Tentukan Target Tabunganmu`. Centang **NumbersOnly**. Rename menjadi: `Input_Target`.
3. **Tombol Set Target:** Tarik **Button** ke bawahnya. Ubah **Text** menjadi: `Set Target`. Rename menjadi: `Tombol_SetTarget`.
4. **Info Saldo:** Tarik **Label** ke layar. Ubah **Text** menjadi: `Saldo Saat Ini: Rp 0`. Centang **FontBold**. Rename menjadi: `Teks_Saldo`.
5. **Info Progress (Status):** Tarik **Label** ke bawah saldo.
   - Ubah **Text** menjadi: `Kekurangan: Rp 0`.
   - Di panel **Properties**, ubah **TextColor** menjadi `Red` (Merah).
   - Rename menjadi: `Teks_Status`.
6. **Database:** Tarik **TinyDB** dari Storage (Rename: `DB_Kel4`).

### B. Kode (Blocks)

Pindah ke **Blocks**. Kita butuh sedikit matematika di sini.

1. **Menyimpan Target yang Diinput:**
   - Tarik blok kuning `when Tombol_SetTarget.Click do`.
   - Klik `DB_Kel4`, tarik blok ungu `call DB_Kel4.StoreValue`. Isi `tag` dengan teks pink `"TargetUang"` dan `valueToStore` dengan blok hijau tua `Input_Target.Text`.
   - _(Opsional: Panggil fungsi Initialize yang akan kita buat di bawah ini agar layarnya langsung update saat tombol diklik)._
2. **Menghitung Progress dan Saldo (Saat Layar Dibuka):**
   - Tarik blok kuning `when ProgressTabungan.Initialize do`.
   - Kita akan membuat dua variabel lokal untuk mempermudah. Dari kategori **Variables**, tarik blok `initialize local name to in do` (blok oranye tua yang agak panjang dengan celah "do").
   - Klik tulisan `name` pertama dan ganti menjadi `Saldo`. Pasangkan dengan blok Math kurang `-` (Isi kiri dengan `GetValue` tag `"TotalMasuk"`, isi kanan dengan `GetValue` tag `"TotalKeluar"`).
   - Klik ikon gir biru pada blok variabel lokal tersebut, lalu tarik blok `name` baru ke bawah agar ada dua variabel. Ganti nama kedua menjadi `Target`. Pasangkan dengan `GetValue` tag `"TargetUang"` (default `0`).
3. **Memperbarui Teks di Layar (Di dalam celah "do" blok lokal):**
   - Klik `Teks_Saldo`, tarik `set Teks_Saldo.Text to`. Gunakan blok `join` dengan teks pink `"Saldo: Rp "` digabung dengan blok merah `get Saldo` (dari Variables).
   - Dari kategori **Control**, tarik blok `if then else` dan letakkan di bawah blok `set Teks_Saldo`.
   - **Kondisi (Bagian if):** Dari kategori **Math**, tarik blok lebih besar atau sama dengan `>=`. Sisi kirinya `get Saldo`, sisi kanannya `get Target`.
   - **Jika Tercapai (Bagian then):**
     - Tarik `set Teks_Status.Text to` isi dengan teks pink: `"SELAMAT! Target Tabungan Tercapai!"`.
     - Tarik `set Teks_Status.TextColor to`, isi dengan blok warna Hijau (dari kategori **Colors**).
   - **Jika Belum Tercapai (Bagian else):**
     - Tarik `set Teks_Status.Text to`. Gunakan blok `join` dengan teks pink `"Kekurangan: Rp "` digabung dengan blok Math kurang `-` (`get Target` dikurangi `get Saldo`).
     - Tarik `set Teks_Status.TextColor to`, isi dengan blok warna Merah (dari kategori **Colors**).

> **PENTING:** Silakan coba Run program secara penuh. Masukkan uang masuk, masukkan target, dan pastikan tulisan status kurang/tercapai berubah secara otomatis! Jangan lupa untuk Save project Anda.
