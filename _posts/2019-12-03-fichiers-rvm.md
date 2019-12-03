---
layout: post
title:  ".ruby-version & .ruby-gemset"
categories: ruby 
---

Pour gérer ses différentes versions de ruby en fonction de ses projets, on peut créer des fichiers à la racine de chaque projet pour spécifier la version de ruby et le gemset utilisé, dès que l'on ira dans ce dossier RVM s'occupera tout seul d'utiliser la bonne version de ruby et le bon gemset.

L'avantage de ces fichiers est qu'ils sont aussi reconnus par chruby et rbenv

Le fichier `.ruby-version` contient uniquement le numéro de version, pour le créer :   
`$ echo 1.9.3 > .ruby-version`

Le fichier `.ruby-gemset` contient uniquement le nom du gemset, pour le créer :    
`echo gemset_name > .ruby-gemset`

## Ressources
Documentation officielle : <https://rvm.io/workflow/projects#project-file-ruby-version>
