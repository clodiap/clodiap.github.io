---
layout: post
title:  "Changer l'url d'un namespace"
categories: ruby-on-rails
---

Il peut être utile dans certains cas de changer l'url d'un namespace.

Par exemple dans le cas du namespace `admin`, si on veut remplacer admin dans l'url par un nom plus difficile à deviner tout en gardant `admin` comme nom de dossier dans notre code, il suffit d'utiliser l'option `path:` :

```ruby
# config/routes.rb
# accessible through /sekret/posts rather than /admin/posts
namespace :admin, path: "sekret" do
  resources :posts
end
```

Et voilà, c'est magique !

## Ressources

* [Documentation namespace sur Devdocs](https://devdocs.io/rails~6.0/actiondispatch/routing/mapper/scoping#method-i-namespace) (Devdocs est un [projet open source](https://github.com/freeCodeCamp/devdocs) regroupant les documentations de beaucoup de langages de programmation.)
* [Documentation API Ruby on Rails](https://api.rubyonrails.org/)

