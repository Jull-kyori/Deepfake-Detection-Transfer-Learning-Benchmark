# Komparasi Arsitektur CNN Pratelatih Berbasis Transfer Learning untuk Deteksi Deepfake Wajah

[![Paper](https://img.shields.io/badge/Paper-SINTA--3-blue.svg)]()
[![Python](https://img.shields.io/badge/Python-3.8+-green.svg)](https://www.python.org/)
[![TensorFlow/Keras](https://img.shields.io/badge/Framework-TensorFlow%2FKeras-orange.svg)](https://www.tensorflow.org/)
[![License](https://img.shields.io/badge/License-MIT-brightgreen.svg)](LICENSE)

Repositori ini berisi kode sumber eksperimen, notebook, dan naskah penelitian mengenai analisis perbandingan performa empat arsitektur *Convolutional Neural Network* (CNN) pratelatih—**EfficientNetB0**, **Xception**, **ResNet50**, dan **MobileNetV2**—dalam mendeteksi citra deepfake wajah menggunakan pendekatan *transfer learning* dengan skema *feature extraction*.

---

## 👨‍💻 Penulis & Peneliti
* **Faza Ilmal Mughni** (*Universitas Muhammadiyah Ponorogo*)
* **Eguh Raga Mustika** (*Universitas Muhammadiyah Ponorogo*)
* **Yovi Litanianda** (*Universitas Muhammadiyah Ponorogo*)

---

## 📌 Abstrak Singkat
Perkembangan teknologi deepfake yang semakin realistis menimbulkan tantangan terhadap keaslian informasi visual. Penelitian ini bertujuan membandingkan performa empat arsitektur CNN pratelatih dalam mendeteksi citra wajah deepfake. Dataset yang digunakan bersumber dari *Deepfake and Real Images* (Kaggle) dengan skema pembagian **3.708** data latih, **2.243** data validasi, dan **800** data uji seimbang. 

Hasil pengujian menunjukkan **EfficientNetB0** memperoleh akurasi tertinggi sebesar **72,6%** dengan efisiensi parameter dan waktu pelatihan terbaik. Sementara **ResNet50** mencatatkan nilai AUC tertinggi sebesar **0,834**.

---

## 📊 Ringkasan Hasil Evaluasi

Berikut adalah tabel komparasi performa dan efisiensi komputasi keempat model pada data uji (800 citra):

### 1. Performa Model pada Data Uji
| No | Model | Accuracy | Precision | Recall | F1-Score | AUC |
|:--:| :--- | :---: | :---: | :---: | :---: | :---: |
| 1 | **EfficientNetB0** | **0.726** | 0.765 | 0.653 | **0.72** | 0.814 |
| 2 | **Xception** | 0.716 | 0.691 | 0.783 | 0.71 | 0.804 |
| 3 | **ResNet50** | 0.715 | 0.667 | **0.860** | 0.71 | **0.834** |
| 4 | **MobileNetV2** | 0.693 | **0.779** | 0.538 | 0.68 | 0.791 |

### 2. Efisiensi Pelatihan & Parameter
| Model | Ukuran Input | Epoch (Stop) | Waktu Pelatihan | Trainable Params | Non-Trainable Params |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **EfficientNetB0** | 224×224 | 6 | **14.9 menit** | 328,705 | 4,050,083 |
| **MobileNetV2** | 224×224 | 6 | 31.3 menit | 328,705 | **2,258,496** |
| **ResNet50** | 224×224 | 8 | 18.8 menit | 525,313 | 23,588,224 |
| **Xception** | 299×299 | 7 | 25.0 menit | 525,313 | 20,861,992 |

---

## 📁 Struktur Repositori

```text
├── notebooks/                  # Notebook Google Colab / Jupyter
│   ├── EfficientNetB0.ipynb    # Pelatihan & evaluasi EfficientNetB0
│   ├── MobileNetV2.ipynb       # Pelatihan & evaluasi MobileNetV2
│   ├── ResNet50.ipynb          # Pelatihan & evaluasi ResNet50
│   └── Xception.ipynb          # Pelatihan & evaluasi Xception
├── paper/                      # File draft/naskah jurnal (PDF/Docx)
│   └── Performa_Deepfake_Detection.pdf
├── README.md                   # Dokumentasi utama proyek
└── LICENSE                     # Lisensi open-source
