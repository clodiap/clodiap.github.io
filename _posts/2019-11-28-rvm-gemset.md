---
layout: post
title:  "Gemsets"
categories: ruby 
---

Pour aisément installer plusieurs versions de Ruby On Rails avec RVM, on peut utiliser des gemsets. Cela permet d'éviter les conflits entre plusieurs versions de rails.

Par exemple pour installer Rails en version 6 :
```bash
$ rvm gemset create rails600  
$ rvm 2.6.5@rails600
$ gem install rails -v 6.0
```
## Ressources

La doc officielle :
<https://rvm.io/gemsets/basics>

Article intéressant :
<https://medium.com/rubycademy/rvm-gemset-as-a-freelancer-6910a1cf2d6d>
