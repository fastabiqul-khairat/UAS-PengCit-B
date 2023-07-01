# UAS-PengCit-B
1. Teori yang mendukung mengenai projek terkait.
   Berikut adalah teori yang mendukung mengenai projek yang saya buat:
   
   a. Grayscale Conversion: Pada langkah ini, gambar asli dikonversi menjadi citra grayscale. Citra grayscale hanya memiliki satu saluran       warna (intensitas), sehingga memudahkan proses deteksi tepi karena hanya perlu memperhatikan perbedaan intensitas piksel.
   
   b. Gaussian Blur: Tahap ini melibatkan penerapan filter Gaussian pada citra grayscale untuk mengurangi noise atau detail yang tidak          diinginkan. Filter Gaussian adalah jenis filter spasial yang digunakan untuk menghaluskan citra dengan mengurangi perbedaan               intensitas antara piksel-piksel tetangganya.
   
   c. Canny Edge Detection: Metode ini adalah algoritma populer untuk mendeteksi tepi dalam citra. Algoritma Canny menggabungkan beberapa       langkah, termasuk deteksi tepi dengan menggunakan gradien citra, penekanan non-maksimum untuk memperoleh tepi yang lebih tipis, dan       histeresis untuk menghilangkan tepi palsu dan mempertahankan tepi yang kuat.
   
   d. Hough Transform: Ini adalah metode yang digunakan untuk mendeteksi garis lurus dalam citra. Transformasi Hough dapat mengubah ruang       piksel menjadi ruang parameter garis, di mana setiap piksel pada garis lurus diubah menjadi parameter garis dalam ruang tersebut.         Dalam implementasi ini, digunakan HoughLinesP yang merupakan varian dari Hough Transform yang mendeteksi garis dengan menggunakan         titik-titik ujung segmen garis.
   
   e. Menggambar Garis pada Gambar Asli: Setelah deteksi garis, langkah terakhir adalah menggambar garis yang terdeteksi pada gambar            asli. Ini dilakukan dengan mengiterasi setiap garis yang terdeteksi dan menggunakan fungsi cv2.line untuk menggambar garis pada           citra asli dengan warna dan ketebalan yang ditentukan.
   
   f. Tampilan Menggunakan Matplotlib: Pada bagian akhir, citra asli dan citra dengan tepi terdeteksi ditampilkan menggunakan Matplotlib.       Dalam contoh ini, subplot dua kolom digunakan untuk menampilkan kedua citra secara berdampingan. Fungsi imshow digunakan untuk            menampilkan citra dalam subplot, sementara set_title digunakan untuk memberikan judul pada setiap subplot.
   
  Dengan menggabungkan langkah-langkah diatas ini, sehingga saya dapat mengidentifikasi tepi dalam gambar dan menandai garis-garis yang     terdeteksi untuk tujuan analisis atau pengolahan selanjutnya.
   
3. Menjelaskan tahapan cara menyelesaikan projek dengan rinci.
   Berikut adalah tahapan-tahapan rinci untuk menyelesaikan proyek deteksi markah jalan atau deteksi  tepi dan garis menggunakan OpenCV:
   
   a. Mengimpor Libraries: Impor library yang diperlukan, yaitu cv2, numpy, dan matplotlib.pyplot.
   
   b. Memuat Gambar: Tentukan path (lokasi) gambar yang ingin Anda deteksi markanya. Gunakan fungsi cv2.imread() untuk membaca gambar           dari path yang ditentukan dan simpan hasilnya dalam variabel image.
   
   c. Konversi ke Grayscale: Gunakan fungsi cv2.cvtColor() dengan parameter cv2.COLOR_BGR2GRAY untuk mengubah gambar ke citra grayscale.        Simpan hasilnya dalam variabel gray.
   
   d. Mengurangi Noise dengan Gaussian Blur: Terapkan Gaussian Blur pada citra grayscale untuk mengurangi noise dan menghaluskan gambar.        Gunakan fungsi cv2.GaussianBlur() dengan kernel size (ukuran kernel) (5, 5) dan simpan hasilnya dalam variabel blur.
   
   e. Deteksi Tepi dengan Canny Edge Detection: Gunakan metode Canny untuk mendeteksi tepi pada citra yang telah di-blur sebelumnya.            Gunakan fungsi cv2.Canny() dengan threshold minimum dan maximum yang sesuai (dalam contoh ini 100 dan 150) dan simpan hasilnya            dalam variabel edges.
   
   f. Deteksi Garis dengan Hough Transform: Gunakan Transformasi Hough untuk mendeteksi garis dalam citra tepi yang telah didapatkan            sebelumnya. Gunakan fungsi cv2.HoughLinesP() dengan parameter-parameter yang sesuai (dalam contoh ini jarak resolusi rho adalah 1         pixel, jarak resolusi theta adalah 1 derajat, threshold adalah 100, panjang minimum garis adalah 100 pixel, dan jarak maksimum            antara segmen garis adalah 10 pixel). Simpan hasilnya dalam variabel lines.
   
   g. Menggambar Garis pada Gambar Asli: Iterasi melalui setiap garis yang terdeteksi dan gunakan fungsi cv2.line() untuk menggambar            garis pada gambar asli menggunakan koordinat titik awal dan akhir garis. Dalam contoh ini, garis digambar dengan warna hijau (0,          255, 0) dan ketebalan 3 piksel.
   
   h. Tampilkan Hasil Menggunakan Matplotlib: Gunakan fungsi plt.subplots() untuk membuat gambar dengan subplot. Tentukan jumlah subplot        (dalam contoh ini 1 baris dan 2 kolom) dan ukuran gambar (dalam contoh ini 10x10). Dapatkan akses ke subplot menggunakan                  axs.ravel(). Gunakan imshow() untuk menampilkan citra dalam setiap subplot, dan set_title() untuk memberikan judul pada setiap            subplot.
   
   i. Menampilkan Gambar: Panggil plt.show() untuk menampilkan gambar yang telah dihasilkan.

   Dengan mengikuti langkah-langkah ini, kita dapat memuat gambar, mengubahnya menjadi citra grayscale, mendeteksi tepi dan garis            menggunakan Canny dan Hough Transform, dan menampilkan hasilnya sesuai dengan yang diinginkan menggunakan Matplotlib.
