# Proyek Akhir: Menyelesaikan Permasalahan Perusahaan Edutech

## Business Understanding
Jaya Jaya Institut, sebuah institusi pendidikan tinggi yang berdiri sejak tahun 2000, telah berhasil meluluskan banyak mahasiswa berprestasi di berbagai bidang selama lebih dari dua dekade. Namun, seperti banyak institusi pendidikan lainnya, mereka menghadapi tantangan besar dalam mengatasi tingginya angka mahasiswa yang tidak menyelesaikan studi atau mengalami dropout.

Masalah dropout ini menjadi perhatian serius karena dapat berdampak pada citra institusi, menurunkan tingkat kelulusan, serta memengaruhi daya tarik bagi calon mahasiswa di masa depan. Selain itu, angka dropout yang tinggi juga dapat menunjukkan adanya permasalahan mendasar dalam proses penerimaan mahasiswa, sistem pembelajaran, atau dukungan akademik yang diberikan oleh institusi.

### Permasalahan Bisnis

Berikut adalah beberapa pertanyaan yang mencerminkan permasalahan bisnis yang ingin diselesaikan oleh Jaya Jaya Institut:
1. Bagaimana metode yang dapat digunakan untuk mendeteksi sejak dini mahasiswa yang berisiko mengalami dropout?
2. Faktor apa saja yang memiliki pengaruh terbesar terhadap keputusan mahasiswa untuk berhenti kuliah?
3. Langkah apa yang dapat diterapkan untuk meningkatkan tingkat retensi mahasiswa dan mendorong lebih banyak mahasiswa menyelesaikan studinya?

### Cakupan Proyek

- **Analisis Data :** Menggunakan data yang ada untuk mengidentifikasi faktor-faktor utama yang mempengaruhi dropout.
- **Visualisasi & Pelaporan :** Mengembangkan dashboard yang dapat digunakan untuk memonitor dan menganalisis faktor-faktor tersebut secara visual.
- **Rekomendasi & Intervensi :** Berdasarkan hasil analisis, memberikan rekomendasi untuk intervensi yang dapat dilakukan untuk mengurangi droput.

### Persiapan

Sumber data: dataset yang digunakan merupakan dataset [Jaya Jaya Institut](https://github.com/dicodingacademy/dicoding_dataset/tree/main/students_performance).

* Setup conda environment:

    ```
    conda create --name myenv python=3.9
    conda activate myenv #MacOS
    conda activate myenv  # Windows
    ```
* Install requirements:
    ```
    pip install -r requirements.txt
    ```
* Setup metabase:
    ```
    docker pull metabase/metabase:v0.46.4
    docker run -p 3000:3000 --name metabase metabase/metabase
    ```
    Akses metabase pada http://localhost:3000/setup dan lakukan setup.

* Setup database (supabase):

    * Buat akun dan login https://supabase.com/dashboard/sign-in.
    * Klik new project
    * Copy URI pada database setting
    * Kirim dataset menggunakan sqlalchemy 
    ```python
    from sqlalchemy import create_engine
 
    URL = "DATABASE_URL"
    
    engine = create_engine(URL)
    dataset.to_sql('dataset', engine)
    ```

## Business Dashboard
Dashboard ini dirancang untuk memberikan wawasan menyeluruh kepada institusi mengenai faktor-faktor yang berkontribusi terhadap status mahasiswa, baik yang dropout, masih terdaftar (enrolled), maupun yang telah lulus (graduated). Dengan adanya dashboard ini, tim institusi dapat:
1. Memantau Tingkat Dropout Secara Proaktif:
- Melalui visualisasi data mengenai persentase mahasiswa yang dropout, masih terdaftar, dan sudah lulus, institusi dapat memantau tren dropout secara real-time. Hal ini memungkinkan pengambilan tindakan cepat jika terjadi peningkatan signifikan dalam tingkat dropout.
2.  Menganalisis Faktor-Faktor yang Mempengaruhi Dropout:
- Dengan analisis mendalam terkait pengaruh faktor seperti nilai akademik, beasiswa, biaya pendidikan, serta latar belakang pendidikan orang tua terhadap status mahasiswa, tim dapat mengidentifikasi elemen-elemen yang berisiko. Dengan demikian, institusi dapat menyesuaikan kebijakan dan strategi intervensi agar lebih efektif dalam mengurangi angka dropout.

  <img width="768" alt="Zefanya Danovanta Tarigan-Dashboard" src="https://github.com/user-attachments/assets/c310e88f-3487-45bf-b7a9-0dec0207677f" />

### Sistem Machine Learning
Untuk menjalankan prototype sistem machine learning yang telah dikembangkan, ikuti langkah-langkah berikut:

Prototype ini telah disiapkan untuk melakukan prediksi berdasarkan model yang telah dibuat. Untuk menjalankannya secara lokal, gunakan perintah berikut di terminal:
`streamlit run app.py`
  <img width="890" alt="Screenshot 2025-02-10 at 14 53 27" src="https://github.com/user-attachments/assets/6ab3f54f-7dd1-42b6-b7c6-bcbc343dd7ef" />

Selain itu, juga dapat mengakses prototype melalui tautan berikut: [Prototype Machine Learning](https://penerapandatascience2-g86gjaa3wdu7fyam5jpn6i.streamlit.app/)

## Conclusion

1. Bagaimana metode yang dapat digunakan untuk mendeteksi sejak dini mahasiswa yang berisiko mengalami dropout ?
* **Jawaban :** Dengan mengembangkan model prediktif menggunakan algoritma seperti Random Forest, Jaya Jaya Institut dapat mendeteksi siswa yang berisiko mengalami dropout sejak awal. Model ini dapat mengidentifikasi siswa berisiko dengan tingkat akurasi yang cukup baik berdasarkan data historis serta faktor-faktor demografis, akademik, dan ekonomi.
  
2. Faktor apa saja yang memiliki pengaruh terbesar terhadap keputusan mahasiswa untuk berhenti kuliah?
- **Jawaban :** Analisis korelasi dan kontribusi fitur dalam model prediktif mengungkapkan bahwa beberapa faktor utama yang mempengaruhi keputusan siswa untuk dropout antara lain latar belakang akademik (seperti nilai dan jumlah mata kuliah yang diambil) serta kondisi ekonomi (seperti beasiswa atau status displaced). Sebagai contoh, siswa yang mengalami kesulitan akademik pada semester pertama atau kedua cenderung memiliki kemungkinan lebih besar untuk dropout.

  <img width="1049" alt="Screenshot 2025-02-10 at 14 52 28" src="https://github.com/user-attachments/assets/dd34f9bf-e919-4000-ba48-95d187b70eb7" />

3. Langkah apa yang dapat diterapkan untuk meningkatkan tingkat retensi mahasiswa dan mendorong lebih banyak mahasiswa menyelesaikan studinya?
- **Jawaban : ** erdasarkan temuan dari model dan analisis data, Jaya Jaya Institut dapat meningkatkan tingkat retensi siswa dengan menerapkan beberapa strategi, seperti menawarkan bimbingan akademik yang lebih intensif, menyesuaikan kurikulum untuk mengurangi beban belajar siswa, dan memberikan dukungan finansial ekstra bagi siswa yang membutuhkan. Intervensi yang lebih awal dan berbasis data akan membantu memastikan lebih banyak siswa berhasil menyelesaikan pendidikan mereka.

### Rekomendasi Action Items

Berikut beberapa rekomendasi action items yang dapat dilakukan institusi untuk mengatasi permasalahan dan mencapai target mereka:

1. **Penerapan Sistem Pemantauan Siswa Berbasis Data**
- Menggunakan model prediktif yang telah dikembangkan untuk melakukan pemantauan berkala terhadap mahasiswa. Dengan sistem ini, institusi dapat mengidentifikasi mahasiswa yang berisiko tinggi mengalami dropout dan memberikan intervensi lebih awal, seperti bimbingan akademik atau dukungan lainnya.
2. **Penguatan Program Dukungan Akademik dan Psikologis**
- Berdasarkan faktor risiko yang telah diidentifikasi, institusi perlu meningkatkan program dukungan akademik dan psikologis. Langkah ini dapat mencakup perluasan akses ke layanan bimbingan belajar, sesi konseling, serta dukungan kesehatan mental bagi mahasiswa yang rentan.
3. **Optimalisasi Kurikulum dan Program Studi**
- Melakukan evaluasi terhadap program studi dengan tingkat dropout yang tinggi dan menyesuaikan kurikulum atau metode pembelajaran. Misalnya, meningkatkan fleksibilitas dalam penjadwalan mata kuliah atau menyediakan materi pendukung tambahan untuk mengurangi tekanan akademik pada mahasiswa.


Link Dashboard : [Jaya Jaya Institut Dashboard](https://lookerstudio.google.com/reporting/75e065a4-0ce4-4850-a4c2-e149e1b33787/page/6U9oE/edit)
