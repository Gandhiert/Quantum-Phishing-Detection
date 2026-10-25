# 🛡️ Quantum Phishing Detection using QSVM

Ahmad/Tim Kelompok - Departemen Teknologi Informasi, ITS
Tugas Kelompok: Komputasi Kuantum untuk Keamanan Siber (Semester Gasal 2026/2027)

## 📌 Deskripsi Proyek
Proyek ini mengimplementasikan **Quantum Support Vector Machine (QSVM)** untuk mendeteksi website phishing. Kami memanfaatkan mekanika kuantum seperti *superposisi* dan *entanglement* untuk memetakan data fitur klasik ke dalam ruang keadaan kuantum (Hilbert Space) guna menemukan pola klasifikasi yang optimal.

## 📊 Dataset & Fitur
Dataset yang digunakan diambil dari Kaggle berisi karakteristik biner website phishing. 
Untuk efisiensi komputasi pada simulator klasik, kami melakukan *downsampling* menjadi **100 baris sampel** dan memilih **2 fitur utama**:
1. `having_IP`: Apakah URL menggunakan alamat IP sebagai pengganti nama domain.
2. `URL_Length`: Struktur panjang karakter dari URL website.

## ⚙️ Arsitektur Sirkuit Kuantum
- **Jumlah Qubit:** 2 Qubit (merepresentasikan 2 fitur data).
- **Quantum Feature Map:** `ZZFeatureMap` (mengubah data klasik menjadi sudut rotasi status kuantum dengan interaksi linear antar qubit).
- **Quantum Kernel:** `FidelityQuantumKernel` (menghitung matriks kesamaan jarak antar data di ruang dimensi kuantum yang tinggi).
- **Classifier:** `QSVC` (Quantum Support Vector Classifier) dari library `qiskit_machine_learning`.

## 📈 Hasil Eksperimen
Berdasarkan simulasi menggunakan `AerSimulator`, model kuantum berhasil dieksekusi dengan performa sebagai berikut:
- **Akurasi Data Training:** 63.75%
- **Akurasi Data Testing (Deteksi Phishing Baru):** 55.00%

*Keterbatasan akurasi disebabkan oleh restriksi jumlah fitur dan baris data agar proses simulasi sirkuit kuantum pada komputer klasik tidak mengalami memory overflow.*
