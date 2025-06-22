# Capstone Project: LLM Applications with Langchain and Data Analysis

## Project Overview
Proyek ini menunjukkan penerapan Model Bahasa Besar (LLM) untuk tugas pemrosesan bahasa alami dan integrasinya dengan alat analisis data. Inti dari proyek ini melibatkan penggunaan pustaka `langchain` untuk berinteraksi dengan LLM yang di-host di Replicate, melakukan tugas-tugas seperti klasifikasi teks, ekstraksi informasi, dan kueri bahasa alami dari Pandas DataFrame.

## Raw Dataset
Proyek ini menggunakan dataset yang dimuat dari `Archive1.zip`. File CSV ini berisi berbagai informasi terkait film termasuk Judul, Tahun, Sutradara, Durasi, Peringkat, Suara, Deskripsi, Bahasa, Negara, Anggaran_USD, BoxOffice_USD, Genre, Perusahaan_Produksi, Peringkat_Konten, Aktor_Utama, Jumlah_Penghargaan, dan Ulasan_Kritikus.

## Insights & Findings
Buku catatan ini menunjukkan beberapa wawasan utama mengenai kemampuan LLM dan integrasinya dengan analisis data:

* **Text Classification**: LLM dapat secara efektif mengklasifikasikan ulasan pelanggan ke dalam kategori sentimen (Positif, Negatif, Campuran) berdasarkan teks yang diberikan. Misalnya, "Kamera ponsel ini luar biasa, fotonya sangat jernih bahkan dalam kondisi kurang cahaya." diklasifikasikan sebagai "Positif".
* **Information Extraction**: LLM mampu mengekstrak entitas spesifik seperti nama, usia, dan pekerjaan dari deskripsi teks yang tidak terstruktur dan memformatnya menjadi objek JSON yang terstruktur. Contohnya termasuk mengekstraksi detail untuk "JessNoLimit", "Windah Basudara", dan "MiawAug".
* **Natural Language Interaction with DataFrames**: `create_pandas_dataframe_agent` memungkinkan pengguna untuk mengkueri dan memvisualisasikan data dalam Pandas DataFrame menggunakan perintah bahasa alami. Ini secara signifikan menurunkan hambatan bagi non-programmer untuk berinteraksi dengan data.
* **LLM Debugging and Self-Correction**: Agen Pandas menunjukkan kemampuan untuk mengidentifikasi impor yang hilang (seperti `matplotlib.pyplot`) dan mengoreksi kodenya sendiri untuk berhasil mengeksekusi perintah plotting.
* **Handling Empty Data**: Ketika mencoba memplot peringkat untuk tahun seperti 2015, di mana tidak ada data yang ada dalam cuplikan yang disediakan, agen dengan benar mengidentifikasi bahwa plot tidak akan menampilkan bilah, menunjukkan nol peringkat untuk tahun tersebut.

## AI Support Explanation
Dukungan AI utama dalam proyek ini disediakan oleh Model Bahasa Besar `ibm-granite/granite-3.3-8b-instruct`, yang diakses melalui platform Replicate. LLM ini digunakan melalui kelas `langchain_community.llms.Replicate`.

AI membantu dengan cara-cara berikut:

* **Natural Language Understanding (NLU)**: LLM memproses masukan teks seperti manusia (misalnya, ulasan pelanggan, deskripsi biografi, kueri analisis data).
* **Natural Language Generation (NLG)**: LLM menghasilkan respons yang dapat dibaca manusia, termasuk label klasifikasi, data JSON terstruktur, dan penjelasan tentang tindakan atau temuannya.
* **Problem-Solving (Agentic Behavior)**: `pandas_dataframe_agent` mencontohkan perilaku agen di mana LLM, bersama dengan alat (Python REPL), merencanakan dan melaksanakan langkah-langkah untuk mencapai tujuan pengguna, seperti menghasilkan plot dari DataFrame. Ini juga dapat melakukan koreksi diri dengan mengidentifikasi dan memperbaiki kesalahan dalam kode yang dihasilkannya.
