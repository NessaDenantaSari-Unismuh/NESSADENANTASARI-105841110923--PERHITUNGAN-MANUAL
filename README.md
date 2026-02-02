# NESSADENANTASARI-105841110923--PERHITUNGAN-MANUAL


# Klasifikasi Tingkat Kemiskinan di Indonesia Menggunakan Algoritma K-Means

## Deskripsi Proyek
Proyek ini bertujuan untuk mengelompokkan (clustering) tingkat kemiskinan di Indonesia menggunakan algoritma **K-Means**.  
Algoritma K-Means digunakan untuk mengelompokkan wilayah berdasarkan indikator sosial ekonomi sehingga diperoleh kategori tingkat kemiskinan seperti rendah, sedang, dan tinggi.

## Tujuan
- Mengelompokkan wilayah di Indonesia berdasarkan tingkat kemiskinan
- Menganalisis pola kemiskinan menggunakan Machine Learning
- Menentukan cluster wilayah dengan karakteristik sosial ekonomi yang serupa


### Algoritma yang Digunakan
- K-Means Clustering

## 🚀 Performa Model
Berdasarkan hasil analisis pada Jupyter Notebook:
- **Akurasi Model:** `96.30%`
- **Metode:** K-Means Clustering dengan Normalisasi Z-Score.
- **Tools:** Python (Pandas, Scikit-Learn), Excel (Manual Validation).

## 📊 Variabel Penelitian
Dataset ini menggunakan 11 indikator kunci untuk menentukan klaster kemiskinan:
1.  **P0**: Persentase Penduduk Miskin.
2.  **Pendidikan**: Rata-rata Lama Sekolah (RLS) penduduk 15+ tahun.
3.  **Kesehatan**: Umur Harapan Hidup (UHH).
4.  **Ekonomi**: Pengeluaran per Kapita, PDRB Harga Konstan, TPT (Pengangguran), dan TPAK (Partisipasi Kerja).
5.  **Infrastruktur**: Akses Sanitasi Layak dan Akses Air Minum Layak.
6.  **Kualitas Hidup**: Indeks Pembangunan Manusia (IPM).

## 🛠️ Tahapan Analisis
Proyek ini mendokumentasikan proses dari data mentah hingga hasil akhir:

### 1. Pre-processing Data
* **Cleaning:** Penghapusan baris kosong (485 baris data tidak relevan dibersihkan).
* **Formatting:** Mengubah tipe data numerik dari format string/koma ke format float.
* **Normalisasi:** Transformasi data menggunakan Z-Score agar variabel dengan satuan berbeda (misal: Rupiah vs Persentase) memiliki bobot yang seimbang.

### 2. Perhitungan K-Means (Manual & Sistem)
Proses klasterisasi divalidasi melalui 6 tahapan iterasi (seperti yang terlihat pada `PERHITUNGAN MANUAL.xlsx`):
* **Iterasi 1-6:** Pembaruan centroid secara terus-menerus hingga posisi klaster stabil (konvergen).
* **Euclidean Distance:** Penentuan klaster wilayah berdasarkan jarak terdekat ke Centroid 1 (Kemiskinan Rendah) atau Centroid 2 (Kemiskinan Tinggi).

### 3. Evaluasi
Hasil prediksi dibandingkan dengan label asli untuk mendapatkan skor akurasi akhir sebesar **0.9630**.

## 📁 Struktur File
- `fix.ipynb`: Script Python lengkap untuk pemrosesan data.
- `Data_kemiskinan_Rapi.csv`: Dataset utama.
- `PERHITUNGAN MANUAL (Sheet 1-6)`: Bukti matematis langkah-langkah algoritma K-Means.

## 📝 Kesimpulan
Hasil penelitian menunjukkan bahwa model K-Means sangat efektif dalam mengelompokkan wilayah miskin di Indonesia. Wilayah dengan IPM rendah dan akses infrastruktur yang minim secara konsisten masuk ke dalam klaster kemiskinan tinggi, yang sejalan dengan data aktual di lapangan.

---
*Dibuat untuk tujuan analisis data dan pemetaan kesejahteraan sosial di Indonesia.*
