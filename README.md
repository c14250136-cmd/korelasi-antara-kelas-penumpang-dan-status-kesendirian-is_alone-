# 🛳️ Titanic EDA (Exploratory Data Analysis)

## 📌 Deskripsi

Proyek ini bertujuan melakukan **Exploratory Data Analysis (EDA)** pada dataset Titanic menggunakan Python (Pandas, Matplotlib, Seaborn).
Analisis difokuskan pada faktor-faktor yang mempengaruhi kemungkinan penumpang untuk selamat, dengan tambahan variabel baru seperti **family\_size** dan **is\_alone**.

---

## 🔧 Variabel Tambahan

Dari dataset asli Titanic (Seaborn), ditambahkan dua variabel baru:

1. **`family_size`**

   * Rumus: `family_size = sibsp + parch + 1`
   * Makna: jumlah total anggota keluarga yang ikut di kapal (termasuk diri sendiri).
   * Contoh: jika seseorang punya 1 saudara (`sibsp=1`) dan 2 orang tua (`parch=2`), maka `family_size = 1+2+1 = 4`.

2. **`is_alone`**

   * Rumus: `is_alone = 1 jika family_size == 1 else 0`
   * Makna: indikator apakah penumpang bepergian sendirian atau bersama keluarga.

---

## 📊 Visualisasi Tambahan

### 1. Distribusi Family Size

![Distribusi Family Size](images/family_size.png)

Mayoritas penumpang memiliki `family_size` kecil (1–3 orang).
Ada juga sebagian besar penumpang yang bepergian sendirian (`family_size = 1`).

---

### 2. Survival Rate Berdasarkan Kelas & Status Kesendirian

![Barplot Class vs IsAlone](images/class_isalone_barplot.png)

* Penumpang **kelas 1** memiliki survival rate tertinggi, baik sendirian maupun bersama keluarga.
* Penumpang **kelas 3** yang sendirian memiliki survival rate paling rendah.
* Pola ini menunjukkan **kelas sosial sangat memengaruhi peluang keselamatan**, dan faktor keluarga memperkuat pola tersebut.

---

### 3. Heatmap Survival Rate: Class × Is Alone

![Heatmap Class vs IsAlone](images/class_isalone_heatmap.png)

* **First Class + Bersama Keluarga (is\_alone=0)** → survival rate mendekati **70%**.
* **Third Class + Sendirian (is\_alone=1)** → survival rate sangat rendah, di bawah **20%**.
* Data ini memperkuat bahwa **akses terhadap sekoci & bantuan lebih mudah didapat oleh penumpang kelas atas, apalagi jika bersama keluarga**.

---

## 📌 Kesimpulan

* Variabel tambahan `family_size` dan `is_alone` membantu menjelaskan perbedaan pola survival.
* **Kelas penumpang (`class`) berperan besar**: semakin tinggi kelas, semakin besar peluang selamat.
* Penumpang yang **sendirian di kelas rendah** paling rentan tidak selamat.
* Faktor **keluarga** memberi keuntungan karena kemungkinan besar mereka saling membantu dalam proses evakuasi.

---

Mau aku bikinin sekalian **versi code Colab final** (langsung save plot ke `images/` biar bisa dipakai di README ini)?
