# Jarkom-Modul-1-D11-2021

Anggota kelompok:
- 05111940000067 - Fika Nur Aini
- 05111940000095 - Fuad Elhasan Irfani
- 05111940000203 - Fidhia Ainun Khofifah
---

6. Cari username dan password ketika melakukan login ke FTP Server!
    - Buka file 6-7.pcap lalu masukkan ```ftp``` pada display filter. Username dan password bisa dilihat di beberapa packet awal
    ![Screenshot 2021-09-24 150307](https://user-images.githubusercontent.com/73324192/134640471-4543e197-2e95-4c47-90a1-8c03c90f61ca.png)
    - Atau masukkan ```ftp.request.command == USER or ftp.request.command == PASS``` agar langsung menemukan username dan passwordnya
    ![Screenshot 2021-09-24 150405](https://user-images.githubusercontent.com/73324192/134640555-8b55753d-0bc8-404e-b257-1e50ecbca449.png)

7. Ada 500 file zip yang disimpan ke FTP Server dengan nama ```0.zip```, ```1.zip```, ```2.zip```, ..., ```499.zip```. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya ```Real.pdf```)
    - Buka file 6-7.pcap lalu masukkan ```ftp-data contains Real.pdf``` pada display filter
    - Klik kanan salah satu paket, Follow --> TCP Stream
    ![Screenshot 2021-09-24 151053](https://user-images.githubusercontent.com/73324192/134641188-86cca697-0e3d-4cc0-aa6d-949dd6786c3a.png)
    - Show data as Raw lalu ```save as``` file dengan ekstensi zip
    ![Screenshot 2021-09-24 151143](https://user-images.githubusercontent.com/73324192/134641261-c5338585-fc91-49bc-bdbf-2e6fe70695fb.png)
    - Didalamnya terdapat file ```Real.pdf```
    ![Screenshot 2021-09-24 151612](https://user-images.githubusercontent.com/73324192/134641786-a347a6e8-faf4-4853-914f-5cf2b97be364.png)

8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
    - Buka file 8-10.pcap lalu masukkan ```ftp.request.command == RETR``` pada display filter
    ![Screenshot 2021-09-24 151809](https://user-images.githubusercontent.com/73324192/134642363-25221e2c-0bfa-45bf-b458-05a2a09f0e3c.png)
    - Kami tidak menemukannya. Kami telah memastikan bahwa filter yang kami pakai sudah benar dengan cara mencoba ```ftp.request.command == STOR```
    ![Screenshot 2021-09-24 151836](https://user-images.githubusercontent.com/73324192/134642386-6d5ec76c-0d9e-4295-9904-c3259786d44c.png)

9. Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama ```secret.zip```. Simpan dan buka file tersebut!
    - Buka file 8-10.pcap lalu masukkan ```ftp-data contains secret.zip```
    - Klik kanan paket, Follow --> TCP Stream
    ![Screenshot 2021-09-24 152235](https://user-images.githubusercontent.com/73324192/134643764-c3403029-12fc-42f5-83d1-c333624e112a.png)
    - Disini kami menemukan history bash yang ternyata akan dicari di soal 10. Untuk menemukan file secret.zip, pindah TCP stream ke stream 10 (stream setelah bash). Show as raw lalu simpan file dengan ekstensi zip
    ![Screenshot 2021-09-24 152338](https://user-images.githubusercontent.com/73324192/134643867-6a217aae-b16b-4c4a-9985-2082684857d8.png)
    ![Screenshot 2021-09-24 152412](https://user-images.githubusercontent.com/73324192/134643915-14a9072f-f87e-4f2f-957b-74e04f4f5bdc.png)
    - Berkut isi dari file zip tersebut. File ini terproteksi dengan password. Password akan dicari pada nomor 10.
    ![Screenshot 2021-09-24 152545](https://user-images.githubusercontent.com/73324192/134644170-4a42336c-ff6d-434f-947a-acb46f6b32b2.png)

10. Selain itu terdapat ```history.txt``` yang kemungkinan berisi history bash server tersebut! Gunakan isi dari ```history.txt``` untuk menemukan password untuk membuka file rahasia yang ada di ```secret.zip```!
    - Buka file 8-10.pcap lalu masukkan ```ftp-data contains history.txt```
    - Klik kanan paket, Follow --> TCP Stream
    ![Screenshot 2021-09-24 153632](https://user-images.githubusercontent.com/73324192/134645081-5076ab0c-54ba-40c9-976e-f5aa14f660cf.png)
    - Dari history bash ini terlihat bahwa password zip ada di file ```bukanapaapa.txt```
    ![Screenshot 2021-09-24 152338](https://user-images.githubusercontent.com/73324192/134643867-6a217aae-b16b-4c4a-9985-2082684857d8.png)
    - Kami menemukan passwordnya di TCP stream 11 (stream setelah file zip)
    ![Screenshot 2021-09-24 153757](https://user-images.githubusercontent.com/73324192/134645171-58c4c42b-0bde-434e-ac41-43dea934f259.png)
    - Masukkan password pada file zip tadi untuk membuka file pdf didalamnya
    ![Screenshot 2021-09-24 153916](https://user-images.githubusercontent.com/73324192/134645190-c87aea61-83ce-44fa-aa4a-1b1d21a51589.png)

11. Filter sehingga wireshark hanya mengambil paket yang berasal dari ```port 80```
    - Masukkan perintah ```src port 80``` pada capture filter.
    - Berikut merupakan tampilan hasil capture filter,
      ![11](https://github.com/feilvan/Jarkom-Modul-1-D11-2021/blob/3adcfb7592365574531d87821230f29eee5faffa/11.png)
      
12. Filter sehingga wireshark hanya mengambil paket yang mengandung ```port 21```
    - Masukkan perintah ```port 21``` pada capture filter.
    - Berikut merupakan tampilan hasil capture filter,
      ![12](https://github.com/feilvan/Jarkom-Modul-1-D11-2021/blob/3adcfb7592365574531d87821230f29eee5faffa/12.png)

13. Filter sehingga wireshark hanya menampilkan paket yang menuju ```port 443```
    - Masukkan perintah ```dst port 443``` pada capture filter.
    - Berikut merupakan tampilan hasil capture filter,
      ![13](https://github.com/feilvan/Jarkom-Modul-1-D11-2021/blob/3adcfb7592365574531d87821230f29eee5faffa/13.png)

14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id
    - Masukkan perintah ```dst host kemenag.go.id``` pada capture filter
    - Kemudian, buka website kemenag.go.id pada browser
    - Berikut merupakan tampilan hasil capture filter,
      ![14](https://github.com/feilvan/Jarkom-Modul-1-D11-2021/blob/3adcfb7592365574531d87821230f29eee5faffa/14.png)

15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
    - Cari IP Address masing-masing device pada command prompt
    - Masukkan perintah ```src net 192.168.39.131``` pada capture filter
    - Berikut merupakan tampilan hasil capture filter,
      ![15](https://github.com/feilvan/Jarkom-Modul-1-D11-2021/blob/3adcfb7592365574531d87821230f29eee5faffa/15.png)
