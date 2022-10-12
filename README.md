# PratiqueDeGitWindows
Afin d'�viter des possibles emerdements, j'utiliserai ce site pour les tests et pratiques dans git sous Windows. Ce document servira donc de journal pour les op�rations.

2022-10-12
0. Ouverture du r�po, dans terminal MINGW64 (git Bash) :
 0.1 git init -b main
 0.2 touch README.md
 0.3 touch .gitignore
  0.3.1 ajout de *.bak
  Note : l'�diteur UltraEdit-32 produit automatiquement un fichier .bak lors de l'ouverture d'un fichier.
 0.4 git add .
 0.5 changements dans README.md dans UltraEdit-32
 Note : dans cette (tr�s vielle) version de l'�diteur (v. 12.10+3),  le contenu est �dit� avec les marques de md, mais il n'y a pas de Wysiwyg!
 
 0.6 commit initial

1. Apr�s commit initial, test du changement du commit par amend :
 1.1 changements dans README.md (plusieurs changements car le terminal a plant� et j'ai d� utiliser G. des t�ches pour le fermer!)
 1.2 plusieurs fois : git add .
 1.3 selon ProGit p.44 : '''git commit --amend'''

  Notes :
  Apr�s plusieurs essais pour corriger les typos.
       
  La commande en 1.3 lance automatiquement l'�diteur par d�faut (Notepad) avec le commentaire inscrit pour corriger le message de commit si n�cessaire. Super!

  1.4 apr�s plusieurs autres commit amend, il n'y a effectivement qu'un seul commit (initial) visible dans le repo.
    