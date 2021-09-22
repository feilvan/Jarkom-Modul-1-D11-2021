# Jarkom-Modul-1-D11-2021


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
