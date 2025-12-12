# A. Pendahuluan

## 1. Deskripsi Dataset

Dataset ini berisi informasi metadata lagu dan karakteristik audio yang berasal dari platform musik Spotify. Setiap baris merepresentasikan satu lagu dan mencakup:

A. Identitas Lagu

* track_id - ID unik lagu
* track_name - Nama lagu
* track_artist - Artis yang membawakan lagu
* track_popularity - Tingkat popularitas lagu (0-100)

B. Informasi Album

* track_album_id - ID unik album
* track_album_name - Nama album
* track_album_release_date - Tanggal rilis album

C. Informasi Playlist

* playlist_name - Nama playlist tempat lagu berada
* playlist_id - ID playlist
* playlist_genre - Genre playlist
* playlist_subgenre - Subgenre playlist

D. Deskripsi Audio

* danceability - Seberapa mudah lagu untuk menari
* energy - Intensitas dan aktivitas lagu
* key - Nada dasar lagu (0=C, 1=C#, dst)
* loudness - Tingkat loudness rata-rata lagu (dB)
* mode - Mode musik (1=major, 0=minor)
* speechiness - Proporsi elemen vokal/ucapan
* acousticness - Seberapa akustik lagu
* instrumentalness - Probabilitas lagu tanpa vokal
* liveness - Indikasi live performance
* valence - Tingkat “positiveness” emosional
* tempo - BPM (beat per minute)
* duration_ms - Durasi lagu dalam milidetik

## 2. Alasan Dataset Menarik

Dataset ini menarik karena menggabungkan banyak aspek lagu sekaligus, mulai dari metadata artis, genre playlist, fitur akustik teknis, hingga tingkat popularitas lagu. Kombinasi informasi tersebut memungkinkan analisis musik yang multidimensi dan lebih komprehensif dibandingkan dataset musik tradisional. Selain itu, dataset ini berasal dari platform streaming modern sehingga lebih representatif terhadap tren konsumsi musik masa kini.

## 3. Tujuan Analisis

* Mencari distribusi karakteristik audio berdasarkan genre
* Mencari korelasi antar fitur audio
* Mencari apakah ada pola pada tren karakteristik lagu
Sebelum melakukan data cleaning, kami menemukan hamabatan:
1. Data Tidak Lengkap / Kurang Konsisten
Beberapa lagu memiliki nilai track_popularity yang sangat rendah (misalnya 8, 2, 1) yang mungkin tidak representatif.
Ada beberapa lagu dengan playlist_genre dan playlist_subgenre yang sama semuanya (pop, dance pop), sehingga analisis berdasarkan genre menjadi terbatas. Tidak ada informasi tentang jumlah streaming, likes, atau playlist follower count, yang penting untuk analisis performa lagu.

2. Data Audio Features yang Kompleks
Banyak kolom teknis seperti danceability, energy, loudness, speechiness, dll. yang memerlukan pemahaman domain musik untuk interpretasi yang tepat.
Nilai seperti instrumentalness dan acousticness seringkali sangat kecil (mendekati nol), mungkin kurang variatif untuk analisis statistik.

3. Duplikasi dan Inkonsistensi Nama
Beberapa lagu muncul lebih dari sekali (misalnya lagu dari Ed Sheeran, The Chainsmokers) dalam playlist yang berbeda, perlu penanganan duplikasi jika analisis dilakukan per lagu unik. Format tanggal track_album_release_date sudah konsisten, tetapi ada data dari tahun berbeda (2017–2020), sehingga tren waktu bisa dianalisis.

4. Tidak Ada Data Demografis atau Geografis
Tidak ada informasi tentang negara asal artis, bahasa lagu, atau target pasar. Tidak ada data tentang usia pendengar atau jenis kelamin, yang penting untuk analisis segmentasi.

5. Tidak Ada Metadata Playlist yang Mendetail
Hanya ada playlist_name dan playlist_id, tapi tidak ada info tentang jumlah lagu dalam playlist, durasi playlist, atau popularitas playlist.

6. Skala dan Satuan yang Beragam
loudness dalam dB (bisa negatif), tempo dalam BPM, duration_ms dalam milidetik — perlu normalisasi jika ingin digunakan dalam model machine learning.

7. Tidak Ada Label atau Target Variabel untuk Predictive Analysis
Jika ingin membangun model untuk memprediksi popularitas, tidak ada variabel target yang jelas selain track_popularity itu sendiri, yang mungkin tidak lengkap.

8. Data Mungkin Tidak Representatif
Dataset ini hanya berisi lagu dari playlist tertentu (terutama "Pop Remix", "Dance Pop", dll.), sehingga generalisasi ke semua genre musik tidak dapat dilakukan.

Maka dari itu kami lakukan data cleaning dan analisis untuk mendapat insight yang berarti
