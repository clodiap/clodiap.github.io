---
layout: post
title:  "Git commit template"
categories: git
---

Pour écrire de meilleurs messages de commit, on peut utiliser un template de commit qui s'affichera à chaque commit.

Parmi les bonnes pratiques, on peut citer :
* Limiter le sujet à 50 caractères
* Capitaliser le premier mot du sujet, celui-ci devra être un verbe à l'impératif (en anglais _of course_)
* La première ligne ne doit pas se terminer par un point
* Sauter une ligne après le sujet
* Écrire un texte explicatif comprenant le pourquoi du comment de cette modif

Tout ceci sera bien utile pour revenir à d'anciens commits, ou pour naviguer dans l'historique du projet.

Par exemple voici le mien (fortement inspiré des liens ci-dessous) :
```
# If applied, this commit will...

# Why is this change needed?
Prior to this change, 

# How does it address the issue?
This change

# Provide links to any relevant tickets, articles or other resources


# ## Help ##
#
# Subject line imperative uppercase verbs:
#
#   Add = Create a capability e.g. feature, test, dependency.
#   Drop = Delete a capability e.g. feature, test, dependency.
#   Fix = Fix an issue e.g. bug, typo, accident, misstatement.
#   Bump = Increase the version of something e.g. a dependency.
#   Make = Change the build process, or tools, or infrastructure.
#   Start = Begin doing something; e.g. enable a toggle, feature flag, etc.
#   Stop = End doing something; e.g. disable a toggle, feature flag, etc.
#   Optimize = A change that MUST be just about performance, e.g. speed up code.
#   Document = A change that MUST be only in the documentation, e.g. help files.
#   Refactor = A change that MUST be just refactoring.
#   Reformat = A change that MUST be just format, e.g. indent line, trim space, etc.
#   Rephrase = A change that MUST be just textual, e.g. edit a comment, doc, etc.
#
# For the subject line:
#   * Use 50 characters maximum.
#   * Do not use a sentence-ending period.
#
# For the body text:
#   * Use as many lines as you like.
#   * Use 72 characters maximum per line for typical word wrap text.

```


## Ressources
* [A useful template for commit messages](https://codeinthehole.com/tips/a-useful-template-for-commit-messages/)
* [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)
* [Better Commit Messages with a .gitmessage Template](https://thoughtbot.com/blog/better-commit-messages-with-a-gitmessage-template)
* [Exemple on github](https://github.com/joelparkerhenderson/git_commit_template)
