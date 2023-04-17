# Tugas lab4_php_modular

### program masih menggunakan dari praktikum 3 hanya dimodifikasi pada praktikum 4 yang ditambahkan file-file seperti header.php dan footer.php serta file lainya seperti .htaccess dan index.php yang ada dalam module praktikum
 

* Buat file header dan footer lalu aplikasikan pada program 

* Halaman Home praktikum 4
  
<img src="gambar/sshf home.png">


*  Halaman tambah barang praktikum 4
  
<img src="gambar/sshf tambah.png">

## Membuat Routing
  
Routing digunakan untuk mempermudah akses halaman web agar SEO Friendly. Langkah awal adalah menyiapkan file utama index.php yang berisi routing untuk mengakses banyak halaman

    <?php

    $mod = @$_REQUEST['mod'];

    switch ($mod) {
        case "home":
            require("home.php");
            break;
        case "tambah":
            require("tambah.php");
            break;
        default:
            require("home.php");
    }
    ?>

* Aktivasi mod_rewrite (.htaccess)
  
Langkah awal yang harus disiapkan adalah aktivasi mod_rewrite pada webserver Apache2 pada configurasi httpd.conf. dan melakukan un-comment pada salah satu baris yg dituju
dan membuat file .htaccess seperti ini

    
    <IfModule mod_rewrite.c>
        RewriteEngine On
        RewriteBase /LAB4_PHP_MODULAR/

        RewriteCond %{REQUEST_FILENAME} !-f
        RewriteCond %{REQUEST_FILENAME} !-d
        RewriteRule ^(.*)$ index.php?mod=$1 [L]
    </IfModule>

hasilnya setelah routing
* Halaman Home routing praktikum 4
  
 <img src="gambar/ss l home.png">

* Halaman tambah barang routing praktikum 4
  
 <img src="gambar/ss l tambah.png">

