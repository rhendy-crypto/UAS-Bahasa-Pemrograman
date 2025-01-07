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
