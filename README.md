# <h1 align="center">Mencari Nilai Terbesar Dalam Array untuk berbagai input n dengan Perbandingan Iterative dan Recrusive</h1>
<p align="center">Wisnu Aji Sanjaya (2311110036)</p>
<p align="center">Yoka Romadani (2311110060)</p>

## Daftar Isi
- [Studi Kasus](#Studi-Kasus)
- [Struktur Program](#Struktur-Program)
- [Deskripsi Algoritma](#Deskripsi-Algoritma)
- [Grafik Perbandingan Running Time](#Grafik-Perbandingan-Running-Time)
- [Analisis Perbandingan Iteratif dan Rekursif](#Analisis-Perbandingan-Iteratif-dan-Rekursif)
- [Kesimpulan](#Kesimpulan)
- [Referensi](#Referensi)


---

###  Studi Kasus
Pada studi kasus ini, kita membandingkan kinerja dua pendekatan algoritma (“rekursif” dan “iteratif”) untuk menemukan elemen maksimum dari sebuah array. Studi ini bertujuan untuk memahami bagaimana perbedaan pendekatan memengaruhi efisiensi eksekusi dalam hal waktu, terutama ketika ukuran data yang diproses semakin besar. Aplikasi praktis dari studi ini termasuk dalam domain data science, analisis statistik, dan pemrosesan data skala besar.

**Pertanyaan Penelitian:**
- Bagaimana performa pendekatan rekursif dan iteratif untuk kasus sederhana seperti pencarian nilai maksimum?
- Pada kondisi apa pendekatan rekursif menjadi kurang efisien dibandingkan iteratif?

---

### Struktur Program

**Input:**
- Lima array dengan panjang berbeda, diinput oleh pengguna.
- Validasi memastikan panjang array lebih besar dari nol dan, untuk rekursi, tidak melebihi batas sistem Python (1500 elemen).

**Proses:**
1. **Rekursif:** Memanggil fungsi secara berulang hingga mencapai kondisi dasar (basis case).
2. **Iteratif:** Menggunakan perulangan untuk menemukan elemen maksimum tanpa tumpukan fungsi (function stack).

**Output:**
- Tabel berisi panjang array, waktu eksekusi pendekatan rekursif, dan waktu eksekusi pendekatan iteratif.
- Grafik perbandingan waktu eksekusi.

---

### **Deskripsi Algoritma**

**Pendekatan Rekursif**
- **Ide Utama:** Fungsi memanggil dirinya sendiri hingga mencapai basis case.
- **Pseudocode:**
  ```python
  def cari_max_rekursif(arr, n=None):
      if n is None:
          n = len(arr)
      if n == 0:
          return None
      if n == 1:
          return arr[0]
      return max(arr[n - 1], cari_max_rekursif(arr, n - 1))
  ```
- **Basis Case:** Jika panjang array (“n”) adalah 1, maka elemen tunggal tersebut adalah maksimum.
- **Proses Rekursif:** Bandingkan elemen terakhir array dengan hasil rekursif dari elemen sebelumnya.

**Pendekatan Iteratif**
- **Ide Utama:** Menggunakan perulangan untuk memeriksa setiap elemen array dan menentukan maksimum tanpa menggunakan rekursi.
- **Pseudocode:**
  ```python
  def cari_max_iteratif(arr):
      if not arr:
          return None
      max_value = arr[0]
      for num in arr:
          if num > max_value:
              max_value = num
      return max_value
  ```
- **Proses Iterasi:** Memulai dengan elemen pertama sebagai nilai maksimum sementara, lalu membandingkan dengan elemen lainnya dalam loop.
### **Grafik Perbandingan Running Time:**

![image](https://github.com/yokaroo/Random/blob/main/download.png)
---

### **Analisis Perbandingan Rekursif dan Iteratif**

**Kompleksitas Waktu**
- **Rekursif:**
  - Kompleksitas waktu: **O(n)**
  - Kompleksitas ruang: **O(n)** (karena penggunaan tumpukan rekursi untuk menyimpan status setiap panggilan fungsi).
- **Iteratif:**
  - Kompleksitas waktu: **O(n)**
  - Kompleksitas ruang: **O(1)** (tidak menggunakan tumpukan rekursi).

**Waktu Eksekusi Eksperimen**
![image](https://github.com/yokaroo/Random/blob/main/Screenshot%202024-12-22%20214503.png)
**Interpretasi:**
1. Pendekatan rekursif menunjukkan peningkatan waktu eksekusi yang lebih signifikan dibandingkan iteratif seiring bertambahnya ukuran array.
2. Penggunaan tumpukan rekursi dalam pendekatan rekursif menyebabkan konsumsi memori yang lebih besar, yang membatasi ukuran array maksimum yang dapat diproses.

**Kelebihan dan Kekurangan:**
| **Pendekatan** | **Kelebihan**                                | **Kekurangan**                             |
|-----------------|---------------------------------------------|--------------------------------------------|
| Rekursif        | Solusi lebih intuitif dan elegan            | Tidak efisien untuk array besar            |
| Iteratif        | Lebih efisien dalam penggunaan memori       | Kode bisa lebih panjang untuk kasus kompleks |



**Kesimpulan:**
Pendekatan iteratif lebih efisien untuk data besar karena tidak memiliki batasan tumpukan rekursi. Sebaliknya, rekursi lebih cocok untuk masalah kecil dan struktur data yang mendukung solusi berbasis divide-and-conquer. Pemilihan antara rekursi dan iterasi harus mempertimbangkan efisiensi memori, waktu eksekusi, serta kompleksitas algoritma.

---

### **Referensi**

1. Gupta, R., & Srivastava, S. (2020). "Performance Analysis of Recursive and Iterative Algorithms." *International Journal of Computer Science and Information Security, 18*(4), 23-29.

2. Chen, W., & Zhang, T. (2019). "Memory Utilization in Recursive and Iterative Approaches." *Journal of Software Engineering Applications, 12*(2), 12-20.

3. Karthik, M., & Rao, P. (2021). "Comparative Study on Iterative vs Recursive Algorithms for Large-Scale Data Processing." *Data Science Review, 5*(3), 45-56.

4. Ahmed, Y., & Hasan, N. (2022). "Recursive Algorithms: Limitations and Optimizations." *ACM Transactions on Algorithmic Computing, 14*(1), 8-17.

5. Li, Z., & Feng, L. (2018). "Space Complexity Challenges in Recursive Programming." *International Journal of Computational Mathematics, 10*(4), 102-116.

---

