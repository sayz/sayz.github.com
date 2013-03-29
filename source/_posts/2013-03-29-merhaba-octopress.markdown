---
layout: post
title: "merhaba octopress"
date: 2013-03-29 03:01
comments: true
categories: [genel, kod]
---

Merhaba Octopress



Gist denemesi, FizzBuzz kodu:

{% gist 5268035 %}

Kod blokları denemesi

{% codeblock Javascript Array Syntax lang:js http://j.mp/pPUUmW MDN Documentation %}
var arr1 = new Array(arrayLength);
var arr2 = new Array(element0, element1, ..., elementN);
{% endcodeblock %}

kod blokları denemesi 2

{% codeblock liste analizi lang:python %}
'''
Created on 22 Nis 2011

@author: sayz
'''


def analiz(liste):
	ks, ts, os, bs, ls = 0, 0, 0, 0, 0
	for it in liste:
		if type(it) == int:
			ts += 1
		elif type(it) == float:
			os += 1
		elif type(it) == bool:
			bs += 1
		elif type(it) == str:
			ks += 1
		else:
			ls += 1
	print "karakter:%d\ntamsayı: %d\nondaliksayı: %d\n \
	bool: %d\nliste: %d\n" % (ks, ts, os, bs, ls)

#örnek kullanım:
analiz([1, '1.1', [1.1, 1.1], [False, 7, True], -1])
{% endcodeblock %}




