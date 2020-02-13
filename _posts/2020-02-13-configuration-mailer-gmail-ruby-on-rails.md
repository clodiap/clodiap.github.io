---
layout: post
title:  "Configuration du mailer de Rails avec gmail"
categories: ruby-on-rails
---

## Configurer son compte gmail

Pour envoyer des emails depuis une app Rails, on peut utiliser une adresse gmail. Pour ce faire il nous faudra configurer notre compte gmail pour l'autoriser à envoyer des emails sans captcha à partir de notre app.

Cliquer sur ces 2 liens (en se connectant avec le compte utilisé dans l'app Rails) :
* [Déverouiller le captcha](http://www.google.com/accounts/DisplayUnlockCaptcha)
* [Donner l'accès aux apps moins sécurisées](https://www.google.com/settings/u/0/security/lesssecureapps)

## Configurer l'app Ruby on Rails

Dans `config/environments/production.rb` :

```ruby
Rails.application.configure do
  config.action_mailer.default_url_options = { host: ENV['MAILER_URL'] }
  config.action_mailer.delivery_method = :smtp
  config.action_mailer.perform_deliveries = true
  config.action_mailer.raise_delivery_errors = false
  config.action_mailer.default :charset => "utf-8"
  config.action_mailer.smtp_settings = {
    :address              => "smtp.gmail.com",
    :domain               => "gmail.com",
    :port                 => 587,
    :user_name            => ENV['GMAIL_USERNAME'],
    :password             => ENV['GMAIL_PWD'],
    :authentication       => "plain",
    :enable_starttls_auto => true
  }
end
```
Avec bien sûr les variables d'environnement définies dans le fichier `.env` si vous utilisez la gem `dotenv-rails`.

`MAILER_URL` correspond à l'adresse du site à partir de laquelle l'email est envoyé (`nameofyourapp.herokuapp.com` pour la production ou `nameofyourapp-staging.herokuapp.com` pour le staging), indispensable pour que `Devise` puisse envoyer des emails (email pour la récupération du mot de passe par exemple).

## Ressources

* [Stackoverflow : How to set up mailer in Rails app for production environment on heroku](https://stackoverflow.com/questions/11997192/how-to-set-up-mailer-in-rails-app-for-production-environment-on-heroku)
* [Stackoverflow : Net::SMTPAuthenticationError when sending email from Rails app (on staging environment)](https://stackoverflow.com/questions/18124878/netsmtpauthenticationerror-when-sending-email-from-rails-app-on-staging-envir)
* [Setting up mailer using devise for forgot password](https://rubyonrailshelp.wordpress.com/2014/01/02/setting-up-mailer-using-devise-for-forgot-password/)
