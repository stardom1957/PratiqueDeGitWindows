# PratiqueDeGitWindows
Afin d'éviter des possibles emerdements, j'utiliserai ce site pour les tests et pratiques dans git sous Windows. Ce document servira donc de journal pour les opérations.

2022-10-12
0. Ouverture du répo, dans terminal MINGW64 (git Bash) :
 0.1 git init -b main
 0.2 touch README.md
 0.3 touch .gitignore
  0.3.1 ajout de *.bak
  Note : l'éditeur UltraEdit-32 produit automatiquement un fichier .bak lors de l'ouverture d'un fichier.
 0.4 git add .
 0.5 changements dans README.md dans UltraEdit-32
 Note : dans cette (très vielle) version de l'éditeur (v. 12.10+3),  le contenu est édité avec les marques de md, mais il n'y a pas de Wysiwyg!
 
 0.6 commit initial

1. Après commit initial, test du changement du commit par amend :
 1.1 changements dans README.md (plusieurs changements car le terminal a planté et j'ai dû utiliser G. des tâches pour le fermer!)
 1.2 plusieurs fois : git add .
 1.3 selon ProGit p.44 : '''git commit --amend'''

  Notes :
  Après plusieurs essais pour corriger les typos.
       
  La commande en 1.3 lance automatiquement l'éditeur par défaut (Notepad) avec le commentaire inscrit pour corriger le message de commit si nécessaire. Super!

  1.4 après plusieurs autres commit amend, il n'y a effectivement qu'un seul commit (initial) visible dans le repo.
    