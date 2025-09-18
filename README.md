# Capstone-Modul-3---Machine-Learning

# 📊 Customer Churn Prediction for E-commerce Company

## 📌 Deskripsi Proyek
Proyek ini bertujuan untuk **memprediksi pelanggan yang berpotensi churn (berhenti berbelanja)** pada sebuah perusahaan e-commerce.  
Dengan model ini, tim marketing dapat **melakukan tindakan pencegahan** seperti memberikan promo, voucher, atau loyalty point sebelum pelanggan benar-benar pergi.

Proyek ini merupakan bagian dari **Capstone Project Module 3** di Purwadhika Digital School.

---

## 🧠 Business Understanding

- **Masalah Utama:** Tingginya tingkat *customer churn* menyebabkan hilangnya pendapatan dan meningkatkan biaya akuisisi pelanggan baru.
- **Stakeholder:** Tim Marketing, Tim Customer Retention, dan Manajemen Perusahaan.
- **Tujuan:** Membuat model machine learning untuk **mendeteksi pelanggan berisiko churn** agar bisa segera diberikan penawaran retensi.

---

## 📁 Dataset

- Total data: 3941 pelanggan  
- Target: `Churn` (1 = churn, 0 = tidak churn)  

---

## ⚙️ Data Preprocessing

Langkah-langkah utama:

- **Imputasi Missing Value**  
  - Numerik → median  
  - Kategorikal → modus  
- **Encoding Kategorikal** → One Hot Encoding  
- **Scaling Numerik** → RobustScaler (lebih tahan outlier)  
- **Pipeline** dibuat dengan `ColumnTransformer` agar proses konsisten dan menghindari data leakage

---

## 🤖 Modeling

Beberapa model yang diuji:

- RandomForest
- XGBoost
- LogisticRegression
- DecisionTree

**Metrik utama yang difokuskan: Recall**, karena tujuan bisnis adalah **menangkap sebanyak mungkin pelanggan churn (mengurangi False Negative).**

---

## ⚡ Hyperparameter Tuning

- Dilakukan pada model **XGBoost** yang memiliki performa awal terbaik
- Setelah tuning:
  - **Recall naik** dari 0.8148 → 0.8444
  - **F1-score naik** dari 0.8333 → 0.8444
  - **Accuracy naik** dari 0.9442 → 0.9468
  - **False Negative turun** dari 25 → 21
  - **True Positive naik** dari 110 → 114
- Evaluasi menggunakan **threshold 0.50**

---

## 💡 Feature Importance & Insight

Top 5 fitur paling berpengaruh:
- `Complain`
- `Tenure`
- `PreferedOrderCat_*`
- `DaySinceLastOrder`
- `SatisfactionScore`

📌 **Insight:**
- Pelanggan yang pernah **komplain**, **baru bergabung**, atau **lama tidak berbelanja** memiliki risiko churn paling tinggi.
- Kelompok ini menjadi **prioritas utama untuk kampanye retensi**.

---

## ✅ Kesimpulan

- Model **XGBoost setelah tuning** mampu mendeteksi pelanggan berisiko churn secara lebih sensitif.
- Model ini cocok digunakan untuk **deteksi dini churn**, bukan untuk menilai nilai pelanggan jangka panjang.
- Bisa membantu menurunkan churn rate dengan cara memberi promo atau loyalty point lebih cepat pada pelanggan berisiko.

---

## 💡 Rekomendasi Penggunaan

- Gunakan model ini secara **bulanan** untuk memprediksi pelanggan berisiko churn
- Fokus pada pelanggan:
  - Tenure rendah
  - Pernah komplain
  - Lama tidak berbelanja
- **Lakukan retraining model setiap 3–6 bulan** agar tetap akurat
- Buat dashboard sederhana agar tim marketing dapat menggunakan model ini tanpa pemahaman teknis mendalam

---

## 🧪 Teknologi yang Digunakan
- Python
- Pandas, NumPy
- Scikit-learn
- XGBoost
- Matplotlib / Seaborn

---

## 📁 Struktur Notebook
1. Business Understanding  
2. Data Understanding  
3. Preprocessing  
4. Modeling & Tuning  
5. Evaluation  
6. Feature Importance  
7. Conclusion & Recommendation  

---

## ✍️ Author
**Muhamad Wildan Trisianly**  
📧 wildan.trisianly@gmail.com  
💻 [github.com/wildantrisianly](https://github.com/wildantrisianly)
