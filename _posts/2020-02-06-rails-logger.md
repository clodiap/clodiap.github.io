---
layout: post
title:  "Rails logger"
categories: ruby-on-rails
---

Pour débugger une app et éviter d'afficher des `puts` partout (qu'il ne faudra pas oublier d'enlever avant de passer en production), on peut utiliser le logger de Ruby on Rails. 

Il existe 5 niveaux de logs : `:debug, :info, :warn, :error, et :fatal`. On peut paramétrer le niveau de log pour chaque environement, ce qui permet par exemple de ne pas logger le niveau `:debug` en production par exemple.

Pour l'utiliser dans un controller, un model, ou un mailer :
```ruby
logger.debug "@name.inspect"
```

Pour l'utiliser ailleurs :
```ruby
Rails.logger.debug "@name.inspect"
```

Pour configurer le niveau de log sur `info` en production, `config/environments/production.rb` :
```ruby
Rails.application.configure do
  config.log_level = :info
end
```


Pour lire ces logs on peut aller dans la console ou bien lire le fichier de logs dans `log/developement.log`.

## Ressources
* [Rubyonrails guides](https://guides.rubyonrails.org/debugging_rails_applications.html#the-logger)
* [TreeHouse quick tips](https://teamtreehouse.com/library/how-to-use-the-logger-in-ruby-on-rails)
