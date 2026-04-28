# Tutorial Membuat Aplikasi KELOMPOK 3 (SMP 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor, membuat project baru, dan berada di tampilan **Designer** (perhatikan tombol **Designer** di pojok kanan atas layar harus aktif/menyala).

---

## TAHAP 0: Membuat Halaman Login (Screen1)

Kita akan membuat halaman Login terlebih dahulu di **Screen1** (Screen bawaan saat pertama kali membuat project).

### A. Desain (Designer)

1. **Input Username:** Di sebelah kiri layar pada panel **Palette** > klik kategori **User Interface**, klik dan tarik (drag) komponen **TextBox** ke gambar HP di tengah layar (Viewer).
   - Beralih ke panel **Properties** di sebelah kanan layar. Cari kolom **Hint**, hapus isinya dan ketik: `Masukkan Username`.
   - Beralih ke panel **Components** (di sebelah kanan gambar HP). Klik komponen `TextBox1`, lalu klik tombol **Rename** di bawahnya. Ubah namanya menjadi: `InputUsername` lalu klik OK.
2. **Input Password:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **PasswordTextBox** ke gambar HP di bawah Username.
   - Di panel **Properties**, cari kolom **Hint** dan ubah menjadi: `Masukkan Password`.
   - Di panel **Components**, klik komponennya lalu klik **Rename**, ubah menjadi: `InputPassword`.
3. **Tombol Login:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Button** ke gambar HP.
   - Di panel **Properties**, cari kolom **Text** dan ubah tulisannya menjadi: `Masuk / Login`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Tombol_Masuk`.
4. **Pesan Notifikasi:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Notifier** ke gambar HP. (Catatan: Komponen ini tidak akan terlihat di layar HP, melainkan muncul di bawah sebagai _Non-visible components_). Biarkan namanya tetap `Notifier1` di panel Components.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** dengan mengklik tombol **Blocks** di pojok kanan atas layar.

1. **Memulai Tombol:** Di panel sebelah kiri bawah (daftar komponen), cari dan klik `Tombol_Masuk`. Akan muncul laci blok, tarik blok kuning paling atas: `when Tombol_Masuk.Click do` ke area putih.
2. **Membuat Syarat:** Di panel kiri atas (Built-in), klik kategori **Control** (warna oranye), tarik blok `if then else` ke dalam celah blok kuning tadi.
3. **Mengatur Syarat Login (Bagian if):**
   - Di panel kiri atas, klik kategori **Logic** (hijau terang), tarik blok `and` pasangkan ke sebelah kanan tulisan `if`.
   - **Di lubang kiri `and`:** Klik kategori **Logic** lagi, tarik blok sama dengan `=`.
     - **Sisi kirinya:** Klik komponen `InputUsername` di panel kiri bawah, scroll dan tarik blok hijau tua `InputUsername.Text`, ke sisi kiri blok `=`.
     - **Sisi kanannya:** Klik kategori **Text** (pink), tarik blok kosong `" "` paling atas. Pasangkan ke sisi kanan `=`, lalu klik tengahnya dan ketik `123`.
   - **Di lubang kanan `and`:** Lakukan hal yang sama. Tarik blok `=` dari **Logic**.
     - **Sisi kirinya:** Klik komponen `InputPassword` di panel kiri bawah, cari dan tarik blok hijau tua `InputPassword.Text`.
     - **Sisi kanannya:** Ambil blok teks pink kosong `" "` dari **Text**, pasangkan lalu ketik `123`.
4. **Jika Login Benar (Bagian then):**
   - Di panel kiri bawah, klik komponen `Notifier1`, cari dan tarik blok ungu `call Notifier1.ShowAlert notice`. Pasangkan ke dalam celah `then`.
   - Klik kategori **Text**, ambil blok kosong `" "`, pasangkan ke sebelah `notice`, dan ketik: `Selamat datang kembali!`.
   - Di panel kiri atas, klik kategori **Control**, scroll agak ke bawah dan tarik blok `open another screen screenName` ke bawah blok ungu tadi.
   - Ambil lagi blok teks pink kosong `" "` dari **Text**, pasangkan, dan ketik persis: `BuatKarakter`.
5. **Jika Login Salah (Bagian else):**
   - Lakukan cara yang sama: klik `Notifier1` di panel kiri bawah, tarik blok ungu `call Notifier1.ShowAlert notice` ke dalam celah `else`.
   - Ambil blok teks pink `" "` dari **Text** dan ketik: `Password Salah kak`.

---

## TAHAP 1: Membuat Screen Baru

Karena aplikasi kelompok Anda sangat lengkap, kita perlu membuat 7 Screen baru.

1. Di bagian paling atas layar App Inventor, klik tombol **Add Screen**.
2. Ketik nama screen satu per satu pada pop-up yang muncul, lalu klik OK (ulangi langkah 1 untuk setiap screen):
   - `BuatKarakter`
   - `HalamanUtama`
   - `CatatUang`
   - `Saldo`
   - `Toko`
   - `Teman`
   - `BebasPet`

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas, huruf besar kecil sama, dan TANPA SPASI)._

---

## TAHAP 2: Desain & Blocks - BuatKarakter

Ganti screen aktif ke **BuatKarakter** melalui kotak dropdown Screen di atas. Pastikan kembali ke mode **Designer**. Di sini pengguna akan memulai perjalanannya.

### A. Desain (Designer)

1. **Gambar Peliharaan:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Image** ke layar HP.
   - Di panel bawah bagian **Media**, klik tombol **Upload File...** lalu pilih gambar peliharaan awal Anda (telur/bayi hewan) dari komputer.
   - Beralih ke panel **Properties**, cari menu **Picture**, klik dan pilih nama file gambar yang baru saja di-upload, lalu klik OK.
2. **Input Nama:** Dari panel **Palette**, tarik **TextBox** ke bawah gambar.
   - Di panel **Properties**, ubah **Hint** menjadi: `Beri nama peliharaanmu!`.
   - Di panel **Components**, Rename menjadi: `Input_NamaPet`.
3. **Input Target:** Tarik **TextBox** kedua ke layar.
   - Di panel **Properties**, centang kotak **NumbersOnly**. Ubah **Hint** menjadi: `Berapa target tabunganmu?`.
   - Di panel **Components**, Rename menjadi: `Input_TargetUang`.
4. **Tombol Mulai:** Tarik **Button** ke bawahnya.
   - Di panel **Properties**, ubah **Text** menjadi: `Mulai Menabung!`.
   - Di panel **Components**, Rename menjadi: `Tombol_Mulai`.
5. **Database:** Dari panel **Palette** > klik kategori **Storage**, tarik **TinyDB** ke layar. Di panel **Components**, Rename menjadi: `DB_Kel3`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. Di panel kiri bawah, klik `Tombol_Mulai`, tarik blok kuning `when Tombol_Mulai.Click do`.
2. Klik komponen `DB_Kel3`, tarik blok ungu `call DB_Kel3.StoreValue`. Pasangkan ke blok kuning.
   - Isi lubang `tag` dengan blok teks pink kosong `" "` dari kategori **Text** dan ketik: `"NamaPet"`.
   - Isi `valueToStore` dengan mengklik `Input_NamaPet` di panel kiri lalu tarik blok hijau tua `Input_NamaPet.Text`.
3. Klik lagi `DB_Kel3`, tarik blok ungu `call DB_Kel3.StoreValue` dan letakkan tepat di bawah blok ungu pertama.
   - Isi `tag` dengan blok teks pink `" "` dan ketik: `"Target"`.
   - Isi `valueToStore` dengan mengklik `Input_TargetUang`, lalu tarik blok hijau tua `Input_TargetUang.Text`.
4. Dari kategori **Control**, scroll ke bawah, tarik blok `open another screen screenName`. Ambil blok teks pink `" "` dari kategori **Text** dan ketik: `HalamanUtama`.

---

## TAHAP 3: Desain & Blocks - HalamanUtama

Ganti screen ke **HalamanUtama** via dropdown atas. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Membuat Header & Logo (Bisa di-copy ke layar lain nanti):**
   - Dari panel **Palette** > klik kategori **Layout**, tarik **HorizontalArrangement** ke layar bagian paling atas.
   - Di panel **Properties**, ubah **Width** menjadi `Fill parent`.
   - Dari panel **Palette** > **User Interface**, tarik komponen **Image** ke dalam kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik **Rename** pada gambar tersebut, ubah menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, scroll ke bawah, cari kotak centang **Clickable** dan **wajib Anda centang**.
   - _(Opsional)_ Tarik **Label** letakkan di sebelah logo jika ingin memberi teks judul.
2. **Info Karakter:** Tarik **Label** ke bawah kotak header.
   - Di panel **Properties**, ubah **Text** menjadi: `Nama Peliharaan`. Centang **FontBold**.
   - Di panel **Components**, Rename: `Teks_NamaPet`.
3. **Gambar Karakter:** Tarik komponen **Image** ke layar. Di panel Properties, set _Picture_ dengan gambar karakter Anda. Rename menjadi: `Gambar_Pet`.
4. **Menu Tombol:** Tarik 4 buah komponen **Button** ke layar secara berurutan dari atas ke bawah.
   - Button 1 -> Di Properties ubah Text: `Catat Uang`. Di Components Rename: `Menu_CatatUang`.
   - Button 2 -> Ubah Text: `Cek Saldo`. Rename: `Menu_Saldo`.
   - Button 3 -> Ubah Text: `Toko Aksesoris`. Rename: `Menu_Toko`.
   - Button 4 -> Ubah Text: `Mutual Friends`. Rename: `Menu_Teman`.
5. **Alat Tambahan (Wajib):**
   - Dari panel **Palette** > **Storage**, tarik **TinyDB** (Rename di Components: `DB_Kel3`).
   - Dari panel **Palette** > **User Interface**, tarik **Notifier** (Rename di Components: `Notifikasi`).
   - Dari panel **Palette** > klik kategori **Sensors**, tarik komponen **Clock** ke layar HP.
   - Beralih ke panel **Properties**, pastikan **TimerEnabled** dicentang dan ubah **TimerInterval** menjadi `30000` (angka ini adalah milidetik, artinya pengingat akan muncul tiap 30 detik. Anda bisa menggantinya jadi `60000` untuk 1 menit).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Refresh):**
   - Di panel kiri bawah, klik `Logo_Aplikasi`. Tarik blok kuning: `when Logo_Aplikasi.Click do`.
   - Dari kategori **Control**, tarik `open another screen screenName`. Pasangkan teks pink `" "` dan ketik: `HalamanUtama`.
2. **Tampilkan Nama Peliharaan:**
   - Di panel kiri bawah, klik nama Screen `HalamanUtama`. Tarik blok kuning `when HalamanUtama.Initialize do`.
   - Klik komponen `Teks_NamaPet`, tarik blok hijau muda `set Teks_NamaPet.Text to`. Masukkan ke dalam blok kuning.
   - Klik `DB_Kel3`, tarik blok ungu `call DB_Kel3.GetValue`. Pasangkan ke blok set.
   - Isi lubang `tag` dengan teks pink `" "` ketik `"NamaPet"`, dan isi `valueIfTagNotThere` dengan teks pink `"Hewanku"`.
3. **Notifikasi Lupa Menabung (Timer):**
   - Di panel kiri bawah, klik komponen `Clock1`, tarik blok kuning `when Clock1.Timer do`.
   - Klik `Notifikasi`, tarik blok ungu `call Notifikasi.ShowAlert notice`.
   - Isi bagian notice dengan teks pink `" "` dan ketik: `"Ayo berikan makan peliharaanmu dengan cara menabung!"`.
4. **Navigasi Tombol (Ulangi untuk ke-4 tombol):**
   - Klik `Menu_CatatUang`, tarik blok kuning `when Menu_CatatUang.Click do`. Pasangkan blok `open another screen` dan isi teks pink `"CatatUang"`.
   - Lakukan hal yang sama persis untuk `Menu_Saldo` (isi layar `"Saldo"`), `Menu_Toko` (isi layar `"Toko"`), dan `Menu_Teman` (isi layar `"Teman"`).

---

## TAHAP 4: Desain & Blocks - CatatUang

Ganti screen aktif ke **CatatUang** via dropdown. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Ganti screen kembali ke `HalamanUtama`. Di panel **Components**, klik komponen `HorizontalArrangement` (Header). Tekan **Ctrl + C** (Copy).
   - Ganti screen kembali ke `CatatUang`. Tekan **Ctrl + V** (Paste).
2. Dari panel **Palette** > **User Interface**, tarik **TextBox**. (Ubah Hint: `Nominal Pemasukan`, Centang kotak _NumbersOnly_, Rename menjadi: `Input_Masuk`).
3. Tarik komponen **Button**. (Ubah Text: `Simpan Pemasukan`, Rename: `Tombol_Masuk`).
4. Tarik komponen **TextBox** kedua. (Ubah Hint: `Nominal Pengeluaran`, Centang _NumbersOnly_, Rename: `Input_Keluar`).
5. Tarik komponen **Button** kedua. (Ubah Text: `Simpan Pengeluaran`, Rename: `Tombol_Keluar`).
6. Dari kategori **Storage**, tarik **TinyDB** (Rename: `DB_Kel3`). Dari kategori **User Interface**, tarik **Notifier** (Rename: `Pesan`).

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. **Simpan Pemasukan:**
   - Klik `Tombol_Masuk`, tarik blok kuning `when Tombol_Masuk.Click do`.
   - Klik `DB_Kel3`, tarik `call DB_Kel3.StoreValue`. Isi tag dengan teks pink `"TotalMasuk"`.
   - Pada `valueToStore`, tarik blok tambah `+` dari kategori **Math**.
     - Sisi kiri `+`: Ambil `call DB_Kel3.GetValue` isi tag `"TotalMasuk"` dan default `0` (dari Math).
     - Sisi kanan `+`: Klik `Input_Masuk` di panel kiri, tarik blok hijau tua `Input_Masuk.Text`.
   - Klik `Pesan`, tarik `ShowAlert notice` isi teks pink `"Pemasukan berhasil dicatat!"`. Letakkan di bawah StoreValue.
2. **Simpan Pengeluaran:**
   - Klik `Tombol_Keluar`, tarik blok kuning `when Tombol_Keluar.Click do`.
   - Klik `DB_Kel3`, tarik `call DB_Kel3.StoreValue`. Isi tag dengan teks pink `"TotalKeluar"`.
   - Pada `valueToStore`, tarik blok tambah `+` dari kategori **Math**.
     - Sisi kiri `+`: Ambil `call DB_Kel3.GetValue` isi tag `"TotalKeluar"` dan default `0`.
     - Sisi kanan `+`: Klik `Input_Keluar`, tarik blok hijau tua `Input_Keluar.Text`.
   - Tampilkan Notifier `ShowAlert notice` isi teks pink `"Pengeluaran berhasil dicatat!"`.

---

## TAHAP 5: Desain & Blocks - Saldo (Evolusi Pet)

Ganti screen aktif ke **Saldo**. Di sini peliharaan Anda akan berevolusi!

### A. Desain (Designer)

1. **Paste Header Utama:** Tekan **Ctrl + V** (Paste) agar Header muncul di atas.
2. Tarik **Label** ke layar. (Di Properties ubah Text: `Saldo Anda: Rp 0`, Centang _FontBold_, Rename: `Teks_Saldo`).
3. Tarik **Image**. Di panel **Media** (bawah), Upload ketiga gambar pet Anda (misal: bayi.png, remaja.png, dewasa.png). Tapi di panel Properties, biarkan menu _Picture_ kosong. Rename komponennya: `Gambar_Pertumbuhan`.
4. Tarik **Button**. (Ubah Text: `Bebaskan Peliharaanku!`, Rename: `Tombol_Bebaskan`).
5. Jangan lupa tarik **TinyDB** (`DB_Kel3`) dan **Notifier** (`Pesan`).

### B. Kode (Blocks)

Pindah ke **Blocks**.

1. **Menghitung Saldo & Evolusi:**
   - Di panel kiri bawah, klik nama Screen `Saldo`. Tarik blok kuning `when Saldo.Initialize do`.
   - Klik kategori **Variables** (oranye tua), tarik blok `initialize local name to in do` (blok panjang dengan celah _do_).
   - Klik ikon **gir (gear) biru** pada blok variabel tersebut. Tarik blok `name` tambahan dari sisi kiri ke bawah blok `name` di sebelah kanan agar variabelnya jadi ada 2 baris.
   - Ganti tulisan `name` pertama menjadi `UangSaldo`. Pasangkan dengan blok kurang `-` dari kategori **Math**. (Sisi kirinya `GetValue` tag `"TotalMasuk"`, Sisi kanannya `GetValue` tag `"TotalKeluar"`).
   - Ganti tulisan `name` kedua menjadi `TargetUang`. Pasangkan dengan `GetValue` tag `"Target"` (default `0`).
   - **Tampilkan Saldo:** Di dalam celah _do_, klik `Teks_Saldo`, tarik `set Teks_Saldo.Text to`. Gunakan blok `join` dari **Text**. (Atas: `"Saldo Anda: Rp "`. Bawah: arahkan kursor ke tulisan `UangSaldo` lalu tarik blok merah `get UangSaldo`).
   - **Logika Evolusi:** Dari kategori **Control**, tarik blok `if then` ke bawah susunan teks saldo. Klik ikon **gir (gear) biru** pada blok `if`, tarik blok `else if` dan blok `else` secara berurutan ke dalam kerangka sebelah kanan.
   - **Kondisi 1 (Capai Target):** Tarik blok lebih besar sama dengan `>=` dari **Math**. Sisi kiri isi dengan merah `get UangSaldo`, sisi kanan merah `get TargetUang`. Di celah _then_, tarik blok hijau muda `set Gambar_Pertumbuhan.Picture to`, isi dengan teks pink persis seperti nama file Anda, misal `"dewasa.png"`.
   - **Kondisi 2 (Setengah Target):** Di bagian _else if_, tarik blok `>=` lagi. Sisi kirinya `get UangSaldo`. Sisi kanannya gunakan blok bagi `/` dari Math (`get TargetUang` dibagi `2`). Di celah _then_, set _Picture_ ke `"remaja.png"`.
   - **Kondisi Else (Awal):** Di celah _else_, set _Picture_ ke `"bayi.png"`.
2. **Tombol Bebaskan:**
   - Klik `Tombol_Bebaskan`, tarik blok kuning `when Click do`.
   - Tarik blok `if then else` dari **Control**.
   - Jika `get UangSaldo` `>=` `get TargetUang`, maka `open another screen` ke `"BebasPet"`.
   - Jika belum (else), tarik `ShowAlert notice` dari `Pesan` dan isi teks pink `"Target belum tercapai! Terus menabung ya!"`.

---

## TAHAP 6: Toko, Teman & BebasPet

Ketiga screen ini adalah pelengkap ekosistem aplikasi Anda. Ganti Screen melalui menu Dropdown atas.

### 1. Screen Toko

- **A. Desain:** Ganti screen ke **Toko**. Tekan **Ctrl + V** untuk Paste Header.
  - Tarik 2 **Button**. Rename jadi `Beli_Makanan` (Text: `Beli Makanan - Rp 5000`) dan `Beli_Aksesoris` (Text: `Beli Topi - Rp 10000`). Tarik **TinyDB** (`DB_Kel3`) dan **Notifier** (`Pesan`).
- **B. Blocks:** - Tarik blok kuning `when Beli_Makanan.Click do`.
  - Klik `DB_Kel3`, tarik `StoreValue` tag `"TotalKeluar"`. Isinya blok Math `+` (`GetValue` tag `"TotalKeluar"` ditambah angka `5000` dari Math).
  - Tampilkan `ShowAlert notice` isi `"Makanan berhasil dibeli! Peliharaanmu senang!"`. Lakukan logika yang sama untuk tombol aksesoris dengan angka `10000`.

### 2. Screen Teman (Mutual Friends)

- **A. Desain:** Ganti screen ke **Teman**. Tekan **Ctrl + V** untuk Paste Header.
  - Tarik komponen **Label** (Ubah Text: `Daftar Teman Menabung`, centang FontBold).
  - Dari kategori **User Interface**, tarik **ListView**. Di panel **Properties**, cari menu **ElementsFromString**, klik dan ketikkan nama tanpa spasi setelah koma, contoh: `Andi(Level5),Budi(Level3),Siska(Level1)`. (Screen ini hanya prototype visual).

### 3. Screen BebasPet

- **A. Desain:** Ganti screen ke **BebasPet**. Tekan **Ctrl + V** untuk Paste Header.
  - Tarik komponen **Image**, di Properties klik _Picture_ pilih gambar pet bebas/bahagia.
  - Tarik **Label**. Di Properties, ubah Font Size menjadi `20`, centang FontBold, dan ubah Text: `Selamat! Target Tercapai dan Peliharaan Kamu Hidup Bebas & Bahagia!`.
  - Tarik **Button**. Ubah Text menjadi: `Kembali ke Beranda`. Di mode **Blocks**, buat blok kuning `when Click do` untuk tombol ini lalu pasangkan `open another screen` `"HalamanUtama"`.

> **PENTING:** Silakan coba Connect/Run aplikasi secara penuh di HP Anda. Mulai dari membuat karakter, login, hingga mencatat uang masuk agar peliharaannya berevolusi dari bayi menjadi dewasa. Jangan lupa klik **Projects > Save project**!
