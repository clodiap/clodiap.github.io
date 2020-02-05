---
layout: post
title:  "Installer livereload dans une app RubyOnRails"
categories: ruby-on-rails 
---

Pour éviter d'avoir à taper F5 dans son navigateur lorsque l'on modifie un fichier, on peut installer les gems suivantes dans son app Rails, ce qui permettra de recharger automatiquement une page dès qu'elle sera modifiée.

Dans le fichier `Gemfile` :
```
group :development do
  gem 'rack-livereload'
  gem 'guard'`$ bundle exec guard`
  gem 'guard-livereload', '~> 2.5', require: false
end
```

Puis taper dans le terminal : `$ bundle install`

Dans le fichier `config / environments / development.rb` :
```
Rails.application.configure do
  config.middleware.insert_after ActionDispatch::Static, Rack::LiveReload
end
```

Puis générer le fichier de config de Guard : `$ guard init livereload`

Et enfin taper dans un terminal `$ bundle exec guard` pour lancer le guard.

## Ressources

* Gem rack-livereload : <https://github.com/onesupercoder/rack-livereload>
* Gem guard-livereload : <https://github.com/guard/guard-livereload>
* Gem guard : <https://github.com/guard/guard>
