# 📉 Customer Churn Monitoring & Segmentation

Project ini bertujuan untuk melakukan **monitoring churn customer** dan **segmentasi risiko churn** menggunakan data transaksi customer yang diambil langsung dari **Google Sheets** dan diproses dengan **Python**.

Customer dikategorikan **churn** apabila **tidak melakukan transaksi selama ≥ 3 bulan**.

---

## 🎯 Objective
- Mengidentifikasi customer yang sudah churn
- Membuat **segmentasi risiko churn**
- Menyediakan **early warning system** sebelum churn
- Menganalisis hubungan **complaint customer terhadap churn**
- Menyediakan visualisasi untuk **monitoring dan laporan manajemen**

---

## 🗂️ Data Source
Data diambil langsung dari **Google Sheets** menggunakan fitur **Publish to web (CSV)**.

### Struktur Data
| Kolom | Deskripsi |
|-----|---------|
| customer_id | ID unik customer |
| customer_name | Nama customer |
| complaint_flag | 0 = tidak komplain, 1 = pernah komplain |
| last_transaksi | Tanggal transaksi terakhir (format DD/MM/YYYY) |

---

## ⚙️ Business Rules
Aturan bisnis yang digunakan dalam analisis:

- **Active**  
  Customer masih melakukan transaksi (< 3 bulan)

- **Churn**  
  Tidak melakukan transaksi selama **≥ 3 bulan**

- **High Risk Churn**  
  Tidak melakukan transaksi selama **≥ 6 bulan**

- **Early Warning**  
  Tidak melakukan transaksi selama **2 bulan**

---

## 🧠 Data Processing
Langkah utama pengolahan data:
1. Load data dari Google Sheets (CSV)
2. Parsing tanggal transaksi (`dayfirst=True`)
3. Menentukan **reference date** (akhir bulan berjalan)
4. Menghitung `months_inactive`
5. Menentukan:
   - `churn_status`
   - `churn_segment`
   - `early_warning`

---

## 📊 Monitoring & Visualization
Project ini menghasilkan beberapa grafik utama:

### 1️⃣ Active vs Churn
Menampilkan perbandingan jumlah customer aktif dan churn.

### 2️⃣ Segmentasi Churn
Distribusi customer berdasarkan:
- Active
- Churn
- High Risk Churn

### 3️⃣ Complaint vs Churn
Analisis hubungan antara:
- Customer yang pernah komplain
- Status churn

### 4️⃣ Distribusi Lama Tidak Transaksi
Histogram jumlah bulan customer tidak melakukan transaksi.

### 5️⃣ Early Warning Churn
Monitoring customer yang:
- Masuk tahap warning
- Sudah churn
- Masih normal

Grafik-grafik ini digunakan untuk **pengambilan keputusan berbasis data**.

---

## 📁 Project Structure
