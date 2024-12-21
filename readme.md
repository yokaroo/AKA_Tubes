```
import time
import matplotlib.pyplot as plt
from prettytable import PrettyTable
```
### Program membandingkan kinerja algoritma rekursif dan iteratif dalam menghitung Array terbesar untuk berbagai nilai input n
```
# Rekursif
def cari_max_rekursif(arr, n=None):
    if n is None:
        n = len(arr)
    if n == 0:
        return None
    if n == 1:
        return arr[0]
    return max(arr[n - 1], cari_max_rekursif(arr, n - 1))
```
```
# Iteratif
def cari_max_iteratif(arr):
    if not arr:
        return None
    max_value = arr[0]
    for num in arr:
        if num > max_value:
            max_value = num
    return max_value
```
```
# Fungsi untuk memperbarui grafik
def update_graph(n_values, recursive_times, iterative_times):
    plt.figure(figsize=(8, 6))
    plt.plot(n_values, recursive_times, label='Recursive', marker='o', linestyle='-')
    plt.plot(n_values, iterative_times, label='Iterative', marker='o', linestyle='-')
    plt.title('Perbandingan Kinerja: Rekursif vs Iteratif')
    plt.xlabel('Panjang Array (n)')
    plt.ylabel('Waktu Eksekusi (detik)')
    plt.legend()
    plt.grid(True)
    plt.show()
```
```
# Fungsi untuk mencetak tabel waktu eksekusi
def print_execution_table(n_values, recursive_times, iterative_times):
    table = PrettyTable()
    table.field_names = ["Panjang Array (n)", "Waktu Rekursif (s)", "Waktu Iteratif (s)"]
    min_len = min(len(n_values), len(recursive_times), len(iterative_times))
    for i in range(min_len):
        table.add_row([n_values[i], recursive_times[i], iterative_times[i]])
    print(table)
```
```
# Program utama
try:
    n_values = []
    recursive_times = []
    iterative_times = []

    # Input panjang array untuk 5 kasus
    for i in range(5):
        n = int(input(f"Masukkan panjang array ke-{i + 1} (n): "))
        if n <= 0:
            print("Masukkan panjang array yang lebih besar dari nol!")
            continue

        n_values.append(n)

        # Membuat array contoh
        array = list(range(n))

        # Ukur waktu eksekusi algoritma rekursif
        start_time = time.time()
        cari_max_rekursif(array)
        recursive_times.append(time.time() - start_time)

        # Ukur waktu eksekusi algoritma iteratif
        start_time = time.time()
        cari_max_iteratif(array)
        iterative_times.append(time.time() - start_time)

    # Cetak tabel waktu eksekusi
    print_execution_table(n_values, recursive_times, iterative_times)

    # Perbarui grafik
    update_graph(n_values, recursive_times, iterative_times)

except ValueError:
    print("Masukkan panjang array yang valid!")
```
