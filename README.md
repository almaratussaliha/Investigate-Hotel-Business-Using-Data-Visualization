# Investigate-Hotel-Business-Using-Data-Visualization
- Source code: https://github.com/almaratussaliha/Investigate-Hotel-Business-Using-Data-Visualization/blob/main/data_preprocessing.ipynb </br>
- Tools: Jupyter lab (Pandas, Matplotlib, Seaborn) </br>

## Overview
<p> Sangat penting bagi suatu perusahaan untuk selalu menganalisa performa bisnisnya. Pada kesempatan kali ini, kita akan lebih mendalami bisnis dalam bidang perhotelan. 
Fokus yang dituju adalah mengetahui bagaimana perilaku pelanggan dalam melakukan pemesanan hotel, dan hubungannya terhadap tingkat pembatalan 
pemesanan hotel. Hasil dari insight yang ditemukan  disajikan dalam bentuk data visualisasi agar lebih mudah dipahami dan bersifat persuasif. <p>



### `1. Data Preprocessing`
Mempersiapkan data mentah menjadi data bersih yang siap diolah. Hal-hal yang perlu dilakukan adalah: mengatasi data null/kosong (missing values), 
mengatasi data yang tidak sesuai (invalid values), dan mengidentifikasi data yang tidak tepat sehingga dapat dihilangkan. </br>

<p>Dataset ini memiliki 29 kolom dan 119.390 baris data. Terdapat feature/kolom yang memiliki nilai kosong diantaranya feature city, children, agent dan company.
Dalam mengatasi nilai kosong tersebut dilakukan perilaku sebagai berikut: </br>
- feature city dapat diisi dengan nilai 'unknown' karena tidak diketahui kota dari pemesan hotel. </br>
- feature children dapat diisi dengan nilai '0' yang menggambarkan tidak ada anak dalam pemesan hotel. </br>
- feature agent and company dapat diisi dengan nilai '0' menandakan jika pemesan hotel tidak berasal dari agent maupun company. </br>

<p> Selanjutnya mengatasi data yang tidak sesuai pada feature meal, dimana data 'undefined' diganti menjadi 'no meal'. </br>
Kemudian mengganti tipe data pada feature yang tidak sesuai, dimana feature yang memiliki tipe data tidak sesuai yaitu children, agent, dan company. Tipe data 
sebelumnya yaitu float diganti menjadi integer. </br>
Terakhir, menghapus baris data yang berisi total tamu hotel = 0, dimana total tamu didapatkan dari jumlah feature adult, children, dan baby. </br>
</p> 

### `2. Monthly Hotel Booking Analysis Based on Hotel Type`
Mencari perbandingan jumlah pemesanan hotel perbulan berdasarkan tipe hotel yaitu city hotel dan resort hotel. Perbandingan pemesanan hotel perbulan
dapat diketahui dengan melakukan agregasi berdasarkan tipe hotelnya. Berikut grafik perbandingannya:
![alt text](https://github.com/almaratussaliha/Investigate-Hotel-Business-Using-Data-Visualization/blob/main/1.png?raw=true)

Kedua jenis hotel mendapatkan jumlah pesanan terbanyak sekitar bulan Juni dan Juli, dimana waktu tersebut bertepatan dengan libur panjang sekolah yang biasa 
dimanfaatkan untuk berlibur. Kemudian jumlah pesanan hotel mengalami penuruan signifikan pada agustus dan september dimana masa liburan telah usai.</br>
Kemudian jumlah pesanan pada bulan November dan Desember mengalami kenaikan kembali karena pada bulan ini merupakan waktu menjelang libur sekolah dan akhir tahun.

### `3. Impact Analysis of Stay Duration on Hotel Bookings Cancellation Rates`
Mencari perbandingan antara durasi menginap terhadap tingkat pembatalan pemesanan hotel. Perbandingan ini dapat diketahui dengan melakukan agregasi antara jumlah
pemesanan hotel yang dibatalkan terhadap durasi menginap untuk setiap jenis hotel. Berikut grafik perbandingannya:
![alt text](https://github.com/almaratussaliha/Investigate-Hotel-Business-Using-Data-Visualization/blob/main/2.png?raw=true)

Jika dilihat dari plot tersebut, terdapat korelasi positif antara lama durasi dan persentase pembatalan pemesanan dimana semakin lama durasi pemesan hotel dilakukan maka semakin besar kemungkinan pesanan tersebut dibatalkan baik city hotel maupun resort hotel.

### `4. Impact Analysis Lead Time on Hotel Booking Cancellation Rate`
Jarak waktu pemesanan hotel bervariasi, ada yang hanya beberapa hari dan ada pula sampai beberapa bulan sebelum kedatangan. Jika dilihat dari dataset, maksimun lead_time (jarak pemesanan) adalah 737 di mana terdapat pesanan yang dilakukan 2 tahun sebelumnya. Untuk mengetahui pengaruh antara jarak pemesanan hotel dengan hari kedatangan memiliki pengaruh terhadap pembatalan hotel dapat dilakukan dengan melakukan agregasi yang menunjukkan jumlah pemesanan hotel yang dibatalkan terhadap jarak waktu pemesanan untuk setiap jenis hotel. Berikut plot perbandingannya:
![alt text](https://github.com/almaratussaliha/Investigate-Hotel-Business-Using-Data-Visualization/blob/main/3.png?raw=true)

Tingkat pembatalan pemesanan paling rendah ada pada pemesanan yang memiliki waktu tunggu kurang dari 30 hari / 1 bulan dan berlaku untuk kedua jenis hotel. Resort hotel cukup stagnan dengan 40% rasio pembatalan, sedangkan City hotel memiliki rasio yg cukup tinggi di atas 60% ketika waktu tunggu sekitar 1 tahun. </br>

## Recommendation
- Libur panjang pada bulan Juni dan Juli maupun libur akhir tahun pada November - Desember adalah waktu di mana rata-rata pemesanan hotel meningkat signifikan. 
Perusahaan hotel bisa mengambil keuntungan dari situasi ini dengan melakukan campaign sebulan sebelum waktu liburan dengan menawarkan discount dan packages liburan. Selain itu pihak hotel juga dapat memberi free voucher yang bisa digunakan ke restoran atau cafe terdekat hotel.
- Semakin lama durasi menginap dan jarak waktu pemesanan maka semakin tinggi pula tingkat pembatalan pemesanan hotel. Untuk mengurangi masalah ini, pihak hotel dapat membuat kebijakan seperti; tidak ada pengembalian (refund) reservasi pada waktu libur. Selain waktu libur, pengembalian dana sebesar 50% untuk pembatalan yang diterima 20 hari sebelum tanggal kedatangan. Jika lewat dari hari yang ditentukan maka tidak ada pengembalian dana setelahnya.  
