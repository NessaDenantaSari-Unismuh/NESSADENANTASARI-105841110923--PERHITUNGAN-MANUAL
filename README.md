# NESSADENANTASARI-105841110923--PERHITUNGAN-MANUAL


# Klasifikasi Tingkat Kemiskinan di Indonesia Menggunakan Machine Learning

## Deskripsi Proyek
Proyek ini bertujuan untuk melakukan klasifikasi tingkat kemiskinan di Indonesia menggunakan algoritma Machine Learning.  
Dataset yang digunakan berisi data indikator sosial ekonomi yang digunakan untuk memprediksi kategori tingkat kemiskinan suatu wilayah.

## Tujuan
- Menganalisis data kemiskinan di Indonesia
- Membangun model klasifikasi menggunakan algoritma Machine Learning
- Mengukur performa model menggunakan metrik evaluasi
- Menyediakan sistem prediksi tingkat kemiskinan berbasis data

## Dataset
Dataset yang digunakan:  
**Klasifikasi Tingkat Kemiskinan di Indonesia.csv**

### Fitur Dataset
Contoh fitur yang digunakan:
- Persentase Penduduk Miskin
- Tingkat Pengangguran
- Rata-rata Lama Sekolah
- Pengeluaran Per Kapita
- Indeks Pembangunan Manusia (IPM)
- Tingkat Kemiskinan (Label/Target)

### Contoh Data
```
Wilayah,Persentase_Miskin,Pengangguran,Lama_Sekolah,Pengeluaran_Per_Kapita,IPM,Tingkat_Kemiskinan
Aceh,15.2,6.5,8.1,9500000,71.2,Tinggi
Jawa Barat,7.4,7.2,9.5,12000000,72.5,Sedang
Bali,4.5,3.1,10.2,15000000,75.8,Rendah
```

## Metodologi

### Tahapan Machine Learning
1. Pengumpulan Data
2. Preprocessing Data
3. Seleksi Fitur
4. Pembagian Data (Training dan Testing)
5. Pembangunan Model Machine Learning
6. Evaluasi Model
7. Prediksi Tingkat Kemiskinan

### Algoritma yang Digunakan
- Decision Tree Classifier

## Implementasi Program (Python)

```python
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score, confusion_matrix, classification_report

# Load dataset
data = pd.read_csv("Klasifikasi Tingkat Kemiskinan di Indonesia.csv")

# Encoding label target
data['Tingkat_Kemiskinan'] = data['Tingkat_Kemiskinan'].map({
    'Rendah': 0,
    'Sedang': 1,
    'Tinggi': 2
})

# Fitur dan target
X = data.drop(columns=['Tingkat_Kemiskinan'])
y = data['Tingkat_Kemiskinan']

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Model Decision Tree
model = DecisionTreeClassifier(criterion="entropy", max_depth=4, random_state=42)
model.fit(X_train, y_train)

# Prediksi
y_pred = model.predict(X_test)

# Evaluasi
accuracy = accuracy_score(y_test, y_pred)
print("Akurasi Model:", accuracy)
print("Confusion Matrix:")
print(confusion_matrix(y_test, y_pred))
print("Classification Report:")
print(classification_report(y_test, y_pred))
```

## Hasil
Model Machine Learning mampu mengklasifikasikan tingkat kemiskinan dengan akurasi yang cukup baik.  
Hasil evaluasi menunjukkan bahwa algoritma Decision Tree dapat digunakan untuk analisis tingkat kemiskinan di Indonesia.

## Struktur Folder Proyek
```
project/
│── Klasifikasi Tingkat Kemiskinan di Indonesia.csv
│── model_decision_tree.py
│── README.md
```

## Kesimpulan
- Machine Learning dapat digunakan untuk analisis tingkat kemiskinan.
- Algoritma Decision Tree efektif untuk klasifikasi data sosial ekonomi.
- Model dapat dikembangkan dengan dataset yang lebih besar dan algoritma lain.

## Pengembangan Selanjutnya
- Menambahkan algoritma lain (KNN, SVM, Naive Bayes)
- Visualisasi data dan model
- Optimasi parameter model

---
Dibuat untuk proyek Machine Learning dan analisis data.
