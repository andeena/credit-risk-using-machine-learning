Dataset Default of Credit Card Clients digunakan untuk memprediksi apakah seorang nasabah akan mengalami gagal bayar (default) pada bulan berikutnya, berdasarkan informasi demografis, riwayat pembayaran, jumlah tagihan, dan jumlah pembayaran 6 bulan terakhir.

Project ini bertujuan untuk:

- Menganalisis performa model machine learning dalam memprediksi credit card default risk pada kondisi data asli tanpa class balancing. 

- Mengevaluasi pengaruh penerapan Synthetic Minority Oversampling Technique (SMOTE) terhadap peningkatan performa model dalam mengatasi imbalanced data. 

- Menguji efektivitas metode SMOTE-ENN dalam meningkatkan kualitas data dan stabilitas performa model dibandingkan teknik balancing lainnya. 

- Menentukan model machine learning terbaik di antara Logistic Regression, Decision Tree, Random Forest, XGBoost, dan Artificial Neural Network (ANN) berdasarkan hasil pengujian pada tiga skenario (Raw data, SMOTE, dan SMOTE-ENN) . 

- Mengidentifikasi kombinasi paling optimal antara algoritma machine learning dan teknik balancing yang mampu menghasilkan model default risk prediction yang stabil, akurat, dan layak diimplementasikan dalam sistem penilaian risiko perbankan.

Dengan perbandingan penelitian sebelumnya sebagai berikut:
| **No** | **Peneliti & Tahun**                                     | **Judul Penelitian**                                                                                                             | **Metode**                                             | **Hasil Utama**                                                                                                        |
| ------ | -------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------- |
| 1      | Amini, L., Ahmad, R., & Abdollahzadeh, H. (2022)         | *Machine Learning for Credit Risk Prediction: A Systematic Literature Review*. Expert Systems with Applications                  | Review sistematik berbagai pendekatan Machine Learning | Model ensemble seperti Random Forest, XGBoost, dan teknik hybrid resampling konsisten unggul pada data tidak seimbang. |
| 2      | Aruleba & Sun (2025)                                     | *Enhanced Credit Risk Prediction Using Deep Learning and SMOTE-ENN Resampling*. Frontiers in Artificial Intelligence             | Deep Neural Network + SMOTE-ENN                        | Teknik SMOTE-ENN meningkatkan recall dan F1-score hingga 15% dibandingkan SMOTE biasa.                                 |
| 3      | Gasmi, I., Neji, S., Mansouri, N., & Soui, M. (2025)     | *Bank Credit Risk Prediction Using Machine Learning Model*. Neural Computing and Applications                                    | Metode Machine Learning klasik & ensemble              | XGBoost menunjukkan performa terbaik dengan AUC mencapai 0.91.                                                         |
| 4      | Rakshith Bhandary & Bidyut Kumar Ghosh (2025)            | *Credit Card Default Prediction: An Empirical Analysis on Predictive Performance Using Statistical and Machine Learning Methods* | Logistic Regression, SVM, Random Forest, XGBoost       | Metode ensemble memberikan recall lebih baik dan stabil dibandingkan regresi logistik.                                 |
| 5      | Shreyas Khandale, Prathamesh Patil, & Rohan Patil (2023) | *Predicting Credit Card Defaults with Machine Learning*                                                                          | Logistic Regression, Random Forest, XGBoost            | Random Forest mencapai akurasi tinggi (83%), tetapi recall kelas default rendah bila tidak dilakukan balancing.        |
| 6      | Wenyuan Li, Lijie Yao, Wei Li, & Chengtao Ji (2025)      | *Visualizing Credit Default Risk: Insights Through Machine Learning*                                                             | XGBoost dan analisis SHAP                              | Model interpretatif mampu menjelaskan variabel penting seperti jumlah tagihan dan keterlambatan pembayaran.            |


Berdasarkan penelitian sebelumnya maka skenario yang dibuat adalah:
| **Scenario**   | **Balancing Technique**     | **Models Used**      |
| -------------- | --------------------------- | -------------------- |
| **Scenario 1** | Raw Data (No Balancing)     | LR, RF, XGB, ANN, DT |
| **Scenario 2** | SMOTE (Oversampling)        | LR, RF, XGB, ANN, DT |
| **Scenario 3** | SMOTE-ENN (Hybrid Sampling) | LR, RF, XGB, ANN, DT |

Setelah dilakukan training pada data sesuai dengan skenario yang dibuat maka didapatkan hasil sebagai berikut:
| **Scenario**  | **Best Model** | **Recall (Class 1)** | **Precision (Class 1)** | **Accuracy** |
| ------------- | -------------- | -------------------- | ----------------------- | ------------ |
| **Raw Data**  | Random Forest  | 56.00%               | 53.00%                  | 79.13%       |
| **SMOTE**     | Random Forest  | 81.28%               | 31.73%                  | 57.40%       |
| **SMOTE-ENN** | XGBoost        | 38.00%               | 63.00%                  | 81.00%       |
