# Prediksi Harga Rumah Tebet

Proyek machine learning untuk memprediksi harga rumah di Tebet, Jakarta Selatan berdasarkan karakteristik properti seperti luas bangunan, luas tanah, jumlah kamar, dan garasi.

## Gambaran Proyek

Proyek ini menggunakan metode Linear Regression untuk melakukan prediksi harga rumah berdasarkan karakteristik properti dari data listing rumah di Tebet, Jakarta Selatan.

Tahapan proyek meliputi eksplorasi data, analisis korelasi, pelatihan model, prediksi, evaluasi model, dan penyimpanan model untuk digunakan pada aplikasi prediksi.

## Dataset

Dataset terdiri dari 11 data listing rumah dengan beberapa variabel berikut:

| Variabel | Keterangan |
|---|---|
| NO | Nomor data |
| NAMA RUMAH | Nama atau judul listing rumah |
| Harga | Harga rumah dalam Rupiah |
| Luas_Bangunan | Luas bangunan dalam m² |
| Luas_Tanah | Luas tanah dalam m² |
| Kamar_Tidur | Jumlah kamar tidur |
| Kamar_Mandi | Jumlah kamar mandi |
| Garasi | Kapasitas garasi |

## Metodologi

Tahapan yang dilakukan dalam proyek ini:

1. Memuat dan memeriksa dataset.
2. Melakukan analisis korelasi antarvariabel numerik.
3. Membuat visualisasi korelasi menggunakan heatmap.
4. Menentukan variabel yang digunakan sebagai fitur model.
5. Membagi dataset menjadi data latih dan data uji.
6. Melatih model Linear Regression.
7. Melakukan prediksi harga rumah.
8. Mengevaluasi performa model menggunakan R² dan RMSE.
9. Menyimpan model untuk digunakan kembali.

## Fitur Model

Model menggunakan lima variabel sebagai fitur:

- Kamar_Tidur
- Kamar_Mandi
- Garasi
- Luas_Bangunan
- Luas_Tanah

Variabel target:

- Harga

Kolom `NO` tidak digunakan sebagai fitur karena merupakan nomor identifikasi data dan tidak memiliki hubungan yang relevan dengan harga rumah.

## Analisis Korelasi

Hasil analisis korelasi menunjukkan hubungan antara beberapa karakteristik properti dengan harga rumah.

| Variabel | Korelasi dengan Harga |
|---|---:|
| Luas_Tanah | 0.81 |
| Luas_Bangunan | 0.75 |
| Garasi | 0.48 |
| Kamar_Mandi | 0.40 |
| Kamar_Tidur | 0.32 |

Berdasarkan hasil tersebut, `Luas_Tanah` memiliki korelasi paling tinggi dengan harga rumah, diikuti oleh `Luas_Bangunan`.

### Heatmap Korelasi

![Heatmap Korelasi](static/images/heatmap_korelasi.png)

## Pemodelan

Metode yang digunakan dalam proyek ini adalah **Linear Regression** dari Scikit-learn.

```python
model = LinearRegression()
model.fit(X_train, y_train)
