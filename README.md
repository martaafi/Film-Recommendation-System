# Film-Recommendation-System
## Pendahuluan
Tim Bisnis meminta untuk membuat Sistem Rekomendasi Film untuk dataset yang diberikan. Dataset yang diberikan adalah dataset MovieLens. Dataset ini berisi informasi mengenai film-film, rating pengguna, tag, dll. Anda diminta untuk membangun sistem rekomendasi yang dapat memberikan rekomendasi untuk film-film yang mungkin ingin dilihat pelanggan berdasarkan film-film yang sudah ditonton sebelumnya.

Dataset yang digunakan adalah dataset MovieLens (ml-25m) yang berisi rating bintang 5 dan aktivitas tagging teks bebas dari MovieLens, sebuah layanan rekomendasi film. Dataset ini berisi 27753444 rating dan 1.129 aplikasi tag dari sekitar 62.000 film. Data ini dibuat oleh 162.000 pengguna dan dirilis pada Desember 2019.
## Langkah Analisis
- **Penggabungan Dataset**: Menggabungkan dua dataset, yaitu `data_movies` dan `data_tags`, berdasarkan `movieID`. Hasil penggabungan ini menghasilkan daftar film yang pernah ditonton oleh pengguna, di mana setiap baris merepresentasikan satu film yang telah ditonton oleh seorang pengguna.  
- **Transformasi Data**: Data dikonversi ke dalam bentuk matriks biner, di mana setiap baris mewakili pengguna dan setiap kolom menunjukkan judul film. Kolom dengan nilai `1` menunjukkan bahwa pengguna telah menonton film tersebut, sedangkan nilai `0` menunjukkan bahwa pengguna belum menontonnya.  
- **Analisis Frequent Itemset**: Mengidentifikasi film-film yang sering ditonton bersama oleh pengguna menggunakan algoritma Apriori. Itemset dikatakan sering ditonton jika nilai supportnya lebih dari atau sama dengan `1%`. `support` adalah metrik yang digunakan untuk mengukur seberapa sering suatu itemset muncul dalam dataset.
- **Analisis Association Rules**: Menganalisis pola dan hubungan antarfilm berdasarkan frequent itemset untuk menemukan kombinasi film yang sering ditonton bersamaan oleh pengguna. Metrik yang digunakan adalah `confidence` dengan batas minimal adalah `1%`
## Tools
- Python
- Tableau
### Apa film yang paling sering ditonton oleh pengguna?
![image](https://github.com/user-attachments/assets/9363cce1-cf8f-4751-9651-05316ff61001)

Tiga film teratas yang paling sering ditonton oleh pengguna adalah `Star Wars: Episode IV - A New Hope (1977)`, `Pulp Fiction (1944)`, dan `Shawshank Redemption, The (1994)`.
### Apa kombinasi film yang paling sering muncul?
![image](https://github.com/user-attachments/assets/3e9c4e45-b7fc-4367-9553-f55db7ce9234)

Dua kombinasi film yang paling sering ditonton oleh pengguna adalah `Shwanshank Redemption, The (1994)` dan `Pulp Fiction (1994)`. Kedua film ini rilis di tahun yang sama dan memiliki popularitas yang tinggi. Hal ini membuat banyak orang yang menonton salah satunya, kemungkinan besar juga akan menonton yang lainnya karena sedang hype atau sedang banyak dibicarakan.

![image](https://github.com/user-attachments/assets/9abc1dfb-1bce-4746-9cf2-325f219a8feb)

Tiga kombinasi film yang paling sering ditonton adalah `Lord of the Rings: The Two Towers, The (2002)`, `Lord of the Rings: The Fellowship of the Ring, The (2001)`, dan `Lord of The Rings: The Return of the King, The (2003)`. Ketiga film ini merupakan bagian dari satu series, sehingga pengguna yang menonton salah satunya kemungkinan besar akan menonton seluruhnya karena alur ceritanya yang saling berhubungan.
### Apa film yang kemungkinan besar akan ditonton oleh pengguna ketika sebelumnya telah menonton film Incepton (2010)?
![image](https://github.com/user-attachments/assets/3508d21f-22ab-4d43-968a-109bfba62c1b)

Ketika pengguna telah menonton film `Inception (2010)`, kemungkinan besar pengguna juga akan menonton film `Matrix, The (1999)`, `Interstellar (2014)`, `Fight Club (1999)`, `Memento (2000)`, `Pulp Fiction (1994)`, dan `Shwanshank Redemption, The (1994)`. Film-film ini memiliki genre, tema, dan gaya penceritaan yang setipe.
### Apa saja film yang dapat direkomendasikan kepada penonton ketika sebelumnya telah menonton film Memento (2000)?
![image](https://github.com/user-attachments/assets/ae74636f-b599-4257-a1ad-24584e7ac87f)

Gambar di atas menunjukkan jaringan keterkaitan antar film yang sering ditonton bersamaan atau direkomendasikan kepada pengguna setelah menonton film tertentu. Jika seorang pengguna telah menonton `Memento (2000)`, maka film yang dapat direkomendasikan selanjutnya adalah `Inception (2010)`, `Pulp Fiction (1994)`, `Matrix, The (1999)`, dan `Fight Club (1999)`.

## Kesimpulan
- Pengguna cenderung lebih sering menonton film yang sedang populer atau sedang hype.
- Pengguna kemungkinan besar akan menonton semua film dalam satu seri atau film lain yang memiliki alur cerita yang saling berhubungan.
- Pengguna lebih tertarik menonton film dengan genre dan tema yang mirip dengan film yang telah mereka tonton sebelumnya.

## Sistem Rekomendasi Film
Dalam pembuatan sistem rekomendasi film, ada beberapa faktor penting yang perlu dipertimbangkan untuk memberikan rekomendasi yang relevan kepada pengguna, yaitu:
- Film yang sedang populer, terutama yang banyak ditonton dan mendapatkan ulasan positif.
- Film dengan genre serupa dengan film yang telah ditonton pengguna sebelumnya, sehingga sesuai dengan preferensinya.
- Film yang merupakan bagian dari sebuah seri, sehingga pengguna yang telah menonton film sebelumnya dalam seri tersebut kemungkinan besar akan tertarik menonton kelanjutannya.
