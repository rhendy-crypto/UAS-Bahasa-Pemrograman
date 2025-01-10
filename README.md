# Program Konsep Modular dan OOP
```Soal
Buatlah program sederhana dengan ketentuan:
• Program harus dibuat dengan konsep modular dan OOP (pisahkan
class data, class view, dan class process)
• Program harus meminta input dari pengguna
• Tambahkan validasi input (dapat menggunakan konsep eksepsi)
• Program menapilkan hasil (dapat berupa table view)
Jawablah dengan benar dan tepat serta lengkap
```
Program ini akan meminta input data siswa (nama dan nilai), melakukan validasi input, dan menampilkan hasilnya dalam bentuk tabel.

## Berikut kode programnya:
```
Python
class Siswa:
    def _init_(self, nama, nilai):
        self.nama = nama
        self.nilai = nilai

class InputView:
    def input_data(self):
        while True:
            try:
                nama = input("Masukkan nama siswa: ")
                if not nama:
                    raise ValueError("Nama tidak boleh kosong.")

                nilai = int(input("Masukkan nilai siswa: "))
                if not 0 <= nilai <= 100:
                    raise ValueError("Nilai harus antara 0 dan 100.")
                return nama, nilai
            except ValueError as e:
                print(f"Input tidak valid: {e}")

class ProsesData:
    def buat_siswa(self, nama, nilai):
        return Siswa(nama, nilai)

class TampilanView:
    def tampilkan_tabel(self, daftar_siswa):
        if not daftar_siswa:
            print("Belum ada data siswa.")
            return

        print("-" * 30)
        print("| {:<15} | {:<5} |".format("Nama", "Nilai"))
        print("-" * 30)
        for siswa in daftar_siswa:
            print("| {:<15} | {:<5} |".format(siswa.nama, siswa.nilai))
        print("-" * 30)

def main():
    input_view = InputView()
    proses_data = ProsesData()
    tampilan_view = TampilanView()
    daftar_siswa = []

    while True:
        nama, nilai = input_view.input_data()
        siswa = proses_data.buat_siswa(nama, nilai)
        daftar_siswa.append(siswa)

        tambah_lagi = input("Tambah siswa lagi? (y/t): ")
        if tambah_lagi.lower() != 'y':
            break

    tampilan_view.tampilkan_tabel(daftar_siswa)

if _name_ == "_main_":
    main()
```

## Penjelasan  Kode:
1. Class Siswa (Data): Merepresentasikan data siswa dengan atribut nama dan nilai.

2. Class InputView (View Input): Bertanggung jawab untuk menerima input dari pengguna dan melakukan validasi. Menggunakan try-except untuk menangani ValueError jika input tidak valid.

3. Class ProsesData (Proses): Membuat objek Siswa berdasarkan input yang diberikan.

4. Class TampilanView (View Output): Menampilkan data siswa dalam bentuk tabel. Menangani kasus jika belum ada data siswa.

5. Fungsi main(): Mengendalikan alur program, membuat instance dari setiap class, dan memanggil method yang sesuai.

## Contoh Penggunaan:
```
Masukkan nama siswa: Budi
Masukkan nilai siswa: 85
Tambah siswa lagi? (y/t): y
Masukkan nama siswa: Ani
Masukkan nilai siswa: 92
Tambah siswa lagi? (y/t): t
------------------------------
| Nama            | Nilai |
------------------------------
| Budi            | 85    |
| Ani             | 92    |
------------------------------
```

## Konsep OOP yang Diterapkan:

• Encapsulation (Enkapsulasi): Data dan method yang bekerja pada data tersebut dibungkus dalam class. Contoh: Class Siswa menyimpan data nama dan nilai.

• Modularitas: Kode dibagi menjadi modul-modul (class) yang terpisah, sehingga lebih mudah dikelola dan dimengerti.

• Separation of Concerns (Pemisahan Tanggung Jawab): Setiap class memiliki tanggung jawab yang spesifik, seperti input, proses, dan output.

## Berikut adalah Kode Programnya:
python
## (1) Class Siswa (Data)
![image](https://github.com/user-attachments/assets/01c1317f-104e-47a8-baa8-5f54bf82453c)

## (2) Class Input View (View Input)
![image](https://github.com/user-attachments/assets/afafa37d-18c6-4bc8-a5ff-bbac5e65697d)

## (3) Class Proses Data (Proses)
![image](https://github.com/user-attachments/assets/0283990a-891b-4505-9a0a-228c4414dd9a)

## (4) Class Tampilan View (View Output)
![image](https://github.com/user-attachments/assets/3601051d-6e60-4457-ae9f-89fdd800fe8a)

## (5) Fungsi Main ()
![image](https://github.com/user-attachments/assets/45f43cb2-4661-4197-b156-147cc748f279)

## (6) Contoh Penggunaan
![image](https://github.com/user-attachments/assets/f739b4e1-8179-423b-8226-889339d227c7)

## Kesimpulan
Dengan penjelasan ini, Kita seharusnya dapat memahami bagaimana program ini bekerja dan bagaimana konsep modular dan OOP diimplementasikan. Program ini juga sudah dilengkapi dengan validasi input menggunakan try-except.

## © Rhendy Zhaky Alvian
email: rhendyzhakyalvian@gmail.com
