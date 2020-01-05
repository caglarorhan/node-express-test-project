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
