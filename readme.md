**Express Notlari**

- `npm i express` ile son surumu indirilip kurulur


    const express = require('express'); // ile dahil edilir    
    const app = express(); ile calistirilir
    
    // kodlar, route'lar vb.
    // Ornek route
    app.get('/about', (req, res)=>{
        res.send('HTML, text veya json gonderilir');
    });
    
    app.listen(3000, ()=>{
    
    };  // ile istenilen portu dinlemesi saglanir,
        //gelen requestlere karsi, ve url isteklerine cevap verir
    
- `res.send()` ile gonderilen cevaplarin json formatinda(obje) yazilanlari express tarafindan otomatik json formatina donusturulup gonderilir. Birden fazla nesne gonderilecekse dizi icerisinde dizi elemani olarak gonderilebilirler.

- `__dirname` ilgili dosyanin yolunu verir, klasor dahil doya adi haric verecektir

- `path` built in core modulu dosya yollariyla ilgili islemler icin onemlidir

- `const path = require('path')`; // ile dahil edilir
- `path.join(__dirname, '../public')` seklinde kullanimi vardir
- Bu durumda statik dosyalar icin yol (ornegin `index.html, index.js, index.css` icin)

        const publicDirectoryPath = path.join(__dirname, '../public');
        app.use(express.static(publicDirectoryPath)); 
   olacaktir. Baska bir degisle bu klasordeki tum dosyalar (html, css, js, jpg, etc.) statik olarak talep edildiginde sunulabilecektir. 
   
    
    


- statik icerikler `./public` klasorunden sunulabilir
- middleware gibi statik sayfalar da (.html vb) `app.use(express.static(statikDosyayolu));`// seklinde sunulabilir


**View Engines -for Express**

-Handlebar'in express icin uyumlu hale getirilmis versiyonu: **HBS** (hbs)

`app.set('view engine','hbs')` ile tum middlewarelerin ustunde ekleriz 

View templateleri kok dizinde ``views`` klasorunde yer alirlar, template dosyalari `.hbs` uzantisini tasirlar.

Kullanimlari sirasinda route icindeki callback fonksiyonunda `res.send() ` yerine `res.render()` kullanmaktir. res.render'a sadece handlebars dosyasinin adini vermemiz gereklidir. Ikinci parametreler ise nesne olarak template e veri gondermeye yarar.

- Eger default olan `views` klasoru yerine baska klasor kullanmak istersek  bunu:
        
        const yeniPath = path.join(__dirname, '../yeniTemplateKlasoru')
        app.set('views', yeniPath); 
ile yapabiliriz.    
    


    app.get('', (req,res)=>{
        res.render('index')
    })
