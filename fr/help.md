---
lang: "fr"
title: "Utiliser le site learnlatex.org"
description: "Cette page présente le site learnlatex.org lui-même et explique la meilleure façon de l'utiliser."
permalink: /fr/help
---

# Aide

## Naviguer sur ce site web

Ce cours se compose de 16 leçons principales, accessibles à partir de la table
des matières de [la page d'accueil](/).

Chaque leçon a un lien avec vers une leçon d'approfondissement sur le même
sujet. Il est possible de suivre les 16 leçons _sans lire les leçons
d'approfondissement_.

À la fin du cours, il y a une leçon spécifique au français, et enfin une
galerie d'exemples de packages illustrant des utilisations de LaTeX
non couvertes par ce cours.

---

## Les exemples

### Exécuter les exemples

Chaque exemple est constitué d'un petit document LaTeX complet, qui apparaît
dans la page sous cette forme :

```latex
\documentclass{article}
\usepackage[T1]{fontenc}

\begin{document}
Texte d'exemple.
\end{document}
```

L'exemple est complet. Cependant, vous pouvez le modifier à votre guise pour
tester des choses, éventuellement dans le cadre d'un exercice proposé en fin de
leçon.

L'éditeur utilisé est [ACE](https://ace.c9.io/).

#### Trois façons d'exécuter un exemple

Que le code-source de l'exemple ait été modifié ou non, il existe trois manières
de l'exécuter :

* Utiliser le service Overleaf,
* Utiliser un service LaTeX en ligne,
* Utiliser votre installation locale de TeX.


##### Utiliser le service Overleaf

Overleaf est un des services les plus apprécié pour travailler par le web avec
LaTeX. The bouton <button>Ouvrir dans Overleaf</button>, présent sous l'exemple,
soumet le code à [Overleaf](https://www.overleaf.com/about).

Si vous n'avez pas encore de compte, ou si les détails de votre compte n'ont
pas déjà été enregistrés dans votre navigateur, vous serez redirigé vers une
page de connexion où vous pourrez vous connecter ou vous inscrire sur
Overleaf. Ce service est gratuit, mais vous devrez donner quelques
informations personnelles (notamment une adresse mail) et accepter les
conditions générales d'utilisation.

Si votre compte Overleaf est déjà en cache dans votre navigateur, alors une
page web Overleaf s'ouvrira dans un nouvel onglet, avec un nouveau projet
contenant le code de l'exemple. À partir de là, vous pourrez le modifier dans
Overleaf, qui lancera automatiquement LaTeX sur votre code en affichant le
résultat ou le journal des erreurs.

Overleaf a des fonctionnalités beaucoup plus évoluées que notre site web
pour l'édition des documents, et vous pouvez enregistrer vos projets dans
votre compte Overleaf pour y revenir plus tard.

##### Utiliser un service LaTeX en ligne

Le bouton <button>LaTeX Online</button>, présent sous l'exemple,
soumet le code au service [TeXLive.net](https://texlive.net)[^1].

Le serveur _TeXLive.net_ a été mis en place spécialement pour supporter ce
site, et utilise notamment [PDF.js](https://mozilla.github.io/pdf.js/) pour
afficher les fichiers PDF sur les navigateurs mobiles ou autres, dépourvus de
lecteur PDF intégré.

Le document PDF résultant (ou une partie du journal des erreurs)
sera affiché dans la page, immédiatement sous l'exemple. Un bouton
<button>Fermer l'affichage</button> apparaîtra pour que vous puissiez effacer
cette sortie (ou la laisser en place et suivre le reste de la leçon).

Notez que **TeXLive.net** ne nécessite ni connexion ou ni inscription
d'aucune sorte, ce qui est très pratique pour les petits exemples, mais
ni ce site ni les sites `latexcgi`, `latexonline.cc` ou `latex-on-http`
ne proposent de mécanisme pour enregistrer votre document. Toute modification
que vous auriez apportée à l'exemple est perdue quand vous quittez la page.

##### Utiliser une installation locale de TeX

Si vous avez un système TeX installé localement, vous pouvez copier le code
de l'exemple à partir de la page, soit en le sélectionnant explicitement,
soit en utilisant les raccourcis clavier de l'éditeur (ctrl-A ctrl-C dans
Windows par exemple). Lancez alors votre éditeur local, et collez le code
de l'exemple dans un document vierge.


### En cas de problème&hellip;

Our examples are based around using an up-to-date LaTeX installation. They all 
work with both of our online demonstration systems, so if you get errors with 
the examples we provide, you might want to check if your LaTeX system is 
up-to-date.

---

## Choisir le moteur TeX

Quand vous compilerez les exemples par _LaTeX Online_, c'est le moteur `pdflatex`
qui sera utilisé par défaut, sauf si l'exemple charge le package `fontspec`,
auquel cas `xelatex` sera utilisé.

Vous pouvez forcer le choix de `pdflatex`, `xelatex`, `lualatex`, `platex` ou
`uplatex` en ajoutant dans le document un commentaire de la forme :

`% !TEX ` _any text_ `lualatex`

où l'espace blanc au début est facultatif et la casse sans importance.
_Tout texte_ entre le premier et le dernier mot est également ignoré. Cela
permet d'écrire `% !TEX program=pdflatex`, comme demandé par certains éditeurs
TeX, mais ne nécessite pas la chaîne `programme=`. Cette syntaxe est
actuellement limitée à la seule spécification d'un des cinq moteurs listés
ci-dessus.

Par exemple dans les exemples [de cette leçon](more-14), vous pouvez voir un tel
commentaire utilisé pour spécifier LuaLaTeX.

Si `platex` ou `uplatex` est demandé, alors le programme `dvipdfmx` sera
automatiquement lancé ensuite pour produire le résultat en PDF à partir
du fichier DVI généré par ces variantes.

---

## Choisir comment afficher le résultat

Si vous utilisez _LaTeX Online_, la sortie PDF sera affichée par défaut en
utilisant [PDF.js](https://mozilla.github.io/pdf.js/). Ce choix permet d'obtenir
un comportement cohérent sur le plus grand nombre de navigateurs.

Si vous préférez utiliser le lecteur PDF de votre navigateur (qu'il soit intégré
ou qu'il s'agisse d'une application externe que vous avez configurée), ajoutez
un commentaire de cette forme :

`% !TEX ` _any text_ `pdf`

Le comportement par défaut peut également être explicitement spécifié en
utilisant `pdfjs` dans le commentaire ci-dessus. Pour le débogage, vous pouvez
parfois souhaiter que le fichier journal soit renvoyé, même si le document
produit un PDF sans erreur. Cela peut être demandé en utilisant `log` dans ce
commentaire.

---

[^1]: Pendant le développement de ce site web, nous avons également utilisé
      [LaTeX.Online](https://latexonline.cc/) et
      [LaTeX-on-HTTP](https://github.com/YtoTech/latex-on-http) et nous
      remercions chaleureusement les développeurs de ces services de les avoir
      adaptés à nos besoins pour permettre à nos exemples de fonctionner dès
      les premières phases de développement de _learnlatex.org_.
