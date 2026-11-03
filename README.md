# Sales Profitability Analysis & Machine Learning

Klasifikasi transaksi **Profit** atau **Loss** menggunakan algoritma Decision Tree dan Gradient Boosting. Proyek pembelajaran dari DQLab yang dikerjakan menggunakan Python dan Scikit-learn.

## Latar Belakang

Strategi penjualan yang tidak tepat di setiap cabang, seperti pemberian diskon terlalu besar ketika penjualan sedang tinggi, dapat menyebabkan kerugian. Proyek ini bertujuan membangun model klasifikasi untuk memprediksi apakah suatu kondisi penjualan menghasilkan **Profit** atau **Loss**, sehingga perusahaan dapat mengevaluasi strategi diskon dan penjualan berdasarkan hasil analisis data.

## Dataset

- **Sumber:** Data Mission.csv (disediakan DQLab untuk pembelajaran).
- **Target:** Kolom `Label` (Profit = 1, Loss = 0).
- **Fitur:** `Region`, `Top Product`, `Top Cust Segment`, `Top Ship Mode`, `Top Branch`, `Top Sub-Product`, `Top City`, `Month`, dan `Discount`.
- **Jumlah data:** 2.955 baris.
- **Jumlah fitur setelah encoding:** 19 kolom.

## Langkah Analisis

1. **Encoding Label:** Mengubah kategori Profit menjadi 1 dan Loss menjadi 0.
2. **Encoding fitur kategorikal:** Menggunakan One Hot Encoding untuk kolom dengan kategori kurang dari 10 dan Label Encoding untuk kolom lainnya.
3. **Transformasi Discount:** Menggunakan fungsi `np.log1p` untuk mentransformasi nilai Discount, kemudian menampilkan distribusinya melalui histogram.
4. **Pemisahan data:** Membagi dataset menjadi 75% data training dan 25% data testing dengan `random_state=0` dan `stratify=y`.
5. **Model Decision Tree:** Membangun model klasifikasi menggunakan `DecisionTreeClassifier(random_state=0)`.
6. **Model Gradient Boosting:** Membangun model tambahan menggunakan `GradientBoostingClassifier(random_state=0)`.
7. **Evaluasi model:** Mengukur performa menggunakan Accuracy Score dan Classification Report, meliputi Precision, Recall, dan F1-score.

## Hasil Evaluasi Model

| Model | Akurasi Training | Akurasi Testing |
|---|---:|---:|
| Decision Tree | 100,00% | 83,76% |
| Gradient Boosting | 91,70% | 88,50% |

### Perbandingan Performa

Gradient Boosting menghasilkan akurasi testing lebih tinggi, yaitu 88,50%, dibandingkan Decision Tree sebesar 83,76%.

Decision Tree menunjukkan indikasi overfitting karena memperoleh akurasi training 100%, tetapi turun menjadi 83,76% pada data testing. Sebaliknya, Gradient Boosting memiliki selisih akurasi training dan testing yang lebih kecil, yaitu sekitar 3,20%.

## Kesimpulan

Berdasarkan hasil evaluasi, Gradient Boosting menjadi model dengan performa terbaik dalam proyek ini. Model tersebut memiliki akurasi testing sebesar 88,50%, lebih tinggi dibandingkan Decision Tree yang memperoleh 83,76%.

Selain itu, Gradient Boosting menunjukkan kemampuan generalisasi yang lebih baik karena perbedaan akurasi antara data training dan testing relatif kecil. Model ini juga memiliki performa lebih baik dalam mengidentifikasi kategori Profit maupun Loss berdasarkan nilai F1-score.

Hasil analisis menunjukkan bahwa pendekatan machine learning dapat membantu mengidentifikasi potensi kerugian berdasarkan karakteristik transaksi, termasuk pemberian diskon. Namun, model masih perlu ditingkatkan dalam mendeteksi kategori Loss, sehingga hasil prediksi sebaiknya digunakan sebagai bahan evaluasi strategi penjualan, bukan sebagai satu-satunya dasar pengambilan keputusan.

## Cara Menjalankan

1. Buka file `Profitability_Analysis.ipynb` menggunakan Google Colab.
2. Jalankan seluruh cell secara berurutan melalui **Runtime → Run all**.
3. Pastikan koneksi internet tersedia untuk memuat dataset dari sumber DQLab.

## Library yang Digunakan

- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn

## Catatan

Dataset dan studi kasus berasal dari materi pembelajaran DQLab. Proyek ini dikerjakan sebagai bagian dari pembelajaran Data Analytics dan Machine Learning untuk pengembangan portofolio.
