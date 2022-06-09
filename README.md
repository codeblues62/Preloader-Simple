# Preloader-Simple
Jika anda pernah mengunjungi sebuah website maupun blog dimana ketika anda sedang membukanya tiba-tiba muncul animasi load, nah itulah yang disebut dengan preloader. Jadi, Preloader adalah sebuah fitur yang memunculkan proses load pada sebuah blog yang dapat kita terapkan dengan menggunakan jQuery, CSS, dan HTML.

## Lalu bagaimana cara kita membuatnya dari awal?
### Langkah Pertama: Siapkan File HTML
```html
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="content-type" content="text/html; charset=utf-8" />
        <title>Preloader Simple ~ CodeXDeres</title>
    </head>
    <body>
      
    </body>
</html>
```
> Kemudian simpan source code ini kedalam file yang berekstensi .html

Jangan lupa tuk menambahkan tag div kosong yang diberi id ring & class tengah `<div id="ring" class="tengah"></div>` sebanyak 4x didalam tag `<body></body>`. Seperti contoh dibawah ini:
```html
<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="content-type" content="text/html; charset=utf-8" />
        <title>Preloader Simple ~ CodeXDeres</title>
    </head>
    <body>
        <div id="ring1" class="tengah"></div>
        <div id="ring2" class="tengah"></div>
        <div id="ring3" class="tengah"></div>
        <div id="ring4" class="tengah"></div>
        
        <iframe src="https://www.facebook.com/" style="height:200px;width:300px;" title="Iframe Example"></iframe>
    </body>
</html>
```
> Jangan lupa tambahkan tag `<iframe></iframe>` untuk menampilkan **Frame** setelah _**Preloader**_ berhasil di load.

### Langkah Kedua: Styling Ring dengan cara Internal CSS atau bisa juga dipisahkan
```css
*{
  padding: 0;
  margin: 0;
}
.tengah{
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  margin: auto;
}
#ring1{
  height: 50px;
  width: 50px;
  border: 8px solid #ccc;
  border-top-color: #ffd700;
  box-shadow: 5px;
  border-radius: 100%;
  
  animation: kiri 2s linear infinite;
}
#ring2{
  height: 100px;
  width: 100px;
  border: 8px solid #ccc;
  border-left-color: #ffd700;
  box-shadow: 5px;
  border-radius: 100%;
  
  animation: kanan 2s linear infinite;
}
#ring3{
  height: 150px;
  width: 150px;
  border: 8px solid #ccc;
  border-right-color: #ffd700;
  border-bottom-color: #ffd700;
  box-shadow: 5px;
  border-radius: 100%;
  
  animation: crossX 3s linear infinite;
}
#ring4{
  height: 150px;
  width: 150px;
  border: 8px solid #ccc;
  border-right-color: #ffd700;
  border-bottom-color: #ffd700;
  box-shadow: 5px;
  border-radius: 100%;
  
  animation: crossY 3s linear infinite;
}

@keyframes kiri{
  0%{
    transform: rotate(0deg);
  }100%{
    transform: rotate(-360deg);
  }
}
@keyframes kanan{
  0%{
    transform: rotate(0deg);
  }100%{
    transform: rotate(360deg);
  }
}
@keyframes crossX{
  0%{
    transform: rotateX(0deg);
  }100%{
    transform: rotateX(-360deg);
  }
}
@keyframes crossY{
  0%{
    transform: rotateY(0deg);
  }100%{
    transform: rotateY(-360deg);
  }
}
```
> Yang membuat ring tersebut bisa berputar dikarenakan kita sudah menginialisasikan `@keyfame Animation` pada sintaks CSS kita. Seperti contoh dibawah ini:
```css
@keyframes crossY{
  0%{
    transform: rotateY(0deg);
  }100%{
    transform: rotateY(-360deg);
  }
}
```

### Langkah Ketiga: Buat Event Ring tersebut menghilang saat Frame akan muncul dengan cara Internal JS atau bisa juga dipisahkan
```javascript
var load1 = document.getElementById('ring1');
var load2 = document.getElementById('ring2');
var load3 = document.getElementById('ring3');
var load4 = document.getElementById('ring4');

window.addEventListener('load',function(){
  load1.style.display='none';
  load2.style.display='none';
  load3.style.display='none';
  load4.style.display='none';
})
```
> Yang membuat Ring tersebut bisa menghilang karena kita buat Event pada `JavaScript`. dengan contoh seperti berikut:
```javascript
// Membuat Variable dengan mengambil Element ID dari Tags HTML
var loading = document.getElementById('NamaID');

// Membuat Event apa yang ingin kita berikan, apakah itu click, load, mouseUp, mouseMove, dll
window.addEventListener('load',function(){
  loading.style.display='none';
})
```

> Bagi kamu yang ingin bergabung bersama komintas kami silahkan Click => [CodeXDeres Indonesian Community](https://t.me/codexderes)
