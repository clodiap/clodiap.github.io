---
layout: post
title:  "Nvm, Foreman, Mailcatcher, MySQL Workbench"
date:   2019-10-19 11:54:37 +0200
categories: ruby-on-rails mysql
---
## Gestionnaire de version pour node
Installer un gestionnaire de version (**nvm**) pour node (<https://github.com/nvm-sh/nvm>)  
`nvm list` liste toutes les versions de nvm installées  
`nvm use 10.15.3` utilise la version 10.15.3  
(mêmes commandes que rvm)

## Gem Foreman
Découverte de la **gem Foreman** qui permet de lancer plusieurs "workers" dans un seul terminal avec un Procfile (<https://github.com/ddollar/foreman>)  

## Gem MailCatcher
Découverte de la **gem MailCatcher** (<https://mailcatcher.me/>) qui permet de checker les mails envoyés en local 

## MySQL Workbench
Logiciel **MySQL Workbench** (<https://dev.mysql.com/downloads/tools/workbench/>) pour explorer une base de données MySQL, on peut également réaliser un graphique de la bdd et ensuite l'exporter dans une nouvelle base (tutoriel Graphikart : <https://www.youtube.com/watch?v=jaQGNDqXHxc>)

## surge.sh
**Surge.sh** (<https://surge.sh/>) pour publier des pages web statiques rapidement en ligne de commande

---------------------

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
