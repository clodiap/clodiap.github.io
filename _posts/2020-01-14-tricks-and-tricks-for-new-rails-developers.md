---
layout: post
title:  "Video : Tricks and treats for new developers by David Padilla"
categories: ruby-on-rails 
---

Une vidéo très sympathique que je viens de regarder et qui donne de bons conseils : <https://www.youtube.com/watch?v=BZbW8FAvf00>

## Le résumé

### Nouveau projet

* Pour un nouveau projet, David Padilla nous conseille de copier un exemple de database.yml (par ex. en `database.sample.yml`) et de le laisser pour les prochains devs qui travaillerons sur le projet (mettre le `database.yml` configuré dans le gitignore). Même chose pour le fichier `secrets.yml`. Cela permet d'avoir un exemple de ce fichier pour le compléter avec ses propres infos.
* On peut créer autant de fichiers de configuration et d'initializers que l'on désire ce qui permet de garder le projet organisé et bien rangé.
* Pas de chiffres / nombres dans le code, utiliser des constantes ou un fichier de config.

### Base de données

* Ne surtout pas mettre `db/schema.rb` dans le `.gitignore` (on pourra ainsi restaurer l'état de la bdd avec `db:setup` ou `db:reset`)
* Ne pas changer la data dans les fichiers de migrations, à la place on pourra utiliser la gem `rails-data-migrations`

### Background jobs

* Ne pas passer d'objets au worker (passer l'id d'un objet et récupérer l'objet avec cet id)
* Toujour envoyer les emails plus tard (`deliver.later`) car il peut y avoir des erreurs de serveur SMTP

### Gems

* Gem __Rubocop__ : pour un projet déjà existant avec trop de warnings, exécuter la commande `$ rubocop --auto-gen-config`, ce qui va créer un fichier `.rubocop_todo.yml` contenant toutes les offenses sous forme d'exceptions (elles n'apparaitront plus).
  * À mettre dans son fichier de config (`.rubocop.yml`) :
```yaml
Style/Documentation:
  Enabled: false
Metrics/MethodLength:
  Max: 10
```
  * On peut aussi faire tourner rubocop dans un git hook (prepush par ex.)
* Gem __Annotate__ : cette gem indiquera en commentaire pour chaque model le schéma de la bdd relatif au model (`$ annotate --routes` va faire de même pour les routes, plus besoin de taper `$ rails routes` pour avoir toutes les routes de l'app !)
* Gem __Bullet__ : va détecter les problèmes de requêtes n+1 de la bdd
* Gem __Oink__ : va détecter les problèmes de mémoire
