# 🎓 Sistem Prediksi Risiko Mahasiswa (Early Warning System)

![Python](https://img.shields.io/badge/Python-3.x-blue?style=flat&logo=python)
![Machine Learning](https://img.shields.io/badge/Model-Random%20Forest-green?style=flat&logo=scikit-learn)
![Frontend](https://img.shields.io/badge/Deployment-Gradio-orange?style=flat&logo=gradio)
![License](https://img.shields.io/badge/License-Educational-lightgrey)

> **Tugas Besar (MID) - Applied Machine Learning** > *Project ini bertujuan untuk mendeteksi dini mahasiswa yang berisiko mengalami kegagalan akademik berdasarkan tren nilai indeks prestasi (SGPA & CGPA).*

---

## 📋 Daftar Isi
- [Tentang Project](#-tentang-project)
- [Profil Pengembang](#-profil-pengembang)
- [Struktur File](#-struktur-file)
- [Dataset & Fitur](#-dataset--fitur)
- [Metodologi](#-metodologi-crisp-dm)
- [Cara Menjalankan](#-cara-menjalankan)
- [Tampilan Aplikasi](#-tampilan-aplikasi)

---

## 📖 Tentang Project

Institusi pendidikan seringkali terlambat menyadari adanya mahasiswa yang mengalami penurunan performa akademik. Evaluasi biasanya baru dilakukan setelah hasil ujian keluar dengan status *Fail* atau *Pass with Grace*, sehingga intervensi dosen wali menjadi tidak efektif.

**Sistem Peringatan Dini (Early Warning System)** ini dibangun untuk mengklasifikasikan mahasiswa ke dalam dua kategori secara otomatis:
1.  **✅ AMAN:** Mahasiswa dengan performa stabil.
2.  **⚠️ BERISIKO:** Mahasiswa yang berpotensi gagal atau membutuhkan bimbingan khusus.

Sistem ini menggunakan algoritma **Random Forest Classifier** karena kemampuannya menangani hubungan non-linear antara data nilai dan risiko, serta telah di-deploy menggunakan **Gradio** untuk kemudahan penggunaan.

---

## 👤 Profil Pengembang

| Atribut | Detail |
| :--- | :--- |
| **Nama** | **Aldi Saputra** |
| **NIM** | 105841115923 |
| **Kelas** | 5AI-A (5E) |
| **Program Studi** | Informatika |
| **Fakultas** | Teknik |
| **Universitas** | Universitas Muhammadiyah Makassar |

---

## 📂 Struktur File

Berikut adalah deskripsi file yang ada dalam repositori ini:

```text
├── 📄 College Exam Result Dataset...csv  # Dataset mentah (Data Nilai Mahasiswa)
├── 📓 Project_Aldi.ipynb                 # Source code utama (Jupyter Notebook)
├── 📄 ALDI SAPUTRA - LK Perancangan...   # Lembar Kerja Perancangan Project
├── 📄 ALDI SAPUTRA...TUGAS BESAR MID...  # Laporan Lengkap Project
└── 📝 README.md                          # Dokumentasi Project (File ini)

📊 Dataset & Fitur
Project ini menggunakan sampel data dari College Exam Result Dataset.

Total Data: 62 Mahasiswa.

Fitur Input (X):

SGPA (Semester Grade Point Average): Indeks prestasi semester saat ini.

CGPA (Cumulative Grade Point Average): Indeks prestasi kumulatif total.

Target Output (Y):

Status diambil dari kolom Result Description.

Jika status Pass ➔ 0 (Aman)

Jika status Fail atau Pass with Grace ➔ 1 (Berisiko)

⚙️ Metodologi (CRISP-DM)
Project ini mengikuti alur standar industri CRISP-DM:

Business Understanding: Memahami urgensi deteksi dini kegagalan akademik.

Data Preparation:

Membersihkan Missing Values.

Konversi label kategorikal menjadi numerik (0/1).

Modeling:

Menggunakan Random Forest Classifier.

Alasan: Akurasi tinggi dan stabil (Ensemble Learning).

Evaluation:

Mengukur Accuracy dan Recall (Fokus meminimalkan False Negative agar mahasiswa berisiko tidak terlewat).

Deployment:

Membuat antarmuka web sederhana menggunakan library Gradio.

🛠 Teknologi yang Digunakan
Bahasa: Python 3.x

Data Processing: Pandas, NumPy

Machine Learning: Scikit-Learn

Interface: Gradio

💻 Cara Menjalankan
Anda dapat menjalankan project ini di komputer lokal atau Google Colab.

1. Prasyarat
Pastikan Python sudah terinstal, lalu install library yang dibutuhkan:

Bash

pip install pandas scikit-learn gradio numpy matplotlib
2. Clone Repositori (Jika menggunakan Git)
Bash

git clone [https://github.com/username-anda/nama-repo.git](https://github.com/username-anda/nama-repo.git)
cd nama-repo
3. Jalankan Notebook
Buka file Project_Aldi.ipynb menggunakan Jupyter Notebook atau VS Code, lalu jalankan semua cell secara berurutan.

4. Gunakan Aplikasi
Di bagian paling bawah notebook, link Gradio akan muncul. Anda bisa memasukkan nilai SGPA dan CGPA menggunakan slider untuk melihat prediksi.

Python

# Contoh Kode Deployment (Snippet)
import gradio as gr

def prediksi_cepat(sgpa, cgpa):
    hasil = rf_model.predict([[sgpa, cgpa]])[0]
    return "BERISIKO" if hasil == 1 else "AMAN"

app = gr.Interface(
    fn=prediksi_cepat,
    inputs=[gr.Slider(0, 10, label="SGPA"), gr.Slider(0, 10, label="CGPA")],
    outputs="text"
)
app.launch()
📱 Tampilan Aplikasi
Antarmuka pengguna dibangun dengan Gradio untuk input yang mudah.

Geser Slider SGPA (Skala 0-10).

Geser Slider CGPA (Skala 0-10).

Lihat hasil prediksi secara Real-time.

Dibuat untuk memenuhi Tugas Besar Mata Kuliah Applied Machine Learning - 2025.
