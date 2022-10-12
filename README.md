# PratiqueDeGitWindows
Afin d'éviter des possibles emerdements, j'utiliserai ce site pour les tests et pratiques dans git sous Windows. Ce document servira donc de journal pour les opérations.

## Version du manuel Pro Git; citations ou références :
Version 2.1.352-2-gf..., 2022-08-29

## 2022-10-12 - création du repo et remote
0. Ouverture du répo, dans un terminal MINGW64 (git Bash) :<br>
 0.1 git init -b main<br>
 0.2 touch README.md<br>
 0.3 touch .gitignore<br>
  0.3.1 ajout de *.bak<br>
  Note : l'éditeur UltraEdit-32 produit automatiquement un fichier .bak lors de l'ouverture d'un fichier.<br>
  
 0.4 git add .<br>
 
 0.5 changements dans README.md dans UltraEdit-32<br>
 Note : dans cette (très vielle) version de l'éditeur (v. 12.10+3),  le contenu est édité avec les marques de md, mais il n'y a pas de Wysiwyg!<br>
 
 0.6 commit initial<br>

1. Après commit initial, test du changement du commit par amend :<br>
 1.1 changements dans README.md (plusieurs changements car le terminal a planté et j'ai dû utiliser G. des tâches pour le fermer!)<br>
 
 1.2 plusieurs fois : git add .<br>
 
 1.3 selon Pro Git p.44 : ```git commit --amend```<br>

  Notes :
  Après plusieurs essais pour corriger les typos.<br>
       
  La commande en 1.3 lance automatiquement l'éditeur par défaut (en l'occurence Notepad) avec le commentaire inscrit pour corriger le message de commit si nécessaire. Super!<br>

  1.4 Après plusieurs autres ```commit amend...```, il n'y a effectivement qu'un seul commit (initial) visible dans le repo.<br>
    
  1.5 Création du remote; notes tirée de DGMaNi/cr20220909.md :<br>
  Note : Les CLI ```gh``` ne fonctionnent pas dans un terminal MINGW64 (git Bash); **fonctionnent seulement dans un terminal Anaconda** :<br>
* Avec un repo local bien en ordre, c'est à dire la commande ```git status``` « retourne nothing added to commit ... »<br>
* Avec un login correct vers le compte GitHub; ```gh auth status``` retourne
... Logged in to github.com as stardom1957...

* Commande ```gh repo create```, avec indications (en interactif) :<br><br>
  - Push an existing local repository to GitHub<br>
  - Path to local repository .<br>
  - intention de faire un push à la fin = Oui<br>
  - Repository name (PratiqueDeGitWindows) (valeur par défaut)<br>
  - Description Repo pour la pratique ...<br>
  - Visibility Public<br>
    ... Created repo...<br>
  - Add a remote? Y<br>
  - What should the new remote be called? (origin) (valeur par défaut)<br>
  - Would you like to push commits from the current branch to "origin"? Y<br>
    ... Pushed commits to https://github.com/stardom1957/PratiqueDeGitWindows.git<br>
    
## Faire des changements
### Changements au dernier commit
 1.6 ```git commit --amend``` : voir 1.1 à 1.4<br>
 
### Unstaging (Pro Git p.47)
Pour enlever un ou des fichiers du « staging area ».
  1.7 Commande « git restore --staged »
  1.8 touch test.txt
  1.9 ajouté qqe lignes de texte
 ```git restore --staged ...```
 