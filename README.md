Events per Day ( Ini adalah jumlah data point yang masuk ke PI Data Archive dalam 1 hari.)
Dihitung dari:
Copy code

Jumlah Tags × (86400 / Sampling Interval)
Dengan input kamu:
Copy code

Tags = 1500
Sampling = 1 detik
Per tag:
Copy code

86400 event/hari
Total:
Copy code

1500 × 86400
= 129,600,000 event/hari
Artinya setiap hari PI menerima 129 juta data sensor.
1️⃣ Compressed Storage GB/day
0.4828 GB
Ini adalah jumlah storage yang benar-benar disimpan di archive setelah compression PI.
Prosesnya:
Copy code

Events × Event Size
Kemudian dikurangi compression:
Copy code

Raw data → Exception filtering → Compression
Di tool kamu:
Copy code

80% compression
Jadi data yang disimpan hanya sekitar 20% dari raw data.
Hasilnya:
Copy code

≈ 0.48 GB per hari
2️⃣ Compressed Storage GB/month
14.48 GB
Ini adalah total storage selama 1 bulan.
Perhitungannya:
Copy code

GB/day × 30
Copy code

0.4828 × 30
≈ 14.48 GB
Jadi setiap bulan historian akan bertambah sekitar 14 GB data.
3️⃣ Compressed Storage GB/year
176.22 GB
Ini adalah total storage dalam 1 tahun.
Rumus:
Copy code

GB/day × 365
Copy code

0.4828 × 365
≈ 176 GB per tahun
Artinya:
Copy code

1 tahun historian ≈ 176 GB
4️⃣ Disk Full Days
1035 hari
Ini adalah estimasi berapa hari disk 500GB akan penuh.
Rumus:
Copy code

Total Storage / GB per day
Copy code

500 / 0.4828
≈ 1035 hari
Jadi disk archive akan penuh sekitar:
Copy code

2.8 tahun
5️⃣ Disk Full Years
2.84 tahun
Ini hanya konversi dari:
Copy code

Days / 365
Copy code

1035 / 365
≈ 2.84 tahun
Artinya dengan konfigurasi sekarang:
Copy code

500 GB archive ≈ 2.8 tahun data
6️⃣ Network Mbps
0.2289 Mbps
Ini adalah estimasi bandwidth network yang dibutuhkan untuk mengirim data ke PI Server.
Rumusnya kira-kira:
Copy code

Events × Event Size × 8 bit
--------------------------------
Seconds per day
Hasilnya:
Copy code

≈ 0.23 Mbps
Artinya traffic data historian sangat kecil.
Sebagai perbandingan:
Copy code

1 CCTV camera ≈ 4–8 Mbps
Jadi PI historian sangat hemat network.
7️⃣ Archive Files per Year
88 file
PI Data Archive menyimpan data dalam file:
Copy code

*.arc
Biasanya ukuran:
Copy code

2 GB per file
Total data setahun:
Copy code

176 GB
Jumlah file:
Copy code

176 / 2
≈ 88 archive file
Jadi dalam setahun PI akan membuat sekitar 88 file archive.
