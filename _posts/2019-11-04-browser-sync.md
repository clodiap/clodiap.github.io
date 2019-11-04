---
layout: post
title:  "Browser-sync"
categories: webdev 
---

[Browser-sync](https://browsersync.io/), outil très pratique pour éviter d'avoir à recharger son navigateur lorsque l'on
travaille avec des pages statiques (équivalent de l'extension "Live Server" sur
VS-Code).

Pour l'installer en global :  
`npm install -g browser-sync`

Le lancer dans le dossier où on se trouve :   
`browser-sync start --server --files .` (le point à la fin signifie qu'il va
surveiller tous les fichiers)  
Pour qu'il ne surveille que les fichiers css :  
`browser-sync start --server --files "*.css"`
