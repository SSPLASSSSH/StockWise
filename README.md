
Tugas 2

- tautan ke adaptable aplikasi saya
https://stockwise.adaptable.app

- penjelasan mengenai implementasi mulai dari inisiasi repository sampai routing url dan deploy ke adaptable

1. Membuat proyek Django baru
Dimulai dengan menginisiasi repository untuk proyek baru, disini saya menamai repository dengan nama StockWise, lalu
saya melakukan deployment django dengan terlebih dahulu mengaktivasi python virtual enviroment lalu menyiapkan library maupun modul yang dibutuhkan di requirements.txt yang kemudian dipasang dengan mengaktifkannya pada command promtp yang telah diaktifkan virtual enviroment. lalu saya membuat proyek django saya dengan nama StockWise dan melakukan push ke repository yang telah saya buat

2. pembuatan aplikasi  main
dengan menjalankan perintah "python manage.py startapp main"(notes : virtual enviroment sudah diaktifkan terlebih dahulu ), saya mulai menginisiasi dengan mendaftarkan aplikasi "main" ke dalam variabel INSTALLED_APP, kemudian membuat dan mengisi main.html. 
Kemudian tambahkan beberapa elemen di models.py(notes : untuk sementara saya hanya menambahkan category), lalu lakukan migrasi model dengan "python manage.py makemigrations" dan "python manage.py migrate"
lalu saya menghubungkan view dengan template dengan menambahkan "from django.shortcuts import render" di views.py dan melakukan modifikasi di fungsi show_main dan diikuti dengan memodifikasi file html.

3. Routing URl
saya mengonfigurasi routing url dengan melakukan modifikasi file urls.py yang ada direktori main, lalu dilanjutkan dengan impor fungsi include pada file urls.py yang ada di direktori StockWise, serta memodifikasi variable patterns 


4. Deploy ke adaptable
deployment saya lakukan dengan cara menghubungkan repository saya dengan adaptable. lalu memilih konfigurasi python dan command yang sesuai, pada adaptable saya menamai aplikasi saya dengan nama SstockwiseE.


- penjelasan mengenai bagan yang berisi request client ke web aplikasi berbasis Django

                                                            
            Client Request     ----->          Django        
            (HTTP Request)                     Web Server    
                                                        
                            |
                            |
                            v
                                        
                        Django View    
                        (views.py)     
                                        
                            |
                            |
                            v
                                        
                            Model Data     
                        (models.py)   
                                        
                            |
                            |
                            v
                                        
                        HTML Template  
                        (HTML File)    
                                        
                            |
                            |
                            v
                                        
                        Server Response 
                        (HTTP Response) 
                                        
                            |
                            |
                            v
                                        
                        Client Browser

- urls.py digunakan sebagai routing dalam aplikasi django yang aka memetakan url yang direquest oleh client ke fungsi atau kelas yang sesuai di views.py

- views.py akan meneruskan request yang didapat dari urls.py untuk diatur sesuai dengan fungsi atau kelas yang akan mengambil permintaan, memprosesnya, dan menghasilkan respons.

-models.py berisi model data yang digunakan untuk mengatur dan mengelola data dari aplikasi. model data ini menghubungkan aplikasi dengan basis data. data yang diterima dari views akan dihubungkan melalui ini.


- penggunaan virtual environment
digunakan untuk mengisolasi depedensi paket, hal ini dilakukan agar tidak ada paket yang bertabrakan dengan proyek lain, selain itu virtual enviroment juga digunakan untuk menjaga setiap update paket sehingga memudahkan saya untuk menjaga paket yag saya inginkan

- MVC,MVT, dan MVVM
MVC adalah singkatan dari "Model-View-Controller," yang merupakan sebuah pola arsitektur perangkat lunak yang digunakan dalam pengembangan aplikasi. Pola arsitektur ini bertujuan untuk memisahkan komponen-komponen utama dalam sebuah aplikasi agar lebih terorganisir dan mudah dikelola. 
MVT adalah singkatan dari Model-View-Template. MVT adalah sebuah konsep arsitektur yang digunakan dalam pengembangan web untuk memisahkan komponen-komponen utama dari sebuah aplikasi.MVT merupakan variasi pola dari MVC yang menggunakan kerangka Django dari python
MVVM adalah singkatan dari "Model-View-ViewModel," yang merupakan pola arsitektur yang digunakan dalam pengembangan perangkat lunak, khususnya aplikasi dengan antarmuka pengguna (UI) yang kompleks. 
 
perbedaan MVC,MVT dan MVVM terletak pada komponen tambahan,data binding,kompleksitas, dan penggunaan umum

pada komponen tambahan MVC memiliki controller untuk mengontrol aplikasi, di MVT ada template yang digunakan untuk merender tampilan HTML. dan di MVVM terdapat ViewModel yang digunakan untuk mengelola data yang ditampilkan di View dan mendukung pengikatan data (data binding).

pada data binding MVC tidak memiliki mekanisme bawaan, di MVT dapat menggunakan template dari django, dan di MVVM terdapat mekanisme bawaan untuk mengatur UI yag kompleks.

mengenai kompleksitas, MVC merupakan arsitektur yang paling sederhana, MVT memiliki beberap fitur tambahan daripada MVC, dan MVVM merupakan arsitektur yang paling canggih

dan dari sisi penggunaan MVC digunakan secara luas untuk berbagai jenis aplikasi termasuk pengembangan web dan aplikasi desktop. MVT digunakan untuk pengembangan aplikasi web dengan menggunakan kerangka kerja Django. dan MVVM untuk  pengembangan aplikasi desktop dan mobile dengan antarmuka pengguna yang kompleks, 


Tugas 3

1. Beberapa perbedaan POST dan GET di Django

    - Metode HTTPS yang digunakan
    pada POST, Variabel data yang dikirim tidak ditampilkan pada URL, sedangkan pada GET, variabel data dikirim terlihat di URL sehingga cocok untuk permintaan yang memmbutuhkan pergantian atau masukkan data variabel baru

    - keamanan data yang dikirim
    untuk data yang bersifat rahasia seperti password, disarankan untuk menggunakan POST sedangkan data-data yang dinilai tidak terlalu privasi dapat menggunakan GET

    - Penggunaan ideal
    Penggunaan POST untuk data yang dikirim melalui server biasaya untuk input data melalui form sedangkan Penggunaan GET untuk mengambil data dari server, atau biasanya untuk input data melalui link

    - Pembatasan panjang string
    pada POST String tidak memiliki batasan sedangkan pada GET memiliki batasan untuk string sepanjang 2047 char

2. Perbedaan utama antara XML, JSON, dan HTML dalam konteks pengiriman data?

    - Tujuan penggunaan
        - XML memiliki tujuan untuk menggambarkan dan mentransfer data, serta struktur data yang sangat kuat dan fleksibel, seperti pertukaran data antar sistem
        - JSON memiliki tujuan untuk pertukaran data antar aplikasi dan server karena memiliki  format yang ringkas dan ringan. penggunaan secara umum untuk pengembangan web
        - HTML memiliki tujuan untuk membuat struktur dan tampilan konten web. berfungsi untuk mengirim data dan merender halaman web

    - Syntax
        - XML memiliki syntax yang lebih rumit dengan elemen-elemen yang diapit oleh tag, atribut, dan struktur yang sangat berlapis-lapis sehingga menyulitkan dibaca manusia secara langsung
        - JSON menggunakan syntax yang lebih sederhana dengan menggunakan key-value pairs yang diapit {} ,hal ini memudahkan manusia membaca secara langsung
        - HTML menggunakan syntax berbasis tag yang mendefinisikan elemen-elemen dan struktur halaman web.

    - Struktur data
        - XML Digunakan untuk menggambarkan data dan struktur data yang sangat terstruktur dan hierarkis.
        - JSON digunakan untuk mengirim data yang memiliki struktur yang lebih sederhana daripada XM
        - HTML Dikhususkan untuk menentukan tampilan dan struktur konten web

3. Beberapa alasan mengapa  JSON sering digunakan dalam pertukaran data antara aplikasi web modern
    - Syntax yang ringan dan ringkas sehingga memiliki payload yang lebih kecil sehingga berpengaruh pada bandwidth yang digunakan

    - Mudah dibaca manusia sehingga dapat lebih mudah dalam pengembangannya

    - Didukung oleh banyak bahasa pemrograman

    - Tidak terkait dengan aplikasi tertentu sehingga dapat digunakan antar platform

    - Terintegrasi dengan browser sehingga mempermudah pertukaran data antara server dan browser

    - Penggunaan secara umum sehingga telah menjadi stadar di komunitas pengembangan web

    dengan kelebihan tersebut pengembang menjadi lebih mudah untuk membuat aplikasi web yang efisien dan mudah dimaintain.

4. Penjelasan kode

    - Membuat input form untuk menambahkan objek model pada app sebelumnya.
        - Membuat kerangka view dengan membuat templates yang diisi base.html
        - Lalu lakukan extends di main.html ke base.html
        - Buat forms.py di main dengan isi model dan deklarasi setiap fields
        - Impor beberapa modul yang dibutuhkan di views.py
        - buat method agar menerima submit  pada form dan menyimpan di views.py

    - Tambahkan 5 fungsi views untuk melihat objek yang sudah ditambahkan dalam format HTML, XML, JSON, XML by ID, dan JSON by ID.
        - Import dan tambahkan path di urls.py untuk HTML
        - buat berkas html baru pada main/template untuk menerima input product
        - kemudian edit main.html agar semua elemen ditampilkan
        - Import modul yang diperlukan pada views.py
        - buat method yang menerima input request untuk diubah menjadi format lain seperti  XML, JSON, XML by ID, dan JSON by ID dengan menggunakan modul serializers. step ini dilakukan satu per satu sesuai format yang diinginkan
    
    - Membuat routing URL untuk masing-masing views
        - import setiap tipe views pada urls.py
        - tambahkan path setiap view pada variabels url_patterns di urls.py
        - cek menggunakan python manage.py runserver di cmd lalu buka localhost/[nama views]

5. SS akses kelima url menggunakan postman
    - HTML
    [![HTML-fix.png](https://i.postimg.cc/yxMMLxhJ/HTML-fix.png)](https://postimg.cc/ctckHsbZ)
    - XML
    [![XML.png](https://i.postimg.cc/Jh3jn2YS/XML.png)](https://postimg.cc/bGJZV3hR)
    - JSON
    [![JSON.png](https://i.postimg.cc/MZg41cpx/JSON.png)](https://postimg.cc/7bMmkZzQ)
    - XML by ID
    [![XML-by-ID.png](https://i.postimg.cc/LXwyk7Rv/XML-by-ID.png)](https://postimg.cc/0MGdPVzJ)
    - JSON by ID
    [![JSON-by-ID.png](https://i.postimg.cc/B6K53v9c/JSON-by-ID.png)](https://postimg.cc/CBwnHSKz)        




