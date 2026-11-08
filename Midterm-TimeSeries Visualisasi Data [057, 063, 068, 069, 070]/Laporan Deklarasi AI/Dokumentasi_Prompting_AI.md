# Dokumentasi Prompting AI : Analisis Tren Kasus Harian COVID-19 di Indonesia (2020-2023)

**Midterm Project - CAK4XBB3 Visualisasi Data**

**Anggota kelompok :** 
- Nia Novela Ariandini (2311102057)
- Anisa Yasaroh (2311102063)
- Fitri Kusumaningtyas (2311102068)
- D'sharlendita Febianda Aurelia (2311102069)
- Muhammad Raafi Al Hafiidh (2311102070)

Dokumen ini melengkapi Lembar Deklarasi Penggunaan AI (PDF). Berisi rincian penggunaan AI, kutipan prompt, ringkasan hasil, dan screenshot percakapan. Screenshot dilampirkan sebagai berkas image  (Screenshot_AI_01.jpeg sampai Screenshot_AI_15.jpeg) dan ditampilkan juga pada dokumen ini.

---

## Lembar Deklarasi Penggunaan AI

> "Kami, Nia Novela Ariandini (2311102057); Anisa Yasaroh (2311102063); Fitri Kusumaningtyas (2311102068); D'sharlendita Febianda Aurelia (2311102069); Muhammad Raafi Al Hafiidh (2311102070), menyatakan bahwa kami **menggunakan** alat AI generatif dalam pengerjaan tugas ini. Seluruh interpretasi, insight, dan kesimpulan yang disampaikan merupakan hasil pemahaman kami sendiri."

| No | Nama Tools AI | Bagian yang Dibantu | Bentuk Bantuan / Tujuan Prompt | Tingkat Ketergantungan |
|---|---|---|---|---|
| 1 | ChatGPT | Data preparation (reshaping) | Saran tahapan pengolahan data: mengubah wide format menjadi tanggal sebagai index. (Gambar 1) | Sedang |
| 2 | ChatGPT | Data cleaning (missing value) | Saran penanganan missing value hasil differencing (disertai screenshot output notebook). (Gambar 2) | Rendah |
| 3 | ChatGPT | Statistik deskriptif | Membantu menjelaskan lalu meringkas hasil describe() dari dataset. (Gambar 3) | Sedang |
| 4 | ChatGPT | Line plot (anotasi puncak) | Saran nama anotasi untuk dua puncak pada line plot beserta alasannya (disertai screenshot grafik). (Gambar 4) | Rendah |
| 5 | ChatGPT | Line plot (anomali dan pola mingguan) | Menanyakan penyebab kasus 0 yang diikuti lonjakan dan pola grafik bergerigi berulang mingguan. (Gambar 5) | Sedang |
| 6 | ChatGPT | Area plot | Saran variabel, pengaturan grafik, milestone, dan arah interpretasi area plot. (Gambar 6) | Sedang |
| 7 | ChatGPT | Area plot (interpretasi) | Meminta evaluasi dan masukan perbaikan atas penjelasan area plot yang sudah ditulis sendiri (disertai screenshot grafik). (Gambar 7) | Rendah |
| 8 | ChatGPT | Multiple time series | Saran pemilihan negara, variabel, pengaturan grafik, dan poin analisis multiple time series. (Gambar 8) | Sedang |
| 9 | ChatGPT | Multiple time series (direct labeling) | Kode Python direct labeling, penebalan garis Indonesia, dan pengaturan offset label (disertai screenshot grafik). Kode dijalankan pada notebook kelompok dengan komentar disesuaikan, dan hasil grafik diinterpretasikan sendiri oleh kelompok. (Gambar 9) | Sedang | (Gambar 9) | Tinggi |
| 10 | ChatGPT | Seasonal plot | Kode Python seasonal plot (satu garis per tahun, indeks 100 = rata-rata tahun tersebut). Kode dimodifikasi kelompok: legend diganti label tahun langsung di ujung garis, serta judul dan ketebalan garis disesuaikan. (Gambar 10) | Sedang |
| 11 | | 11 | ChatGPT | Moving average (zoom gelombang) | Kode Python untuk memperbesar gelombang Delta dan Omicron beserta penanda puncak (disertai screenshot grafik). Kode dijalankan pada notebook kelompok, dan hasil grafik diperiksa serta diinterpretasikan sendiri oleh kelompok. (Gambar 11) | Sedang |
| 12 | | 12 | ChatGPT | Moving average (summary window) | Kode Python tabel ringkasan (tanggal puncak, nilai puncak, jumlah NaN, rata-rata perubahan harian). Kode dimodifikasi kelompok: tabel dipisah menjadi dua (Delta dan Omicron) dan jumlah NaN dihitung dari seluruh data Indonesia. (Gambar 12) | Sedang |
| 13 | ChatGPT | Moving average (interpretasi window) | Membantu menjelaskan lalu meringkas hasil tabel summary efek ukuran window (disertai screenshot tabel). (Gambar 13) | Sedang |
| 14 | ChatGPT | Insight (perancangan) | Saran insight yang dapat disusun dan kode ringkasan per gelombang (puncak kasus, puncak kematian, rasio kematian per 100 kasus). (Gambar 14) | Sedang |
| 15 | | 15 | ChatGPT | Penyusunan analisis time series | Penyusunan draf analisis (tren, area plot, perbandingan ASEAN, dst.) beserta saran pengembangan (disertai 12 screenshot grafik dan tabel). Draf dijadikan acuan, lalu disusun ulang dan diringkas kelompok menjadi pembahasan per gambar pada laporan, dengan angka dicocokkan ke output notebook. (Gambar 15) | Sedang |

---

## Dokumentasi per Screenshot

### Gambar 1: Mengubah dataset JHU CSSE dari wide format ke format time series

![Gambar 1](Screenshot_AI_01.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Data preparation (reshaping)
- **Deklarasi untuk apa:** Menanyakan tahapan mengubah dataset JHU CSSE (wide format) agar tanggal menjadi index/baris.
- **Kutipan prompt:**
  > "Saya sedang mengerjakan UTS Visualisasi data time series, dan akan menggunakan dataset berikut ini. Dataset ini kan menggunakan wide format yang dimana setiap baris mewakili negara atau provinsi, sedangkan setiap kolom berisi tanggal dengan jumlah kasus kumulatif. Agar lebih mudah dianalisis sebagai data time series, aku ingin mengubah format tersebut menjadi tanggal ke baris (index). Bagaimana ya tahapan pengolahan data nya?"
- **Hasil / respons AI:** AI memberi lima tahapan: (1) memilih data tingkat negara (baris dengan Province/State kosong), (2) menghapus kolom Province/State, Lat, dan Long, (3) menjadikan Country/Region sebagai index, (4) transpose agar tanggal menjadi baris dan negara menjadi kolom, (5) mengurutkan tanggal secara kronologis. Disarankan memastikan kolom tanggal berformat datetime.
- **Tingkat ketergantungan:** Sedang

### Gambar 2: Penanganan 1 missing value pada Kasus Baru dan Kematian Baru

![Gambar 2](Screenshot_AI_02.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Data cleaning (missing value)
- **Deklarasi untuk apa:** Meminta saran langkah lanjutan setelah ditemukan 1 missing value pada kolom Kasus Baru dan Kematian Baru.
- **Kutipan prompt:**
  > "Saya sedang mengerjakan proyek analisis COVID-19 menggunakan dataset JHU CSSE dari GitHub. Kemudian saat saya melakukan data cleaning, terdapat 1 missing value pada Kasus Baru dan Kematian Baru. Saran kmu bagaimana ya selanjutnya?"
- **Hasil / respons AI:** AI menjelaskan bahwa nilai kosong kemungkinan muncul dari proses differencing pada tanggal pertama. Disarankan: memeriksa posisi missing value, menghapus baris tersebut, memeriksa ulang data, lalu melanjutkan ke pengecekan nilai negatif. AI menegaskan agar missing value tidak langsung diganti 0.
- **Tingkat ketergantungan:** Rendah

### Gambar 3: Penjelasan dan peringkasan hasil describe()

![Gambar 3](Screenshot_AI_03.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Statistik deskriptif
- **Deklarasi untuk apa:** Meminta bantuan menjelaskan hasil describe() dan kemudian meringkasnya.
- **Kutipan prompt:**
  > "bantu jelaskan hasil describe dari dataset JHU CSSE tersebut"
  >
  > "bantu persingkat"
- **Hasil / respons AI:** AI menjelaskan 1.104 observasi pada setiap variabel: rata-rata total kasus 3.344.571 (maksimum 6.738.225), rata-rata total kematian 90.883 (maksimum 160.941), rata-rata kasus baru sekitar 6.103 per hari (maksimum 64.718), dan rata-rata kematian baru sekitar 145 per hari (maksimum 2.069). Kesimpulan: kasus dan kematian berfluktuasi cukup besar selama periode pengamatan.
- **Tingkat ketergantungan:** Sedang

### Gambar 4: Penamaan anotasi dua puncak kasus harian

![Gambar 4](Screenshot_AI_04.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Line plot (anotasi puncak)
- **Deklarasi untuk apa:** Meminta saran nama anotasi untuk dua puncak kasus terbesar pada line plot.
- **Kutipan prompt:**
  > "Pada line plot kasus harian COVID-19 Indonesia, terdapat dua puncak kasus terbesar. Menurut kamu, nama anotasi apa yang paling cocok untuk diberikan pada kedua puncak tersebut? Jelaskan juga secara singkat alasan pemilihan nama anotasinya dan apa yang dimaksud dengan masing-masing gelombang tersebut."
- **Hasil / respons AI:** AI menyarankan label Gelombang Delta (2021, sekitar Juni-Agustus 2021) dan Gelombang Omicron (2022, sekitar Januari-Maret 2022). AI mencatat bahwa Delta dan Omicron adalah nama varian, dan dataset JHU CSSE tidak mencatat varian secara langsung, sehingga penamaan didasarkan pada konteks historis.
- **Tingkat ketergantungan:** Rendah

### Gambar 5: Kasus 0 yang diikuti lonjakan dan garis bergerigi

![Gambar 5](Screenshot_AI_05.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Line plot (anomali dan pola mingguan)
- **Deklarasi untuk apa:** Meminta pendapat tentang anomali kasus 0 pada awal September 2022 dan pola bergerigi pada line plot.
- **Kutipan prompt:**
  > "aku lihat pada grafik line plot, pada september awal tahun 2022 ada yg menyentuh 0 kasus, kemudian langsung ada lonjakan. itu gimana ya? apakah perlu dicari tau penyebab nya?"
  >
  > "bagaimana dengan garis grafik terlihat bergerigi dengan pola yang berulang setiap minggu?"
- **Hasil / respons AI:** AI menyatakan pola tersebut perlu diperiksa dan kemungkinan merupakan anomali pelaporan (keterlambatan atau penggabungan laporan), sehingga nol belum tentu berarti tidak ada penularan; dianjurkan dicek ke data JHU CSSE dan laporan resmi dan dicatat sebagai keterbatasan data. Pola bergerigi kemungkinan weekly reporting pattern, dan dapat diperiksa dengan seasonal plot.
- **Tingkat ketergantungan:** Sedang

### Gambar 6: Saran pengerjaan area plot kematian kumulatif

![Gambar 6](Screenshot_AI_06.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Area plot
- **Deklarasi untuk apa:** Meminta saran pengerjaan area plot setelah line plot.
- **Kutipan prompt:**
  > "Pada penugasan setelah line plot, aku diminta membuat area plot, saran pengerjaan dari kamu bagaimana ya?"
- **Hasil / respons AI:** AI menyarankan area plot kematian kumulatif (total_deaths) dengan sumbu X tanggal dan sumbu Y jumlah kematian kumulatif, warna area transparan, serta milestone 50.000, 100.000, dan 150.000 kematian (dipilih sebagai acuan visual, bukan batas epidemiologis). Interpretasi difokuskan pada periode akumulasi tercepat dan perbedaan kemiringan area.
- **Tingkat ketergantungan:** Sedang

### Gambar 7: Evaluasi penjelasan area plot yang ditulis kelompok

![Gambar 7](Screenshot_AI_07.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Area plot (interpretasi)
- **Deklarasi untuk apa:** Meminta AI mengevaluasi penjelasan area plot yang sudah ditulis kelompok.
- **Kutipan prompt:**
  > "Bantu evaluasi penjelasan diagram tersebut ya, berikut penjelasan ku: Bentuk area yang paling curam itu ada di Juli-Agustus 2021 dengan total kematian naik dari 50 ribu (akhir Mei 2021) ke 100 ribu (awal Agustus 2021) hanya dalam waktu 2 bulan. Sedangkan sebaliknya, untuk naik dari 100 ribu ke 150 ribu dibutuhkan sekitar 7 bulan, padahal gelombang Omicron punya kasus harian lebih tinggi. Setelah Maret 2022 area hampir datar."
- **Hasil / respons AI:** AI menilai penjelasan sudah sesuai pola grafik, lalu memberi catatan bahwa kasus harian yang lebih tinggi pada Omicron tidak selalu berarti kematian kumulatif naik lebih cepat. AI memberi versi redaksi yang diperbaiki dan catatan evaluasi: tanggal milestone sesuai anotasi, istilah "area paling curam" tepat, dan grafik hanya menunjukkan pola akumulasi, bukan penyebab.
- **Tingkat ketergantungan:** Rendah

### Gambar 8: Saran pengerjaan perbandingan Indonesia dan negara ASEAN

![Gambar 8](Screenshot_AI_08.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Multiple time series
- **Deklarasi untuk apa:** Meminta saran pengerjaan visualisasi multiple time series.
- **Kutipan prompt:**
  > "Setelah visualisasi area plot, di penugasan diminta untuk melakukan visualisasi multiple time series. saran pengerjaan dari kmu seperti apa ya baiknya?"
- **Hasil / respons AI:** AI menyarankan Indonesia sebagai fokus dengan empat negara ASEAN pembanding (contoh: Malaysia, Thailand, Singapura, Filipina), variabel total kasus kumulatif, tabel pengaturan grafik (sumbu, warna, direct labeling tanpa legend), poin analisis, dan periode seragam 1 Maret 2020 - 9 Maret 2023. AI mengingatkan bahwa kasus kumulatif dipengaruhi jumlah penduduk dan kapasitas tes.
- **Tingkat ketergantungan:** Sedang

### Gambar 9: Merapikan grafik dengan label nama negara di ujung garis

![Gambar 9](Screenshot_AI_09.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Multiple time series (direct labeling)
- **Deklarasi untuk apa:** Meminta agar grafik lebih menarik dan nyaman dilihat dengan nama negara di ujung garis.
- **Kutipan prompt:**
  > "apakah gambar grafik berikut ini bisa dibuat lebih menarik dan nyaman dilihat? mungkin nama negara nya di letakkan di ujung garis"
- **Hasil / respons AI:** AI memberikan kode direct labeling: legend dihilangkan, nama negara beserta kasus kumulatif terakhir ditampilkan di ujung garis, sumbu Y dalam satuan juta, garis Indonesia dibuat lebih tebal, offset label untuk Malaysia dan Thailand agar tidak bertumpuk, dan plt.xlim untuk ruang label. Disertai tabel penjelasan fungsi tiap bagian kode.
- **Peran kelompok:** Kode dijalankan pada notebook kelompok dengan komentar disesuaikan, dan hasil grafik diinterpretasikan sendiri oleh kelompok.
- **Tingkat ketergantungan:** Sedang

### Gambar 10: Seasonal plot mingguan per tahun

![Gambar 10](Screenshot_AI_10.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Seasonal plot
- **Deklarasi untuk apa:** Meminta cara melihat apakah pola mingguan berulang setiap tahun dengan satu garis mewakili satu tahun.
- **Kutipan prompt:**
  > "Misal aku mau melihat apakah pola tersebut berulang setiap tahun. itu gimana ya caranya? biar lengkap gitu. aku mau melihat pola dengan setiap garis mewakili 1 tahun"
- **Hasil / respons AI:** AI menyarankan Seasonal Plot Mingguan per Tahun dan memberi kode: pengelompokan berdasarkan Tahun dan Hari, rata-rata Kasus Baru, normalisasi agar nilai 100 menjadi rata-rata tahunan, lalu plot satu garis per tahun. Disertai cara membaca grafik (di atas 100 berarti lebih tinggi dari rata-rata tahun tersebut).
- **Peran kelompok:** Kode dimodifikasi kelompok: legend diganti label tahun langsung di ujung garis, serta judul dan ketebalan garis disesuaikan.
- **Tingkat ketergantungan:** Sedang

### Gambar 11: Kode zoom gelombang Delta dan Omicron dengan MA 7 dan MA 30 hari

![Gambar 11](Screenshot_AI_11.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Moving average (zoom gelombang)
- **Deklarasi untuk apa:** Meminta kode Pandas dan Matplotlib untuk zoom in gelombang Delta dan Omicron dengan data asli, MA 7, dan MA 30.
- **Kutipan prompt:**
  > "Bantu saya membuat kode Python untuk memperbesar (zoom in) grafik gelombang COVID-19, khususnya gelombang Delta dan Omicron. Gunakan Pandas dan Matplotlib. Tampilkan kurva data asli dan Moving Average 7 serta 30 hari, lengkap dengan penanda titik puncak jika diperlukan. Sertakan komentar singkat dan penjelasan hasil grafik."
- **Hasil / respons AI:** AI menyarankan dua grafik terpisah dan memberi dua blok kode: zoom Delta (Juni-September 2021) dan zoom Omicron (Januari-Maret 2022), masing-masing menampilkan data asli, MA 7 hari, MA 30 hari, dan garis vertikal penanda puncak tiap kurva.
- **Peran kelompok:** Kode dijalankan pada notebook kelompok, dan hasil grafik diperiksa serta diinterpretasikan sendiri oleh kelompok.
- **Tingkat ketergantungan:** Sedang

### Gambar 12: Kode tabel ringkasan efek ukuran window dan trade-off

![Gambar 12](Screenshot_AI_12.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Moving average (summary window)
- **Deklarasi untuk apa:** Meminta pembuatan summary untuk melihat efek ukuran window dan trade-off-nya.
- **Kutipan prompt:**
  > "sekarang tolong bantu buatkan summary nya untuk melihat Efek Ukuran Window dan Trade-off-nya"
- **Hasil / respons AI:** AI memberi kode tabel ringkasan yang membandingkan tanggal puncak, nilai puncak, jumlah NaN di awal, dan rata-rata perubahan harian untuk data asli, MA 7, dan MA 30 pada gelombang Delta dan Omicron, beserta cara membaca hasilnya dan kesimpulan singkat tentang trade-off ukuran window.
- **Peran kelompok:** Kode dimodifikasi kelompok: tabel dipisah menjadi dua (Delta dan Omicron) dan jumlah NaN dihitung dari seluruh data Indonesia.
- **Tingkat ketergantungan:** Sedang

### Gambar 13: Penjelasan dan peringkasan hasil tabel efek window

![Gambar 13](Screenshot_AI_13.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Moving average (interpretasi window)
- **Deklarasi untuk apa:** Meminta bantuan menjelaskan hasil summary efek ukuran window dan trade-off-nya, kemudian meringkasnya.
- **Kutipan prompt:**
  > "Tolong bantu jelaskan hasil dari summary untuk Efek Ukuran Window dan Trade-off-nya"
  >
  > "persingkat"
- **Hasil / respons AI:** AI menjelaskan tiga hal: kehalusan kurva (rata-rata perubahan harian turun dari 988 pada data asli menjadi 259 pada MA 7 dan 189 pada MA 30), kehilangan data awal (6 NaN pada MA 7 dan 29 NaN pada MA 30), serta perubahan nilai dan posisi puncak (puncak makin rendah dan makin terlambat pada window yang lebih besar). Kesimpulan: MA 7 cocok sebagai kurva tren utama, MA 30 cocok untuk gambaran umum.
- **Tingkat ketergantungan:** Sedang

### Gambar 14: Saran jenis insight dan kode ringkasan per gelombang

![Gambar 14](Screenshot_AI_14.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Insight (perancangan)
- **Deklarasi untuk apa:** Meminta arahan insight apa yang dibutuhkan untuk bagian analisis.
- **Kutipan prompt:**
  > "Aku akan menyusun insight apa ya yg kira2 aku butuhkan?"
- **Hasil / respons AI:** AI menyarankan membandingkan puncak kasus, puncak kematian, dan rasio kematian terhadap kasus pada setiap gelombang, serta memberi kode ringkasan per gelombang. Lima insight yang disarankan: gelombang paling tinggi, puncak kematian, rasio kematian, perbandingan Delta dan Omicron, serta perubahan antarperiode. Disertai catatan cara membaca rasio kematian per 100 kasus.
- **Tingkat ketergantungan:** Sedang

### Gambar 15: Draf analisis time series dari grafik, tabel, dan perhitungan

![Gambar 15](Screenshot_AI_15.jpeg)

- **Tools AI:** ChatGPT
- **Bagian yang dibantu:** Penyusunan analisis time series
- **Deklarasi untuk apa:** Meminta AI menyusun analisis time series berdasarkan hasil grafik, tabel, dan perhitungan yang tersedia, tanpa mengarang angka, serta saran pengembangan.
- **Kutipan prompt:**
  > "Bantu saya menyusun analisis time series COVID-19 berdasarkan hasil grafik, tabel, dan perhitungan yang tersedia. Pastikan setiap pernyataan sesuai data, tidak mengarang angka, serta berikan saran pengembangan analisis."
- **Hasil / respons AI:** AI menghasilkan draf "Analisis Time Series COVID-19 di Indonesia" yang merangkum visualisasi yang digunakan dan membahas tren: gelombang Delta (puncak 15 Juli 2021: 56.757 kasus; MA 7 hari 18 Juli 2021: 50.039; MA 30 hari 6 Agustus 2021: 40.948) dan Omicron (puncak 16 Februari 2022: 64.718; MA 7 hari 20 Februari 2022: 55.675; MA 30 hari 5 Maret 2022: 43.645), selisih puncak 7.961 kasus, area plot kematian kumulatif, dan perbandingan kumulatif lima negara ASEAN, disertai saran pengembangan analisis. (Pada screenshot, respons terlihat sebagian.)
- **Peran kelompok:** Draf dijadikan acuan, lalu disusun ulang dan diringkas kelompok menjadi pembahasan per gambar pada laporan, dengan angka dicocokkan ke output notebook.
- **Tingkat ketergantungan:** Sedang

---

## Catatan Verifikasi

- Respons AI dipakai sebagai bahan bantu (saran langkah, kode, dan masukan redaksi). Interpretasi dan kesimpulan akhir disusun dan diperiksa oleh kelompok.