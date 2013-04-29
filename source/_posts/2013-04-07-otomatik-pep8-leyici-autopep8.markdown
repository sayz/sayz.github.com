---
layout: post
title: "otomatik pep8'leyici: autopep8"
date: 2013-04-07 21:45
comments: true
categories: [python, '19']
---

herkese merhabalar;

autopep8 için bölüm'ün e-posta listesine attığım e-postayı buraya da geçeyim.$ 

bildiğiniz gibi python için bir kod yazım stili var: pep8 (bilmeyenler için<sup>([1])</sup>), neyse, işte python ile yeni kod yazmaya başlayan arkadaşlar genellikle bu kurallara, stile uymakta zorlanır veya erinirler bunları uygulamaya, ne bileyim işleçler arasında boşluk bırakmak falan zor gelir kimisine. 

biliyorsunuz genelde tembel insanlarız bizler :-) o yüzden adamlar sırf bu bizim eringeçliğimizi bildikleri için erinmemişler :-) ve kalkıp bir otomatik "pep8"leyici (tabir bana ait) yazmışlar, adı autopep8.

#####peki nedir bu autopep8, yenilir mi içilir mi? 

kısaca şudur: 

sen karman çorman yazıyorsun kodu<sup>([2])</sup> ve autopep8 sadece tek satırlık komutla kodunu pep8'e uygun hale<sup>([3])</sup> getiriyor.

* önce autopep8'i kuralım sistemimize:

 ~$: `sudo easy_install -ZU autopep8` 

 * kurulumdan sonra şöyle kullanabilirsiniz autopep8'i:

  ~$: `autopep8 -ia bozuk_kod.py`

  artık kodunuz pep8 standartlarına uygun hale gelmiş oldu.

  iki dosya arasındaki farkı görmek için [şuradaki](https://gist.github.com/sayz/5331516/revisions) gist karşılaştırmasına bakabilirsiniz.

  autopep8'e sokmadan önce bozuk_kod.py doyasının pep8 çıktısı 144 satırdı.<sup>([4])</sup>

  daha fazlası [burada](https://github.com/hhatto/autopep8).

  [1]: http://www.python.org/dev/peps/pep-0008/
  [2]: http://goo.gl/BYUeu
  [3]: http://goo.gl/C5LqP
  [4]: http://goo.gl/1Gcmh

  \HTH

  --
  sayz
