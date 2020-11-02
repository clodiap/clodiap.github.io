---
layout: post
title:  "Configuration de Sidekiq pour une app Ruby on Rails"
categories: ruby-on-rails
---


ActiveJob nous permet d'éxécuter des taches (appels à une API, envoi d'email) en arrière-plan. Pour l'utiliser nous avons besoin d'un autre outil qui va nous permettre de stocker ses tâches dans une file d'attente ('queue' en anglais), j'ai choisi Sidekiq, mais il en existe d'autres tels que Resque.

Et pour faire tourner Sidekiq nous aurons aussi besoin d'un serveur Redis.

## Installation

Commençons par le gemfile :

```ruby
# .gemfile
gem 'sidekiq'
gem 'redis', '~> 4.0' # déjà dans les gems par défaut
```
Suivi d'un petit `bundle install` des familles.

## Configuration

Puis passons à la configuration dans les différents fichiers :

```ruby
# config/application.rb
config.active_job.queue_adapter = :sidekiq
```

```yaml
# config/sidekiq.yml
:concurrency: 2
:logfile: ./log/sidekiq.log
:queues:
  - default
  - mailers
```

### Redis
Configuration de Redis pour Heroku (ne pas oublier d'installer Redis sur Heroku et de remplir la variable d'environnement `REDIS_URL` dans les 'config vars') et en local :
```ruby
# config/initializers/redis.rb
uri = ENV['REDIS_URL'] || 'redis://localhost:6379/'
REDIS = Redis.new(url: uri)
```

### Procfile
Les `Procfile` dev et production ([Voir mon article sur les 'Procfile'](/ruby-on-rails/2019/12/16/procfile-rails-guard-sidekiq.html)) :
```bash
# Procfile.dev
worker: bundle exec sidekiq -q default -q mailers
```

```bash
# Procfile
worker: bundle exec sidekiq -e production -C config/sidekiq.yml
```

### Routes
Pour avoir accès à l'interface web de Sidekiq, on peut inclure dans les routes :

```ruby
# config/routes.rb
require 'sidekiq/web'

Rails.application.routes.draw do
  authenticate :user, ->(user) { user.admin? } do
    mount Sidekiq::Web => '/sidekiq'
  end
end
```

## Ressources

* [Documentation ActiveJob](https://guides.rubyonrails.org/active_job_basics.html)
* [ActiveJob Adapters](https://api.rubyonrails.org/v6.0.3.4/classes/ActiveJob/QueueAdapters.html)
* [Sidekiq](https://github.com/mperham/sidekiq)
* [Sidekiq wiki](https://github.com/mperham/sidekiq/wiki)
