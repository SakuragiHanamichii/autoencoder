# autoencoder
# 📹 CCTV Frames Autoencoder with Image Sharpening Enhancement 🔍✨

Proyek ini merupakan implementasi **Autoencoder sederhana berbasis Convolutional Neural Network (CNN)** menggunakan **PyTorch** untuk melakukan **rekonstruksi dan perbaikan kualitas gambar CCTV**. Selain itu, hasil rekonstruksi juga diperhalus menggunakan teknik **image sharpening convolution** agar hasil gambar lebih tajam dan detail.

Project ini cocok untuk:
- Eksperimen image restoration sederhana
- Studi kasus preprocessing data CCTV
- Pengenalan Autoencoder berbasis CNN
- Visualisasi dan perbandingan hasil rekonstruksi gambar

---

## 📌 Latar Belakang

Dalam dunia pengawasan CCTV, sering kali kualitas gambar yang ditangkap memiliki resolusi rendah atau mengalami noise. Salah satu pendekatan untuk memperbaiki kualitas tersebut adalah menggunakan **Autoencoder**, sebuah arsitektur neural network yang mampu mempelajari representasi fitur penting dari data, kemudian melakukan rekonstruksi ulang gambar.

Selain rekonstruksi, diterapkan juga **sharpening filter** berbasis kernel konvolusi untuk meningkatkan ketajaman hasil rekonstruksi, sehingga detail gambar menjadi lebih jelas.

---

## 📦 Fitur Utama

✅ Download dataset CCTV otomatis via **KaggleHub**  
✅ Preprocessing gambar: resize, konversi tensor, normalisasi  
✅ Custom `Dataset` class menggunakan PyTorch `Dataset` dan `DataLoader`  
✅ CNN-based **Autoencoder** (Encoder-Decoder)  
✅ **Sharpening convolution** untuk enhancement hasil gambar  
✅ Kalkulasi **Loss (MSE)** dan **PSNR (Peak Signal-to-Noise Ratio)** per epoch  
✅ Visualisasi hasil input dan output per epoch  
✅ Visualisasi grafik **Loss** dan **PSNR** per epoch  

---

## 📚 Dataset

Dataset digunakan dari Kaggle:

**CCTV Gender Classifier Dataset**  
🔗 [https://www.kaggle.com/datasets/hossamrizk/cctv-gender-classifier-dataset](https://www.kaggle.com/datasets/hossamrizk/cctv-gender-classifier-dataset)

Dataset ini berisi ribuan gambar frame CCTV yang bisa dimanfaatkan untuk berbagai eksperimen klasifikasi, deteksi, maupun rekonstruksi seperti di proyek ini.

---

## 🛠️ Teknologi & Library

- [PyTorch](https://pytorch.org/)
- [Torchvision](https://pytorch.org/vision/stable/index.html)
- [Matplotlib](https://matplotlib.org/)
- [PIL (Pillow)](https://pillow.readthedocs.io/en/stable/)
- [KaggleHub](https://github.com/Kaggle/kagglehub)

---

## 🚀 Cara Install & Jalankan

### 1️⃣ Clone repository:

```bash
git clone https://github.com/SakuragiHanamichii/repo-autoencoder-cctv.git
cd repo-autoencoder-cctv

📈 Penjelasan Training Metrics
Loss (MSE): Mengukur perbedaan pixel antara gambar asli dengan hasil rekonstruksi. Semakin kecil, semakin baik.

PSNR (dB): Mengukur kualitas rekonstruksi gambar dalam decibel. Semakin tinggi nilai PSNR, semakin bagus kualitas rekonstruksi.
![download (1)](https://github.com/user-attachments/assets/80dd468c-2875-451c-b1df-01a9c0c25e18)

📑 Penjelasan Metode
📌 Autoencoder CNN
Encoder: 3 layer Conv2D untuk mengubah gambar 128x128x3 menjadi fitur 16x16x256.

Decoder: 3 layer ConvTranspose2D untuk mengembalikan fitur ke gambar 128x128x3.

Loss Function: Mean Squared Error (MSE)

📌 Image Sharpening Enhancement
Setelah rekonstruksi, gambar diperhalus menggunakan sharpening kernel berikut:
[[ 0, -1,  0],
 [-1,  5, -1],
 [ 0, -1,  0]]
Diterapkan menggunakan F.conv2d pada hasil rekonstruksi agar detail gambar lebih tajam.

📌 Kelebihan Proyek
✅ Simple & mudah dipahami (cocok untuk pemula deep learning)
✅ Menggunakan real-world CCTV dataset
✅ Visualisasi hasil gambar langsung per epoch
✅ Kombinasi Autoencoder + Image Sharpening
✅ Bisa dijalankan di CPU maupun GPU (jika tersedia)

Catatan:
Proyek ini dibuat untuk tujuan edukasi dan eksperimen. Performansi dan hasil dapat bervariasi tergantung dataset, parameter training, dan arsitektur model.
