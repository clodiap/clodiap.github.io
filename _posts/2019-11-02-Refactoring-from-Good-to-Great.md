---
layout: post
title:  "Refactoring from Good to Great"
categories: refactoring 
---

– Vidéo de **Ben Orenstein** très intéressante sur le refactoring : <https://www.youtube.com/watch?v=DC-pQPq0acs> :  
- se méfier des paramètres qui vont toujours ensemble, préférer les grouper au sein d'un objet  
- méthode `cover?` (range) : plus efficace que `include?` (`include?` va checker tous les nb du range alors que cover va regarder le 1er et le dernier et déduire la réponse)  
`(1..9).cover?(5) # returns true`  
- refactoring when you need to change in order to make the change the simpliest possible

## Récapitulatif

1. attention aux "god objects" (classes qui gèrent plus que ce qu'elles devraient gérer)

>The first rule of classes is that they should be very small,
>the second rule of classes is that they should be even smaller than that

2. attention aux fichiers que l'on change le plus (gem churn : <https://github.com/danmayer/churn> , qui va regarder les fichiers les plus modifiés)

3. quand il y a un bug dans un fichier, il y a des chances qu'il y en ai un autre pas loin

## Livres conseillés 
- **Clean Code** de Robert C. Martin, 
- **Refactoring** de Fowler, 
- **Growing object-oriented software guided by tests** de Nat Pryce

