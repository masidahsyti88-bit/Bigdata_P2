Big Data Batch Processing with PySpark
Praktikum 2 – Batch Data Ingestion & Processing

📌 Deskripsi Project
Project ini merupakan implementasi Batch Data Processing menggunakan Apache Spark (PySpark) untuk memproses data transaksi e-commerce.
Pipeline ini mensimulasikan arsitektur data engineering sederhana dengan pendekatan Data Lake Architecture yang terdiri dari:
Raw Layer
Clean Layer
Curated Layer
Tujuan utama praktikum ini adalah memahami konsep batch processing, optimasi menggunakan format Parquet, serta teknik partitioning untuk meningkatkan performa query.

🏗️ Arsitektur Pipeline
Alur pipeline:
Raw CSV → Data Cleaning → Transformasi → Simpan ke Parquet
                               ↓
                      Agregasi & Analitik
                               ↓
                    Curated Business Output

Struktur folder:
bigdata-project/
│
├── data/
│   ├── raw/
│   ├── clean/
│   │   ├── parquet/
│   │   └── partitioned_by_category/
│   └── curated/
│       ├── top_products/
│       ├── category_revenue/
│       └── avg_transaction/
│
├── scripts/
│   └── batch_pipeline_enterprise.py
│
└── logs/
⚙️ Teknologi yang Digunakan
Python 3
PySpark
Parquet Format
Git & GitHub
WSL Ubuntu

📊 Proses yang Dilakukan
1️⃣ Data Ingestion
Membaca dataset ecommerce_raw.csv menggunakan Spark DataFrame.

2️⃣ Data Cleaning
Menghapus null values
Validasi tipe data
Filtering data tidak valid

3️⃣ Penyimpanan ke Parquet
Data disimpan dalam format Parquet karena:
Lebih kecil ukurannya (compression)
Column-based storage
Lebih cepat untuk analitik

4️⃣ Partitioning
Data dipartisi berdasarkan kolom category menggunakan:
.partitionBy("category")

Tujuan:
Mendukung Partition Pruning
Mengurangi pembacaan data yang tidak diperlukan
Meningkatkan performa query

5️⃣ Agregasi & Analitik
Pipeline menghasilkan:
🔝 Top 5 Produk berdasarkan total quantity
💰 Total Revenue per Category
📈 Rata-rata nilai transaksi per customer

📈 Insight Bisnis
Dari hasil agregasi diperoleh:
Produk dengan quantity tertinggi menunjukkan item paling diminati pelanggan.
Kategori dengan revenue terbesar berkontribusi signifikan terhadap pendapatan.
Rata-rata transaksi membantu mengidentifikasi customer bernilai tinggi.
Pipeline ini menunjukkan bagaimana data engineering mendukung pengambilan keputusan berbasis data.

▶️ Cara Menjalankan
Aktifkan virtual environment:
source venv/bin/activate
Jalankan pipeline:
python scripts/batch_pipeline_enterprise.py
Jika berhasil, akan muncul:

PIPELINE COMPLETED SUCCESSFULLY
Total Execution Time: X seconds

🎯 Tujuan Pembelajaran
Melalui praktikum ini, mahasiswa memahami:
Konsep Batch Processing
Implementasi Spark DataFrame
Optimasi dengan Parquet
Konsep Partition Pruning
Simulasi Data Lake sederhana

👩‍💻 Author

Syti Masidah
230104040060
Big Data & Data Engineering Practice
