
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

 Tugas 4

 1. Django UserCreationForm adalah sebuah bagian framework dari python. Form ini digunakan untuk membuat formulir pendaftaran pengguna dalam aplikasi web django.UserCreationForm menyediakan field sepeti username,password, email dan field yang yang sesuai dengan keinginan pengembang pada laman registrasi

    - Kelebihan
        - Mudah digunakan
        bagian dari framework django sehingga hanya butuh untuk mengimpor dan mengintegrasikan form ini untuk diaplikasikan
        - Memiliki validasi bawaan
        memiliki validasi bawaan seperti panjang password, email yang valid dan lain sebagainya
        - Fleksibilitas
        dapat mengkustomisasi field n dan menambah field sesuai keinginan.
    
    - Kekurangan
        - Terbatas pada Django
        dirancang khusus untuk pengguna aplikasi Django sehingg tidak dapat digunakan di framework lain
        - Hanya memiliki fitur dasar
        tidak memiliki fitur tambahan atau yang lebih canggih seperti konfirmasi email,verifikasi captcha dan fitur keamanan lainnya
        - Tidak dapat digunakan untuk semua kasus
        terdapat beberapa kasus yang tidk cukup menggunakan Django UserCreationForm


2. perbedaan antara autentikasi dan otorisasi dalam konteks Django adalah 
    autentikasi merupakan proses verifikasi identitas pengguna, verifikasi biasanya melibatkan username dan password yang disandigkan dengan data pengguna di database. tujuan autentikasi adalah bahwa haya pengguna yang terverifikasi dapat masuk ke sistem untuk menjaga akses ke sumber daya aplikasi. Sedangkan otorisasi merupakan izin untuk pengguna terverifikasi untuk melakukan tindakan tertentu dalam aplikasiberdasarkan peran pengguna. Tujuan dari otorisasi adalah membatasi akses pengguna terhadap tindakan di dalam aplikasi sesuai dengan perannya

    mengapa keduanya penting?
    - meninngkatkan keamanan
    penggunaan  autetnikasi dan otorisasi membantu keamanan aplikasi dengan memastikan pengguna yang terverifikasi yang masuk sistem dan meastikan pengguna yang terverifikasi hanya mendapatkan akses yang telah ditentukan
    - Menjaga privasi 
    Menjaga privasi pengguna dalam kebijakan keamanan data
    - Kenyamanan pengalaman pengguna
    Membuat pengguna merasa aman dengan fitur yang dimiliki aplikasi dengan hanya melihat data yang mereka inginkan

3. Cookies dalam konteks aplikasi web merupakan potongan data yang disimpan di perangkat clien pengguna saat mengunjungi situs web. Cookies digunakan oleh server web untuk mengidentifikasi dan melacak pengguna serta menyimpan informasi yang perlu dipertahankan antara permintaan-permintaan HTTP. Sedangkan Django menggunakan cookies untuk mengelola data pelanggan dengan cara melakukan konfigurasi terlebih dahulu kemudian melakukan pengaturan data sesi(dalam bentuk dictionary) kemudian penympanan dalam cookie dan yangterakhir melakukan pengambilan data sesi.Dengan menggunakan cookies untuk mengelola data sesi pengguna, Django memungkinkan pengembang untuk menyimpan informasi penting pada sisi klien pengguna dan mempertahankannya di seluruh sesi pengguna. Hal ini berguna untuk mengidentifikasi pengguna yang masuk, menyimpan preferensi, atau melacak status sesi.

4. penggunaan cookies aman secara default dalam pengembangan web jika diimplementasikan secara tepat sesuai dengan framework yang digunakan dan dilakukan pengawasan secara berkalauntuk menghindari beberapa resiko yang dapat ditimbulkan dari cookies, beberapa resiko penggunaan cookies adalah
    - Risiko privasi
    
        data yang diambil cookies rentan disalahgunakan oleh oknum tidak bertanggung jawab dalam organisasi pengebang(careless insider)
    - XSS

        Rentan akan serangan XSS yang berakibat data pengguna dapat diakses secara illegal
    - CSRF

        Rentan akan serangan CSRF yang mengakibatkan tindakan yang tidak diinginkan pengguna , dapat diatasi dengan menggunakan toke CSRF
    - Cookie theft


        rentan ke pencuriansesi pengguna yag mengakibatkan penyerang mendapatkan akses ke akun pengguna
    - Session Hijacking

        serangan untuk mengambil ali sesi dari pengguna terverifikasi, dapat dicegah dengan melakukan enkripsi data
    - Cookie overflow

        terlalu besarnya ukuran cookies sehingga menggangu peforma aplikasi
    - Cookie sniffing

        pencurian yang terjadi akibat koneksi yang tidak aman
    - Cookies kadaluwarsa

        Cookies yang tidak kadaluwarsa dengan baik dapat memberikan risiko bagi pengguna jika data sesi atau otentikasi 
        tersimpan terlalu lama.

5. Step -step

    - Implementasikan fungsi registrasi, login, dan logout untuk memungkinkan pengguna untuk mengakses aplikasi sebelumnya dengan lancar.
        - Impor beberapa modulyang diperlukan(disini saya menggunakan UserCreationForm)
        - buat method agar menampilkan beberapa fitur yang diinginkan
        - buat page html baru untuk laman register
        - kemudian impor fungsi yang dibuat di urls.py dan tambahkan path untuk mengakses fungsi yang sudah diimpor
        - untuk fungsi login lakukan import modul yang diperlukan
        - edit fungsi login yang telah saya buat sebelumnya untuk dapat melakukan autentikasi
        - buat page login dengan html
        - kemudian impor fungsi yang dibuat di urls.py dan tambahkan path untuk mengakses fungsi yang sudah diimpor
        - untuk fungsi logout step yang diperlukan sama dengan login namun terdapat perbedaan di implementasi method
    
    - Membuat dua akun pengguna dengan masing-masing tiga dummy data menggunakan model yang telah dibuat pada aplikasi sebelumnya untuk setiap akun di lokal.
        - meregister dua akun
        - login akun pertama
        - menambahkan 3 data produk
        - ulangi dari step kedua untuk akun kedua

    - Menghubungkan model Item dengan User.
        - import modul yang dibutuhkan
        - isi user pada models.py method Product dengan "models.ForeignKey(User, on_delete=models.CASCADE)"
        - ubah conditional   pada create product agar sesuai dengan user yang diautentikasi
        - isi variablename pada method show_main di views.py dengan "request.user.username"
    
    - Menampilkan detail informasi pengguna yang sedang logged in seperti username dan menerapkan cookies seperti last login pada halaman utama aplikasi.
        - buat perubahan pada method login_user untuk dapat menampilkan last login
        - tambhakan last login pada show_main dengan isi  "request.COOKIES['last_login']"
        - kemudian ubah fungsi logout agar menyimpan cookies last login
        - tambahkan tulisan untuk last login di main.html



Tugas 5

1. elemen selector yang umum digunakan
    - Universal selector
    digunakan untuk memilih semua dokumen di HTML, digunakan ketika mengatur padding, amrgin atau nilaiu default lainnya.
    - Type Selector
   memilih elemen dengan tipe tertentu, digunkan untuk mengatur gaya secaraumum pada type trertentu
    - Class Selector
    memilih elemen dengan kelas tertentu, digunakan untuk mengaplikasikan gaya ke elemen dengan class yang sama

2. beberapa HTML5tag yang saya ketahui
    <html>: Elemen root yang mengelilingi seluruh konten halaman web.
    <head>: Berisi informasi meta, tautan ke berkas eksternal, dan elemen-elemen lain yang tidak terlihat oleh pengguna.
    <title>: Menentukan judul halaman yang akan ditampilkan di bilah judul browser.
    <meta>: Digunakan untuk memberikan informasi meta tentang halaman web, seperti karakter set dan deskripsi.
    <style>: Mengandung aturan gaya CSS yang diterapkan pada elemen di halaman.
    <script>: Digunakan untuk menyisipkan kode JavaScript ke dalam halaman web.
    <body>: Berisi semua konten yang akan ditampilkan di halaman web, seperti teks, gambar, dan elemen-elemen interaktif.
    <h1>, <h2>, ...,: Elemen heading yang digunakan untuk mengatur hierarki judul dalam dokumen.
    <div>: Elemen kontainer umum yang digunakan untuk mengelompokkan dan mengatur elemen-elemen lain.

3. Margin adalah ruang di luar batas elemen HTML yang digunakan untuk mengatur jarak antara elemen dengan elemen lain di sekitarnya. Sebaliknya, padding adalah ruang di dalam batas elemen yang mengatur jarak antara konten elemen dan batas elemen itu sendiri. Margin tidak memiliki warna dan dapat tumpang tindih dengan margin elemen lain, sedangkan padding dapat memiliki warna dan tidak tumpang tindih dengan padding elemen lain. Keduanya penting dalam mengatur tata letak dan tampilan elemen di halaman web.
4. Bootstrap adalah framework CSS yang menawarkan gaya dan komponen siap pakai, sangat cocok untuk proyek dengan tenggat waktu cepat dan tim besar. Tailwind CSS, di sisi lain, mengadopsi pendekatan "utility-first" yang memberikan fleksibilitas yang besar dalam mengatur tampilan sesuai kebutuhan. Pilih Bootstrap jika  menginginkan solusi cepat dan baku, sementara Tailwind cocok untuk pengembang yang ingin lebih mengutamakan kontrol desain dan tampilan yang lebih kustom sesuai proyeknya.
5. implementasi setiap checklist
    saya mencoba menggunakan bootsrap dan  tailwind anmun pada akhirnya say ahanya menggunakan bootstrap karena ada beberap template dengan dokunetasi yang mudah dipahami sehingga memudahkan saya.
    setiap page saya menerapka suatu font theme yaitu kuning dan hitam dengan melakukan setting baik di bagian body, table script dan sebagainya
    pada tugas kali ini, untuk memahami HTMLtag5 dan bentuk template saya banyak dibantu oleh AI. seperti bagaimana cara iterasi untuk setiap product dan menghapusnya
    pada daftar inventory, saya mencoba menggunakan card yang sudah ada templatenya, namun saya  coba cocokan dengan elemen yang saya buat di HTML saya.

