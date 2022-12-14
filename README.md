# Praktikum-6
### Program Data Mahasiswa

Pada praktikum 6, kita akan membuat program sederhana untuk membuat data mahasiswa menggunakan Dictionary dengan python.

## <b>Flowchart </b>

![5](https://user-images.githubusercontent.com/115614173/204259630-3a4fe6cb-308e-4e02-a13c-cb878da0721e.png)

#### Codingan Praktikum 6

python
x = {}

while True:
    c = input("\n(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar: ")

    if c.lower() == 't':
        print("Tambah Data")
        nama = input("Nama           : ")
        nim = int(input("NIM            : "))
        uts = int(input("Nilai UTS      : "))
        uas = int(input("Nilai UAS      : "))
        tugas = int(input("Nilai Tugas    : "))
        akhir = tugas*30/100 + uts*35/100 + uas*35/100
        x[nama] = nim, uts, uas, tugas, akhir

    elif c.lower() == 'u':
        print("Ubah Data")
        nama = input("Masukkan Nama  : ")
        if nama in x.keys():
            nim = int(input("NIM            : "))
            uts = int(input("Nilai UTS      : "))
            uas = int(input("Nilai UAS      : "))
            tugas = int(input("Nilai Tugas    : "))
            akhir = tugas * 30 / 100 + uts * 35 / 100 + uas * 35 / 100
            x[nama] = nim, uts, uas, tugas, akhir
        else:
            print("Nama {0} tidak ditemukan".format(nama))

    elif c.lower() == 'h':
        print("Hapus Data")
        nama = input("Masukkan Nama  : ")
        if nama in x.keys():
            del x[nama]
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))

    elif c.lower() == 'c':
        print("Cari Data")
        nama = input("Masukkan Nama : ")
        if nama in x.keys():
            print("="*73)
            print("|                             Daftar Mahasiswa                          |")
            print("="*73)
            print("| Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*73)
            print("| {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                  .format(nama, nim, uts, uas, tugas, akhir))
            print("="*73)
        else:
            print("Nama {0} Tidak Ditemukan".format(nama))

    elif c.lower() == 'l':
        if x.items():
            print("="*78)
            print("|                               Daftar Mahasiswa                             |")
            print("="*78)
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            i = 0
            for z in x.items():
                i += 1
                print("| {no:2d} | {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                      .format(z[0][:13], z[1][0], z[1][1], z[1][2], z[1][3], z[1][4], no=i))
            print("=" * 78
        else:
            print("="*78)
            print("|                               Daftar Mahasiswa                             |")
            print("="*78)
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            print("|                                TIDAK ADA DATA                              |")
            print("="*78)

    elif c. lower() == 'k':
        break

    else:
        print("Pilih menu yang tersedia")


#### Penjelasan :

1.) Pertama kita membuat sebuah dictionary kosong yang nantinya akan diinputkan data ketika program dijalankan.<br>
python<br>
x = {}


2.) Lalu kita membuat kondisi perulangan dan sebuah keterangan untuk pilihan menu yang akan menjalankan program. <br>
python<br>
while True:<br>
    c = input("\n(T)ambah, (U)bah, (H)apus, (C)ari, (L)ihat, (K)eluar: ")


3.) Membuat syntax untuk menambahkan data.<br>
python<br>
    if c.lower() == 't':<br>
        print("Tambah Data")<br>
        nama = input("Nama           : ")<br>
        nim = int(input("NIM            : "))<br>
        uts = int(input("Nilai UTS      : "))<br>
        uas = int(input("Nilai UAS      : "))<br>
        tugas = int(input("Nilai Tugas    : "))<br>
        akhir = tugas*30/100 + uts*35/100 + uas*35/100<br>
        x[nama] = nim, uts, uas, tugas, akhir

Disini apabila kita menginputkan 't' maka kita akan diminta untuk menginputkan beberapa data. Data yang kita inputkan akan masuk ke dictionary 'x' yang telah dibuat tadi dengan data 'nama' sebagai keys dan sisanya sebagai valuesnya.

4.) Membuat syntax untuk mengubah data.<br>
python<br>
    elif c.lower() == 'u':<br>
        print("Ubah Data")<br>
        nama = input("Masukkan Nama  : ")<br>
        if nama in x.keys():<br>
            nim = int(input("NIM            : "))<br>
            uts = int(input("Nilai UTS      : "))<br>
            uas = int(input("Nilai UAS      : "))<br>
            tugas = int(input("Nilai Tugas    : "))<br>
            akhir = tugas * 30 / 100 + uts * 35 / 100 + uas * 35 / 100<br>
            x[nama] = nim, uts, uas, tugas, akhir<br>
        else:<br>
            print("Nama {0} tidak ditemukan".format(nama))

Apabila kita menginput 'u' maka akan ada keterangan untuk mengubah data dan kita akan diminta untuk menginputkan nama yang mau diubah datanya, apabila nama tidak ada maka outputnya "Nama {} tidak ditemukan". Dimana `{}` adalah nama/data yang mau kita ubah.

5.) Membuat syntax untuk menghapus data.<br>
python<br>
    elif c.lower() == 'h':<br>
        print("Hapus Data")<br>
        nama = input("Masukkan Nama  : ")<br>
        if nama in x.keys():<br>
            del x[nama]<br>
        else:<br>
            print("Nama {0} Tidak Ditemukan".format(nama))

Apabila kita menginput 'h' maka kita akan diminta menginput nama yang akan dihapus. Jika nama ada di dalam dictionary, maka system akan menghapus keys/nama tersebut beserta valuesnya pada statement `del x[nama]`.

6.) Membuat syntax untuk mencari data.<br>
python<br>
    elif c.lower() == 'c':<br>
        print("Cari Data")<br>
        nama = input("Masukkan Nama : ")<br>
        if nama in x.keys():<br>
            print("="*73)<br>
            print("|                             Daftar Mahasiswa                          |")<br>
            print("="*73)<br>
            print("| Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")<br>
            print("="*73)<br>
            print("| {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                  .format(nama, nim, uts, uas, tugas, akhir))<br>
            print("="*73)<br>
        else:<br>
            print("Nama {0} Tidak Ditemukan".format(nama))<br>

Apabila kita menginputkan 'c' maka kita akan diminta untuk memasukkan nama yang akan dicari. Apabila nama yang dicari ada di dalam dictionary maka outputnya akan menampilkan data dari nama tersebut.

7.) Membuat syntax untuk melihat atau menampilkan data.<br>
python<br>
    elif c.lower() == 'l':<br>
        if x.items():<br>
            print("="*78)<br>
            print("|                               Daftar Mahasiswa                             |")<br>
            print("="*78)<br>
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")<br>
            print("="*78)<br>
            i = 0<br>
            for z in x.items():<br>
                i += 1<br>
                print("| {no:2d} | {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"<br>
                      .format(z[0][:13], z[1][0], z[1][1], z[1][2], z[1][3], z[1][4], no=i))<br>
            print("=" * 78)<br>
        else:<br>
            print("="*78)<br>
            print("|                               Daftar Mahasiswa                             |")<br>
            print("="*78)<br>
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")<br>
            print("="*78)<br>
            print("|                                TIDAK ADA DATA                              |")<br>
            print("="*78)

Apabila kita menginput 'l' maka sistem akan menampilkan data - data yang sudah kita masukkan. Jika kita belum memasukkan data maka outputnya menjadi "TIDAK ADA DATA".

8.) Membuat syntax untuk menghentikan perulangan.<br>
python<br>
    elif c. lower() == 'k':<br>
        break

Apabila kita menginput 'k' maka program akan langsung berhenti.

9.) Membuat syntax untuk apabila memilih pilihan yang tidak ada di menu.<br>
python<br>
    else:<br>
        print("Pilih menu yang tersedia")

Jika kita menginputkan selain yang ada pada menu (t, u, h, c, l, k) maka kita akan diminta untuk memilih menu yang tersedia.

## <b>Tampilan Output </b>

### Tambah Data

![1](https://user-images.githubusercontent.com/115614173/204243643-89569548-fa7a-4317-b9df-439868837c56.png)

## Ubah Data

![2](https://user-images.githubusercontent.com/115614173/204243795-6f09409b-b7f4-4e8e-abf3-6755bf960cd1.png)

### Hapus Data

![3](https://user-images.githubusercontent.com/115614173/204243976-e2d3c382-501a-4897-b92f-9a3022d26d5a.png)

### Cari Data 

![4](https://user-images.githubusercontent.com/115614173/204244229-8b104c46-2290-4a48-aa18-2fffc439b88b.png)

### SELSAI 


