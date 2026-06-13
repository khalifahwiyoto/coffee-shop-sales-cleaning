# ☕ Coffee Shop Sales Analysis (End-to-End Project)

## 📌 Deskripsi Proyek
Proyek ini bertujuan untuk menganalisis **149.116 baris data transaksi** dari sebuah bisnis kedai kopi (*coffee shop*). Analisis dilakukan secara *end-to-end* mulai dari database hingga visualisasi untuk menemukan tren penjualan, jam sibuk cabang (*Golden Hours*), serta performa produk untuk membantu manajemen mengambil keputusan bisnis yang tepat.

## 🛠️ Tech Stack & Alur Kerja
1. **SQL (SQLite):** Digunakan untuk *Data Ingestion* awal dan agregasi berat seperti mencari produk dan kategori terlaris menggunakan perintah `GROUP BY` & `ORDER BY`.
2. **Python (Pandas di Google Colab):** Digunakan untuk *Data Cleaning* tingkat lanjut, rekayasa fitur waktu (`transaction_datetime` & `transaction_hour`), serta menangani eror format tipe data.
3. **Power BI / Tableau:** *(Tahap Selanjutnya)* Digunakan untuk membuat dashboard interaktif bertema kopi guna menyajikan metrik bisnis (KPI) secara visual.

## 💡 Tantangan Data Cleaning yang Berhasil Diatasi
Saat memproses kolom `transaction_date` di Python, sempat terjadi `ValueError` karena Pandas mencoba membaca data dengan format standar Amerika (Bulan/Hari/Tahun). Isu ini berhasil saya selesaikan dengan menerapkan argumen `format='mixed'` dan `dayfirst=True` agar Python mengenali secara akurat bahwa angka di depan adalah Hari (format Hari/Bulan/Tahun). 

Selain itu, kolom jam yang keras kepala berwujud `object` berhasil dijinakkan dengan menyatukannya ke dalam satu kolom kesatuan berjenis `datetime64[ns]` resmi.
