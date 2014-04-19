---
layout: post
title: "resolv.conf dosyasında bayrak hatası (chattr)"
date: 2014-04-19 16:25
comments: true
categories: [linux, hatalar]

---

Geçen gün malum mahkeme kararları dolayısıyla Youtube'a giremeyince dns ayarlarını değiştirmek için ```resolv.conf``` dosyasına google dnslerini ekledim.
Daha sonra değişmesin diye bu dosyayı kitlemek için her zamanki gibi ```chattr``` kullanmak istedim ki bana şöyle bi hata verdi:

```
	$  sudo chattr +a /etc/resolv.conf 
chattr: Operation not supported - /etc/resolv.conf üzerinde bayraklar okunurken hata oluştu
```

önce anlayamadım tabii ne olduğunu sonra google amcadan yardım istedim ki ```resolv.conf``` dosyası sembolik linkmiş meğer:

```
	$  ls -al /etc/resolv.conf 
lrwxrwxrwx 1 root root 29 Nis 13 05:56 /etc/resolv.conf -> ../run/resolvconf/resolv.conf
```

bu sefer şunu denedim:

```
	$  sudo chattr +a /run/resolvconf/resolv.conf 
chattr: Inappropriate ioctl for device - /run/resolvconf/resolv.conf üzerinde bayraklar okunurken hata oluştu
```

bu sefer başka bir hata!

ben de yine google amcaya danışarak şu çözümü uyguladım:

```
	$  sudo cp /etc/resolv.conf /etc/resolv.conf.yedek
	$  sudo rm /etc/resolv.conf
	$  sudo cp /etc/resolv.conf.yedek /etc/resolv.conf
	$  ls -al /etc/resolv.conf 
-rw-r--r-- 1 root root 211 Nis 19 16:22 /etc/resolv.conf
```

bunu yaptıktan sonra da son darbeyi vurdum ve sonuca gittim:

```
	$  sudo chattr +a /etc/resolv.conf
```

belki aynı problemle karşılaşanlar falan olur, bi yardımı olur...


