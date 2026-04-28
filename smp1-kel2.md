# Tutorial Membuat Aplikasi KELOMPOK 2 (SMP 1 Surakarta)

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

Kita perlu membuat 3 Screen baru sesuai dengan konsep aplikasi pengelolaan tabungan Anda.

1. Di bagian paling atas layar App Inventor, klik tombol **Add Screen**.
2. Akan muncul kotak pop-up. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, klik **Add Screen**, ketik nama: `CatatanMasuk` lalu klik OK.
4. Ulangi langkah 1, klik **Add Screen**, ketik nama: `CatatanKeluar` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas, huruf besar kecilnya sama, dan TANPA SPASI)._

> **PENTING:** Silakan coba Connect/Run program di HP Anda (Pilih menu Connect > AI Companion) untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama** (Cek dropdown nama screen). Kembali ke mode **Designer**. Di sini kita membuat Header dengan Logo, menu utama, dan sistem batas (limit) pengeluaran bulanan.

### A. Desain (Designer)

1. **Membuat Header & Logo (Bisa di-copy ke layar lain nanti):**
   - Dari panel **Palette** > klik kategori **Layout**, tarik **HorizontalArrangement** ke layar HP bagian paling atas.
   - Di panel **Properties**, cari menu **Width**, klik dan pilih `Fill parent`, lalu klik OK.
   - Dari panel **Palette** > klik kategori **User Interface**, tarik komponen **Image** dan masukkan _ke dalam_ kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik komponen gambar tersebut, klik tombol **Rename**, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, scroll ke bawah, cari kotak centang bernama **Clickable** dan **wajib Anda centang** (agar logo bisa ditekan untuk me-refresh halaman).
   - _(Opsional)_ Dari panel Palette **User Interface**, tarik komponen **Label** dan letakkan di dalam kotak di sebelah kanan logo jika ingin memberi teks judul aplikasi.
2. **Info Limit:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Label** ke layar HP di bawah kotak header.
   - Di panel **Properties**, cari kolom **Text** dan ubah menjadi: `Batas Pengeluaran Bulanan: Rp 0`.
   - Di panel **Properties** yang sama, centang kotak **FontBold** agar hurufnya tebal.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Teks_Limit`.
3. **Form Set Limit:**
   - Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke bawah judul Limit tadi.
   - Di panel **Properties**, ubah **Hint** menjadi: `Tentukan Batas (Misal: 50000)`.
   - Centang kotak **NumbersOnly** (agar keyboard berupa angka).
   - Di panel **Components**, Rename menjadi: `Input_Limit`.
   - Tarik komponen **Button** ke bawah TextBox. Di panel **Properties**, ubah **Text** menjadi: `Set Batas`. Di panel **Components**, Rename menjadi: `Tombol_SetLimit`.
4. **Menu Masuk & Keluar:**
   - Tarik komponen **Button** baru ke layar. Ubah **Text** menjadi: `Catat Pemasukan`. Rename menjadi: `Menu_Masuk`.
   - Tarik komponen **Button** lagi ke layar. Ubah **Text** menjadi: `Catat Pengeluaran`. Rename menjadi: `Menu_Keluar`.
5. **Alat Tambahan (Wajib):**
   - Dari panel **Palette** > kategori **Storage**, tarik komponen **TinyDB** ke layar HP. Rename menjadi: `DB_Kel2`.
   - Dari panel **Palette** > kategori **User Interface**, tarik komponen **Notifier** ke layar HP. Rename menjadi: `Peringatan`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Logika Logo (Refresh Halaman Utama):**
   - Di panel kiri bawah, cari dan klik komponen `Logo_Aplikasi`. Tarik blok kuning teratas: `when Logo_Aplikasi.Click do`.
   - Di panel kiri atas, klik kategori **Control**, scroll dan tarik blok `open another screen screenName` ke dalam blok kuning.
   - Klik kategori **Text**, tarik blok teks kosong `" "` paling atas. Pasangkan ke sebelah `screenName`, lalu ketik: `HalamanUtama`.
2. **Navigasi Menu:**
   - Di panel kiri bawah, klik `Menu_Masuk`, tarik blok kuning `when Menu_Masuk.Click do`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`. Ambil blok teks pink `" "` dari kategori **Text** dan ketik: `CatatanMasuk`.
   - Lakukan cara yang **sama persis** untuk `Menu_Keluar` (klik di panel kiri, ambil blok kuning click), lalu arahkan `screenName` ke blok teks pink `" "` berisi: `CatatanKeluar`.
3. **Menampilkan Limit (Saat Layar Dibuka):**
   - Di panel kiri bawah, klik nama Screen `HalamanUtama`. Tarik blok kuning `when HalamanUtama.Initialize do`.
   - Klik komponen `Teks_Limit`, cari dan tarik blok hijau muda `set Teks_Limit.Text to`. Masukkan ke dalam blok kuning.
   - Klik kategori **Text**, tarik blok `join` dan pasangkan.
     - **Lubang atas join:** Pasangkan teks pink `" "` dan ketik `"Batas Pengeluaran Bulanan: Rp "`.
     - **Lubang bawah join:** Klik komponen `DB_Kel2` di panel kiri bawah, tarik blok ungu `call DB_Kel2.GetValue`. Isi lubang `tag` dengan teks pink `" "` ketik `"BatasUang"`, lalu isi `valueIfTagNotThere` dengan blok Math (angka `0`).
4. **Menyimpan Limit Baru:**
   - Di panel kiri bawah, klik `Tombol_SetLimit`, tarik blok kuning `when Tombol_SetLimit.Click do`.
   - Klik `DB_Kel2`, tarik blok ungu `call DB_Kel2.StoreValue` dan masukkan ke blok kuning.
   - Isi lubang `tag` dengan teks pink `" "` dan ketik `"BatasUang"`.
   - Isi `valueToStore` dengan mengklik `Input_Limit` di panel kiri bawah lalu tarik blok hijau tua `Input_Limit.Text`.
   - **Update Layar:** Agar angkanya langsung berubah, klik komponen `Teks_Limit`, tarik lagi blok hijau muda `set Teks_Limit.Text to`. Gunakan blok `join` dan susunan `DB_Kel2.GetValue` yang _persis sama_ dengan langkah 3 di atas, letakkan di bawah susunan blok `StoreValue`.

---

## TAHAP 3: Desain & Blocks - CatatanMasuk

Ganti screen aktif ke **CatatanMasuk** melalui menu dropdown Screen di bagian atas layar. Kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Ganti screen kembali ke `HalamanUtama` sebentar melalui dropdown atas.
   - Di panel **Components**, klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard komputer Anda.
   - Ganti screen kembali ke `CatatanMasuk`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo otomatis terpasang rapi di bagian atas layar.
2. **Input Keterangan:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke bawah header.
   - Di panel **Properties**, ubah **Hint** menjadi: `Keterangan (Contoh: Dikasih Ibu)`.
   - Di panel **Components**, Rename menjadi: `Input_Keterangan`.
3. **Input Nominal:** Tarik **TextBox** kedua ke bawahnya.
   - Di panel **Properties**, centang kotak **NumbersOnly**. Ubah **Hint** menjadi: `Nominal Uang`.
   - Di panel **Components**, Rename menjadi: `Input_Nominal`.
4. **Tombol Simpan:** Dari panel **Palette**, tarik komponen **Button**.
   - Di panel **Properties**, ubah **Text** menjadi: `Simpan Pemasukan`.
   - Di panel **Components**, Rename menjadi: `Tombol_Simpan`.
5. **Alat Tambahan (Wajib):** - Dari panel **Palette** > **Storage**, tarik **TinyDB** ke layar (Rename di panel Components: `DB_Kel2`).
   - Dari panel **Palette** > **User Interface**, tarik **Notifier** ke layar (Rename di panel Components: `Pesan`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Simpan Pemasukan:**
   - Di panel kiri bawah, klik `Tombol_Simpan`, tarik blok kuning `when Tombol_Simpan.Click do`.
   - Klik `DB_Kel2`, tarik blok ungu `call DB_Kel2.StoreValue`. Pasangkan ke blok kuning.
   - Isi `tag` dengan teks pink `" "` dari kategori **Text**, dan ketik: `"TotalMasuk"`.
   - Di lubang `valueToStore`, klik kategori **Math** (warna biru muda), tarik blok tambah `+`.
     - **Sisi kiri blok `+`:** Klik `DB_Kel2`, tarik blok ungu `call DB_Kel2.GetValue`. Isi `tag`-nya dengan teks pink `"TotalMasuk"` dan `valueIfTagNotThere` dengan angka `0` (dari Math).
     - **Sisi kanan blok `+`:** Klik komponen `Input_Nominal` di panel kiri bawah, scroll dan tarik blok hijau tua `Input_Nominal.Text`.
2. **Notifikasi:**
   - Di panel kiri bawah, klik komponen `Pesan`. Tarik blok ungu `call Pesan.ShowAlert notice`. Letakkan tepat di bawah blok `StoreValue` (masih di dalam kuning).
   - Pasangkan teks pink kosong `" "` pada bagian `notice` dan ketik: `"Pemasukan Tersimpan!"`.

---

## TAHAP 4: Desain & Blocks - CatatanKeluar

Ganti screen aktif ke **CatatanKeluar** melalui dropdown di atas. Beralih ke mode **Designer**. Di sini sistem akan mengecek apakah pengeluaran Anda melebihi limit yang sudah dibuat di Halaman Utama.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Pastikan Anda berada di screen `CatatanKeluar`. Tekan tombol **Ctrl + V** (Paste) di keyboard Anda agar Header dan Logo kembali terpasang rapi di bagian paling atas layar.
2. **Input Keterangan:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke bawah header.
   - Di panel **Properties**, ubah **Hint** menjadi: `Keterangan (Contoh: Beli Jajan)`.
   - Di panel **Components**, Rename menjadi: `Input_Keterangan`.
3. **Input Nominal:** Tarik **TextBox** kedua ke bawahnya.
   - Di panel **Properties**, centang kotak **NumbersOnly**. Ubah **Hint** menjadi: `Nominal Pengeluaran`.
   - Di panel **Components**, Rename menjadi: `Input_Nominal`.
4. **Tombol Simpan:** Dari panel **Palette**, tarik komponen **Button**.
   - Di panel **Properties**, ubah **Text** menjadi: `Simpan Pengeluaran`.
   - Di panel **Components**, Rename menjadi: `Tombol_Simpan`.
5. **Alat Tambahan (Wajib):** - Dari **Palette** > **Storage**, tarik **TinyDB** ke layar (Rename di Components: `DB_Kel2`).
   - Dari **Palette** > **User Interface**, tarik **Notifier** ke layar (Rename di Components: `PeringatanLimit`).

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Simpan Pengeluaran:**
   - Di panel kiri bawah, klik `Tombol_Simpan`, tarik blok kuning `when Tombol_Simpan.Click do`.
   - Klik komponen `DB_Kel2`, tarik blok ungu `call DB_Kel2.StoreValue`.
   - Isi lubang `tag` dengan teks pink `" "` lalu ketik: `"TotalKeluar"`.
   - Di lubang `valueToStore`, klik kategori **Math** (biru muda), tarik blok tambah `+`.
     - **Sisi kiri `+`:** Klik `DB_Kel2`, ambil `call DB_Kel2.GetValue`, isi tag dengan teks pink `"TotalKeluar"` (default angka `0`).
     - **Sisi kanan `+`:** Klik `Input_Nominal` di panel kiri bawah, tarik blok hijau tua `Input_Nominal.Text`.
2. **Cek Notifikasi Over-Limit (Boros):**
   - Di panel kiri atas, klik kategori **Control** (oranye), tarik blok `if then` dan letakkan tepat di bawah susunan blok `StoreValue` tadi (masih di dalam blok kuning).
   - **Kondisi (Bagian if):** Dari kategori **Math**, cari dan tarik blok perbandingan matematika (biasanya bentuk aslinya adalah sama dengan `=`). Klik lambang `=` tersebut dan ubah (pilih) menjadi lambang lebih besar `>`.
     - **Sisi kiri `>`:** Klik `DB_Kel2`, tarik blok ungu `call DB_Kel2.GetValue`. Isi tag-nya dengan teks pink `"TotalKeluar"` (default `0`).
     - **Sisi kanan `>`:** Klik `DB_Kel2` lagi, tarik blok ungu `call DB_Kel2.GetValue`. Isi tag-nya dengan teks pink `"BatasUang"` (default `0`).
   - **Peringatan (Bagian then):**
     - Jika Total Pengeluaran lebih besar dari Batas Uang, maka sistem harus menampilkan notifikasi.
     - Klik komponen `PeringatanLimit` di panel kiri bawah, tarik blok ungu `call PeringatanLimit.ShowAlert notice` dan masukkan ke dalam celah `then`.
     - Pasangkan teks pink kosong `" "` dari kategori **Text** pada bagian `notice` lalu ketik: `AWAS! Pengeluaran Anda sudah melebihi batas bulanan!`.

> **PENTING:** Silakan Save project Anda (Menu Projects > Save project). Coba jalankan secara penuh melalui HP (Menu Connect > AI Companion). Mulai dari login, masuk Halaman Utama lalu atur batas uang (misal 50000), lalu masuk ke menu Catat Pengeluaran dan masukkan nominal 60000. Periksa apakah notifikasi peringatan borosnya langsung muncul!
