# Final Project Teknik Sampling Dan Data Wrangling

## Deskripsi singkat:
	Project ini bertujuan untuk melakukan preprocessing, analisis, dan visualisasi dari dataset Spotify untuk mendapatkan insight.

## Struktur File:
	* data/raw/		: Dataset mentah
	* data/processed/		: Dataset yang sudah melalui preprocessing
	* notebooks/		: Folder yang berisikan kode utama
	* requirements.txt	: Daftar library yang digunakan

## Setup envirorment:
	* pandas 2.0.3
	* numpy 1.24.3
	* matplotlib 3.7.2
	* seaborn 0.12.2
	* jupyter 1.0.0

## Menjalankan Program:
	Jalankan file 'notebooks/project.ipnyb'

## Authors:
	* Radithya Mahaputra (5052241019)
	* Yafi Muhammad Faldin (5052241026)
	* Muhammad Naqib Bariq (5052241013)

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
