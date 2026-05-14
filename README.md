# 📊 AI-Employee-Sentiment-Analysis

Sistem otomatisasi analisis sentimen survei kepuasan karyawan berbasis **n8n** dan **Groq AI**. Workflow ini menerapkan prinsip **ETL** untuk mengolah ribuan feedback karyawan menjadi data analitik yang terstruktur.

---

## 🚀 Fitur Utama
* **Bulk Processing**: Menggunakan fitur *Looping* n8n untuk menangani ribuan data tanpa risiko timeout.
* **Structured Output**: Memaksa AI memberikan output JSON yang konsisten menggunakan *Structured Output Parser*.
* **Sentiment Categorization**: Mengklasifikasikan feedback ke dalam kategori: *Facilities, Management, Salary,* atau *Workload*.
* **Automated Action Plan**: AI memberikan rekomendasi tindakan nyata berdasarkan keluhan atau saran karyawan.
* **Data Write-back**: Sinkronisasi otomatis hasil analisis kembali ke Google Sheets secara real-time.

---

## 🛠️ Alur Kerja (Workflow)
1.  **Read Data**: Mengambil seluruh baris survei dari Google Sheets.
2.  **Looping**: Memproses baris satu per satu untuk menjaga stabilitas memori.
3.  **AI Analysis**: Analisis sentimen dan kategori feedback menggunakan LLM.
4.  **Formatting**: Mengubah hasil analisis menjadi skema JSON yang kaku (ENUM).
5.  **Update Data**: Menulis hasil (Sentimen, Kategori, Action Plan) kembali ke kolom yang sesuai di Google Sheets.

---

## ⚙️ Persiapan
* **n8n**: Import file `Survey Kepuasan Karyawan.json` ke instance n8n Anda.
* **Google Sheets**: Siapkan sheet dengan kolom `employee_id`, `feedback`, `sentiment`, `category`, dan `action_plan`.
* **AI Model**: Gunakan kredensial Groq.
---
