# 🧠 Depression Detection with 1D-CNN

Deteksi depresi menggunakan sinyal suara melalui model **Convolutional Neural Network (1D-CNN)**. Proyek ini bertujuan untuk mengidentifikasi tanda-tanda depresi dari rekaman suara berbasis dataset DAIC-WOZ, menggunakan teknik deep learning untuk klasifikasi biner (depresi / tidak depresi).

---

## 📘 Ringkasan

Model dikembangkan untuk membantu skrining awal gejala depresi menggunakan fitur-fitur akustik dari audio rekaman. Dataset yang digunakan adalah **DAIC-WOZ**, dan sistem dibangun dengan pipeline: preprocessing audio → ekstraksi fitur → pelatihan 1D-CNN → evaluasi model.

---

## 🔧 Fitur

- Ekstraksi fitur audio (MFCC, pitch, energy)
- Pelatihan dan evaluasi model 1D-CNN
- Pemetaan label berdasarkan skor PHQ-8
- Script inference untuk prediksi audio baru
- Visualisasi hasil (jika tersedia)

---

## 🗃️ Dataset

Dataset yang digunakan adalah **DAIC-WOZ**, yang berisi sesi wawancara antara avatar otomatis dan peserta manusia. Label depresi diambil berdasarkan skor PHQ-8.

> ⚠️ Dataset ini tidak dibagikan dalam repositori karena hak akses dibatasi. Silakan unduh dari situs resminya: [DAIC-WOZ Dataset](https://dcapswoz.ict.usc.edu/)

---

## ⚙️ Instalasi

1. Clone repositori:

```bash
git clone https://github.com/baniadamtampubolon/depression-detection-cnn1d.git
cd depression-detection-cnn1d
```

2. Buat environment dan install dependensi:
```bash
python -m venv venv
source venv/bin/activate   # atau venv\Scripts\activate untuk Windows
pip install -r requirements.txt
```

## 📁 Struktur Direktori
``` bash
depression-detection-cnn1d/
├── data/
│   ├── raw/              # Dataset mentah (audio asli)
│   └── features/         # Fitur hasil ekstraksi (MFCC dsb)
├── models/               # Model yang telah dilatih
├── notebooks/            # Jupyter Notebook eksplorasi
├── preprocess.py         # Ekstraksi fitur audio
├── train.py              # Pelatihan model
├── predict.py            # Prediksi dari audio baru
├── config.json           # Konfigurasi pelatihan
├── requirements.txt      # Daftar dependensi
└── README.md             # Dokumentasi proyek
```

## 🛠️ Langkah Praproses
Jalankan perintah berikut untuk ekstraksi fitur:

```bash
python preprocess.py --input_dir data/raw --output_dir data/features
Output akan berupa file .npy atau .h5 berisi MFCC dan fitur lainnya.
```

## 🎯 Melatih Model
Gunakan perintah berikut untuk melatih model CNN:

```bash
python train.py --data_dir data/features --epochs 50 --batch_size 32
Model hasil pelatihan akan disimpan di folder models/.
```
