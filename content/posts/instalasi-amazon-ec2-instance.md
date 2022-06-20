+++ 
draft = false
date = 2022-06-18T21:30:11+07:00
title = "Instalasi Amazon EC2 Instance"
description = "Cara instalasi Amazon EC2 Instance pada AWS"
slug = ""
authors = ["Pajri Zahrawaani Ahmad"]
tags = ["AWS","Cloud Computing"]
categories = ["AWS"]
externalLink = ""
series = []
+++

## Apa itu AWS?
&nbsp;&nbsp;&nbsp;&nbsp; __AWS (Amazon Web Service)__ merupakan salah satu penyedia layanan komputasi awan (*cloud computing*) yang banyak digunakan di seluruh dunia. AWS sendiri memiliki banyak sekali fitur-fitur yang berguna salah satunya yaitu Amazon EC2. Fitur-fitur pada AWS dikelompokkan menjadi 3 kategori, yaitu *free trials* yang memiliki durasi layanan yang pendek, 12 *months free* yang memiliki durasi layanan 12 bulan (1 tahun) yang dihitung sejak pertama kali mendaftar, dan *always free* yang tidak memiliki durasi dalam pemakaiannya.

&nbsp;&nbsp;&nbsp;&nbsp; __Amazon EC2 (Elastic Compute Cloud)__ merupakan salah satu fitur dari AWS yang menyediakan kapasitas komputasi yang dapat diskalakan. AWS dapat digunakan untuk membuat, mengonfigurasi keamanan dan jaringan server virtual (VPS) sesuai kebutuhan. Amazon EC2 memungkinkan penggunanya dapat meningkatkan ataupun menurunkan skala untuk untuk menangani perubahan ataupun mengurangi kebutuhan untuk memperkirakan traffic. Untuk Amazon EC2 sendiri termasuk pada kategori __12 *months free*__.

<center>
	<script type="text/javascript">
		atOptions = {
			'key' : 'fde2bfab6f69ce53948ce55e9d8aa544',
			'format' : 'iframe',
			'height' : 50,
			'width' : 320,
			'params' : {}
		};
		document.write('<scr' + 'ipt type="text/javascript" src="http' + (location.protocol === 'https:' ? 's' : '') + '://www.topdisplayformat.com/fde2bfab6f69ce53948ce55e9d8aa544/invoke.js"></scr' + 'ipt>');
	</script>
</center>

## Pembuatan Amazon EC2 Instance
Dibawah ini langkah-langkah dalam pembuatan Amazon EC2 Instance:
1. Login terlebuh dahulu ke [AWS Console](https://aws.amazon.com/console/) (sebagai root user). Jika belum punya akun, bisa mendaftar terlebih dahulu.
	
	{{<figure src="/images/instalasi-amazon-ec2-instance/step_1.PNG" caption="Gambar 1 Login AWS Console" >}}

1. Setelah login, maka akan dialihkan pada dashboard AWS. Pada bagian *Build a solution*, pilih layanan "Launch a virtual machine with EC2" pada AWS Management Console.

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_2.PNG" caption="Gambar 2 Pilihan fitur AWS" >}}

1. Selanjutnya, pilih OS Image yang memiliki label "*free tier eligible*" supaya dapat digunakan tanpa mengurangi credit (untuk contoh saya memilih OS Ubuntu 18.04 64-bit).

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_3.PNG" caption="Gambar 3 Tampilan pemilihan OS" >}}

1. Lalu pada instance type, pilih tipe yang memiliki label "*free tier eligible*" (untuk contoh saya memilih tipe t2.micro).

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_4.PNG" caption="Gambar 4 Tampilan pemilihan OS Type">}}


1. Kemudian pada bagian Key pair (login), klik "create new key pair".
	
	{{<figure src="/images/instalasi-amazon-ec2-instance/step_5.1.PNG" caption="Gambar 5.1 Tampilan pengaturan key pair">}}

	&nbsp;&nbsp;&nbsp;&nbsp; Ketika menekannya, maka akan muncul form seperti gambar 5.2. Kemudian isi key pair name sesuai keinginan, pilih key type "RSA" dan private key format (saya memakai putty, jadi saya pilih format .ppk), jika sudah kemudian klik "Create key pair". Maka akan ada file key yang otomatis terunduh sesuai format yang sebelumnya dipilih.

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_5.2.PNG" caption="Gambar 5.2 Tampilan lanjutan pengaturan key pair">}}

1. Untuk bagian *network settings*, dapat diatur seperti pada gambar dibawah ini.

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_6.PNG" caption="Gambar 6 Tampilan pengaturan network">}}

1. Untuk bagian "*Configure storage*" dapat dibiarkan saja (*default*). Jika pengaturan dirasa sudah sesuai, bisa menekan "*Launch instance*" pada bagian "*Summary*" untuk membuat VM/Instance. Jika ingin membuat lebih dari 1 VM secara bersamaan, dapat dilakukan dengan mengisi "Number of instances" sesuai dengan jumlah yang diinginkan.

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_7.PNG" caption="Gambar 7 Tampilan AWS Management Console">}}

1. Ketika instance berhasil dibuat, akan ada tampilan seperti pada gambar dibawah ini.

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_8.PNG" caption="Gambar 8 Tampilan ketika Instance berhasil dibuat">}}

1.  Melihat informasi instance yang telah dibuat dengan menekan tombol "View all instances". Maka akan muncul tampilan seperti pada gambar dibawah ini.

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_9.PNG" caption="Gambar 9 Tampilan Dashboard Instances">}}

<center>
	<script type="text/javascript">
		atOptions = {
			'key' : 'fde2bfab6f69ce53948ce55e9d8aa544',
			'format' : 'iframe',
			'height' : 50,
			'width' : 320,
			'params' : {}
		};
		document.write('<scr' + 'ipt type="text/javascript" src="http' + (location.protocol === 'https:' ? 's' : '') + '://www.topdisplayformat.com/fde2bfab6f69ce53948ce55e9d8aa544/invoke.js"></scr' + 'ipt>');
	</script>
</center>

## Akses Instance lewat PuTTY
1. Buka software PuTTY, kemudian buka menu Connection > SSH > Auth, lalu masukkan file .ppk yang sebelumnya terunduh, kemudian klik Open.

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_10.PNG" caption="Gambar 10 Membuka private key pada PuTTY">}}

1. Kemudian buka menu Session, lalu isi \<ubuntu\>@\<Public IP\> pada hostname, lalu klik "Open".

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_11.PNG" caption="Gambar 11 Tampilan PuTTY">}}

1. VM/Instance sudah dapat diakses.

	{{<figure src="/images/instalasi-amazon-ec2-instance/step_12.PNG" caption="Gambar 12 Tampilan Terminal shell Instance">}}

## Refference
* https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/concepts.html
* https://id.wikipedia.org/wiki/Amazon_Web_Services
* https://www.kodingindonesia.com/belajar-aws-ec2-bagian-1-membuat-instance-amazone-web-services-elastic-compute-cloud/