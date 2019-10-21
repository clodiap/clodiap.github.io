---
layout: post
title:  "Jekyll, Vim"
categories: jekyll 
---

## Jekyll

Installer et publier un blog Jekyll sur Github (<https://jekyllrb.com>).

```
gem install jekyll bundler
jekyll new blog
cd blog
bundle exec jekyll serve
```
Et hop le blog est en ligne en local à l'adresse : <http://localhost:4000>

Pour le mettre en ligne sur github, il suffit de créer un repository nommé : username.github.io, de définir ce repo comme l'origin du dossier où jekyll est installé et de pusher le blog sur github, il sera accessible à l'adresse : username.github.io, il sera accessible à l'adresse : username.github.io

## Vim

Mettre en commentaire avec le plugin vim-commentary :  
`gc` passer la ligne en commentaire en Visual mode  
`gcc` passer la ligne en commentaire en Normal mode  
`gcap` passer le paragraphe en commentaire en Normal mode 

**Vim sans plugin** : <https://www.youtube.com/watch?time_continue=1217&v=XA2WjJbmmoM> :  
`:ls` liste des fichiers ouverts (buffers)   
`:b string` ouvre le fichier dont le nom contient la `string` 
 
**Autocomplétion**  
`début_de_nom_de_variable_ou_autre + ctrl N` propose l'autocomplétion des variables dans l'app  
`début_de_nom_de_variable_ou_autre + ctrl X + ctrl N` propose l'autocomplétion des variables **dans le fichier**   
`début_de_chemin_de_fichier + ctrl X + ctrl F` propose l'autocomplétion pour les noms de fichiers dans l'app
