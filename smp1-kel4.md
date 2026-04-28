# Tutorial Membuat Aplikasi KELOMPOK 4 (SMP 1 Surakarta)

Pastikan Anda sudah login ke MIT App Inventor, membuat project baru, dan berada di tampilan **Designer** (perhatikan tombol **Designer** di pojok kanan atas layar harus aktif/menyala).

---

## TAHAP 0: Membuat Halaman Login (Screen1)

Kita akan membuat halaman Login terlebih dahulu di **Screen1** (Screen bawaan saat pertama kali membuat project).

### A. Desain (Designer)

1. **Input Username:** Perhatikan panel **Palette** di sebelah kiri layar. Klik kategori **User Interface**, lalu klik dan tarik (drag) komponen **TextBox** ke gambar HP di tengah layar (Viewer).
   - Beralih ke panel **Properties** di sebelah kanan layar. Cari kolom **Hint**, hapus isinya dan ketik: `Masukkan Username`.
   - Beralih ke panel **Components** (di sebelah kanan gambar HP). Klik tulisan `TextBox1`, lalu klik tombol **Rename** di bawahnya. Ubah namanya menjadi: `InputUsername` lalu klik OK.
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

Sesuai dengan konsep aplikasi Anda, kita perlu membuat 3 Screen baru.

1. Di bagian paling atas layar App Inventor, klik tombol **Add Screen**.
2. Akan muncul kotak pop-up. Ketik nama: `HalamanUtama` lalu klik OK.
3. Ulangi langkah 1, klik **Add Screen**, ketik nama: `ProgressTabungan` lalu klik OK.
4. Ulangi langkah 1, klik **Add Screen**, ketik nama: `InputUang` lalu klik OK.

_(Catatan: Pastikan penulisan nama Screen persis seperti di atas, huruf besar kecilnya sama, dan TANPA SPASI)._

> **PENTING:** Silakan coba Connect/Run program di HP Anda (Pilih menu Connect > AI Companion) untuk memastikan bisa login dengan username "123" dan password "123".

---

## TAHAP 2: Desain & Blocks - HalamanUtama

Pastikan di bagian atas layar App Inventor, Anda sedang berada di Screen **HalamanUtama** (Cek kotak dropdown di sebelah tombol Add Screen). Kita kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Membuat Header & Logo (Bisa di-copy ke layar lain nanti):**
   - Dari panel **Palette** > klik kategori **Layout**, tarik **HorizontalArrangement** ke layar HP bagian paling atas.
   - Di panel **Properties**, cari menu **Width**, klik dan pilih `Fill parent`, lalu klik OK.
   - Dari panel **Palette** > klik kategori **User Interface**, tarik komponen **Image** dan masukkan _ke dalam_ kotak HorizontalArrangement tadi.
   - Di panel **Components**, klik komponen gambar tersebut, klik tombol **Rename**, ubah namanya menjadi: `Logo_Aplikasi`.
   - Di panel **Properties**, scroll ke bawah, cari kotak centang bernama **Clickable** dan **wajib Anda centang** (agar logo bisa ditekan seperti tombol untuk me-refresh halaman).
   - _(Opsional)_ Dari panel Palette **User Interface**, tarik komponen **Label** dan letakkan di dalam kotak di sebelah kanan logo jika ingin memberi teks judul aplikasi.
2. **Membuat Judul:** Dari panel **Palette** > kategori **User Interface**, tarik komponen **Label** ke layar HP, letakkan di bawah kotak header.
   - Di panel **Properties**, cari kotak **Text** dan ubah menjadi: `Daftar Menu Aplikasi Menabung`.
   - Di panel **Properties** yang sama, centang kotak **FontBold** agar hurufnya menjadi tebal.
3. **Menu Input Uang:** Dari panel **Palette** > **User Interface**, tarik komponen **Button** ke bawah teks judul tadi.
   - Di panel **Properties**, ubah **Text** menjadi: `Catat Pemasukan / Pengeluaran`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Menu_Input`.
4. **Menu Progress:** Tarik komponen **Button** kedua ke bawah tombol pertama.
   - Di panel **Properties**, ubah **Text** menjadi: `Cek Progress Tabungan`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Menu_Progress`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks** (pojok kanan atas).

1. **Logika Logo (Refresh Halaman Utama):**
   - Di panel kiri bawah, cari dan klik komponen `Logo_Aplikasi`. Tarik blok kuning teratas: `when Logo_Aplikasi.Click do`.
   - Di panel kiri atas, klik kategori **Control**, scroll ke bawah lalu tarik blok `open another screen screenName` ke dalam blok kuning.
   - Klik kategori **Text**, tarik blok teks kosong `" "` paling atas. Pasangkan ke sebelah `screenName`, lalu klik tengahnya dan ketik: `HalamanUtama`.
2. **Logika Tombol Input:**
   - Di panel kiri bawah, klik `Menu_Input`. Tarik blok kuning `when Menu_Input.Click do`.
   - Dari kategori **Control**, tarik blok `open another screen screenName`.
   - Dari kategori **Text**, ambil blok kosong `" "` dan ketik: `InputUang`.
3. **Logika Tombol Progress:**
   - Lakukan hal yang sama: klik `Menu_Progress` di panel kiri bawah, tarik blok kuning `when Menu_Progress.Click do`.
   - Tarik blok `open another screen screenName` dari kategori **Control**, ambil blok teks kosong `" "` dari kategori **Text**, dan ketik: `ProgressTabungan`.

---

## TAHAP 3: Desain & Blocks - InputUang

Ganti screen aktif ke **InputUang** melalui kotak dropdown Screen di bagian atas layar. Pastikan Anda berada di mode **Designer**. Di sini pengguna akan memasukkan nominal uang.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Ganti screen kembali ke `HalamanUtama` sebentar melalui dropdown atas.
   - Di panel **Components**, klik komponen `HorizontalArrangement` (Header) yang berisi Logo Anda.
   - Tekan tombol **Ctrl + C** (Copy) di keyboard komputer Anda.
   - Ganti screen kembali ke `InputUang`. Tekan tombol **Ctrl + V** (Paste). Header dan Logo otomatis terpasang rapi di bagian atas layar HP.
2. **Input Nominal:** Dari panel **Palette** > **User Interface**, tarik komponen **TextBox** ke layar di bawah header.
   - Di panel **Properties**, cari kolom **Hint** dan ubah menjadi: `Nominal Uang (Contoh: 10000)`.
   - Di panel **Properties**, cari dan centang kotak **NumbersOnly** (agar keyboard yang muncul nanti hanya angka).
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Input_Nominal`.
3. **Tombol Pemasukan:** Dari panel **Palette**, tarik komponen **Button** ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Simpan Sebagai Pemasukan`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Tombol_Masuk`.
4. **Tombol Pengeluaran:** Tarik komponen **Button** satu lagi ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Simpan Sebagai Pengeluaran`.
   - Di panel **Components**, klik **Rename**, ubah menjadi: `Tombol_Keluar`.
5. **Alat Tambahan (Wajib):**
   - Dari panel **Palette**, klik kategori **Storage**, tarik komponen **TinyDB** ke layar HP (Akan masuk ke bawah layar). Di panel **Components**, Rename menjadi: `DB_Kel4`.
   - Dari panel **Palette**, klik kategori **User Interface**, tarik komponen **Notifier** ke layar HP. Di panel **Components**, Rename menjadi: `Pesan`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**.

1. **Menyimpan Pemasukan:**
   - Di panel kiri bawah, klik `Tombol_Masuk`, tarik blok kuning `when Tombol_Masuk.Click do`.
   - Di panel kiri bawah, klik `DB_Kel4`, tarik blok ungu `call DB_Kel4.StoreValue`. Pasangkan ke dalam blok kuning.
   - Di bagian `tag`, pasangkan blok teks pink kosong `" "` dari kategori **Text**, ketik: `"TotalMasuk"`.
   - Di bagian `valueToStore`, klik kategori **Math** (biru muda), cari dan tarik blok tambah `+`.
     - **Sisi kiri blok `+`:** Klik `DB_Kel4` di panel kiri bawah, tarik blok ungu `call DB_Kel4.GetValue`.
       - Isi bagian `tag` dengan teks pink `" "` lalu ketik `"TotalMasuk"`.
       - Isi bagian `valueIfTagNotThere` dengan mengklik kategori **Math**, ambil blok angka `0` paling atas.
     - **Sisi kanan blok `+`:** Klik komponen `Input_Nominal` di panel kiri bawah, scroll ke bawah, tarik blok hijau tua `Input_Nominal.Text`.
   - Di panel kiri bawah, klik `Pesan`, tarik blok ungu `call Pesan.ShowAlert notice` dan taruh di bawah blok TinyDB tadi. Isi bagian `notice` dengan teks pink `" "` dan ketik: `"Pemasukan Berhasil Disimpan!"`.
2. **Menyimpan Pengeluaran:**
   - Lakukan hal yang **sama persis** dengan logika di atas, namun diawali dengan mengklik `Tombol_Keluar` lalu pilih blok kuning `when Tombol_Keluar.Click do`.
   - Ubah tulisan teks pink pada tag di `StoreValue` dan `GetValue` menjadi: `"TotalKeluar"`.
   - Ubah tulisan teks pink pada pesan Notifier menjadi: `"Pengeluaran Berhasil Dicatat!"`.

---

## TAHAP 4: Desain & Blocks - ProgressTabungan

Ganti screen aktif ke **ProgressTabungan** melalui dropdown di atas. Beralih kembali ke mode **Designer**.

### A. Desain (Designer)

1. **Paste Header Utama:**
   - Tekan tombol **Ctrl + V** (Paste) di keyboard Anda agar Header dan Logo kembali terpasang rapi di bagian paling atas layar.
2. **Input Target:** Dari **Palette** > **User Interface**, tarik **TextBox** ke bawah header.
   - Di panel **Properties**, ubah **Hint** menjadi: `Tentukan Target Tabunganmu`.
   - Centang kotak **NumbersOnly**.
   - Di panel **Components**, Rename menjadi: `Input_Target`.
3. **Tombol Set Target:** Tarik **Button** ke bawahnya.
   - Di panel **Properties**, ubah **Text** menjadi: `Set Target`.
   - Di panel **Components**, Rename menjadi: `Tombol_SetTarget`.
4. **Info Saldo:** Tarik **Label** ke layar.
   - Di panel **Properties**, ubah **Text** menjadi: `Saldo Saat Ini: Rp 0`. Centang kotak **FontBold**.
   - Di panel **Components**, Rename menjadi: `Teks_Saldo`.
5. **Info Progress (Status):** Tarik **Label** ke bawah saldo.
   - Di panel **Properties**, ubah **Text** menjadi: `Kekurangan: Rp 0`.
   - Di panel **Properties**, cari menu **TextColor**, klik dan pilih `Red` (Merah).
   - Di panel **Components**, Rename menjadi: `Teks_Status`.
6. **Database:** Dari **Palette** > **Storage**, tarik **TinyDB** ke layar HP. Di panel **Components**, Rename menjadi: `DB_Kel4`.

### B. Kode (Blocks)

Pindah ke tampilan **Blocks**. Kita butuh sedikit matematika di sini.

1. **Menyimpan Target yang Diinput:**
   - Di panel kiri bawah, klik `Tombol_SetTarget`, tarik blok kuning `when Tombol_SetTarget.Click do`.
   - Klik `DB_Kel4`, tarik blok ungu `call DB_Kel4.StoreValue`.
   - Pasangkan teks pink `" "` pada `tag` dan ketik `"TargetUang"`.
   - Pasangkan blok hijau tua `Input_Target.Text` (didapat dengan mengklik komponen `Input_Target`) pada bagian `valueToStore`.
2. **Menghitung Progress dan Saldo (Saat Layar Dibuka):**
   - Di panel kiri bawah, klik komponen Screen `ProgressTabungan`. Tarik blok kuning `when ProgressTabungan.Initialize do`.
   - Klik kategori **Variables** (warna oranye tua), tarik blok bernama `initialize local name to in do` (bentuknya agak panjang dengan celah "do").
   - Klik tulisan `name` yang ada di blok tersebut dan ketik ganti menjadi `Saldo`.
   - Klik kategori **Math**, tarik blok kurang `-` pasangkan ke sebelah `Saldo`.
     - **Sisi kiri `-`:** Klik `DB_Kel4`, ambil `call DB_Kel4.GetValue`, isi tag dengan teks pink `"TotalMasuk"`.
     - **Sisi kanan `-`:** Klik `DB_Kel4`, ambil `call DB_Kel4.GetValue`, isi tag dengan teks pink `"TotalKeluar"`.
   - **Menambah Variabel Baru:** Klik ikon **gir (gear) biru** di sudut kiri atas blok variabel oranye tersebut. Akan muncul balon pop-up kecil. Tarik blok `name` dari sisi kiri ke bawah blok `name` yang ada di sisi kanan. Nanti akan muncul baris variabel baru di blok utama. Klik lagi ikon gir biru untuk menutupnya.
   - Ganti tulisan `name` yang baru muncul menjadi `Target`. Pasangkan dengan `call DB_Kel4.GetValue` dari `DB_Kel4` (isi tag dengan teks pink `"TargetUang"`, dan `valueIfTagNotThere` dengan angka `0`).
3. **Memperbarui Teks di Layar (Di dalam celah "do" blok variabel):**
   - Klik komponen `Teks_Saldo` di panel kiri bawah, cari dan tarik blok hijau tua `set Teks_Saldo.Text to`. Masukkan ke dalam celah `do`.
   - Klik kategori **Text**, tarik blok `join` pasangkan ke blok tadi.
     - **Lubang atas `join`:** Pasang teks pink `" "` dan ketik `"Saldo: Rp "`.
     - **Lubang bawah `join`:** Arahkan kursor mouse Anda (jangan diklik, cukup diamkan di atasnya) ke tulisan `Saldo` pada blok variabel lokal oranye. Akan muncul menu kecil, tarik blok merah `get Saldo` dan pasangkan.
   - Dari kategori **Control**, tarik blok `if then else` dan letakkan tepat di bawah blok `set Teks_Saldo` tadi.
   - **Kondisi (Bagian if):** Dari kategori **Math**, tarik blok matematika. Klik tanda panahnya dan ubah menjadi lambang lebih besar atau sama dengan `>=`.
     - Sisi kirinya: Hover (arahkan kursor) ke tulisan `Saldo`, tarik blok merah `get Saldo`.
     - Sisi kanannya: Hover ke tulisan `Target`, tarik blok merah `get Target`.
   - **Jika Tercapai (Bagian then):**
     - Klik komponen `Teks_Status`, tarik blok `set Teks_Status.Text to`. Pasangkan teks pink `" "` dan ketik: `"SELAMAT! Target Tabungan Tercapai!"`.
     - Klik lagi `Teks_Status`, tarik blok `set Teks_Status.TextColor to`. Klik kategori **Colors** (panel kiri atas), tarik kotak warna **Hijau** dan pasangkan.
   - **Jika Belum Tercapai (Bagian else):**
     - Klik komponen `Teks_Status`, tarik blok `set Teks_Status.Text to`. Ambil blok `join` dari kategori **Text**.
       - Atas: Pasang teks pink `" "` dan ketik `"Kekurangan: Rp "`.
       - Bawah: Ambil blok Math kurang `-`. Sisi kirinya isi dengan blok merah `get Target`, sisi kanannya isi dengan blok merah `get Saldo`.
     - Klik komponen `Teks_Status`, tarik blok `set Teks_Status.TextColor to`. Klik kategori **Colors**, tarik kotak warna **Merah** dan pasangkan.

> **PENTING:** Silakan coba Connect/Run program secara penuh di HP Anda. Masukkan uang pemasukan di menu Input, lalu masuk ke menu Progress dan tentukan target. Pastikan tulisan status kurang/tercapai dan warnanya berubah secara otomatis! Jangan lupa untuk Save project Anda di menu bagian atas (Projects > Save project).
