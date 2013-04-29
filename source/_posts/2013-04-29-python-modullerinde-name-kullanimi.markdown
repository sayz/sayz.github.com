---
layout: post
title: "python modüllerinde __name__ Özelliğinin kullanımı"
date: 2013-04-29 22:45
comments: true
categories: [python, '19']
---

####Modüller yenilir mi, içilir mi?

Öncelikle python'da modüllerden ufak bi' bahsedeyim. Bildiğiniz gibi **bir betik içersinde** kodlarımızı tekrar tekrar yazmamak için bir kez fonksiyon tanımlamamız yeterli. O fonksiyonu kullanarak kodları tekrar kullanabiliyoruz. Peki ya aynı fonksiyona başka bir Python programında da ihtiyacımız olursa ne yapacağız? Cevap tabii ki modül kullanmak. 

Python'da modül yazmak için birçok metod var ama bunlardan en basit ve en yaygın olanı fonksiyonlar ve değişkenler için .py uzantılı dosyaları kullanmak. Yani **evet**, şimdiye kadar yazdığınız her python betiği aynı zamanda birer modül. Diğer bir modül oluşturma yöntemi de [C veya C++ programlama dilleri ile yazmaktır][1].

Yani sonuç olarak python'da modül dediğimiz şey aslında bizim yazdığımız betiklerdir. Yani yazdığımız her python betiği bir modül olarak başka bir betikte içe aktarılabilir(`import`).  Modüller için ayrıca [buraya][2] bakabilirsiniz.

####Bir modül'ün ismi

Yavaş yavaş asıl değinmek istediğim konuya geleyim. Python'da her modülün bir ismi vardır. Python yorumlayıcısı bir modülü yorumlarken o modüldeki tüm kodları çalıştırmadan önce  bazı değişkenler tanımlar. Bunlardan birisi `__name__` değişkenidir. Bu değişken, o modül'ün çalıştırılma şekline göre başka değerler alır. 

<!-- more -->

Eğer python yorumlayıcısı bizim yazdığımız modülü ana program olarak çalıştırıyorsa `__name__` değişkeni `'__main__'` değerini alır. Ancak yazmış olduğumuz modül başka bir modül içinden çağırılıyorsa bu sefer `__name__` değişkeni kendi modül'ünün adını alır. 

Anlaşılması için bunları bir örnekle açıklayayım;

Örneğin `ornek_modul.py` isminde bir dosyaya kaydedeceğimiz şöyle bir betik yazalım:

``` python __name__ özelliğinin kullanımı
if __name__ == '__main__':
    print('Kendi dosyam tarafından çalıştırıldım.')
else:
    print('Başka bir modül tarafından içe aktarılarak çalıştırıldım.')
```
Şimdi bu betikle ilgili çıktılara bakalım:

```bash çıktı testleri
$ python3 ornek_modul.py
Kendi dosyam tarafından çalıştırıldım.
$ python3
>>> import ornek_modul
Başka bir modül tarafından içe aktarılarak çalıştırıldım.
>>>

```

Görüldüğü gibi `ornek_modul.py` doyasını kendi başına çalıştırısak `__name__` değişkeni `'__main__'` değerini alıyor. Fakat python'un etkileşimli kabuğuna girip `ornek_modul` modülünü içeri aktarırsak 1. koddaki `else` bloğuna düşeriz çünkü `__name__` değişkeni bu defa modülün ismi olan `ornek_modul` değerini almış olur.

kaynaklar:  

 - [a byte of python][3]
 - [stackoverflow][4]
 - [python docs][5]


  [1]: http://docs.python.org/3/extending/index.html
  [2]: http://docs.python.org/3/tutorial/modules.html
  [3]: http://swaroopch.com/notes/python/
  [4]: http://stackoverflow.com/questions/419163/what-does-if-name-main-do
  [5]: http://docs.python.org/