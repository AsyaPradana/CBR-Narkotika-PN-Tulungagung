# :pill: CBR-Narkotika-PN-Tulungagung :syringe:

## 📌 Deskripsi Proyek

Proyek ini merupakan implementasi **Case-Based Reasoning (CBR)** untuk analisis dan pencarian putusan perkara narkotika pada Pengadilan Negeri Tulungagung.

Sistem dibangun menggunakan pendekatan:

* Case Base Construction
* Case Representation
* Case Retrieval
* Case Solution Reuse
* Model Evaluation

Dataset yang digunakan berupa putusan perkara narkotika yang diperoleh dari Direktori Putusan Mahkamah Agung Republik Indonesia dan telah diproses menjadi basis kasus terstruktur.

---

## Tujuan

Membangun sistem yang mampu:

1. Menyimpan putusan sebagai basis kasus.
2. Merepresentasikan setiap kasus dalam bentuk fitur terstruktur.
3. Menemukan kasus lama yang paling mirip dengan kasus baru.
4. Memberikan rekomendasi putusan berdasarkan kasus terdahulu.
5. Mengevaluasi performa retrieval dan prediksi.

---

## Struktur Repository

```text
CBR-Narkotika-PN-Tulungagung/
│
├── data/
│   ├── raw/
│   │   ├── case_001.txt
│   │   ├── case_002.txt
│   │   └── ...
│   │
│   ├── processed/
│   │   ├── cases.csv
│   │   └── cases.json
│   │
│   ├── eval/
│   │   ├── queries.json
│   │   ├── retrieval_metrics.csv
│   │   └── prediction_metrics.csv
│   │
│   └── results/
│       └── predictions.csv
│
├── notebooks/
│   ├── Tahap1_CaseBased.ipynb
│   ├── Tahap2_CaseRepresentation.ipynb
│   ├── Tahap3_CaseRetrieval.ipynb
│   ├── Tahap4_CaseSolutionReuse.ipynb
│   └── Tahap5_ModelEvaluation.ipynb
│
├── logs/
│   └── cleaning.log
│
├── .gitignore
├── README.md
└── requirement.txt
```

---

# Metodologi

## :one: Case Base Construction

Tujuan:

* Mengumpulkan dan membersihkan dokumen putusan.
* Mengubah dokumen menjadi format teks yang siap diproses.

Output:

* File TXT pada folder:

```text
data/raw/
```

---

## :two: Case Representation

Tujuan:

* Mengekstraksi metadata putusan.
* Mengekstraksi informasi hukum penting.
* Melakukan feature engineering.

Fitur yang diekstraksi:

* Nomor perkara
* Pasal
* Terdakwa
* Dakwaan
* Putusan
* Jumlah kata

Output:

```text
data/processed/cases.csv
data/processed/cases.json
```

---

## :three: Case Retrieval

Tujuan:

Menemukan kasus lama yang paling mirip dengan query baru.

Metode:

* TF-IDF Vectorization
* Cosine Similarity

Fungsi utama:

```python
retrieve(query, k=5)
```

Output:

* Top-k kasus paling relevan.

---

## :four: Case Solution Reuse

Tujuan:

Menggunakan solusi dari kasus lama untuk membantu memprediksi hasil kasus baru.

Metode:

* Majority Voting
* Weighted Similarity

Fungsi utama:

```python
predict_outcome(query)
```

Output:

```text
data/results/predictions.csv
```

---

## :five: Model Evaluation

Tujuan:

Mengukur performa sistem retrieval dan prediksi.

Metrik:

* Accuracy
* Precision
* Recall
* F1-Score

Output:

```text
data/eval/retrieval_metrics.csv
data/eval/prediction_metrics.csv
```

---

# 💻 Instalasi

Clone repository:

```bash
git clone https://github.com/AsyaPradana/CBR-Narkotika-PN-Tulungagung.git

cd CBR-Narkotika-PN-Tulungagung
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

# 📄 Requirements

Contoh isi requirements.txt:

```text
pandas
numpy
scikit-learn
matplotlib
nltk
transformers
torch
tqdm
```

---

# 💻 Cara Menjalankan Pipeline

## Tahap 1

Buka notebook:

```text
notebooks/Tahap1_CaseBased.ipynb
```

Jalankan seluruh cell untuk melakukan preprocessing dokumen.

---

## Tahap 2

Buka:

```text
notebooks/Tahap2_CaseRepresentation.ipynb
```

Output:

```text
data/processed/cases.csv
data/processed/cases.json
```

---

## Tahap 3

Buka:

```text
notebooks/Tahap3_CaseRetrieval.ipynb
```

Contoh penggunaan:

```python
retrieve(
    "perantara jual beli sabu",
    k=5
)
```

---

## Tahap 4

Buka:

```text
notebooks/Tahap4_CaseSolutionReuse.ipynb
```

Contoh:

```python
predict_outcome(
    "memiliki narkotika golongan I"
)
```

---

## Tahap 5

Buka:

```text
notebooks/Tahap5_ModelEvaluation.ipynb
```

Contoh:

```python
metrics = evaluate_retrieval(
    queries,
    k=5
)

print(metrics)
```

---

# 📊 Hasil Retrieval

Input Query:

```text
perantara jual beli sabu
```

Output:

```text
Case ID: 42
Similarity: 0.34
```

---

# 📊 Hasil Evaluasi

Metrik evaluasi disimpan pada:

```text
data/eval/retrieval_metrics.csv
data/eval/prediction_metrics.csv
```

Contoh hasil:

| Metric    | Score |
| --------- | ----- |
| Accuracy  | 0.20  |
| Precision | 1.00  |
| Recall    | 0.20  |
| F1-Score  | 0.33  |

---

# Teknologi yang Digunakan

* Python
* Pandas
* NumPy
* Scikit-Learn
* Matplotlib
* NLTK
* Google Colab
* GitHub

---

### Dibuat oleh Asya Cahya Pradana (202210370311041) -  Penalaran Komputer A 

