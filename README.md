# Analisis Tren Kasus Harian COVID-19 di Indonesia (2020–2023)

**Midterm Project – Visualisasi Data | Kelompok 4**

## Anggota Kelompok
1. Nia Novela Ariandini (2311102057)
2. Anisa Yasaroh (2311102063)
3. Fitri Kusumaningtyas (2311102068)
4. D'sharlendita Febianda Aurelia (2311102069)
5. Muhammad Raafi Al Hafiidh (2311102070)

> Proyek ini menganalisis perkembangan kasus harian dan kematian akibat COVID-19 di Indonesia pada periode 1 Maret 2020–9 Maret 2023 menggunakan pendekatan *time series* berdasarkan dataset Johns Hopkins University CSSE.

## Isi Notebook

Notebook `UTS.ipynb` mencakup pengolahan data, visualisasi, dan analisis tren sebagai berikut:

- **Visualisasi 1 – Line Plot:** Menampilkan jumlah kasus baru harian COVID-19 di Indonesia untuk mengamati tren dan puncak gelombang pandemi.
- **Visualisasi 2 – Area Plot:** Menggambarkan perkembangan jumlah kematian kumulatif COVID-19 di Indonesia.
- **Visualisasi 3 – Multiple Time Series:** Membandingkan jumlah kasus kumulatif Indonesia dengan Malaysia, Filipina, Thailand, dan Vietnam.
- **Visualisasi 4 – Calendar Heatmap dan Seasonal Plot:** Menampilkan distribusi kasus baru per bulan serta pola pelaporan kasus berdasarkan hari dalam seminggu.
- **Analisis Tren – Moving Average dan Exponential Fit:** Menghaluskan fluktuasi kasus menggunakan MA 7 hari dan MA 30 hari, serta membandingkan laju pertumbuhan kasus pada gelombang Delta dan Omicron.

## Sumber Data

- **Nama dataset:** COVID-19 Data Repository – Johns Hopkins University Center for Systems Science and Engineering (JHU CSSE).
- **File dataset:** `time_series_covid19_confirmed_global.csv` dan `time_series_covid19_deaths_global.csv`.
- **URL sumber:** [GitHub – CSSE COVID-19 Data](https://github.com/CSSEGISandData/COVID-19).
- **Cakupan analisis:** Indonesia, Malaysia, Filipina, Thailand, dan Vietnam.
- **Periode dan jumlah observasi:** 1 Maret 2020–9 Maret 2023, sebanyak 1.104 observasi harian untuk Indonesia.

## Cara Menjalankan

**1. Instal library yang dibutuhkan**

```bash
pip install pandas numpy matplotlib seaborn jupyter
```

**2. Jalankan Jupyter Notebook**

```bash
jupyter notebook UTS.ipynb
```

**3. Jalankan notebook**

Buka file `UTS.ipynb`, kemudian jalankan seluruh cell secara berurutan menggunakan opsi **Run All**. Koneksi internet diperlukan untuk mengambil dataset dari repository JHU CSSE.

## Link Presentasi dan Notebook

- **Link Presentasi:** [Lihat Presentasi Midterm Project](https://drive.google.com/file/d/1AlbUoi7bByZWHK1ekGYaVe_P8Fb0KlwF/view?usp=sharing)
- **Link Google Colab:** [Buka Notebook di Google Colab](https://colab.research.google.com/drive/1MgnWiuwnmM1JnY5bHAhxj73DRcUtVjYb?usp=sharing)
