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

3. 
saya mengonfigurasi routing url dengan melakukan modifikasi file urls.py yang ada direktori main, lalu dilanjutkan dengan impor fungsi include pada file urls.py yang ada di direktori StockWise, serta memodifikasi variable patterns 


4. 
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








