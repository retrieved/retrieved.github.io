---
layout: post
title: "octopress + github page di ubuntu"
date: 2014-07-21 04:38:39 +0800
comments: true
categories: 
---
Octopress adalah platform blogging yang "wow" direkomendasikan kepada siapapun yang tidak keberatan melakukan pekerjaan dengan sedikit codingan, tetapi dibalik semua itu anda akan belajar beberapa keterampilan baru yang kren misal nya, belajar apa itu version control system dengan <a href="http://git-scm.com/book/en/Getting-Started-About-Version-Control" target="_blank" style="text-decoration:none">GIT</a> dan pastinya memiliki blog yang keren.<blockquote>sudah banyak tutorial yang mendetail tentang cara membuat blog dengan octopress. situs resmi octopress memiliki dokumentasi yang mendetail, dan pada tutorial ini mecoba menuliskan kembali langkah - langkah setup octopress di ubuntu. ok langsung saja Let’s get started!!</blockquote>
Berikut langkah-langkah dan persiapan set-up octopress:
{% codeblock %}
install git
buat repository di github
install ruby (pada tutorial ini installasi ruby menggunakan rvm)
clone octopress github repository (master branch)
install tema default octopress
configurasi octopress untuk halam github deploy
generate, commit dan push blog anda di repository github(master branch)
buat post pertama anda
{% endcodeblock %}
<h5>Install Git</h5>
buka terminal pada ubuntu anda dengan menekan CTRL + ALT + T, dan ketikkan perintah ini :
{% codeblock Install Git %}
sudo add-apt-repository ppa:git-core/ppa
sudo apt-get update
sudo apt-get install git-core
{% endcodeblock %}
untuk melihat versi git ketikkan perintah berikut setelah intalasi selesai
{% codeblock %}
git --version
{% endcodeblock %}
<h5>Membuat account github baru dan sebuah halam github repository</h5>
Default penamaan konvensi untuk halaman repositori Github adalah {username}.github.io... Anda dapat mengakses halaman situs Github anda (HTML statis hanya) melalui URL berikut http:// {username} github.io.
Halaman Github dasarnya memungkinkan Anda untuk meng-host situs HTML statis langsung di Github. 
<!-- more -->
<h5>Install RVM</h5>
Sebelum kita melakukan installasi, kita harus menjalankan update untuk memastikan bahwa semua paket yang kita download ke VPS up to date:
{% codeblock %}
sudo apt-get update
{% endcodeblock %}
Setelah itu selesai, kita bisa mulai menginstal RVM, Manager Ruby Version. Ini adalah program besar yang memungkinkan Anda menggunakan beberapa versi Ruby pada satu server; Namun, dalam kasus ini, kita hanya akan menggunakannya untuk menginstal versi terbaru dari Ruby.jika di ubuntu anda belum terinstall curl maka lakukan langkah berikut :
{% codeblock %}
sudo apt-get install curl
{% endcodeblock %}
setelah itu kita akan mengintall RVM yang nanti digunakan untuk menginstall ruby
{% codeblock %}
\curl -L https://get.rvm.io | bash -s stable
source ~/.rvm/scripts/rvm
{% endcodeblock %}
setelah installasi selesai, kita perlu menginstall beberapa depedancies secara atomatis dengan menuliskan kode berikut pada terminal anda:
{% codeblock %}
rvm requirements
{% endcodeblock %}
<h5>install ruby</h5>
{% codeblock %}
rvm install ruby
{% endcodeblock %}
sekarang ruby dengan versi terakhir telah terinstall, Namun, karena kita diakses melalui sebuah program yang memiliki berbagai versi Ruby, kita perlu memberitahu sistem untuk menggunakan versi kita hanya diinstal secara default.
{% codeblock %}
rvm use ruby --default
{% endcodeblock %}
untuk memastikan installasi berhasil, ketikan perintah berikut untuk mengetahui versi ruby yang kita gunakan
{% codeblock %}
ruby --version
{% endcodeblock %}
<h5>Install RubyGems</h5>
Langkah berikutnya memastikan bahwa kita memiliki semua komponen yang diperlukan dari Ruby. Kita dapat terus menggunakan RVM untuk menginstal gems; ketik baris ini ke dalam terminal.
{% codeblock %}
rvm rubygems current
gem --version
{% endcodeblock %}
<h5>Clone halaman github repository octopress (master branch)</h5>
pada langkah ini Anda akan  mengkloning master barach dari repositori github Octopress resmi. Saya pikir sangat penting untuk dicatat bahwa lokasi di mana Anda clone repositori ini akan berfungsi sebagai direktori  repositori untuk blog Anda. Karena itu, saya sarankan penamaan direktori yang sama seperti repositori Github Pages Anda, misalnya ubuntu.github.io.
{% codeblock Clone halaman github repository octopress %}
cd <MAIN_GIT_DIR> // e.g. `cd /home/ubuntu/githome`
git clone https://github.com/imathis/octopress.git {USERNAME}.github.io
//`e.g. clones repo to  /home/ubuntu/githome/ubuntu.github.io`
{% endcodeblock %}
<blockquote>
catatan : pada bagian git ini mungkin ada sedikit keluhan jika Anda belum setup email global dan / atau nama pengguna. Jika itu terjadi, jalankan perintah yang diperlukan dan coba lagi.
</blockquote>
<h5>Install bundler</h5>
Sekarang Anda telah mengkloning repositori Octopress, Anda harus menginstal  ruby gems ​ tambahan yang dibutuhkan Octopress. 

Octopress source  memiliki sebuah file bernama `Gemfile`. File ini berisi daftar semua `ruby` `gems` ​​yang diperlukan, dan bundler akan melihat file ini dan secara otomatis mengambil `ruby` `gems` ​​yang diperlukan untuk Anda.
{% codeblock %}
gem install bundler
bundle install
{% endcodeblock %}
<h5>Install default theme</h5>
Pada bagian ini Anda siap untuk menginstal default tema Octopress. Untuk melakukan ini, Anda akan menggunakan perintah `rake`. The Octopress sumber berisi sebuah file bernama `Rakefile` yang mendefinisikan berbagai `rake` target (script) yang dapat dieksekusi melalui perintah `rake`
{% codeblock %}
rake install
{% endcodeblock %}
<h5>Konfigurasi Octopress pada halaman github deployment</h5>
Octopress memiliki script `rake` yang secara otomatis mengkonfigurasi repositori yang baru Anda kloning untuk deployment Github Pages. Script itu sendiri hanya memerlukan input minimal, tetapi penting untuk benar-benar memahami bagaimana menggunakannya.

Script ini telah diperbarui sejak Octopress 2.0 untuk mendukung bekerja dengan Github melalui HTTPS bukan pendekatan SSH yang lebih tradisional. Saya pribadi lebih suka pendekatan ini, karena Anda tidak perlu khawatir tentang menghasilkan kunci SSH.

Github sekarang merekomendasikan menggunakan HTTPS bukan SSH. <a href="https://github.com/blog/642-smart-http-support" target="_blank" style="text-decoration:none">klik disini</a> untuk lebih jelasnya.

Agar Octopress benar-benar mendukung HTTPS, ketika `rake` meminta Anda untuk memasukkan URL repositori Github, pastikan Anda menggunakan HTTPS untuk URL repositori (misalnya `https://github.com/ubuntu/ubuntu.github.io.git`) . Untuk referensi, URL SSH adalah: `git@github.com: ubuntu / ubuntu.github.io.git`. Jika Anda tertarik untuk bekerja dengan URL SSH, <a href="https://help.github.com/articles/generating-ssh-keys" target="_blank" style="text-decoration:none">klik disini</a> untuk lebih jelasnya..


beberapa hal penting dari perintah script itu:
<ol>
<li>mengganti nama asal octopress (origin remote octopress), ini akan membiarkan anda meperbarui octopress melalui remote octopress.</li>
<li>menambahkan ke halaman github repo anda sebagai default origin remote</li>
<li>perubahan branch aktif dari master ke source. Ini berarti bahwa root directory repositori sekarang akan dikaitkan dengan source branch dalam halaman github repositori Anda.</li>
<li>Ini akan mengkonfigurasi URL standar blog Anda berdasarkan pada URL repositori Github Pages (misalnya http://ubuntu.github.io)</li>
<li>menciptakan sebuah direktori baru bernama _deploy pada direktori repositori root anda. Direktori ini akan berisi kode yang berhubungan dengan master branch repositori Anda.</li>
</ol>
Satu hal penting yang perlu diperhatikan: direktori `_deploy`, yang sesuai dengan `master branch` dari halaman repositori Github, adalah di mana HTML dikompilasi dan ditempatkan. `master branch` berisi HTML yang akan disajikan kepada pengguna browser web ketika mengarahkan ke blog Anda.

`source` branch (yang juga kebetulan direktori repositori root anda misalnya /home/user/githome/ubuntu.github.io berisi `markdown` , `SASS`, `JavaScript` yang dikompilasi melalui Jekyll ke HTML.<br>
Anda harus memastikan bahwa semuanya telah diatur dengan benar dengan menjalankan perintah berikut:
{% codeblock %}
#di root repo directory anda
git remote -v
# hasil output remotes anda, :
#octopress https://github.com/imathis/octopress.git (fetch)
#octopress https://github.com/imathis/octopress.git (push)
#origin https://github.com/ubuntu/ubuntu.github.io.git (fetch)
#origin https://github.com/ubuntu/ubuntu.github.io.git (push)
git branch -a #mengkonfirmasi bahwa dir root repo menunjuk ke `source` branch
# source
cd deploy
git branch -a #mengkonfirmasi bahwa dir deploy menunjuk ke `master` branch
# master
cd\ #kembali ke root direktori anda
{% endcodeblock %}
<h5>Generate, commit, dan push blog anda ke Github (master branch)</h5>
Pada poin ini Anda dapat meng`generate` HTML anda, mem`preview`, dan melakukan `commit` untuk Github anda. Ada berbagai script `rake` yang dapat digunakan untuk melakukan tugas-tugas ini:
<ul>
<li><em>rake generate</em> : ini akan mengkompilasi segala sesuatu di <em>{root REPO direktori DIR> / source}</em> (<em>markdown, SASS,</em> dan <em>JavaScript</em>) dan menempatkan HTML yang dihasilkan ke dalam <em>{root REPO DIR> / folder publik}</em>.</li>
<li><em>rake preview</em> : ini akan menjalankan server web lokal (pada port 4000), yang akan membantu Anda melihat blog Anda secara lokal. Ini akan mendeteksi perubahan pada <em>markdown</em>, sehingga Anda bisa me refresh blog setelah melakukan perubahan <em>markdown</em> dan melihat kembali hasil perubahan itu.</li>
<li><em>rake deploy</em> :  Ini akan menyalin semua HTML yang dihasilkan dari <em>{root REPO DIR/public}</em> untuk <em>{root REPO DIR> / _deploy}</em> dan <em>commit</em> kemudian <em>push</em> kode di <em>{root REPO DIR / _deploy}</em> ke <em>master branch</em> repositori halaman Github  Anda.</li>
</ul>
Jadi silakan `generate` dan `push` `master` branch blog Anda ke Github.
{% codeblock %}
rake generate
rake deploy
# Catatan: Anda harus mengisikan username dan password Github anda
{% endcodeblock %}
<h5>Commit dan push source files anda ke github (source branch)</h5>
Tidak ada skrip `rake` untuk melakukan `source` branch Anda, sehingga Anda harus melakukannya dengan menggunakan `git`.

Melakukan `source` branch sangat penting, karena berfungsi sebagai dasar untuk HTML yang akan dihasilkan.

Pastikan Anda dalam direktori root untuk repositori Anda (lokal) ketika menjalankan perintah ini.
{% codeblock %}
git add .
git commit -m "initial commit for source files"
git push origin source
#NOTE: itu sangat penting untuk melakukan push dan commit ke source branch anda
{% endcodeblock %}
<h5>Buat postingan di blog pertama anda</h5>
untuk memastikan bahwa blog Octopress Anda bekerja dengan benar, saya sarankan membuat posting blog awal. Anda selalu dapat menghapus postingan ini nanti.
Untuk melakukan ini, Anda akan menjalankan `rake new_post ['Judul posting blog']` .
{% codeblock %}
rake new_post['Hello World']
# membuat source/_posts/2011-08-01-hello-world.markdown 
{% endcodeblock %}
Ini akan membuat file baru `markdown` di direktori `<root REPO DIR> / source / _posts`. Nama file `markdown` akan didasarkan dari judul yang Anda berikan dalam naskah `rake`. Nama ini juga akan berfungsi sebagai dasar untuk permalink Anda dengan posting blog.

Anda kemudian dapat pergi ke `<root REPO DIR> / source / _posts` dan mengedit file `markdown` yang baru dibuat. Saya merekomendasikan untuk menggunakan program seperti `MarkdownPad 2` untuk os window dan `gedit` pada ubuntu untuk melakukan pengeditan post anda.

Setiap file `markdown` akan memiliki YAML "header" dengan beberapa Octopress info spesifik yang akan digunakan ketika kompilasi `markdown` ke HTML.
untuk lebih detail nya silahkan kunjungi doc octopress <a href="http://octopress.org/docs/blogging/" target="_blank" style="text-decoration:none">di sini</a>
<br>
Di bawah header, Anda akan menambahkan `markdown` untuk postingan blog Anda. Setelah mengedit dan menyimpan file `markdown`, Anda mungkin ingin melihat itu, dan kemudian jika Anda senang dengan hal itu, commit dan push ke `master` branch repositori halaman github anda.
{% codeblock %}
rake generate
rake preview
# buka di tab baru dengan mengunjungi link ini > http://localhost:4000
rake deploy 
{% endcodeblock %}
Dan ingat untuk selalu commit `source` branch halaman github repository anda.dan menyimpan file `markdown`,
{% codeblock %}
#make sure your in the <ROOT REPO DIR>
git add .
git commit -m "added first blog post"
git push origin source 
{% endcodeblock %}
Jika Anda ingin menghapus postingan blog Anda, anda dapat menghapus file `markdown`. Dari `<root REPO DIR> / source / _posts`. Setelah memastikan sudah melakukan `rake generate` dan `rake deploy`.
<br>
<br>
<strong>Daftar Pustaka</strong>... :D<br>
http://robstrube.com/blog/2013/07/30/octopress-plus-github-pages-on-windows-tutorial/
