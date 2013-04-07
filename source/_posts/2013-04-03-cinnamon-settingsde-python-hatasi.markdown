---
layout: post
title: "cinnamon settings'de python hatası"
date: 2013-04-03 16:16
comments: true
categories: [python, linux, hatalar]
---

masaüstü sistem olarak linux mint cinnamon 14 kullanıyorum geçenlerde cinnamon'un ayarlarını açmaya çalıştığımda açılmadı konsola yazdığımda şöyle bir hata alıyorum:

    sayz@caravasar$  cinnamon-settings 
    /usr/lib/python2.7/dist-packages/gobject/constants.py:24: Warning: g_boxed_type_register_static    : assertion `g_type_from_name (name) == 0' failed
    import gobject._gobject

    >>>
    
hata cinnamon'dan değil python'dan kaynaklanıyor belli ki ama daha çözüme ulaşamadım ulaşınca buraya da geçeceğim. [launchpad](http://goo.gl/CtZUv)'de de hata kaydı açılmış bunula ilgili.
