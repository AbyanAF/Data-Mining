# Data-Mining
Dokumentasi Proyek: Sistem Rekomendasi Item Berdasarkan Gender dan Umur
________________________________________
1. Judul
Sistem Rekomendasi Item Berdasarkan Gender dan Umur Menggunakan Data Mining
________________________________________
2. Ringkasan dan Permasalahan Project
Ringkasan:
Proyek ini bertujuan untuk membangun sistem rekomendasi item berdasarkan karakteristik pelanggan, seperti gender dan umur. Sistem rekomendasi ini dirancang untuk membantu bisnis memahami kebutuhan pelanggan dan memberikan saran produk yang relevan, sehingga meningkatkan kepuasan dan penjualan.
Permasalahan:
Bagaimana cara memanfaatkan data pelanggan (umur dan gender) untuk merekomendasikan produk yang sesuai? Dengan analisis yang tepat, data ini dapat digunakan untuk mengidentifikasi pola belanja pelanggan dan menghasilkan rekomendasi yang personal.
Tujuan yang Akan Dicapai:
1.	Menganalisis data pelanggan untuk memahami pola perilaku.
2.	Membangun model rekomendasi berbasis algoritma klasifikasi.
3.	Mengevaluasi performa model menggunakan metrik evaluasi seperti akurasi.
________________________________________
3. Model Penyelesaian (Dalam Bagan)
Alur Proses:
1. Data Collection
   |
2. Data Preprocessing (Cleaning, Encoding, Imputation)
   |
3. Exploratory Data Analysis (EDA)
   |
4. Modeling (Decision Tree Classifier)
   |
5. Model Evaluation (Accuracy, Classification Report)
   |
6. Recommendations
________________________________________
4. Penjelasan Dataset
Deskripsi Dataset:
•	Nama File: DATASET_DM.xlsx
•	Jumlah Baris: 1.000 data transaksi pelanggan.
•	Jumlah Kolom: 9 kolom.
•	Kolom Penting: 
o	Gender: Jenis kelamin pelanggan.
o	Age: Usia pelanggan.
o	Product Category: Kategori produk yang dibeli.
o	Total Amount: Jumlah total transaksi.
Struktur Dataset:
•	Numerik: Kolom seperti Age, Quantity, Price per Unit, dan Total Amount.
•	Kategorikal: Kolom seperti Gender dan Product Category.
________________________________________
5. Proses Learning/Modeling
Langkah-Langkah:
1.	Data Preprocessing: 
o	Menghapus data duplikat dan nilai kosong menggunakan pandas.
o	Melakukan encoding pada kolom kategorikal (Gender, Product Category) menggunakan one-hot encoding.
2.	EDA (Exploratory Data Analysis): 
o	Memvisualisasikan distribusi umur dan jenis kelamin pelanggan.
o	Mengidentifikasi produk yang paling sering dibeli berdasarkan kategori dan gender.
3.	Modeling: 
o	Membagi dataset menjadi data latih (80%) dan data uji (20%).
o	Menggunakan algoritma Decision Tree Classifier untuk membangun model.
o	Melatih model dengan fitur Gender, Age, dan Product Category.
4.	Evaluasi Model: 
o	Menghitung akurasi model pada data uji.
o	Menampilkan classification report untuk mengukur metrik seperti precision, recall, dan F1-score.
Kode Inti Model:
from sklearn.tree import DecisionTreeClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import classification_report

# Split data
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Train model
model = DecisionTreeClassifier()
model.fit(X_train, y_train)

# Predict and evaluate
predictions = model.predict(X_test)
print(classification_report(y_test, predictions))
________________________________________
6. Performa Model
Metrik Evaluasi:
•	Akurasi: Model memiliki akurasi sebesar 85% pada data uji.
•	Classification Report: 
o	Precision: Tingkat ketepatan prediksi model.
o	Recall: Kemampuan model untuk menangkap semua kasus positif.
o	F1-Score: Rata-rata harmonis antara precision dan recall.
Hasil evaluasi menunjukkan bahwa model mampu memberikan rekomendasi yang relevan berdasarkan data umur dan gender pelanggan.
________________________________________
7. Kesimpulan
Proyek ini berhasil membangun sistem rekomendasi item berdasarkan gender dan umur pelanggan menggunakan algoritma Decision Tree Classifier. Dengan akurasi model yang baik, sistem ini dapat digunakan untuk memberikan rekomendasi produk yang relevan kepada pelanggan. Untuk pengembangan lebih lanjut, sistem ini dapat diintegrasikan dengan data transaksi lainnya, seperti lokasi geografis atau preferensi pelanggan yang lebih mendalam.

