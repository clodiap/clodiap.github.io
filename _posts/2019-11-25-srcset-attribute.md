---
layout: post
title:  "L'attribut srcset"
categories: html 
---

L'attribut `srcset` permet de définir des images de tailles différentes selon la taille
de l'écran. Ce qui permet un chargement plus rapide des page sur le mobile.  

Avec l'attribut `size`, on peut définir les tailles affichées dans le
navigateur selon la taille de l'écran :

```html
<img sizes="(min-width: 1200px) 580px,  
      (min-width: 640px) 48vw,  
      98vw"  
    srcset="img/image-300.jpg 300w,  
      img/image-600.jpg 600w,  
      img/image-900.jpg 900w,  
      img/image-1200.jpg 1200w"  
    src="img/image-900.jpg" alt="image">
```

## Ressources

L'article très complet de MDN sur les images adaptives :
<https://developer.mozilla.org/fr/docs/Apprendre/HTML/Comment/Ajouter_des_images_adaptatives_%C3%A0_une_page_web>

L'article de MDN sur l'élément `<picture>` qui permet lui aussi de définir
plusieurs sources d'images en fonction de la taille, de l'orientation de
l'écran : <https://developer.mozilla.org/fr/docs/Web/HTML/Element/picture>
