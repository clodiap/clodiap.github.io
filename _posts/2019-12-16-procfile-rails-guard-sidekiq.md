---
layout: post
title:  "Procfile pour Rails server, Guard et Sidekiq"
categories: ruby-on-rails 
---

Il arrive que l'on ai besoin d'ouvrir plusieurs terminaux lorsque l'on travaille sur une app Rails : un pour le serveur, un pour le guard, et un autre pour Sidekiq par exemple. Voici ma config pour faire tourner ces 3 programmes avec un seul terminal.

## Foreman

C'est la gem Foreman qui va nous permettre cela, pour l'installer : `gem install foreman`. On peut aussi utiliser Hivemind (<https://github.com/DarthSim/hivemind>) si on est sous mac.

## Procfile

Ensuite il faudra créer un fichier Procfile, on peut créer un `Procfile.dev` pour l'utiliser en développement (le `Procfile` sera utilisé en prod sur Heroku par exemple, il n'y aura pas le guard dans celui-ci).

Procfile.dev :
```bash
web: rails s -p 3000
guard: bundle exec guard
worker: bundle exec sidekiq -q default -q mailers
```

Pour le Procfile de production, on peut inclure une ligne qui permettra d'effectuer les migrations à chaque déploiement :
`release: bundle exec rails db:migrate`

## Lancement

Dans un terminal on peut maintenant taper `$ foreman start -f Procfile.dev` et on aura les 3 processus qui tourneront.

## Ressources

* Foreman : <https://github.com/ddollar/foreman>
* Hivemind : <https://github.com/DarthSim/hivemind>
* Procfile sur Heroku : <https://devcenter.heroku.com/articles/procfile>
