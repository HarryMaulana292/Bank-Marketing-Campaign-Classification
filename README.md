# Bank-Marketing-Campaign-Classification
---
## Business Problem Understanding
**`Context`**

Bank A adalah salah satu lembaga keuangan yang menyediakan berbagai produk dan layanan keuangan. Salah satu produk keuangan yang cukup dikenal masyarakat adalah deposito berjangka. Mekanisme deposito berjangka adalah nasabah mendepositokan sejumlah uang di bank atau lembaga keuangan, dan uang tersebut baru bisa diambil setelah jangka waktu tertentu. Sebagai kompensasinya, nasabah akan diberikan bunga tetap sesuai dengan nominal uang yang didepositokan.

Namun demikian, sebagai badan usaha yang memiliki produk keuangan dan nasabah masing-masing, bank tetap harus bersaing agar tidak kehilangan nasabah. Salah satu cara yang bisa dilakukan adalah dengan melakukan kampanye pemasaran.

**`Problem Statement`**

Kampanye pemasaran dapat memakan waktu dan sumber daya jika bank menargetkan semua nasabah tanpa melakukan penyaringan terlebih dahulu. Hal ini karena jika kampanye pemasarannya dilakukan kepada seluruh nasabah, maka waktu dan biaya tersebut akan menjadi sia-sia jika nasabahnya tidak akan deposit. 

Dengan ini, tim marketing bank ingin meningkatkan efisiensi kampanye pemasaran dengan mengetahui nasabah mana yang memiliki peluang tinggi akan deposit sehingga waktu dan sumber daya yang digunakan bisa lebih efisien.

**`Goals`**

Dari sekian banyak nasabah bank, akan membutuhkan banyak waktu dan biaya jika ingin menyeleksi secara manual nasabah yang memiliki potensi tinggi untuk deposit. Oleh karena itu, tim marketing bank ingin memiliki kemampuan untuk bisa memprediksi kemungkinan seorang nasabah akan deposit atau tidak agar kampanye pemasaran berjalan lebih efisien.

Selain itu, mereka juga ingin mengetahui faktor apa saja yang membuat nasabah mau deposit atau tidak. Dengan itu mereka dapat menyusun rencana yang jauh lebih baik dalam pendekatan kepada nasabah tersebut.

**`Analytic Approach`**

Berdasarkan permasalahan yang ada, kita akan melakukan analisis data untuk menemukan pola yang membedakan nasabah yang akan deposit dan yang tidak deposit.

Kemudian akan dibuat sebuah model klasifikasi yang akan membantu bank untuk dapat memprediksi probabilitas seorang nasabah akan deposit atau tidak.

Adapun tujuan kita melakukan klasifikasi ini pada dasarnya adalah untuk membantu bank mengoptimalkan upaya pemasaran mereka dengan cara yang lebih efektif.

Adapun tujuan secara khusus melakukan klasifikasi ini antara lain sebagai berikut.

1. `Identifikasi target pasar yang potensial`</p>
    Dengan menganalisis data nasabah yang ada, klasifikasi dapat membantu mengidentifikasi kelompok nasabah yang memiliki kecenderungan tinggi untuk melakukan deposit. Hal ini memungkinkan bank untuk fokus pada target pasar yang memiliki potensi tinggi untuk menghasilkan pendapatan lebih besar.

1. `Pengembangan strategi pemasaran yang tepat`</p>
    Dengan kita memahami karakteristik dan kebutuhan nasabah yang cenderung melakukan deposit, perusahaan dapat mengembangkan strategi pemasaran yang lebih tepat dan relevan. Misalnya, mereka dapat menyesuaikan pesan pemasaran, kanal komunikasi, atau penawaran produk yang disesuaikan dengan kebutuhan dan preferensi nasabah potensial.

1. `Pengelolaan sumber daya yang lebih efisien`</p>
    Dengan klasifikasi yang baik, bank dapat mengalokasikan sumber daya mareka dengan lebih efisien. Mereka dapat mengurangi biaya dan usaha yang tidak perlu dalam memasarkan produk atau layanan mereka kepada nasabah yang memiliki kecenderungan rendah untuk melakukan deposit. Sebaliknya, mereka dapat memfokuskan upaya pemasaran mereka pada nasabah yang lebih memungkinkan untuk melakukan deposit, menghasilkan hasil yang lebih baik dengan menggunakan sumberdaya yang tersedia seminimal mungkin.

   **Metric Evaluation**

Target :
* 0 : Nasabah `tidak deposit`
* 1 : Nasabah `deposit`

Type Error:
* FP (False Positive) : Nasabah diprediksi akan deposit namun ternyata tidak deposit</p>
    Konsekuensi FP : Waktu dan sumber daya yang digunakan kepada nasabah tersebut akan terbuang sia-sia

* FN (False Negative) : Nasabah diprediksi tidak akan deposit namun ternyata deposit</p>
    Konsekuensi FN : Bank akan kehilangan kesempatan untuk bisa mendapatkan keuntungan dari nasabah yang sebenarnya bisa deposit

Berdasarkan konsekuensinya, pada dasarnya recall dan presisi pada case ini penting sehingga kita akan menggunakan metrics F-Score. Perlu diketahui bahwa tujuan utama dari campaign pemasaran bank ini adalah untuk menarik lebih banyak nasabah agar deposit. Maka dari itu kita akan membuat model yang dapat memprediksi sebanyak mungkin kelas positif yang benar dan sesedikit mungkin prediksi false positif dan false negatif.

Kemudian, prioritas kita akan ditujukan untuk mengurangi False Negative sehingga bank tidak kehilangan kesempatan untuk mendapatkan nasabah yang deposit. Karena False Negative yang menjadi prioritas, maka recall dari model akan lebih diprioritaskan untuk ditingkatkan. Sehingga `metrics` F-Score yang digunakan adalah `F2-Score`.
---
