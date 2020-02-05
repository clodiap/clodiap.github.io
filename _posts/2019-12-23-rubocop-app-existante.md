---
layout: post
title:  "Rubocop sur une app existante"
categories: ruby-on-rails
---

Si on fait tourner rubocop sur une app existante, on risque d'avoir une somme d'offenses assez conséquente, ce qui limitera notre envie d'utiliser ce fantastique outil.

Pour remédier à ce problème, la commande `$ rubocop --safe-auto-correct` va corriger les erreurs les plus safe.

Ensuite, pour les autres offenses, la commande `$ rubocop --auto-gen-config` va générer un fichier `.rubocop_todo.yml` contenant toutes les offenses, ce qui nous permettra de les corriger à notre rythme et de ne plus les voir.

## Ressources

* Doc de rubocop : <https://docs.rubocop.org/en/latest/>
* rubocop --safe-auto-correct : <https://docs.rubocop.org/en/latest/auto_correct/#safe-auto-correct>
* rubocop --auto-gen-config : <https://docs.rubocop.org/en/latest/configuration/#automatically-generated-configuration>
