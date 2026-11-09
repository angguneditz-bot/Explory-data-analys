# Cleaning Log

Dataset: transaksi_koperasi_2025.csv
Baris mentah: 1543 → baris bersih: 1493

| No. | Langkah | Baris terdampak | Alasan |
|---|---|---:|---|
| 1 | Konversi total_bayar ke angka | 250 | Menghapus Rp dan pemisah ribuan |
| 2 | Konversi tanggal per format | 1543 | Memisahkan format tanggal agar tidak salah dibaca |
| 3 | Buang spasi awal dan akhir kolom teks | 160 | Menghindari perbedaan akibat spasi tersembunyi |
| 4 | Placeholder teks menjadi kosong | 19 | Placeholder bukan nilai data sebenarnya |
| 5 | Placeholder -999 pada rating menjadi kosong | 49 | Nilai -999 bukan rating yang valid |
| 6 | Seragamkan kategori | 2 | Menyatukan variasi penulisan kategori |
| 7 | Hapus duplikat persis | 39 | Menyimpan satu baris untuk data identik |
| 8 | Satukan duplikat menurut id_transaksi | 15 | Menyimpan satu baris untuk setiap ID transaksi |
| 9 | Buang baris tanpa id_transaksi | 1 | ID transaksi diperlukan untuk penelusuran data |
| 10 | jumlah <= 0 menjadi kosong | 29 | Nilai perlu diperiksa karena bisa berupa kesalahan atau retur |
| 11 | Diskon di luar 0-100 menjadi kosong | 9 | Diskon di luar rentang valid perlu dikonfirmasi |
| 12 | Tandai total yang tidak cocok | 50 | Menandai selisih tanpa mengubah total asli |
| 13 | saldo_simpanan dibiarkan kosong | 156 | Tidak melakukan imputasi karena pola kehilangan perlu diperiksa |
| 14 | Tandai keberlakuan berat_kg | 290 | Berat tidak berlaku untuk kategori jasa dan pulsa |
| 15 | Tandai keberadaan catatan kasir | 1004 | Menandai transaksi yang tidak memiliki catatan kasir |