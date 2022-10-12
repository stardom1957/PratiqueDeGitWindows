# PratiqueDeGitWindows
Afin d'�viter des possibles emerdements, j'utiliserai ce site pour les tests et pratiques dans git sous Windows. Ce document servira donc de journal pour les op�rations.

## Version du manuel Pro Git; citations ou r�f�rences :
Version 2.1.352-2-gf..., 2022-08-29

## 2022-10-12 - cr�ation du repo et remote
0. Ouverture du r�po, dans un terminal MINGW64 (git Bash) :<br>
 0.1 git init -b main<br>
 0.2 touch README.md<br>
 0.3 touch .gitignore<br>
  0.3.1 ajout de *.bak<br>
  Note : l'�diteur UltraEdit-32 produit automatiquement un fichier .bak lors de l'ouverture d'un fichier.<br>
  
 0.4 git add .<br>
 
 0.5 changements dans README.md dans UltraEdit-32<br>
 Note : dans cette (tr�s vielle) version de l'�diteur (v. 12.10+3),  le contenu est �dit� avec les marques de md, mais il n'y a pas de Wysiwyg!<br>
 
 0.6 commit initial<br>

1. Apr�s commit initial, test du changement du commit par amend :<br>
 1.1 changements dans README.md (plusieurs changements car le terminal a plant� et j'ai d� utiliser G. des t�ches pour le fermer!)<br>
 
 1.2 plusieurs fois : git add .<br>
 
 1.3 selon Pro Git p.44 : ```git commit --amend```<br>

  Notes :
  Apr�s plusieurs essais pour corriger les typos.<br>
       
  La commande en 1.3 lance automatiquement l'�diteur par d�faut (en l'occurence Notepad) avec le commentaire inscrit pour corriger le message de commit si n�cessaire. Super!<br>

  1.4 Apr�s plusieurs autres ```commit amend...```, il n'y a effectivement qu'un seul commit (initial) visible dans le repo.<br>
    
  1.5 Cr�ation du remote; notes tir�e de DGMaNi/cr20220909.md :<br>
  Note : Les CLI ```gh``` ne fonctionnent pas dans un terminal MINGW64 (git Bash); **fonctionnent seulement dans un terminal Anaconda** :<br>
* Avec un repo local bien en ordre, c'est � dire la commande ```git status``` � retourne nothing added to commit ... �<br>
* Avec un login correct vers le compte GitHub; ```gh auth status``` retourne
... Logged in to github.com as stardom1957...

* Commande ```gh repo create```, avec indications (en interactif) :<br><br>
  - Push an existing local repository to GitHub<br>
  - Path to local repository .<br>
  - intention de faire un push � la fin = Oui<br>
  - Repository name (PratiqueDeGitWindows) (valeur par d�faut)<br>
  - Description Repo pour la pratique ...<br>
  - Visibility Public<br>
    ... Created repo...<br>
  - Add a remote? Y<br>
  - What should the new remote be called? (origin) (valeur par d�faut)<br>
  - Would you like to push commits from the current branch to "origin"? Y<br>
    ... Pushed commits to https://github.com/stardom1957/PratiqueDeGitWindows.git<br>

* par la suite ```git remote -v```` donne ceci :
>origin  https://github.com/stardom1957/PratiqueDeGitWindows.git (fetch)
>origin  https://github.com/stardom1957/PratiqueDeGitWindows.git (push)


## Faire des changements
### Changements au dernier commit avec git commit --amend
3. ```git commit --amend``` : voir 1.1 � 1.4<br>
 
### Unstaging (Pro Git p.47) avec git restore
Pour enlever un ou des fichiers du � staging area �.<br>
4. La commande est ```git restore --staged```<br>
 4.1 libre
  
 4.2 touch test.txt<br>
 4.3 ajout� qqe lignes de texte<br>
  
 4.4 ajout� test.txt au staging area<br>
 4.5 ```git restore --staged test.txt```<br>
  
 4.6 ```git status``` indique que test.txt est Untracted (car pas encore commited)<br>
 4.7 git add test.txt<br>
  
 4.8 git commit -m "Test de unstaging sur test.txt"<br>
 4.9 ajout� quatre nlle lignes � text.txt<br>
  
 4.10 ```git add .```<br>
  
 4.11 ```git restore --staged test.txt```<br>
       Cette fois git status indique fichier test.txt modified<br>
       ATTENTION : pas de git commit --amend pour ce commit � partir de ce point car il y a eu push vers origin (Pro Git, p. 45)

 4.12 Modifi� test.txt (enlev�s des lignes au d�but)<br>
 4.13 git add ., puis git commit -m "Nouveau fichier test.txt"
 4.14 ```git push origin main```
  
### Annuler les modifications d'un fichier avec git restore (Pro Git p. 48)
Cette op�ration annule toutes les modifications d'un fichier consign�es dans le dernier commit.
5. La commande est ```git restore <fichier>```
 5.1 ajout de 4 lignes � test.txt
 4.2 bien s�r, git status indique que le fichier est modifi� et ```cat test.txt``` montre les nlles lignes.
 4.3 fermeture de test.txt dans l'�diteur
 4.3 ```git restore test.txt```, puis
 4.4 ```cat test.tst```confirme que les changements sont disparuset ```git status```, n'indique aucune modification au fichier.
 
