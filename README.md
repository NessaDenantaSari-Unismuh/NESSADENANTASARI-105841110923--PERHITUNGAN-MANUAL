# NESSADENANTASARI-105841110923--PERHITUNGAN-MANUAL


# Klasifikasi Tingkat Kemiskinan di Indonesia Menggunakan Algoritma K-Means

## Deskripsi Proyek
Proyek ini bertujuan untuk mengelompokkan (clustering) tingkat kemiskinan di Indonesia menggunakan algoritma **K-Means**.  
Algoritma K-Means digunakan untuk mengelompokkan wilayah berdasarkan indikator sosial ekonomi sehingga diperoleh kategori tingkat kemiskinan seperti rendah, sedang, dan tinggi.

## Tujuan
- Mengelompokkan wilayah di Indonesia berdasarkan tingkat kemiskinan
- Menganalisis pola kemiskinan menggunakan Machine Learning
- Menentukan cluster wilayah dengan karakteristik sosial ekonomi yang serupa

## Dataset
Dataset yang digunakan:  
**Klasifikasi Tingkat Kemiskinan di Indonesia.csv**

### Fitur Dataset
Beberapa fitur yang digunakan:
- Persentase Penduduk Miskin
- Tingkat Pengangguran
- Rata-rata Lama Sekolah
- Pengeluaran Per Kapita
- Indeks Pembangunan Manusia (IPM)

### Contoh Data
```
Wilayah,Persentase_Miskin,Pengangguran,Lama_Sekolah,Pengeluaran_Per_Kapita,IPM
Aceh,15.2,6.5,8.1,9500000,71.2
Jawa Barat,7.4,7.2,9.5,12000000,72.5
Bali,4.5,3.1,10.2,15000000,75.8
```

## Metodologi

### Tahapan K-Means Clustering
1. Pengumpulan Data
2. Preprocessing Data (normalisasi, seleksi fitur)
3. Menentukan jumlah cluster (K)
4. Proses clustering menggunakan K-Means
5. Evaluasi hasil clustering
6. Interpretasi cluster

### Algoritma yang Digunakan
- K-Means Clustering

## Implementasi Program (Python)

```python
import pandas as pd
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler
import matplotlib.pyplot as plt

# Load dataset
data = pd.read_csv("Klasifikasi Tingkat Kemiskinan di Indonesia.csv")

# Menghapus kolom non-numerik (misalnya Wilayah)
X = data.drop(columns=['Wilayah'])

# Normalisasi data
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)

# Menentukan jumlah cluster (K)
k = 3
kmeans = KMeans(n_clusters=k, random_state=42)
clusters = kmeans.fit_predict(X_scaled)

# Menambahkan hasil cluster ke dataset
data['Cluster'] = clusters

print(data.head())

# Visualisasi hasil clustering (contoh 2 fitur)
plt.scatter(X_scaled[:, 0], X_scaled[:, 1], c=clusters, cmap='viridis')
plt.title("Hasil Clustering K-Means")
plt.xlabel("Fitur 1")
plt.ylabel("Fitur 2")
plt.show()
```

## Hasil
Algoritma K-Means berhasil mengelompokkan wilayah di Indonesia ke dalam 3 cluster:
- Cluster 0 : Tingkat kemiskinan rendah
- Cluster 1 : Tingkat kemiskinan sedang
- Cluster 2 : Tingkat kemiskinan tinggi

Hasil clustering menunjukkan bahwa wilayah dengan karakteristik sosial ekonomi yang mirip berada dalam cluster yang sama.

## Struktur Folder Proyek
```
project/
│── Klasifikasi Tingkat Kemiskinan di Indonesia.csv
│── kmeans_clustering.py
│── README.md
```

## Kesimpulan
- Algoritma K-Means efektif digunakan untuk mengelompokkan tingkat kemiskinan di Indonesia.
- Clustering membantu memahami pola kemiskinan berdasarkan indikator sosial ekonomi.
- Model dapat dikembangkan dengan jumlah cluster yang berbeda dan fitur tambahan.

## Pengembangan Selanjutnya
- Menentukan jumlah cluster optimal menggunakan metode Elbow atau Silhouette Score
- Visualisasi cluster menggunakan PCA
- Perbandingan dengan algoritma clustering lain

---
Dibuat untuk proyek Machine Learning menggunakan algoritma K-Means.

