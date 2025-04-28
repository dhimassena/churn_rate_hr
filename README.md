# Proyek Pertama: Menyelesaikan Permasalahan Human Resources
- **Nama:** [Dhimas Sena Rahmantara]
- **Email:** [dhimassr@gmail.com]
- **ID Dicoding:** [dhimassena]

## Business Understanding

### Latar Belakang Bisnis
Jaya Jaya Maju merupakan salah satu perusahaan multinasional yang telah berdiri sejak tahun 2000. Ia memiliki lebih dari 1000 karyawan yang tersebar di seluruh penjuru negeri. 

Walaupun telah menjadi menjadi perusahaan yang cukup besar, Jaya Jaya Maju masih cukup kesulitan dalam mengelola karyawan. Hal ini berimbas tingginya attrition rate (rasio jumlah karyawan yang keluar dengan total karyawan keseluruhan) hingga lebih dari **10%**.

Untuk mencegah hal ini semakin parah, manajer departemen HR ingin meminta bantuan Anda mengidentifikasi berbagai faktor yang mempengaruhi tingginya attrition rate tersebut. Selain itu, ia juga meminta Anda untuk membuat business dashboard untuk membantunya memonitori berbagai faktor tersebut.

### Permasalahan Bisnis
Beberapa permasalahan bisnis yang akan coba diselesaikan adalah sebagai berikut.
1. Apakah saja faktor yang menyebabkan karyawan keluar perusahaan?
2. Apakah attrition lebih sering terjadi pada karyawan dengan gaji tinggi atau rendah?
3. Apakah departemen tertentu memiliki tingkat attrition yang lebih tinggi?
4. Job Role mana saja yang memiliki tingkat attrition tertinggi?
5. Bagaimana perbandingan karyawan attrition laki-laki dan perempuan?
6. Apakah ada cara untuk mendeteksi karyawan yang akan melakukan attrition?

### Cakupan Proyek
Pengerjaan proyek ini mencakup beberapa hal, diantaranya:
1. **Melakukan Exploratory Data Analysis (EDA)** terhadap data attrition yang diberikan. Hal tersebut dilakukan agar mendapatkan insight mengenai pola attrition yang terjadi pada karyawan Jaya Jaya Maju.
2. **Membuat Model Machine Learning** untuk membantu Department HR mendeteksi karyawan dengan kemungkinan melakukan attrition.
3. **Membuat Visualisasi Dashboard** untuk agar dapat menampilkan kondisi terkini yang terjadi pada karyawan Jaya Jaya Maju.

### Persiapan
**Sumber Data**
Dataset yang dipakai adalah [Dataset Karyawan Jaya Jaya Maju] (https://raw.githubusercontent.com/dicodingacademy/dicoding_dataset/refs/heads/main/employee/employee_data.csv)

**Setup Environment**
Visualisasi Dashboard HR Jaya Jaya Maju dapat dijalan dengan langkah-langkah berikut.
1. Menjalankan `hr.ipynb`
   - Lihat file `requirements.txt` untuk melihat dependensi yang dibutuhkan.
   - Jalankan seluruh isi file `hr.ipynb` menggunakan Google Colab / Jupyter Notebook.
2. **Menjalankan Dashboard**:
   Pastikan sudah menginstal Docker pada komputer. Lalu ikuti langkah-langkah di bawah ini:
   - Jalankan perintah berikut
      ```
      docker pull metabase/metabase:latest
      ```
   - Jalankan container metabase menggunakan perintah
      ```
      docker run -p 3000:3000 --name humres metabase/metabase
      ```
   - Login ke Metabase menggunakan username dan password berikut:
      ```
      username: root@mail.com
      password: root123
      ```
---

## Business Dashboard
Hasil visualisasi dashboard yang telah dikerjakan dapat menunjukkan kondisi karyawan Jaya Jaya Maju secara real-time. Mulai dari kondisi jumlah karyawan, hubungan beberapa penyebab karyawan melakukan attrition, hingga prediksi karyawan dengan probabilitasnya jika akan melakukan attrition.

### Tutorial Mengakses Dashboard
**Menggunakan Metabase**
1. Buka metabase di browser dengan menggunakan Docker
2. Username dan Password untuk masuk ke Metabase dengan username:`root@mail.com`, password: `root123`

## Conclusion
Proyek ini berhasil menjawab beberapa pertanyaan bisnis seputar masalah attrition karyawan yang terjadi di Perusahaan Jaya Jaya Maju. Berikut ini adalah penjelasannya.
1. Apakah saja faktor yang menyebabkan karyawan keluar perusahaan?
   - Dari analisis dan prediksi yang dilakukan beberapa faktor karyawan melakukan attrition antara lain; lembur **(OverTime)**, usia **(Age)**, lama bekerja baik secara keseluruhan ataupun di Perusahaan Jaya Jaya Maju **(TotalWorkingYears & YearsAtCompany)**, hingga gaji bulanan **(MonthlyIncome)**.
2. Apakah attrition lebih sering terjadi pada karyawan dengan gaji tinggi atau rendah?
   - Mereka yang melakukan attrition dari sisi pendapatan adalah karyawan yang memiliki gaji yang cenderung rendah, yakni umumnya sekitar angka **US1000 s/d US6000**.
3. Apakah departemen tertentu memiliki tingkat attrition yang lebih tinggi?
   - Departemen yang memiliki tingkat attrition terbesar adalah Departemen **RnD** dengan **107** karyawan dan disusul Departemen **Sales** dengan **66** karyawan.
4. Job Role mana saja yang memiliki tingkat attrition tertinggi?
   - Terdapat 4 Job Role yang menyumbangkan angka attrition tertinggi. Diantaranya:
     * **Laboratory Technician, 49 orang**
     * **Sales Excecutive, 39 orang**
     * **Research Scientist, 38 orang**
     * **Sales Representative, 25 orang**
5. Bagaimana perbandingan karyawan attrition laki-laki dan perempuan?
   - Perbandingan antara karyawan attrition laki-laki dan perempuan terjadi lebih banyak pada karyawan laki-laki. Yakni dengan jumlah attrition laki-laki **108** orang berbanding **71** orang pada karyawan perempuan.
6. Apakah ada cara untuk mendeteksi karyawan yang akan melakukan attrition?
   - Terdapat cara mendeteksi hal tersebut adalah dengan melakukan prediksi dengan menggunakan model machine learning dan membuat visualisasi dashboard karyawan yang langsung dapat dipantau oleh HR Jaya Jaya Maju. Dimana dalam melakukan prediksi, model machine learning yang dikembangkan memiliki akurasi tertinggi sebesar **87%** dengan menggunakan algoritma Random Forest.

### Rekomendasi Action Items untuk Perusahaan
Berikut ini beberapa aksi / langkah yang dapat diambil Perusahaan Jaya Jaya Maju untuk menurunkan tingkat attrition yang terjadi.
1. Mengevaluasi jam kerja lembur **(OverTime)** karyawan.
2. Mengevaluasi kebijakan / beban kerja berdasarkan **Department** dan **Job Role**. Karena attrition pada beberapa department dan job role banyak terjadi dibandingkan dengan department dan job role lainnya.
3. Memberikan program probation / onboarding khususnya terhadap karyawan berusia muda / fresh graduate tentang budaya kerja Perusahaan Jaya Jaya Maju untuk meningkatkan motivasi dan semangat bekerja.
4. Mengevaluasi range salary karyawan dengan memperhatikan standar salary terhadap job role mereka. Atau bisa juga dengan memberikan bonus, insentif, atau tunjangan di samping gaji pokok yang mereka miliki.
