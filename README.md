# Prediksi Pembakaran Kalori 🔥

Proyek kali ini ingin memprediksi pembakaran kalori pada tiap user yang berencana berolahraga sehingga tiap user dapat membuat to do list untuk mencapai targetnya untuk menjaga kesehatan dan juga penampilan. Pada pembuatan model saya menggunakan metode Supervised Learning Regression. Saya akan melakukan proses modeling dengan menggunakan cross validation untuk menentukan model mana yang paling baik, sehingga dapat melakukan hyperparameter tuning pada proses selanjutnya menggunakan model terbaik. Sehingga hasil score prediksi semakin akurat lagi. Metrics evaluasi yang digunakan adalah MAE (Mean Absolute Error), metrics ini digunakan agar mudah menjelaskan hasil project kepada stakeholder dan juga karena toleransi pada pembakaran kalori tidak terlalu mempengaruhi user secara langsung.

## Daftar Isi 🗒️
1. [Link Terkait Project](#link-terkait-project-)
2. [Project Overview](#project-overview-)
3. [Latar Belakang Masalah](#latar-belakang-masalah-)
4. [Metode yang Digunakan](#metode-yang-digunakan-)
5. [Kesimpulan Analisa dan Further Improvement](#kesimpulan-analisa-dan-further-improvement-)
6. [File yang Tersedia](#file-yang-tersedia-)
7. [Libraries](#libraries-)
8. [Author](#author-️)

## Link Terkait Project ⛓️‍💥

 - [Dataset](https://www.kaggle.com/datasets/adilshamim8/workout-and-fitness-tracker-data)
 - [Deployment Calorie Burned](https://huggingface.co/spaces/adeindrar/Calories_Burned)

## Project Overview 📝

Dalam proyek ini, saya melakukan berbagai proses untuk menghasilkan model terbaik. Mulai dari eksplorasi data, feature engineering, melakukan beberapa model regresi dengan base parameter, cross validation, dll. Berikut langkah-langkah yang saya lakukan dalam proses pembuatan proyek ini:

1. **Import Libraries**:
    - Import seluruh library yang diperlukan dalam proses pembuatan model agar mudah dibaca saat memerlukan dokumentasi.

2. **Data Loading**:
    - Load dataset yang akan digunakan sebagai acuan model, lalu lakukan eksplorasi sederhana untuk data cleaning seperti cek duplicat data dan missing value agar memudahkan ke proses selanjutnya.

3. **Exploratory Data Analysis (EDA)**:
    - Melakukan analisis dengan beberapa pertanyaan dan juga memvisualisasikan hasil analisis dengan grafik sederhana. Analisis terdiri dari statistik inferensial dan juga statistik deskriptif.

4. **Feature Engineering**:
    - Pada bagian ini terdiri dari split data train dan test, handle outlier, cardinality handling, feature selection dan juga membuat pipeline untuk preprocessing.

5. **Model Definition**:
    - Mendefinisikan model-model yang akan digunakan dalam prosesnya. Terdapat 5 model yaitu K-Nearest Neighbors Regressor, Support Vector Regressor, Decision Tree Regressor, Random Forest Regressor, dan AdaBoost Regressor.

6. **Model Training**:
    - Training model dengan base parameter.

7. **Model Evaluation**:
    - Evaluasi model-model yang telah di fit pada data train dengan menggunakan metrics Mean Absolute Error (MAE), QQ Plot Residuals, dan pengecekan Homoscedasticity. Dilakukan juga Cross-validation lalu Hyperparameter tuning pada model terbaik.

8. **Model Saving**:
    - Save model terbaik untuk di test menggunakan data inference.

## Latar Belakang Masalah 🧐

Kesehatan adalah hal paling utama dalam kehidupan. Untuk menjaga kesehatan, masyarakat sering mencari cara untuk mengetahui apa saja yang perlu mereka lakukan dalam menjaga kesehatan. Salah satu cara yang sering ditemui adalah dengan melakukan olahraga fitness. Selain menjaga kesehatan, olahraga juga mempertahankan bentuk tubuh ideal, dapat mengendalikan stress, mengurangi kecemasan dll. Project yang akan dibuat kali ini akan memprediksi hasil pembakaran kalori dari dataset yang akan dimodeling.

## Metode yang Digunakan 🛠️

- Supervised Learning Regression
- Statistik Inferensial
- Statistik Deskriptif
- Visualisasi Data
- Cross Validation
- Hyperparameter Tuning

## Kesimpulan Analisa dan Further Improvement 🧠

**Kesimpulannya**:

Hasil akhir dari model `AdaBoost Regressor` mampu memprediksi pembakaran kalori dengan metrics evaluasi Mean Absolute Erroe (MAE) kurang lebih sebesar `225`, dimana jika hasil yang ditampilkan saat prediksi data sebesar 500 kalori pembakaran, maka data aktual nya berkisar antara 275-725 kalori. Untuk konteks aplikasi fitness dalam memprediksi pembakaran kalori, kesalahan (225) cukup signigikan sehingga model ini menunjukkan hasil underfit dan tidak cukup menangkap pola kompleks dari data pengguna. Dari hasil metrics evaluasi QQ Plot model juga tidak menunjukkan hasil yang normal, didapatkan pola vertikal yang terkonsentrasi disekitar 0 yang menandakan variasi residual sangat kecil. Pengecekan Homoscedasticity juga menunjukkan bahwa residuals tidak menyebar secara acak di sekitar garis nol, malah membentuk pola linear yang sangat teratur. Biasanya residual yang baik harus menyebar secara acak tanpa pola tertentu, sehingga kemungkinan data yang digunakan pada modeling kali ini belum cukup baik digunakan untuk memprediksi hasil pembakaran kalori.

**Further Improvement**:
- Model masih memiliki error yang sangat tinggi untuk aplikasi pembakaran kalori yang jika dilakukan deployment untuk customer dapat menurunkan kepercayaan. Maka perlu perluasan dataset yang lebih banyak lagi seperti fitur heart rate, durasi latihan, body composition dll.
- Model saat ini bisa dijadikan sebagai baseline dimana dapat dilanjutkan untuk melakukan Hyperparameter tuning lebih lanjut, melakukan eksperimen lain dengan model (misalnya Gradient Boosting, XGBoost, Neural Networks), atau melakukan feature engineering kembali.
- Jika model ingin dilakukan percobaan deployment, dapat diberikan disclaimer bahwa "Prediksi kalori adalah estimasi, akurasi masih dalam pengembangan"
- Dapat dilakukan segmentasi dalam hasil prediksi daripada mencoba prediksi angka yang presisi seperti memberi kategori (misalnya "rendah", "sedang", "tinggi" pembakaran kalori).

## File yang Tersedia 📂

- `data_inf_ade_indra.ipynb`: Jupyter Notebook yang berisikan data inference atau data yang belum pernah dilihat oleh model untuk melihat performa model.
- `modeling_ade_indra.ipynb`: Jupyter Notebook berisi langkah-langkah analisis data, pemilihan model terbaik, evaluasi model dan insight yang didapatkan.
- `pipe_ada.pkl` : Hasil model yang disimpan dalam bentuk pipeline
- `README.md`: Penjelasan dari proyek ini.
- `workout_fitness_tracker_data.csv`: File data mentah dataset.


## Libraries 📚
- Pandas
- Seaborn
- Matplotlib
- Scikit-Learn
- Scipy
- Phik
- Pickle

## Author ✍️
**Ade Indra Rukmana**

[LinkedIn](https://www.linkedin.com/in/ade-indra-rukmana/)