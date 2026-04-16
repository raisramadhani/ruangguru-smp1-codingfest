# Tutorial Membuat Aplikasi KELOMPOK 3 (SMP 1 Surakarta)

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
   - Dari kategori **Control**, tarik blok `open another screen screenName`. Isi dengan teks pink `" "` dan ketik: `BuatKarakter`.
5. **Jika Login Salah (Bagian else):**
   - Tarik lagi blok ungu `call Notifier1.ShowAlert notice` ke dalam `else`. Isi dengan teks pink `" "` dan ketik: `Password Salah kak`.

---

## TAHAP 1: Membuat Screen Baru

Karena aplikasi kelompok Anda sangat lengkap, kita perlu membuat 7 Screen baru.

1. Di bagian atas layar, klik tombol **Add Screen**.
2. Ketik nama screen satu per satu (ulangi langkah 1 untuk setiap screen):
   - `BuatKarakter`
   - `HalamanUtama`
   - `CatatUang`
   - `Saldo`
   - `Toko`
   - `Teman`
   - `BebasPet`

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas tanpa spasi)._

---

## TAHAP 2: Desain & Blocks - BuatKarakter

Ganti screen aktif ke **BuatKarakter**. Di sini pengguna akan memulai perjalanannya.

### A. Desain (Designer)

1. **Gambar Peliharaan:** Dari panel **Palette** > **User Interface**, tarik komponen **Image**. Upload gambar peliharaan awal Anda (telur atau bayi hewan) di bagian **Picture** pada Properties.
2. **Input Nama:** Tarik **TextBox**. Ubah **Hint** menjadi: `Beri nama peliharaanmu!`. Rename menjadi: `Input_NamaPet`.
3. **Input Target:** Tarik **TextBox** kedua. Centang kotak **NumbersOnly**. Ubah **Hint** menjadi: `Berapa target tabunganmu?`. Rename menjadi: `Input_TargetUang`.
4. **Tombol Mulai:** Tarik **Button**. Ubah **Text** menjadi: `Mulai Menabung!`. Rename menjadi: `Tombol_Mulai`.
5. **Database:** Tarik **TinyDB** dari kategori Storage. Rename menjadi: `DB_Kel3`.

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. Tarik blok kuning `when Tombol_Mulai.Click do`.
2. Klik `DB_Kel3`, tarik blok ungu `call DB_Kel3.StoreValue`.
   - Isi `tag` dengan teks pink `"NamaPet"`. Isi `valueToStore` dengan blok hijau tua `Input_NamaPet.Text`.
3. Tarik lagi blok ungu `call DB_Kel3.StoreValue`.
   - Isi `tag` dengan teks pink `"Target"`. Isi `valueToStore` dengan blok hijau tua `Input_TargetUang.Text`.
4. Dari kategori **Control**, tarik blok `open another screen screenName`. Isi dengan teks pink `"HalamanUtama"`.

---

## TAHAP 3: Desain & Blocks - HalamanUtama

Ganti screen ke **HalamanUtama**. Di sini peliharaan akan selalu mengingatkan kita untuk menabung.

### A. Desain (Designer)

1. **Info Karakter:** Tarik **Label**. Ubah Text menjadi: `Nama Peliharaan`. Centang FontBold. Rename: `Teks_NamaPet`.
2. **Gambar Karakter:** Tarik **Image**. Upload gambar karakter peliharaan Anda. Rename: `Gambar_Pet`.
3. **Menu Tombol:** Tarik 4 **Button** ke layar.
   - Button 1 -> Text: `Catat Uang`, Rename: `Menu_CatatUang`.
   - Button 2 -> Text: `Cek Saldo`, Rename: `Menu_Saldo`.
   - Button 3 -> Text: `Toko Aksesoris`, Rename: `Menu_Toko`.
   - Button 4 -> Text: `Mutual Friends`, Rename: `Menu_Teman`.
4. **Alat Tambahan:** - Tarik **TinyDB** (Rename: `DB_Kel3`).
   - Tarik **Notifier** (Rename: `Notifikasi`).
   - Dari kategori **Sensors**, tarik **Clock**. Di Properties, pastikan **TimerEnabled** dicentang dan ubah **TimerInterval** menjadi `30000` (artinya pengingat akan muncul setiap 30 detik. Anda bisa menggantinya lebih lama jika mau).

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. **Tampilkan Nama Peliharaan:**
   - Tarik blok kuning `when HalamanUtama.Initialize do`.
   - Klik `Teks_NamaPet`, tarik `set Teks_NamaPet.Text to`. Pasangkan dengan blok ungu `call DB_Kel3.GetValue` (tag: `"NamaPet"`, default: `"Hewanku"`).
2. **Notifikasi Lupa Menabung (Timer):**
   - Klik `Clock1` di panel kiri, tarik blok kuning `when Clock1.Timer do`.
   - Tarik blok ungu `call Notifikasi.ShowAlert notice`. Isi dengan teks pink `"Ayo berikan makan peliharaanmu dengan cara menabung!"`.
3. **Navigasi Tombol:** Buat blok `when Click do` untuk keempat tombol menu, lalu pasangkan `open another screen` untuk masing-masing tujuannya (`"CatatUang"`, `"Saldo"`, `"Toko"`, `"Teman"`).

---

## TAHAP 4: Desain & Blocks - CatatUang

Ganti screen ke **CatatUang**.

### A. Desain (Designer)

1. Tarik **TextBox** (Hint: `Nominal Pemasukan`, _NumbersOnly_, Rename: `Input_Masuk`) dan **Button** (Text: `Simpan Pemasukan`, Rename: `Tombol_Masuk`).
2. Tarik **TextBox** (Hint: `Nominal Pengeluaran`, _NumbersOnly_, Rename: `Input_Keluar`) dan **Button** (Text: `Simpan Pengeluaran`, Rename: `Tombol_Keluar`).
3. Tarik **TinyDB** (`DB_Kel3`) dan **Notifier**.

### B. Kode (Blocks)

1. **Simpan Pemasukan:** Saat `Tombol_Masuk.Click`, gunakan `StoreValue` tag `"TotalMasuk"`. Isinya blok Math `+` (`GetValue` tag `"TotalMasuk"` ditambah `Input_Masuk.Text`). Tampilkan Notifier sukses.
2. **Simpan Pengeluaran:** Saat `Tombol_Keluar.Click`, gunakan `StoreValue` tag `"TotalKeluar"`. Isinya blok Math `+` (`GetValue` tag `"TotalKeluar"` ditambah `Input_Keluar.Text`). Tampilkan Notifier sukses.

---

## TAHAP 5: Desain & Blocks - Saldo (Evolusi Pet)

Ganti screen ke **Saldo**. Di sini pet Anda akan bertumbuh!

### A. Desain (Designer)

1. Tarik **Label** (Text: `Saldo Anda: Rp 0`, FontBold, Rename: `Teks_Saldo`).
2. Tarik **Image**. Upload ketiga gambar pet Anda (bayi, remaja, dewasa) di bagian Media, tapi biarkan _Picture_ awalnya kosong. Rename: `Gambar_Pertumbuhan`.
3. Tarik **Button** (Text: `Bebaskan Peliharaanku!`, Rename: `Tombol_Bebaskan`).
4. Tarik **TinyDB** (`DB_Kel3`) dan **Notifier** (`Pesan`).

### B. Kode (Blocks)

1. **Menghitung Saldo & Evolusi:**
   - Tarik blok kuning `when Saldo.Initialize do`.
   - Buat 2 variabel lokal dari kategori **Variables** (`initialize local name to`). Namakan `UangSaldo` (isinya `GetValue` "TotalMasuk" dikurangi `GetValue` "TotalKeluar") dan `TargetUang` (isinya `GetValue` "Target").
   - Set `Teks_Saldo.Text` dengan teks `"Saldo Anda: Rp "` digabung (`join`) dengan variabel `UangSaldo`.
   - **Logika Evolusi:** Dari kategori **Control**, tarik blok `if then` dan tambahkan `else if`.
   - **Kondisi 1 (Sudah Capai Target):** Jika variabel `UangSaldo` **>=** variabel `TargetUang`, maka `set Gambar_Pertumbuhan.Picture to` teks pink `"dewasa.png"` (Sesuaikan dengan nama file gambar Anda!).
   - **Kondisi 2 (Setengah Target):** Else if, gunakan blok Math bagi `/`. Jika variabel `UangSaldo` **>=** (`TargetUang` / `2`), maka `set Gambar_Pertumbuhan.Picture to` teks pink `"remaja.png"`.
   - **Kondisi Else:** `set Gambar_Pertumbuhan.Picture to` teks pink `"bayi.png"`.
2. **Tombol Bebaskan:** - Saat `Tombol_Bebaskan.Click`. Gunakan blok `if then else`.
   - Jika `UangSaldo` >= `TargetUang`, maka `open another screen` `"BebasPet"`.
   - Jika belum (else), tampilkan pesan Notifier `"Target belum tercapai! Terus menabung ya!"`.

---

## TAHAP 6: Toko, Teman & BebasPet (Prototype)

Ketiga screen ini adalah fitur pemanis. Kerjakan satu per satu secara singkat.

**1. Screen Toko:**

- **Designer:** Tarik 2 **Button** (`Beli_Makanan` dan `Beli_Aksesoris`). Tarik **TinyDB** (`DB_Kel3`) dan **Notifier**.
- **Blocks:** Saat `Beli_Makanan.Click`, kita memotong saldo. Tarik `StoreValue` tag `"TotalKeluar"`. Isinya blok Math `+` (`GetValue` "TotalKeluar" ditambah angka `5000` atau berapapun harga makanannya). Munculkan pesan Notifier `"Makanan berhasil dibeli!"`.

**2. Screen Teman (Mutual Friends):**

- **Designer:** Fitur ini hanya berupa purwarupa (prototype) tampilan statis. Tarik komponen **ListView**. Di panel Properties, cari kotak **ElementsFromString** lalu isikan nama teman bohongan Anda, misal: `Andi (Level 5), Budi (Level 3), Siska (Level 1)`.

**3. Screen BebasPet:**

- **Designer:** Tarik **Image**, upload gambar peliharaan Anda yang sedang bahagia/terbang. Tarik **Label** dengan ukuran font besar: `Selamat! Target Tercapai dan Peliharaan Kamu Hidup Bebas & Bahagia!`.

> **PENTING:** Silakan coba jalankan aplikasi, mulai dari mengisi target, login, hingga simulasi menabung agar peliharaannya bisa berubah dari bayi menjadi dewasa. Jangan lupa di-Save!
