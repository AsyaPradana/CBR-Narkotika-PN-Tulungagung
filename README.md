# Case Based Reasoning Narkotika PN Tulungagung

## Deskripsi

Implementasi Case-Based Reasoning (CBR) untuk analisis putusan perkara narkotika pada Pengadilan Negeri Tulungagung.

## Struktur Repository

data/
├── raw/              # hasil ekstraksi teks putusan
└── processed/        # hasil representasi kasus

notebooks/
├── Tahap1_CaseBase.ipynb
└── Tahap2_CaseRepresentation.ipynb

README.md

## Tahap 1 - Membangun Case Base

* Mengunduh 50 putusan narkotika dari Direktori Putusan Mahkamah Agung
* Konversi PDF ke TXT
* Pembersihan teks
* Validasi hasil ekstraksi

## Tahap 2 - Case Representation

* Ekstraksi metadata
* Ekstraksi fakta hukum
* Penyimpanan ke CSV/JSON

## Tools

* Python
* Google Colab
* pandas
* pdfplumber
* scikit-learn
