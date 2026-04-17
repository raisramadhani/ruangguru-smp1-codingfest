# Tutorial Membuat Aplikasi KELOMPOK 1 (SMP 1 Surakarta)

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

Sesuai dengan konsep aplikasi Anda, kita hanya membutuhkan 1 Screen tambahan.

1. Di bagian atas layar, klik tombol **Add Screen**.
2. Ketik nama: `HalamanUtama` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi)._

> **PENTING:** Silakan coba Run program di HP Anda untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama**. Di sini kita membuat Header dengan Logo sebagai identitas aplikasi, dilanjutkan dengan area untuk input data tabungan agar bisa masuk ke Leaderboard peringkat kelas.

### A. Desain (Designer)

1. **Membuat Header & Logo (Bisa di-copy jika ada Screen baru nanti):**
   - Dari panel **Palette** > **Layout**, tarik **HorizontalArrangement** ke layar bagian paling atas.
   - Di panel **Properties**, ubah **Width** menjadi `Fill parent`.
   - Dari panel **Palette** > **User Interface**, tarik komponen **Image** ke dalam kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik tombol **Rename Component** pada gambar tersebut, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, cari kotak centang bernama **Clickable** dan **wajib dicentang** (agar logo bisa ditekan untuk me-refresh/kembali ke halaman utama).
   - Tarik komponen **Label** letakkan di sebelah logo jika ingin memberi teks judul aplikasi SMP 1.
2. **Membuat Judul Leaderboard:** Dari panel **Palette** > **User Interface**, tarik komponen **Label** ke layar tepat di bawah header.
   - Di panel **Properties**, ubah **Text** menjadi: `Leaderboard Penabung Terbanyak!`.
   - Jangan lupa centang kotak **FontBold** agar hurufnya tebal.
3. **Input Nama:** Tarik komponen **TextBox** ke bawah judul.
   - Di panel **Properties**, ubah **Hint** menjadi: `Nama Penabung`.
   - Di panel **Components**, klik **Rename Component** dan ubah namanya menjadi: `Input_Nama`.
4. **Input Nominal:** Tarik komponen **TextBox** kedua ke bawahnya.
   - Di panel **Properties**, ubah **Hint** menjadi: `Nominal Menabung`.
   - Centang kotak **NumbersOnly** (agar keyboard angka yang muncul saat aplikasi dijalankan).
   - Klik **Rename Component**, ubah menjadi: `Input_Nominal`.
5. **Tombol Tambah:** Dari panel **Palette**, tarik komponen **Button** ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Tambah ke Leaderboard`.
   - Klik **Rename Component**, ubah menjadi: `Tombol_Tambah`.
6. **Daftar Leaderboard:** Dari **Palette** > **User Interface**, tarik komponen **ListView** ke bawah layar.
   - Di panel **Properties**, ubah **Height** dan **Width** menjadi `Fill parent` agar daftarnya memenuhi ruang kosong di bawah.
   - Klik **Rename Component**, ubah menjadi: `Daftar_Leaderboard`.
7. **Alat Tambahan:**
   - Dari kategori **Storage**, tarik komponen **TinyDB** ke layar (komponen ini akan sembunyi di bawah). Rename menjadi: `DB_Kel1`.
   - Dari kategori **User Interface**, tarik komponen **Notifier**. Rename menjadi: `Notifikasi`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**. Kita akan menyusun logika logo dan variabel list agar daftar peringkat bisa terus bertambah tanpa menimpa data yang lama.

**Bagian 1: Logika Logo (Refresh Halaman Utama)**

1. Di panel kiri, temukan dan klik `Logo_Aplikasi`. Tarik blok kuning teratas: `when Logo_Aplikasi.Click do`.
2. Klik kategori **Control** (warna oranye), tarik blok `open another screen screenName`.
3. Klik kategori **Text** (warna pink), tarik blok teks kosong `" "` paling atas. Pasangkan ke blok control tadi, lalu ketik di dalamnya: `HalamanUtama`.

**Bagian 2: Menyiapkan Variabel**

1. Di panel kiri, klik kategori **Variables** (warna oranye tua), tarik blok `initialize global name to`.
2. Ganti tulisan `name` menjadi `DataPeringkat`.
3. Pasangkan dengan blok biru muda `create empty list` dari kategori **Lists**.

**Bagian 3: Menampilkan Data Saat Layar Dibuka**

1. Di panel kiri, klik `HalamanUtama` (ikon HP/Screen paling atas). Tarik blok kuning: `when HalamanUtama.Initialize do`.
2. Klik kategori **Variables**, tarik blok `set to` dan pilih `global DataPeringkat`. Masukkan ke dalam blok kuning.
3. Klik `DB_Kel1`, tarik blok ungu `call DB_Kel1.GetValue`. Pasangkan ke blok `set` tadi.
   - Isi `tag`-nya dengan teks pink `" "` (dari kategori **Text**) dan ketik: `PapanSkor`.
   - Isi `valueIfTagNotThere` dengan blok biru muda `create empty list`.
4. Klik `Daftar_Leaderboard`, tarik blok hijau muda `set Daftar_Leaderboard.Elements to` dan taruh di bawah blok variabel tadi. Pasangkan dengan blok merah `get` (dari Variables) dan pilih `global DataPeringkat`.

**Bagian 4: Menyimpan Data Baru ke Leaderboard**

1. Di panel kiri, klik `Tombol_Tambah`, tarik blok kuning `when Tombol_Tambah.Click do`.
2. **Ambil Data Lama:** Tarik blok `set to` pilih `global DataPeringkat`. Pasangkan dengan blok ungu `call DB_Kel1.GetValue`. Isi `tag`-nya dengan teks pink `"PapanSkor"`, dan `valueIfTagNotThere` dengan `create empty list`.
3. **Tambahkan Data Baru:** Klik kategori **Lists**, tarik blok biru muda `add items to list`. Taruh di bawah susunan tadi.
   - Di bagian `list`: isi dengan blok merah `get global DataPeringkat`.
   - Di bagian `item`: tarik blok pink `join` (dari kategori **Text**). Buat agar blok `join` memiliki 3 lubang kosong menggunakan ikon gir biru kecil.
   - Lubang 1: klik `Input_Nama`, tarik blok hijau tua `Input_Nama.Text`.
   - Lubang 2: tarik teks pink `" "`, ketik `- Rp` (beri spasi di awal dan akhir huruf).
   - Lubang 3: klik `Input_Nominal`, tarik blok hijau tua `Input_Nominal.Text`.
4. **Simpan ke Database:** Klik `DB_Kel1`, tarik blok ungu `call DB_Kel1.StoreValue`.
   - Isi `tag` dengan teks pink `"PapanSkor"`.
   - Isi `valueToStore` dengan blok merah `get global DataPeringkat`.
5. **Update Tampilan Layar:** Klik `Daftar_Leaderboard`, tarik blok hijau muda `set Daftar_Leaderboard.Elements to`. Pasangkan dengan blok merah `get global DataPeringkat`.
6. **Munculkan Pesan:** Klik `Notifikasi`, tarik blok ungu `call Notifikasi.ShowAlert notice`. Isi `notice` dengan teks pink `" "` dan ketik: `Data berhasil masuk ke Leaderboard!`.

> **PENTING:** Silakan coba Run program dari awal sampai akhir, periksa apakah tombol logo bisa diklik, dan apakah nama serta nominal yang Anda ketik berhasil masuk ke daftar Leaderboard secara berurutan. Jangan lupa Save project Anda!
