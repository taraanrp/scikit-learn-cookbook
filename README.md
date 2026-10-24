# scikit-learn Cookbook — Reproduksi Kode & Pendalaman Teori

Reproduksi Bab 1–13 dari *scikit-learn Cookbook, Third Edition* (John Sukup, Packt, 2025) yang sudah dieksekusi dan dijelaskan, lengkap dengan teori di balik setiap resep.

![Python](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.5.2-F7931E?logo=scikitlearn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)
![Bahasa](https://img.shields.io/badge/Bahasa-Indonesia-red)

---

## Tentang

Repositori ini adalah **tugas pengayaan individu untuk mata kuliah Machine Learning** (S1 Teknik Komputer, Telkom University). Tugasnya berupa *reproduksi kode + pendalaman teori* dari *scikit-learn Cookbook, Third Edition*, yang menargetkan scikit-learn 1.5.

Di repositori ini, artinya:

* **Reproduksi kode:** kode setiap resep dari [repositori resmi Packt](https://github.com/PacktPublishing/Scikit-Learn-Cookbook-Third-Edition) dijalankan ulang sesuai urutan buku, dengan logika dan dataset asli yang tidak diubah, dalam satu notebook per bab. Semua notebook dieksekusi dari atas ke bawah dan disimpan **beserta outputnya**, sehingga setiap tabel dan plot langsung terlihat di GitHub. Sebuah skrip membandingkan kode setiap notebook dengan kode resmi (mengabaikan komentar dan spasi) dan hasilnya identik, kecuali tambahan yang ditandai jelas seperti dijelaskan di bawah. Pengecualiannya Bab 1: repositori resmi tidak memiliki kode untuk bab itu, sehingga kodenya disalin dari teks buku dan dicek dengan skrip terhadap teks buku tersebut. Komentar kode diterjemahkan ke Bahasa Indonesia, tetapi kodenya sendiri (termasuk judul dan label plot) tetap sama dengan buku.
* **Pendalaman teori:** setiap resep dibungkus dengan penjelasan yang ditulis khusus untuk repositori ini:
  * **Tujuan**: masalah yang diselesaikan resep.
  * **Teori**: intuisi dengan bahasa sederhana → matematika dalam LaTeX dengan setiap simbol didefinisikan → cara scikit-learn mengimplementasikannya (kelas, parameter kunci dan nilai default, apa yang dilakukan `fit`/`transform`/`predict`) → asumsi, kelebihan, keterbatasan, serta kapan sebaiknya (tidak) dipakai.
  * **Interpretasi output** setelah setiap output yang penting, ditulis berdasarkan *nilai hasil eksekusi yang sebenarnya*.
  * **Poin Penting**, ditambah tabel ringkasan bab dan referensi.

**Konvensi di dalam notebook**

| Penanda | Arti |
|---|---|
| Sel kode bertag `added` (komentarnya diakhiri `(tambahan)`) | Bukan dari buku. Ini sel pengecekan kecil yang mencetak angka di balik sebuah interpretasi (misalnya jumlah *support vector*, papan peringkat *grid search*). Sel ini hanya membaca objek yang sudah di-fit dan tidak pernah mengubah hasil buku. |
| Baris yang diakhiri `# (tambahan)` | Baris kosmetik yang disisipkan ke sel buku, hanya untuk memberi label sumbu atau judul pada setiap plot. |
| Sel `> **Catatan:**` | Menjelaskan sesuatu tentang kode buku: peringatan yang tidak berbahaya, nilai basi yang tercetak, atau hal lain yang perlu diluruskan. |

Setiap notebook diawali sel persiapan yang memberi *seed* pada NumPy (`random_state = 42`) dan mencetak versi pustaka. Hal ini membuat beberapa sel buku yang tidak memiliki `random_state` sendiri tetap dapat direproduksi.

---

## Daftar Isi

| # | Bab | Topik yang dibahas | Notebook |
|---|---|---|---|
| 1 | Konvensi Umum dan Elemen API scikit-learn | Filosofi desain, *estimator* (`fit`/`predict`/`fit_predict`), *transformer* (`fit`/`transform`/`fit_transform`), kelas kustom, *pipeline* dan MLOps, `coef_`/`intercept_`/`score`, `get_params`/`set_params`, *metadata routing*, praktik terbaik | [Chapter_01.ipynb](Chapter_01.ipynb) |
| 2 | Alur Kerja Pra-Model dan Pra-pemrosesan Data | Imputasi (sederhana, KNN, iteratif), penskalaan, normalisasi, *one-hot*/*label encoding*, `ColumnTransformer`, *pipeline*, fitur polinomial, *binning*, RFE, `SelectFromModel` | [Chapter_02.ipynb](Chapter_02.ipynb) |
| 3 | Teknik Reduksi Dimensi | PCA (*loadings*, variansi yang dijelaskan), LDA, t-SNE, PCA sebelum *classifier*, K-means vs label sebenarnya | [Chapter_03.ipynb](Chapter_03.ipynb) |
| 4 | Membangun Model dengan Metrik Jarak dan *Nearest Neighbors* | Klasifikasi k-NN, jarak Euclidean/Manhattan/Minkowski, *grid search*, *cross-validation*, kurva belajar, *confusion matrix*, *precision/recall/F1* | [Chapter_04.ipynb](Chapter_04.ipynb) |
| 5 | Model Linear dan Regularisasi | OLS, multikolinearitas, Ridge, Lasso, ElasticNet, jalur koefisien, regresi polinomial, spline | [Chapter_05.ipynb](Chapter_05.ipynb) |
| 6 | Regresi Logistik Lanjutan dan Pengembangannya | Regresi logistik biner, *one-vs-rest* vs multinomial, penalti L1/L2 dan `C`, klasifikasi multilabel, ROC/AUC | [Chapter_06.ipynb](Chapter_06.ipynb) |
| 7 | *Support Vector Machine* dan Metode Kernel | SVC margin maksimum, SVR, kernel linear/polinomial/RBF, *tuning* `C`, SVM dengan fitur lebih banyak daripada sampel, Platt scaling | [Chapter_07.ipynb](Chapter_07.ipynb) |
| 8 | Algoritme Berbasis Pohon dan Metode Ensemble | *Decision tree* (CART), *random forest*, *gradient boosting*, *grid search* atas ensemble, *stacking* | [Chapter_08.ipynb](Chapter_08.ipynb) |
| 9 | Pemrosesan Teks dan Klasifikasi Multikelas | *Bag of words*, TF-IDF, *n-gram*, *POS tagging*, Naive Bayes/SVM/regresi logistik untuk teks, *one-vs-rest* vs *one-vs-one*, evaluasi model teks | [Chapter_09.ipynb](Chapter_09.ipynb) |
| 10 | Teknik *Clustering* | K-means dan *elbow*, *agglomerative*/*dendrogram*, DBSCAN dan *k-distance*, *silhouette*/Davies–Bouldin/ARI, *spectral clustering*, *Gaussian mixture* | [Chapter_10.ipynb](Chapter_10.ipynb) |
| 11 | Deteksi *Novelty* dan *Outlier* | *Isolation Forest*, *One-Class SVM*, *Local Outlier Factor*, evaluasi detektor, penanganan outlier | [Chapter_11.ipynb](Chapter_11.ipynb) |
| 12 | *Cross-Validation* dan Teknik Evaluasi Model | k-fold/*stratified*, LOOCV, *nested* CV, `cross_validate`, *grid* vs *randomized search*, *learning*/*validation curve* | [Chapter_12.ipynb](Chapter_12.ipynb) |
| 13 | *Deploying* Model scikit-learn ke Produksi | `pickle`/`joblib`, latensi vs *throughput*, pemantauan dan `partial_fit`, metadata berversi, `Pipeline` dan gerbang CI | [Chapter_13.ipynb](Chapter_13.ipynb) |

> **Catatan Bab 1:** repositori kode resmi tidak memuat kode untuk Bab 1, jadi kode di notebook Bab 1 disalin langsung dari teks buku (halaman 3–10), bukan direkonstruksi dari ingatan. Bab ini bersifat konseptual: hanya 4 dari 9 resepnya yang memuat kode, dan resep tanpa kode dibahas sebagai teori saja.

---

## Ringkasan Bab

**Bab 1 — Konvensi Umum dan Elemen API scikit-learn.** Bab ini memperkenalkan "tata bahasa" yang dipakai semua bab berikutnya. *Estimator* belajar dengan `fit()` dan memprediksi dengan `predict()` (atau `fit_predict()` untuk *clustering*), *transformer* mempelajari statistik dengan `fit()` lalu menerapkannya dengan `transform()`, dan hasil belajar disimpan di atribut berakhiran garis bawah seperti `coef_` dan `mean_`. Hiperparameter dibaca dan diubah dengan `get_params()`/`set_params()`, mekanisme yang dipakai *grid search* di balik layar. Contoh-contohnya sangat kecil (lima titik data), jadi setiap angka dapat dihitung ulang dengan tangan, dan sel pengecekan melakukannya: garis $\hat y = 0.05 + 0.95x$, z-score ±1,2247, dan $R^2$ 0,981. Output hasil eksekusi cocok dengan output yang dicetak buku, kecuali intersep yang berbeda di digit ke-16 karena pembulatan *floating-point*. Bab ini juga membahas secara konseptual kelas kustom, *pipeline* dan MLOps, *metadata routing*, serta praktik terbaik.

**Bab 2 — Alur Kerja Pra-Model dan Pra-pemrosesan Data.** Model membutuhkan matriks fitur yang lengkap, numerik, dan berskala baik, dan bab ini membangunnya. Nilai yang hilang diisi dengan `SimpleImputer` (statistik kolom), `KNNImputer` (nilai dari baris yang mirip), dan `IterativeImputer` (setiap fitur diregresikan terhadap fitur lainnya). Fitur diskalakan ulang dengan `StandardScaler`/`MinMaxScaler`, atau baris dinormalisasi menjadi panjang satu dengan `Normalizer`. Kategori diubah menjadi angka melalui *one-hot* atau *integer encoding*, dan `ColumnTransformer` mengarahkan setiap jenis kolom ke langkah yang tepat. Semua ini dirangkai dalam `Pipeline` agar pra-pemrosesan hanya dipelajari dari data latih. Bab ditutup dengan rekayasa fitur (suku polinomial, *binning*) dan seleksi fitur (RFE, `SelectFromModel`). Output hasil eksekusi juga menunjukkan bahwa *pipeline* mainan di buku memakai target (`Position_Senior`) yang dapat dihitung persis dari dua fiturnya. Kedua metode seleksi fitur mengungkap kebocoran ini.

**Bab 3 — Teknik Reduksi Dimensi.** Banyak fitur bersifat redundan, dan dimensi yang tinggi merugikan model maupun visualisasi. **PCA** memutar data terstandardisasi ke arah-arah ortogonal dengan variansi maksimum. Pada data Wine, dua komponen menyimpan 55 % variansi tetapi sudah memisahkan ketiga kultivar, dan *loadings* menunjukkan makna setiap komponen. **LDA** memakai label untuk memaksimalkan sebaran antarkelas relatif terhadap sebaran dalam-kelas (paling banyak $K-1$ sumbu) dan memisahkan kultivar sepenuhnya. **t-SNE** adalah *embedding* non-linear yang menjaga ketetanggaan, khusus untuk visualisasi, dan mengungkap satu klaster per angka tulisan tangan beserta gaya tulisan yang berbeda. Latihannya mengukur biaya memampatkan data digits dengan PCA (64 → 39 fitur, −1,1 poin akurasi) dan membandingkan klaster K-means dengan angka sebenarnya (ARI 0,657).

**Bab 4 — Membangun Model dengan Metrik Jarak dan *Nearest Neighbors*.** *k-nearest neighbors* memprediksi dengan suara terbanyak di antara titik latih terdekat, sehingga perilakunya sepenuhnya bergantung pada metrik jarak, jumlah tetangga, dan penskalaan fitur. Bab ini membandingkan anggota keluarga Minkowski (`minkowski` default di scikit-learn *adalah* jarak Euclidean), men-*tuning* $k$, pembobotan, dan metrik dengan `GridSearchCV` ber-*cross-validation*, lalu mengevaluasi model hasil *tuning* dengan skor *cross-validation*, kurva belajar, *confusion matrix*, serta *precision*, *recall*, dan F1 per kelas. Konsep kunci: pembelajaran *lazy* dan non-parametrik; *curse of dimensionality*; pemilihan model yang jujur dengan k-fold CV; dan membaca papan peringkat yang pengaturan "terbaik"-nya bisa jadi seri dengan banyak pengaturan lain.

**Bab 5 — Model Linear dan Regularisasi.** *Ordinary least squares* mem-fit jumlah berbobot dari fitur dengan meminimalkan galat kuadrat, tetapi dengan banyak fitur yang berkorelasi koefisiennya menjadi besar dan tidak stabil. Ridge (L2), Lasso (L1), dan ElasticNet (keduanya) menambahkan penalti yang menukar sedikit bias dengan variansi yang jauh lebih rendah, dan jalur koefisien menunjukkan bobot mengecil seiring membesarnya penalti. Fitur polinomial dan basis B-spline kemudian memungkinkan model yang tetap linear dalam parameternya mem-fit hubungan yang melengkung. Temuan penting dari output hasil eksekusi: langkah buku yang menciptakan multikolinearitas menimpa 7 dari 10 fitur informatif, sehingga $R^2$ yang dapat dicapai terbatas sekitar 0,21. Ini menjelaskan skor yang rendah, dan mengapa model dengan regularisasi terkuat (ElasticNet) bergeneralisasi paling baik.

**Bab 6 — Regresi Logistik Lanjutan dan Pengembangannya.** Regresi logistik memetakan skor linear melalui sigmoid menjadi peluang kelas, dengan koefisien yang dibaca sebagai perubahan log-odds. Bab ini membahas klasifikasi biner (Breast Cancer), strategi multikelas (*one-vs-rest* vs softmax), regularisasi L1/L2 melalui kebalikan kekuatan `C` (L1 pada `C=0.1` hanya mempertahankan 7 dari 30 fitur), klasifikasi multilabel dengan satu model per label (termasuk *subset accuracy*, Hamming loss, dan ko-okurensi label), serta evaluasi dengan *precision*, *recall*, F1, dan ROC/AUC. Bab ini menunjukkan mengapa akurasi saja tidak cukup ketika jenis kesalahan memiliki biaya berbeda, dan mengapa penskalaan penting baik untuk konvergensi solver maupun penalti.

**Bab 7 — *Support Vector Machine* dan Metode Kernel.** SVM memilih *hyperplane* pemisah dengan margin terlebar, solusi yang hanya ditentukan oleh *support vector*, dengan `C` mengendalikan seberapa banyak pelanggaran margin yang ditoleransi. *Kernel trick* (polinomial, RBF) menghasilkan batas non-linear dengan mengganti hasil kali dalam dengan fungsi kemiripan. Bab ini membahas SVC dan SVR, perbandingan kernel, *tuning* `C` (kurva *underfit* → optimum → *overfit* yang jelas), perilaku SVM linear ketika fitur lebih banyak daripada sampel (akurasi latih 1.000 vs akurasi uji 0.747, sesuai prediksi teorema Cover), dan kalibrasi peluang dengan Platt scaling untuk analisis ROC. Reproduksi ini juga mencatat bahwa satu sel buku mencetak akurasi basi (0.75) yang tersisa dari resep sebelumnya. Nilai sebenarnya 0.947.

**Bab 8 — Algoritme Berbasis Pohon dan Metode Ensemble.** *Decision tree* memisah data secara rakus berdasarkan penurunan ketidakmurnian. Model ini mudah ditafsirkan dan tidak memerlukan penskalaan, tetapi pohon yang tumbuh penuh *overfitting*. *Random forest* merata-ratakan pohon *bootstrap* yang sudah didekorelasi untuk mengurangi variansi. *Gradient boosting* menambahkan pohon dangkal yang di-fit pada kesalahan saat itu (pseudo-residual) untuk mengurangi bias. *Stacking* mempelajari cara menggabungkan model-model yang berbeda. Pada Iris, pohon tunggal, kedua model *boosting*, dan ensemble *stacking* semuanya salah mengklasifikasikan enam bunga yang sama di daerah tumpang tindih, sementara *forest* memperbaiki dua di antaranya. Ini menunjukkan bahwa kapasitas model yang lebih besar tidak dapat memperbaiki sampel yang memang ambigu. *Grid search* dan latihan (Wine, Breast Cancer, Digits) melengkapi perbandingannya.

**Bab 9 — Pemrosesan Teks dan Klasifikasi Multikelas.** Teks diubah menjadi matriks *sparse* berdimensi tinggi: `CountVectorizer` menghitung kata (*bag of words*), `TfidfVectorizer` menimbangnya dengan IDF lalu menormalisasi L2 (rumusnya dihitung ulang secara manual dan cocok), dan *n-gram* serta *POS tagging* menambahkan konteks. Pada Reuters, TF-IDF mengungguli BoW dengan classifier yang sama (0,903 vs 0,883). Klasifikasi 15 genre Brown hanya mencapai 0,23–0,33 karena beberapa genre cuma punya 3–5 dokumen latih; Naive Bayes bahkan runtuh ke dua genre. *One-vs-rest* (15 model) sedikit lebih baik daripada *one-vs-one* (105 model). Pada ulasan film, regresi logistik mencapai 0,803 dan koefisiennya memperlihatkan kata sentimen (*bad*, *worst*) maupun nama film yang dihafal.

**Bab 10 — Teknik *Clustering*.** K-means, *agglomerative clustering*, DBSCAN, *spectral clustering*, dan *Gaussian mixture* diterapkan pada data sintetis, sehingga hasil setiap algoritme bisa dilihat dan diukur dengan ARI. Dengan seed buku, dua pasang dari empat *blobs* saling menempel, sehingga *elbow*, *dendrogram*, dan *silhouette* sama-sama menunjuk struktur 2 kelompok. Pada *moons*, DBSCAN (ARI 0,96) dan *spectral* (1,0) jauh mengungguli K-means (0,24) dan GMM (0,53); pada lingkaran bersarang K-means gagal total. Metrik internal (*silhouette*) dan eksternal (ARI) bisa memilih jumlah *cluster* yang berbeda.

**Bab 11 — Deteksi *Novelty* dan *Outlier*.** *Isolation Forest* (panjang jalur isolasi), LOF (kepadatan lokal relatif), dan *One-Class SVM* (batas kernel) dibandingkan pada data simulasi. Reproduksi ini menemukan dua masalah di kode buku: data uji "normal" untuk *One-Class SVM* dibangkitkan di lokasi lain (±6σ dari data latih), sehingga 0 dari 100 diterima (91/100 jika dari distribusi yang sama); dan ROC-AUC dihitung dengan tanda skor terbalik (tercetak 0,0051, yang benar 0,9949). Strategi penanganan (hapus, median, *winsorization*) dibandingkan secara kuantitatif.

**Bab 12 — *Cross-Validation* dan Teknik Evaluasi Model.** k-fold, *stratified* k-fold, LOOCV, dan *nested* CV dijalankan dan sebaran skor fold ditampilkan. Selisih rata-rata antar-varian sering lebih kecil daripada sebaran antar-fold. *Nested* CV yang dicetak buku adalah $R^2$, bukan MSE seperti LOOCV di sel yang sama. *Grid* dan *randomized search* menemukan daerah C yang setara (selisih uji 1 sampel). *Learning curve* menunjukkan celah latih–CV menyempit ke 0,006 (bias tinggi), dan `random_state` di `learning_curve` tidak berpengaruh tanpa `shuffle=True`.

**Bab 13 — *Deploying* Model scikit-learn ke Produksi.** Model disimpan dan dimuat dengan `pickle`/`joblib` (identik, dengan versi scikit-learn tercatat di artefak), latensi dan *throughput* diukur (biaya tetap per panggilan mendominasi; `n_jobs=1` ±7–11 kali lebih cepat untuk satu sampel), model SGD dipantau dan diperbarui dengan `partial_fit`, dan *pipeline* diberi gerbang validasi. Sel tambahan memperlihatkan bahwa data "baru" buku adalah masalah klasifikasi lain (akurasi 0,30–0,38, dan pembaruan menjatuhkan akurasi data lama ke 0,440), metadata versi ditulis tangan ("1.3.2" padahal 1.5.2), *snapshot* validasi memakai data latih (1,000 vs *holdout* 0,956), dan gerbang CI memakai data acak (0,55 vs 0,880 dengan *holdout* sungguhan).

---

## Struktur Repositori

```text
scikit-learn-cookbook/
├── Chapter_01.ipynb
├── Chapter_02.ipynb
├── Chapter_03.ipynb
├── Chapter_04.ipynb
├── Chapter_05.ipynb
├── Chapter_06.ipynb
├── Chapter_07.ipynb
├── Chapter_08.ipynb
├── Chapter_09.ipynb
├── Chapter_10.ipynb
├── Chapter_11.ipynb
├── Chapter_12.ipynb
├── Chapter_13.ipynb
├── .gitignore
└── README.md
```

Semua dataset dibangkitkan di dalam kode atau dimuat melalui *dataset loader* scikit-learn. Tidak ada file data yang disimpan di repositori. California Housing (Bab 2) diunduh sekali pada eksekusi pertama dan disimpan di cache `~/scikit_learn_data`. Bab 9 memakai korpus NLTK (`movie_reviews`, `reuters`, `brown`, `punkt`, `punkt_tab`, `averaged_perceptron_tagger_eng`, `stopwords`) yang diunduh otomatis oleh kode buku ke `~/nltk_data` saat pertama kali dijalankan. Bab 13 menulis file artefak model (`*.joblib`, `*.pkl`, metadata) ke folder `artifacts_ch13/`, yang diabaikan Git lewat `.gitignore`.

---

## Cara Memulai

```bash
# 1. Clone repositori
git clone https://github.com/happhify/scikit-learn-cookbook.git
cd scikit-learn-cookbook

# 2. Buat dan aktifkan virtual environment (Python 3.10–3.13)
python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# 3. Instal versi pustaka persis yang dipakai untuk menghasilkan output
pip install scikit-learn==1.5.2 numpy==2.1.3 pandas==2.2.3 scipy==1.14.1 \
            matplotlib==3.9.4 seaborn==0.13.2 jupyter==1.0.0 notebook==6.5.4 ipykernel==6.23.1 \
            nltk==3.10.4

# 4. Jalankan Jupyter dan buka notebook bab mana pun
jupyter notebook
```

Untuk mengeksekusi ulang notebook dari command line (output ditulis ulang di file yang sama):

```bash
jupyter nbconvert --to notebook --execute --inplace Chapter_02.ipynb
```

Setiap notebook selesai dalam waktu jauh di bawah dua menit di laptop. Yang paling lambat adalah Bab 7 (≈ 1,5 menit), karena *grid search* atas SVM pada data tanpa penskalaan, dan Bab 9 (≈ 1 menit, ditambah unduhan korpus NLTK pada eksekusi pertama). Angka waktu di Bab 13 (latensi prediksi) bergantung pada mesin dan berubah setiap eksekusi.

---

## Lingkungan

Semua notebook dieksekusi dengan:

| Pustaka | Versi |
|---|---|
| Python | 3.13.5 |
| scikit-learn | 1.5.2 |
| NumPy | 2.1.3 |
| pandas | 2.2.3 |
| SciPy | 1.14.1 |
| Matplotlib | 3.9.4 |
| seaborn | 0.13.2 |
| nltk (Bab 9) | 3.10.4 |
| joblib | 1.6.0 |
| Jupyter / notebook / ipykernel | 1.0.0 / 6.5.4 / 6.23.1 |
| nbformat / nbconvert | 5.11.1 / 7.17.2 |

Bab 1–8 dieksekusi dengan Python 3.13.5; Bab 9–13 dieksekusi dengan Python 3.13 di Linux memakai versi pustaka yang sama persis (ditambah `nltk`). Versi-versi ini mengikuti `requirements.txt` repositori resmi (scikit-learn ≥ 1.5, jupyter 1.0.0, notebook 6.5.4, ipykernel 6.23.1), dengan NumPy, pandas, dan SciPy dikunci pada rilis dari periode yang sama dengan scikit-learn 1.5. Kode buku berjalan **tanpa perubahan API apa pun** pada scikit-learn 1.5.2. Satu-satunya peringatan adalah `UserWarning` tentang nama fitur yang tidak berbahaya, dijelaskan di Bab 5. Satu catatan kecil: di Bab 6, jumlah iterasi yang dilaporkan solver `lbfgs` pada data tanpa penskalaan sedikit berbeda dari satu eksekusi ke eksekusi lain (efek *floating-point* pada aljabar linear *multithreaded*). Prediksi dan metriknya tidak berubah.

---

## Referensi & Ucapan Terima Kasih

* Sukup, J. (2025). *scikit-learn Cookbook, Third Edition: Over 80 recipes for machine learning in Python with scikit-learn*. Packt Publishing.
* Repositori kode resmi: [PacktPublishing/Scikit-Learn-Cookbook-Third-Edition](https://github.com/PacktPublishing/Scikit-Learn-Cookbook-Third-Edition). Seluruh kode resep di notebook berasal dari repositori ini (Lisensi MIT); penjelasannya adalah tulisan saya sendiri.
* scikit-learn developers. *scikit-learn 1.5 User Guide and API Reference*: <https://scikit-learn.org/1.5/>
* Pedregosa, F. et al. (2011). Scikit-learn: Machine Learning in Python. *Journal of Machine Learning Research*, 12, 2825–2830.
* Makalah dan buku teks lainnya dikutip di bagian *Referensi* setiap notebook.

**Penggunaan alat AI.** Sesuai izin tugas, sebuah *large language model* (Claude dari Anthropic) membantu menulis penjelasan teori dan interpretasi output, menerjemahkannya ke Bahasa Indonesia, serta menyiapkan notebook. Untuk Bab 9–13, Claude juga menjalankan notebook, menulis sel pengecekan tambahan (bertag `added`), menemukan dan mencatat masalah pada kode buku, serta memeriksa dengan skrip bahwa sel kode buku identik dengan repositori resmi. Setiap interpretasi telah diperiksa terhadap output hasil eksekusi yang sebenarnya, dan setiap sel kode dijalankan di lingkungan yang tercantum di atas.

---

## Penulis

**Hadi Nugroho**
NIM 101032330235 — S1 Teknik Komputer, Telkom University
GitHub: [@happhify](https://github.com/happhify)
