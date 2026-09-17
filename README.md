# ⚡ Studi Kasus Mandiri 3: Eksplorasi Data Sensor Kualitas Produk Elektronik

Proyek mandiri terakhir ini berfokus pada eksplorasi data hasil pengujian sensor otomatis di stasiun uji akhir perakitan komponen elektronik (`sensor_kualitas_elektronik.csv`). Tujuannya adalah menganalisis karakteristik kelistrikan, menangani ketimpangan kelas (*class imbalance*), serta mengidentifikasi parameter sensor yang paling berpengaruh terhadap status kelayakan mutu produk (*Lolos* vs *Gagal*) sebagai fondasi pembangunan model Machine Learning prediktif.

---

## 📂 Alur Kerja Proyek & Langkah Analisis

1. **Memuat Dataset:** Mengimpor pustaka utama (`pandas`, `numpy`, `matplotlib`, `seaborn`), memuat dataset berukuran 1.800 baris dan 7 kolom, serta menampilkan sepuluh baris pertama.
2. **Inspeksi Menyeluruh:** Menggunakan `df.info()`, `df.describe()`, dan `df.value_counts()` untuk mendeteksi proporsi target kelas. Ditemukan adanya *class imbalance* (86.94% produk Lolos dan 13.06% produk Gagal).
3. **Pembersihan Data & Imputasi:** Mengatasi data kosong pada kolom `Tegangan_Output_Volt` dan `Arus_Output_Ampere` menggunakan strategi imputasi **median** agar keutuhan dataset tetap terjaga tanpa menghapus informasi penting secara sembarangan.
4. **Visualisasi Data & EDA:**
   * **Visualisasi 1 (Histogram):** Menampilkan distribusi sebaran suhu komponen (*Suhu_Komponen_Celcius*) yang mendekati distribusi normal (kisaran 40–50°C).
   * **Visualisasi 2 (Boxplot):** Membandingkan sebaran tegangan output berdasarkan status akhir produk (`Status_Akhir`), menunjukkan perbedaan karakteristik antara produk lolos dan gagal.
   * **Visualisasi 3 (Scatter Plot dengan Hue):** Memetakan hubungan antara suhu komponen dan arus output dengan pewarnaan berdasarkan status kelulusan produk (`hue='Status_Akhir'`).

---

## 🛠️ Tech Stack
* **Python**
* **Pandas & NumPy** (Manipulasi & Imputasi Data)
* **Matplotlib & Seaborn** (Visualisasi Statistik Lanjutan)

---

## 💡 Temuan Utama & Insight Bisnis
* **Proporsi Mutu:** Sebagian besar komponen elektronik dinyatakan lolos uji standar (86.94%), sementara 13.06% mengalami kegagalan (*class imbalance* khas industri manufaktur).
* **Korelasi Sensor & Kualitas:** Parameter sensor seperti tegangan output, arus output, dan suhu komponen terbukti memiliki pola serta korelasi yang kuat terhadap status kelulusan unit.
* **Potensi Machine Learning:** Temuan ini membuktikan bahwa parameter sensor kelistrikan sangat potensial dan valid untuk dijadikan fitur utama dalam membangun model klasifikasi otomatis guna mendeteksi kegagalan produk secara dini di masa mendatang.

---

## 🚀 Cara Menjalankan
1. Pastikan file dataset `sensor_kualitas_elektronik.csv` berada dalam satu direktori dengan notebook.
2. Buka file `.ipynb` menggunakan **Jupyter Notebook** atau **Google Colab**.
3. Jalankan sel kode secara berurutan.
