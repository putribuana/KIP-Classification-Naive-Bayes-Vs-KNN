# Perbandingan Naive Bayes vs KNN dalam Mengklasifikasikan Data Penerima Beasiswa KIP KULIAH

## Informasi Dataset
Dataset berisi 15 Kolom yaitu: 
1. NAMA MAHASISWA: Identitas mahasiswa.
2. JURUSAN: Bidang studi mahasiswa.
3. FORMULIR CALON PENERIMA: Status formulir beasiswa.
4. FC KTP: Salinan KTP mahasiswa.
5. FC KK: Salinan Kartu Keluarga mahasiswa.
6. KIP/KKS/PKH: Kepemilikan kartu bantuan sosial.
7. FC IJAZAH: Salinan ijazah terakhir.
8. PRESTASI: Riwayat prestasi akademik/non-akademik.
9. FOTO RUMAH: Foto tempat tinggal mahasiswa.
10. FC REK LISTRIK: Salinan rekening listrik.
11. S.TIDAK MAMPU: Status surat keterangan tidak mampu.
12. PK. ORANG TUA: Pekerjaan orang tua.
13. JUM UKT: Jumlah UKT yang harus dibayar.
14. TANGGUNGAN ORTU: Jumlah tanggungan orang tua.
15. STATUS DITERIMA: Status akhir permohonan beasiswa.

## Perbandingan Akurasi
- **Naive Bayes**: **73.75%**
- **KNN**: **95%**

KNN memiliki akurasi yang jauh lebih tinggi dibandingkan Naive Bayes.

---

## Analisis Kinerja Berdasarkan Report

### a) Naive Bayes
- **Kelas "TIDAK" (Tidak menerima beasiswa)**  
  - **Precision = 1.00** → Semua prediksi "TIDAK" benar.  
  - **Recall = 0.05** → Hanya **5% dari data "TIDAK" yang terdeteksi dengan benar** (sangat buruk).  
  - **F1-score = 0.09** → Kombinasi precision dan recall menunjukkan model sangat lemah dalam mengenali "TIDAK".

- **Kelas "YA" (Menerima beasiswa)**  
  - **Precision = 0.73** → 73% dari prediksi "YA" benar.  
  - **Recall = 1.00** → Semua data "YA" diklasifikasikan dengan benar.  
  - **F1-score = 0.85** → Model lebih cenderung memprediksi "YA" dibandingkan "TIDAK".

**Problem Naive Bayes**:  
- Model **hampir selalu memprediksi "YA"** karena recall kelas "TIDAK" sangat rendah.  
- **Bias terhadap kelas mayoritas** (overfitting ke "YA").  
- Tidak mampu menangani korelasi antar fitur karena asumsi **indepedensi fitur**.

---

### b) KNN
- **Kelas "TIDAK" (Tidak menerima beasiswa)**  
  - **Precision = 0.91** → 91% dari prediksi "TIDAK" benar.  
  - **Recall = 0.91** → 91% dari data "TIDAK" diklasifikasikan dengan benar.  
  - **F1-score = 0.91** → Model cukup baik dalam mengenali "TIDAK".

- **Kelas "YA" (Menerima beasiswa)**  
  - **Precision = 0.97** → 97% dari prediksi "YA" benar.  
  - **Recall = 0.97** → 97% dari data "YA" diklasifikasikan dengan benar.  
  - **F1-score = 0.97** → Model sangat baik dalam mengenali "YA".

**Keunggulan KNN**:  
- **Lebih akurat dibandingkan Naive Bayes**.  
- **Lebih baik dalam mengenali kedua kelas ("YA" dan "TIDAK")**.  
- Tidak mengasumsikan independensi fitur seperti Naive Bayes.
