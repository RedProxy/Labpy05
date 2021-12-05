# PERTEMUAN 10
# Praktikum 5 - Dictonary
## 1. Latihan Dictionary

**Dictionary** adalah tipe data pada python yang berfungsi untuk menyimpan kumpulan data/nilai dengan pendekatan _key-value_. Setiap _key_ dipisahkan dari value-nya oleh titik dua (:), sedangkan _item_ dipisahkan oleh koma, dan semuanya tertutup dalam kurung kurawal {}.

Dictionary sendiri memiliki dua buah komponen inti:
1.	**Key** merupakan nama atribut suatu item pada dictionary.
2.	**Value** adalah nilai yang disimpan pada suatu atribut.

### A. Program

![Gambar 1](image/lat1.prog.jpeg)

![Gambar 2](image/lat1.1.prog.jpeg)

### B. Penjelasan

1. Membuat dictionary daftar kontak.
	```python
	s={'Ari': '081267888', 'Dina': '087677776'}
	```
2. Untuk menampilkan salah satu kontak, gunakan `s['Ari']`. **s** adalah variable dictionary, sedangkan `['Ari']` adalah keys dari sebuah dictionary.
```python
	print("Menampilkan kontak Ari :", s['Ari'])
```
3. Jika ingin menambahkan kontak baru gunakan `variable_dictionary['keys']=value;`. 
	```python
	s['Riko']='087654544';
	```
4. Untuk mengubah kontak yang lama dengan yang baru, gunakan `variable_dictionary['keys']=value;`. Disini saya akan  mengubah valuenya yang semula `'Dina': '087677776'` menjadi `'Dina': '088988776'`.

	```python
	s['Dina']='088988776';
    ```
5. Untuk menampilkan semua nama kontak, gunakan `keys()`.
	```python
	print(s.keys())
	```
6. Jika ingin menampilkan semua nomor kontak, gunakan `values()`.
	```pyhton
	print(s.values())
	```
7. Untuk menampilkan daftar kontak beserta nomor teleponnya, gunakan `items()`.
	```pyhton
	print(s.items())
	```
8. Untuk menghapus salah satu kontak, gunakan statement `del variable_dictionary[keys];`.
	```python
	del s['Dina'];
	```
### C. Output

![Gambar 3](image/outputlat1.jpeg)

## Tugas Pratikum 5

### A. Flowchart

![Gambar 4](image/flowchart.jpeg)

### B. Program

![Gambar 5](image/prak1prog.jpeg)

![Gambar 6](image/prak1.1prog.jpeg)

![Gambar 7](image/prak1.2prog.jpeg)

![Gambar 8](image/prak1.3prog.jpeg)

### C. Penjelasan

1. Membuat dictionary kosong yang nantinya akan diinput dengan data.
	```python
	data={}
	```

2. Membuat perulangan dengan _while_ dan terdapat pilihan menu untuk menjalankan program.
	```python
	while True:
    print()
    a=input("[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari, (K)eluar] :")
    print()
	```
3. Menambahkan data nim, nama, nilai tugas, uts, dan uas. Data yang diinputkan akan masuk ke dalam dictionary **data** dengan **nim** sebagai keys sedangkan nama, tugas, uts dan uas sebagai **values**.
	```python
	if a=="t" or a=="T":
        print("TAMBAH DATA")
        print("-----------")
        nim=int(input("NIM\t: "))
        nama=input("Nama\t: ")
        tugas=int(input("Tugas\t: ")) 
        uts=int(input("UTS\t: "))
        uas=int(input("UAS\t: "))
        akhir=(int(tugas)*30/100)+(int(uts)*35/100)+(int(uas)*35/100)
        data[nim]=nama, tugas, uts, uas, akhir
	```
4. Menampilkan atau melihat data. Jika sebelumnya belum menginput data, maka tampilannya akan "Tidak ada data". Apabila sudah menginput data, maka data yang telah diinput tadi akan ditampilkan.
	```python
	elif a=="l" or a=="L":
        if data.items():
            print("DAFTAR NILAI")
            print("------------")
            print(72*"=")
            print("| {0:^10} | {1:^10} | {2:^6} | {3:^6} | {4:^6} |   {5:^12}  |".format("NIM", "NAMA", "TUGAS", "UTS", "UAS", "NILAI AKHIR"))
            print(72*"=")
            for item in data.items(): 
                print("| {0:>10} | {1:>10} | {2:>6} | {3:>6} | {4:>6} |   {5:>12}  |".format(nim, nama, tugas, uts, uas, akhir))
                print(72*"=")
            print()
        else:
            print("DAFTAR NILAI")
            print("------------")
            print(72*"=")
            print("| {0:^10} | {1:^10} | {2:^6} | {3:^6} | {4:^6} |   {5:^12}  |".format("NIM", "NAMA", "TUGAS", "UTS", "UAS", "NILAI AKHIR"))
            print(72*"=")
            print("|                             TIDAK ADA DATA                           |")
            print(72*"=")
            print()
	```
5. Apabila ingin mengubah data, maka anda akan diminta untuk menginputkan **nim** terlebih dahulu. Setelah itu input data yang ingin diubah.
	```python
	 elif a=="u" or a=="U":
        print("UBAH DATA")
        print("---------")
        b=input("Masukkan NIM anda: ")
        print()
        if data.keys():
            tugas=int(input("Tugas\t: ")) 
            uts=int(input("UTS\t: "))
            uas=int(input("UAS\t: "))
            akhir=(int(tugas)*30/100)+(int(uts)*35/100)+(int(uas)*35/100)
	```
6. Jika ingin menghapus data, anda akan diminta untuk menginput **nim**. Lalu data yang telah diinput diawal tadi akan dihapus beserta valuesnya (nama, nilai tugas, nilai uts dan nilai uas).
	```python
	elif a=="h" or a=="H":
        print("HAPUS DATA")
        print("----------")
        b=input("Masukkan NIM anda: ")
        print()
        if data.keys():
            del data[nim]
	```
7. Apabila ingin mencari data, anda akan diminta untuk menginput **nim** kemudian data yang anda cari akan muncul berdasarkan nim yang diinput tadi.
	```python
	elif a=="c" or a=="C":
        print("CARI DATA")
        print("---------")
        b=input("Masukkan NIM anda: ")
        print()
        if data.keys():
            print(72*"=")
            print("| {0:^10} | {1:^10} | {2:^6} | {3:^6} | {4:^6} |   {5:^12}  |".format("NIM", "NAMA", "TUGAS", "UTS", "UAS", "NILAI AKHIR"))
            print(72*"=")
            print("| {0:>10} | {1:>10} | {2:>6} | {3:>6} | {4:>6} |   {5:>12}  |".format(nim, nama, tugas, uts, uas, akhir))
            print(72*"=")
            print()
	```
8. Jika data sudah selesai diinput, pilih menu **'k'/'K'** maka program akan terhenti.
	```python
	elif a=="k" or a=="K":
         break
	```

### D. Output

![Gambar 9](image/outputprak.jpeg)

![Gambar 10](image/outputprak1.1.jpeg)

![Gambar 11](image/outputprak1.2.jpeg)

![Gambar 12](image/outputprak1.3.jpeg)