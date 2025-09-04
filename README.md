# ⚙️ Analisis Regresi GLS (Generalized Least Squares) dengan Python & R

![Python](https://img.shields.io/badge/Python-3.7+-blue.svg)
![R](https://img.shields.io/badge/R-4.0+-purple.svg)
![License](https://img.shields.io/badge/License-MIT-red.svg)
![Affiliation](https://img.shields.io/badge/Affiliation-UNTIRTA-orange.svg)

Repositori ini menyajikan alur kerja komprehensif untuk analisis regresi linier menggunakan metode **Generalized Least Squares (GLS)**. GLS adalah pendekatan yang kuat untuk mengatasi pelanggaran asumsi klasik yang kompleks, khususnya ketika **heteroskedastisitas dan autokorelasi** terjadi secara bersamaan. Proyek ini mendemonstrasikan implementasi paralel di **Python** dan **R** untuk diagnosis dan pemodelan GLS.

## ✨ Fitur Utama

- **🎯 Diagnosis Ganda**: Memulai dengan model OLS untuk mendiagnosis adanya heteroskedastisitas (Uji Breusch-Pagan) dan autokorelasi (Uji Durbin-Watson, plot ACF/PACF).
- **⚙️ Pemodelan GLS Lanjutan**: Menunjukkan dua pendekatan untuk menangani masalah gabungan:
    - **Python**: Proses *Feasible GLS* (FGLS) iteratif yang secara manual men-tuning parameter untuk struktur varians dan korelasi AR(1) hingga konvergen.
    - **R**: Penggunaan fungsi `gls()` dari paket `nlme` yang canggih untuk secara simultan memodelkan heteroskedastisitas (`weights`) dan autokorelasi (`correlation`).
- **📈 Diagnosis Visual Autokorelasi**: Menggunakan plot ACF (Autocorrelation Function) dan PACF (Partial Autocorrelation Function) untuk mengidentifikasi struktur korelasi sisaan, seperti AR(1).
- **🔄 Validasi Ulang Komprehensif**: Melakukan kembali serangkaian uji asumsi pada sisaan model GLS final untuk memastikan semua masalah telah berhasil diatasi.
- **📊 Analisis Komparatif**: Memungkinkan perbandingan metodologi dan hasil antara pendekatan FGLS iteratif di Python dan pendekatan berbasis fungsi di R.

## 🔧 Tumpukan Teknologi (Tech Stack)

- **Bahasa**: `Python 3.7+`, `R 4.0+`
- **Pustaka Python**: `statsmodels`, `pandas`, `numpy`, `scipy`, `matplotlib`, `seaborn`, `openpyxl`
- **Pustaka R**: `nlme`, `lmtest`, `car`, `readxl`, `knitr`, `rmarkdown`
- **Lingkungan**: `Jupyter Notebook / Lab`, `RStudio`

## 🚀 Cara Memulai

### Prasyarat
- **Perangkat Lunak**: Python 3.7+, R 4.0+, Jupyter Notebook/Lab, dan RStudio.
- **File Data**: Pastikan file `data_simulasi_gls.xlsx` berada di dalam direktori proyek Anda.

### Instalasi & Penggunaan

1.  **Unduh Repositori**: *Clone* atau unduh proyek ini ke komputer Anda.

2.  **Untuk Pengguna Python**:
    - Buka terminal atau command prompt, lalu instal paket yang diperlukan:
      ```bash
      pip install pandas openpyxl numpy statsmodels scipy matplotlib seaborn jupyterlab
      ```
    - Jalankan Jupyter Lab/Notebook dan buka file Python (.ipynb).
    - **Penting**: Ubah `file_path` di dalam skrip agar sesuai dengan lokasi file `data_simulasi_gls.xlsx` di komputer Anda.

3.  **Untuk Pengguna R**:
    - Buka RStudio, lalu instal paket yang diperlukan dengan menjalankan perintah berikut di *console*:
      ```r
      install.packages(c("nlme", "lmtest", "car", "readxl", "knitr", "rmarkdown"))
      ```
    - Buka file `.Rmd` atau `.md`.
    - **Penting**: Ubah `file_path` di dalam skrip agar sesuai dengan lokasi file `data_simulasi_gls.xlsx` di komputer Anda.

4.  **Jalankan Analisis**: Eksekusi semua sel (Python) atau *chunks* (R) untuk mereplikasi seluruh alur kerja.

## 📊 Metrik Hasil & Ringkasan Output GLS

Fokus evaluasi model GLS adalah pada kriteria informasi dan signifikansi parameter koreksi. R-squared tidak lagi menjadi metrik utama.

| Metrik           | Deskripsi                                                                 | Contoh Nilai    |
| ---------------- | ------------------------------------------------------------------------- | --------------- |
| `AIC` / `BIC`    | Kriteria informasi untuk perbandingan model (nilai lebih rendah lebih baik). | `1089` / `1102` |
| `Log-Likelihood` | Nilai log-likelihood dari model final, digunakan dalam perhitungan AIC/BIC. | `-539.5`        |
| `Rho / Phi`      | Estimasi parameter autokorelasi AR(1). Nilai signifikan mengkonfirmasi adanya autokorelasi. | `0.63`          |
| `P-value (Uji Asumsi)` | Setelah GLS, p-value dari uji Breusch-Pagan dan Durbin-Watson diharapkan tidak lagi signifikan (> 0.05). | `> 0.05`        |
| `VIF`            | Nilai VIF tidak terpengaruh oleh koreksi sisaan (tetap sama seperti OLS).  | `< 5`           |


## ⚖️ Lisensi & Ketentuan Penggunaan

- **Hak Cipta**: © 2025 Ferdian Bangkit Wijaya - Seluruh Hak Dilindungi.
- **Penggunaan Akademik**: Diizinkan secara bebas untuk keperluan penelitian, tesis, dan pendidikan non-komersial dengan atribusi.
- **Penggunaan Komersial**: Memerlukan izin tertulis dari pengembang.

## 👨‍💻 Author

- **Ferdian Bangkit Wijaya**
- Program Studi Statististika, Fakultas Teknik
- **Universitas Sultan Ageng Tirtayasa (UNTIRTA)**
- Banten, Indonesia 🇮🇩

---

> Proyek ini dirancang sebagai panduan mendalam untuk menangani pelanggaran asumsi yang kompleks, menunjukkan bagaimana GLS dapat menghasilkan estimasi yang lebih efisien dan andal.
