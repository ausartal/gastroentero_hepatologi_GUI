<div align="center">

# Sistem Pakar Gastroentero-Hepatologi

### Aplikasi GUI Java Swing — Diagnosis penyakit berbasis Decision Tree

[![Java](https://img.shields.io/badge/Java-21-ED8B00?logo=openjdk&logoColor=white)](https://openjdk.org/)
[![Maven](https://img.shields.io/badge/Maven-3.9-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)
[![Swing](https://img.shields.io/badge/UI-Java%20Swing-3776AB?logo=java&logoColor=white)](https://docs.oracle.com/javase/tutorial/uiswing/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Sistem pakar edukatif untuk mata kuliah **Artificial Intelligence**.  
Pengguna memilih gejala klinis, lalu mesin inferensi Decision Tree memberikan rekomendasi diagnosis beserta jalur keputusannya.

</div>

---

## Preview

<div align="center">
  <img src="assets/screenshots/main-gui.png" alt="Tampilan utama Sistem Pakar" width="820">
</div>

## Fitur

- Antarmuka modern (kartu gejala, badge kategori, panel hasil).
- **Checklist gejala** yang dijelaskan dalam bahasa natural.
- Mesin **Decision Tree** dengan cabang Infeksi / Non-Infeksi.
- Hasil diagnosis: nama penyakit, kategori, confidence, dan gejala pendukung.
- Tombol **Diagnosa** dan **Reset** untuk eksperimen cepat.
- Dibangun dengan Java 21 + Swing (Look & Feel Nimbus).

## Basis Pengetahuan

| Kategori | Penyakit | Contoh gejala |
|---|---|---|
| Infeksi | Influenza | Demam, batuk, pilek, sakit tenggorokan |
| Infeksi | Demam Berdarah | Demam tinggi, nyeri sendi, ruam, mual |
| Non-Infeksi | Diabetes | Sering haus, sering BAK, lelah, luka sulit sembuh |
| Non-Infeksi | Hipertensi | Sakit kepala, pusing, penglihatan kabur, TD tinggi, mimisan |

Struktur pohon:

```text
Diagnosa Penyakit
├── Infeksi
│   ├── Influenza
│   └── Demam Berdarah
└── Non-Infeksi
    ├── Diabetes
    └── Hipertensi
```

## Struktur Repository

```text
gastroentero_hepatologi_GUI/
├── assets/screenshots/          # Preview GUI untuk dokumentasi
├── src/main/java/com/mycompany/gastroentero_hepatologi/
│   ├── Gastroentero_Hepatologi.java   # Entry point
│   ├── MainFrame.java                 # Window utama
│   ├── SymptomPanel.java              # Form pemilihan gejala
│   ├── ResultPanel.java               # Panel hasil diagnosis
│   ├── InferenceEngine.java           # Mesin inferensi
│   ├── KnowledgeBase.java             # Gejala, penyakit, pohon keputusan
│   ├── DecisionTreeNode.java
│   ├── DiagnosisResult.java
│   ├── Disease.java
│   └── Symptom.java
├── pom.xml
├── LICENSE
└── README.md
```

## Cara Menjalankan

Prasyarat: **JDK 21+** dan **Maven 3.9+**.

```bash
git clone https://github.com/ausartal/gastroentero_hepatologi_GUI.git
cd gastroentero_hepatologi_GUI

# Kompilasi
mvn -q -DskipTests compile

# Jalankan GUI
mvn -q exec:java
# atau
java -cp target/classes com.mycompany.gastroentero_hepatologi.Gastroentero_Hepatologi
```

### Alur penggunaan

1. Centang gejala yang dialami pasien di panel kiri.
2. Tekan **Diagnosa**.
3. Baca hasil di panel kanan: penyakit terduga, kategori, dan skor kecocokan.

## Arsitektur

| Komponen | Tanggung jawab |
|---|---|
| `KnowledgeBase` | Dataset gejala, penyakit, dan struktur Decision Tree |
| `InferenceEngine` | Traversal pohon + scoring berdasarkan gejala terpilih |
| `SymptomPanel` | Interaksi checklist gejala |
| `ResultPanel` | Visualisasi hasil diagnosis |

## Catatan

Implementasi ini ditujukan untuk **pembelajaran sistem pakar dan Decision Tree**, bukan untuk diagnosis medis nyata.

## Penulis

**Ahmad Nabah Falah** — [@ausartal](https://github.com/ausartal)
