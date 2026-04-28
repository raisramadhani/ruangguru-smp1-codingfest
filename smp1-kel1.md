# Tutorial Membuat Aplikasi KELOMPOK 1 (SMP 1 Surakarta)

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
4. **Pesan Notifikasi:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Notifier** ke gambar HP. (Catatan: Komponen ini tidak akan terlihat di layar HP, melainkan muncul di bagian bawah layar sebagai _Non-visible components_). Biarkan namanya tetap `Notifier1` di panel Components.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** dengan cara mengklik tombol **Blocks** di pojok kanan atas layar.

1. **Memulai Tombol:** Di panel sebelah kiri bawah (daftar komponen), cari dan klik `Tombol_Masuk`. Akan muncul laci berisi blok, tarik blok kuning paling atas: `when Tombol_Masuk.Click do` ke area putih yang kosong.
2. **Membuat Syarat:** Di panel kiri atas (Built-in), klik kategori **Control** (warna oranye), tarik blok `if then else` ke dalam celah blok kuning tadi.
3. **Mengatur Syarat Login (Bagian if):**
   - Di panel kiri atas, klik kategori **Logic** (hijau terang), tarik blok `and` pasangkan ke sebelah kanan tulisan `if`.
   - **Di lubang kiri `and`:** Klik kategori **Logic** lagi, tarik blok sama dengan `=`.
     - **Sisi kirinya:** Klik komponen `InputUsername` di panel kiri bawah, scroll ke bawah dan cari blok hijau tua `InputUsername.Text`, tarik ke sisi kiri blok `=`.
     - **Sisi kanannya:** Klik kategori **Text** (warna pink), tarik blok kosong `" "` paling atas. Pasangkan ke sisi kanan `=`, lalu klik bagian tengahnya dan ketik `123`.
   - **Di lubang kanan `and`:** Lakukan hal yang sama. Tarik blok `=` dari kategori **Logic**.
     - **Sisi kirinya:** Klik komponen `InputPassword` di panel kiri bawah, cari dan tarik blok hijau tua `InputPassword.Text`.
     - **Sisi kanannya:** Ambil blok teks pink kosong `" "` dari kategori **Text**, pasangkan lalu ketik `123`.
4. **Jika Login Benar (Bagian then):**
   - Di panel kiri bawah, klik komponen `Notifier1`, cari dan tarik blok ungu `call Notifier1.ShowAlert notice`. Pasangkan ke dalam celah `then`.
   - Klik kategori **Text**, ambil blok kosong `" "`, pasangkan ke sebelah `notice`, dan ketik: `Selamat datang kembali!`.
   - Di panel kiri atas, klik kategori **Control**, scroll agak ke bawah dan tarik blok `open another screen screenName` ke bawah blok ungu tadi.
   - Ambil lagi blok teks pink kosong `" "` dari kategori **Text**, pasangkan, dan ketik persis: `HalamanUtama`.
5. **Jika Login Salah (Bagian else):**
   - Lakukan cara yang sama: klik `Notifier1` di panel kiri bawah, tarik blok ungu `call Notifier1.ShowAlert notice` ke dalam celah `else`.
   - Ambil blok teks pink `" "` dari kategori **Text** dan ketik: `Password Salah kak`.

---

## TAHAP 1: Membuat Screen Baru

Sesuai dengan konsep aplikasi Anda, kita hanya membutuhkan 1 Screen tambahan.

1. Di bagian paling atas layar App Inventor, klik tombol **Add Screen**.
2. Akan muncul kotak pop-up. Ketik nama: `HalamanUtama` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas, huruf besar kecilnya sama, dan TANPA SPASI)._

> **PENTING:** Silakan coba Connect/Run program di HP Anda (Pilih menu Connect > AI Companion) untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama** (Cek kotak dropdown di sebelah tombol Add Screen). Pastikan Anda kembali ke mode **Designer**.

Di sini kita membuat Header dengan Logo sebagai identitas aplikasi, dilanjutkan dengan area untuk input data tabungan agar bisa masuk ke Leaderboard peringkat kelas.

### A. Desain (Designer)

1. **Membuat Header & Logo:**
   - Dari panel **Palette** > klik kategori **Layout**, tarik **HorizontalArrangement** ke layar HP bagian paling atas.
   - Di panel **Properties**, cari menu **Width**, klik dan pilih `Fill parent`, lalu klik OK.
   - Dari panel **Palette** > klik kategori **User Interface**, tarik komponen **Image** dan masukkan _ke dalam_ kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik komponen gambar tersebut, klik tombol **Rename**, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, scroll ke bawah, cari kotak centang bernama **Clickable** dan **wajib Anda centang** (agar logo bisa ditekan seperti tombol untuk me-refresh halaman).
   - _(Opsional)_ Dari panel Palette **User Interface**, tarik komponen **Label** dan letakkan di dalam kotak di sebelah kanan logo jika ingin memberi teks judul aplikasi.
2. **Membuat Judul Leaderboard:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Label** ke layar HP tepat di bawah kotak header.
   - Di panel **Properties**, cari kolom **Text** dan ubah menjadi: `Leaderboard Penabung Terbanyak!`.
   - Di panel **Properties** yang sama, centang kotak **FontBold** agar hurufnya tebal.
3. **Input Nama:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke bawah judul.
   - Di panel **Properties**, ubah **Hint** menjadi: `Nama Penabung`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Input_Nama`.
4. **Input Nominal:** Tarik komponen **TextBox** kedua ke bawah Input Nama.
   - Di panel **Properties**, ubah **Hint** menjadi: `Nominal Menabung`.
   - Di panel **Properties**, cari dan centang kotak **NumbersOnly** (agar keyboard yang muncul hanya angka).
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Input_Nominal`.
5. **Tombol Tambah:** Dari panel **Palette** > **User Interface**, tarik komponen **Button** ke layar HP.
   - Di panel **Properties**, ubah **Text** menjadi: `Tambah ke Leaderboard`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Tombol_Tambah`.
6. **Daftar Leaderboard:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **ListView** ke bagian bawah layar HP.
   - Di panel **Properties**, cari menu **Height**, klik dan pilih `Fill parent`, lalu klik OK.
   - Lakukan hal yang sama pada menu **Width**, pilih `Fill parent`, lalu klik OK (agar daftarnya memanjang memenuhi layar bawah).
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Daftar_Leaderboard`.
7. **Alat Tambahan (Wajib):**
   - Dari panel **Palette** > klik kategori **Storage**, tarik komponen **TinyDB** ke layar HP (akan masuk ke bawah layar). Di panel **Components**, Rename menjadi: `DB_Kel1`.
   - Dari panel **Palette** > klik kategori **User Interface**, tarik komponen **Notifier** ke layar HP. Di panel **Components**, Rename menjadi: `Notifikasi`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**. Kita akan menyusun logika logo dan variabel list agar daftar peringkat bisa terus bertambah tanpa menimpa data yang lama.

**Bagian 1: Logika Logo (Refresh Halaman Utama)**

1. Di panel kiri bawah, cari dan klik komponen `Logo_Aplikasi`. Tarik blok kuning teratas: `when Logo_Aplikasi.Click do`.
2. Di panel kiri atas, klik kategori **Control**, scroll ke bawah lalu tarik blok `open another screen screenName` ke dalam blok kuning.
3. Klik kategori **Text**, tarik blok teks kosong `" "` paling atas. Pasangkan ke sebelah `screenName`, lalu ketik: `HalamanUtama`.

**Bagian 2: Menyiapkan Variabel (List Kosong)**

1. Di panel kiri atas, klik kategori **Variables** (warna oranye tua), tarik blok `initialize global name to` ke area putih yang kosong.
2. Klik tulisan `name` pada blok tersebut dan ganti ketik menjadi: `DataPeringkat`.
3. Di panel kiri atas, klik kategori **Lists** (warna biru muda), tarik blok `create empty list` dan pasangkan ke sebelah blok variabel tadi.

**Bagian 3: Menampilkan Data Saat Layar Dibuka**

1. Di panel kiri bawah, klik nama screen `HalamanUtama` (ikon HP paling atas). Tarik blok kuning: `when HalamanUtama.Initialize do`.
2. Klik kategori **Variables**, tarik blok `set to` ke dalam blok kuning. Klik tanda panah kecil (_dropdown_) pada tulisan `to` dan pilih `global DataPeringkat`.
3. Di panel kiri bawah, klik `DB_Kel1`, tarik blok ungu `call DB_Kel1.GetValue`. Pasangkan ke sebelah kanan blok `set` tadi.
   - Isi lubang `tag` dengan blok teks pink `" "` (dari kategori **Text**) dan ketik: `"PapanSkor"`.
   - Isi lubang `valueIfTagNotThere` dengan blok biru muda `create empty list` (dari kategori **Lists**).
4. Di panel kiri bawah, klik komponen `Daftar_Leaderboard`, scroll dan tarik blok hijau muda `set Daftar_Leaderboard.Elements to`. Taruh tepat di bawah blok variabel (masih di dalam celah kuning).
5. Klik kategori **Variables**, ambil blok merah `get`, pasangkan ke blok hijau muda tadi. Klik tanda panah kecilnya dan pilih `global DataPeringkat`.

**Bagian 4: Menyimpan Data Baru ke Leaderboard**

1. Di panel kiri bawah, klik `Tombol_Tambah`, tarik blok kuning `when Tombol_Tambah.Click do`.
2. **Ambil Data Lama:** Klik kategori **Variables**, tarik blok `set to`. Klik tanda panah kecilnya dan pilih `global DataPeringkat`. Pasangkan ke dalam blok kuning.
   - Ambil blok ungu `call DB_Kel1.GetValue` dari komponen `DB_Kel1`. Pasangkan ke blok `set`.
   - Isi `tag`-nya dengan teks pink `" "` dan ketik `"PapanSkor"`. Isi `valueIfTagNotThere` dengan `create empty list` dari kategori **Lists**.
3. **Tambahkan Data Baru:** Klik kategori **Lists**, tarik blok biru muda `add items to list`. Taruh di bawah susunan `set` tadi.
   - Di lubang `list`: klik kategori **Variables**, ambil blok merah `get` dan pilih `global DataPeringkat`.
   - Di lubang `item`: klik kategori **Text**, tarik blok pink `join`.
   - **Menambah Lubang Join:** Klik ikon **gir (gear) biru** kecil pada blok `join` tersebut. Tarik satu blok `string` dari sebelah kiri dan tumpuk ke bawah susunan `string` di sebelah kanan, sehingga sekarang blok `join` memiliki 3 lubang. Klik lagi ikon gir biru untuk menutupnya.
   - **Lubang 1 (Atas):** Klik komponen `Input_Nama` di panel kiri bawah, scroll dan tarik blok hijau tua `Input_Nama.Text`.
   - **Lubang 2 (Tengah):** Tarik blok teks pink kosong `" "`, ketik: `- Rp` (Pastikan Anda memberi spasi sebelum tanda strip dan sesudah huruf p).
   - **Lubang 3 (Bawah):** Klik komponen `Input_Nominal` di panel kiri bawah, scroll dan tarik blok hijau tua `Input_Nominal.Text`.
4. **Simpan ke Database:** Klik komponen `DB_Kel1` di panel kiri bawah, tarik blok ungu `call DB_Kel1.StoreValue` dan taruh di bawah susunan `add items to list`.
   - Isi `tag` dengan teks pink `" "` dan ketik: `"PapanSkor"`.
   - Isi `valueToStore` dengan blok merah `get` (dari kategori Variables) lalu pilih `global DataPeringkat`.
5. **Update Tampilan Layar:** Klik komponen `Daftar_Leaderboard`, tarik blok hijau muda `set Daftar_Leaderboard.Elements to`. Pasangkan dengan blok merah `get` lalu pilih `global DataPeringkat`.
6. **Munculkan Pesan:** Klik komponen `Notifikasi` di panel kiri bawah, tarik blok ungu `call Notifikasi.ShowAlert notice`. Pasangkan blok teks pink kosong `" "` pada bagian `notice` dan ketik: `Data berhasil masuk ke Leaderboard!`.

> **PENTING:** Silakan coba Connect/Run program dari awal sampai akhir di HP Anda. Periksa apakah tombol logo bisa diklik, dan apakah Nama serta Nominal yang Anda ketik berhasil masuk ke daftar Leaderboard secara berurutan. Jangan lupa Save project Anda (Pilih menu bagian atas: Projects > Save project)!
