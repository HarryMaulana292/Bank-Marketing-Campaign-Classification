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

**`Metric Evaluation`**

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
## Conclusion

1. Dengan Accuracy sebesar 60,3%, maka model yang dibuat masih belum baik jika digunakan untuk memprediksi kedua kelas (nasabah yang deposit dan yang tidak deposit). Hal ini terjadi karena adanya trade-off antara recall dan presisi. Karena kita kita memfokuskan untuk memperbanyak prediksi benar untuk nasabah yang akan deposit, maka prediksi yang benar untuk nasabah yang tidak deposit akan berkurang. Adapun Error rate pada model yang digunakan adalah 39,7%.

1. Dengan Sensitivity sekitar 89,9%, maka model yang dibuat terbilang bagus jika digunakan untuk memprediksi kelas positif (nasabah yang deposit).

1. Dengan Specificity sekitar 31,7%, maka model yang dibuat terbilang sangat buruk jika digunakan untuk memprediksi kelas negatif (nasabah yang tidak akan deposit)

1. Dengan F2-Score sekitar 80,2%, maka model yang dibuat terbilang cukup baik jika digunakan untuk memprediksi nasabah yang akan deposit dan tidak deposit dengan lebih mementingkan kelas positif (nasabah yang melakukan deposit).

Adapun feature yang paling penting dalam klasifikasi nasabah yang akan deposit dan yang tidak deposit adalah feature contact_other (jenis komunikasi terakhir yang dilakukan kepada nasabah selain celullar dan telephone) lalu diikuti dengan feature poutcome_success (hasil kampanye marketing terakhir nasabah yang sukses). 

Selain itu, berdasarkan [thefinancialbrand.com](https://thefinancialbrand.com/news/bank-marketing/bank-marketing-budgets-advertising-roi-strategy-88835/), jika seandainya biaya kampanye marketing bank adalah $1 dan total waktu yang digunakan untuk marketing per nasabah adalah 5 menit maka : 
1. Tanpa menggunakan model machine learning (semua nasabah diasumsikan tertarik untuk deposit)

    Berdasarkan confusion matrix, jika semua nasabah diasumsikan tertarik maka ada 1465 total nasabah dan hanya ada 718 orang yang tertarik deposit, maka:
    * Total biaya yang dikeluarkan : 1465 x $1 = $1465
    * Kerugian sebesar : (1465 - 718) x $1 = $747
    * Total waktu yang digunakan : 1465 x 5 = 7325 menit atau sekitar 122,08 jam
  
2. Dengan menggunakan model machine learning (berdasarkan confusion matrix : 646 diprediksi benar deposit dan 510 diprediksi deposit namun tidak deposit)

    Berdasarkan confusion matrix, jika ada 1156 nasabah yang diprediksi akan deposit dan hanya ada 646 orang yang diprediksi benar deposit, maka:
    * Total biaya yang dikeluarkan : 1156 x $1 = $1156
    * Kerugian sebesar : (1156 - 646) x $1 = $510
    * Total waktu yang digunakan : 1156 x 5 = 5780 menit atau sekitar 96,33 jam

Dengan begini bank telah menghemat sekitar (747 - 510) = $237 sekitar biaya marketing atau dengan kata lain mengurangi kerugian marketing sebesar 31,7%. Selain itu, bank juga dapat menghemat waktu sekitar (122,08 - 96,33) = 25,75 jam atau mengurangi waktu yang digunakan untuk menghubungi tiap nasabah sekitar 21,09%.

---
## Recommendation

Hal-hal yang dapat dilakukan untuk mengembangkan project dan modelnya agar lebih baik untuk ke depannya adalah sebagai berikut.
* Data other pada feature contact dibuat lebih spesifik lagi. Dengan membuat data dari feature contact lebih spesifik selain cellular dan telephone (contoh : email, whatsapp, facebook, atau platform lainnya) sehingga informasi yang dapat diperoleh untuk feature yang paling penting dalam klasifikasi penentuan apakah nasabah akan deposit atau tidak bisa lebih jelas dan baik.
* Menambahkan data/feature baru seperti biaya marketing untuk tiap nasabah dan keuntungan yang diperoleh dari marketing yang dilakukan tiap nasabah. Dengan ini kita bisa melakukan analisis lebih lanjut terkait efisiensi marketing yang dilakukan terhadap nasabah. Data ini juga bisa kita gunakan untuk melakukan perhitungan keuntungan jika kita menggunakan model yang telah dibuat ini. 
* Memperbanyak data dari bank itu sendiri agar prediksi yang dibuat bisa semakin baik.
* Menggunakan hyperparameter space yang lebih luas untuk mencari hyperparameter terbaik jika tetap menggunakan model Adaboost.

---
Link Slide PPT dapat diakses di [sini](https://www.canva.com/design/DAFly_7VLhY/hkq7xcELBnH5rbi84fYocA/view?utm_content=DAFly_7VLhY&utm_campaign=designshare&utm_medium=link&utm_source=publishsharelink)

Model deploymeny using streamlit dapat diakses di [sini](https://harrymaulana292-deployment-bank-marketing-campaign-c-app-ilnq8b.streamlit.app/)
