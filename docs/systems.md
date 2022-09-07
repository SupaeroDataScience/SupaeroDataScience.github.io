# FSD319 - Seminars

## Python

Le couteau suisse de Python 3

- Pour Windows, une distribution anaconda pour Python 3 (le plus récent)  est recommandé, car il gère automatiquement votre chemin et vos environnements Python

   - https://www.anaconda.com/distribution/#download-section

- Si vous n'êtes pas sûr de l'environnement python que vous utilisez, veuillez lire ce qui suit avant de continuer :

   - https://realpython.com/python-virtual-environments-a-primer/

La grande (mais non exhaustive) liste des paquets python que nous utiliserons cette année à installer en utilisant soit pip soit conda :

 

numpy
pandas
scipy
matplotlib
scikit-learn
jupyter
keras
torch
geos
graphviz
nltk
networkx
statsmodels
pyspark
altair
cython
cma
gym
gym[atari]
gym[classic_control]
gym[box2d]
gym[algorithms]
roboschool

Cartopy
Installez également Cartopy, qui a d'autres dépendances :
https://scitools.org.uk/cartopy/docs/latest/installing.html#installing

Quelques outils utiles pour jupyter notebooks :

Replier les cellules d'un notebook (https://stackoverflow.com/questions/33159518/collapse-cell-in-jupyter-notebook) :

$ pip install jupyter_contrib_nbextensions
$ jupyter contrib nbextension install --user

$ pip install jupyter_nbextensions_configurator
$ jupyter nbextensions_configurator enable --user

Ouvrir des notebooks en double-cliquant dessus (https://github.com/takluyver/nbopen) :

$ pip install nbopen
$ python -m nbopen.install_xdg

Les présentations basées sur les notebooks (https://github.com/damianavila/RISE) :

$ pip install RISE

Avoir des git diffs et des git merge lisibles sur les notebooks (https://github.com/jupyter/nbdime) :

$ pip install nbdime
$ nbdime config-git –enable –global

Pilotes GPU pour Deep Learning

Uniquement pour ceux qui ont un GPU dédié sur leur machine personnelle

Installation de drivers CUDA :
https://developer.nvidia.com/cuda-downloads

Installation de drivers OpenCL :
→Si le PC a une carte graphique NVIDIA, les drivers OpenCL et CUDA sont là :
http://www.nvidia.com/Download/index.aspx?lang=en-us
→Si le PC a une carte graphique AMD, les drivers OpenCL sont là :
https://www.amd.com/en-us/solutions/professional/hpc/opencl
→ Si le PC a seulement un processeur Intel, les drivers OpenCL sont là :
https://software.intel.com/en-us/articles/opencl-drivers
→ Sur Mac, OpenCL est déjà installé :
https://support.apple.com/fr-fr/HT202823

→Version GPU de Tensorflow et Pytorch:

pip install tensorflow-gpu pytorch-gpu

## SSH



## Systems

### Git

Auto-formation Git et GitHub : commencez par visionner les vidéos (et pratiquer en même temps) :
https://www.youtube.com/playlist?list=PLjwdMgw5TTLXuY5i7RW0QqGdW0NZntqiP (jusqu'à la vidéo 11 incluse au strict minimum)
Et faites les activités guidées de :
https://lab.github.com/githubtraining/introduction-to-github

Vous devez créer une clé SSH pour votre compte en suivant les instructions suivantes: https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent


Exercice

    Créez un compte GitHub si ce n'est pas déjà fait.
    Créez un fork du dépôt https://github.com/SupaeroDataScience/etudiants-sdd-XXXXXX où XXXXXX est l'année scolaire en cours (par exemple 201819)
    Copiez votre clé publique dans un fichier avec le nom prénom-nom-login_github.pub (faites attention que vous copiez la partie publique et non la partie privée)
    Faites un commit en ajoutant ce fichier
    Faites un Pull Request au dépôt de base (https://github.com/SupaeroDataScience/etudiants-sdd-XXXXXX) pour que les modifications que vous avez faites soient intégrées dessus.


Ressources supplémentaires

    https://www.youtube.com/playlist?list=PL0lo9MOBetEHhfG9vJzVCTiDYcbhAiEqL
    https://learngitbranching.js.org/
    https://git-scm.com/book/en/v2
    La cheat-sheet git https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf


### Éditeur de texte
Programmer n'est pas comme écrire des documents Word, il s'agit souvent de travailler avec de nombreux fichiers différents, de manipuler de grandes quantités de texte de manière spécifique et répétée, et de suivre une syntaxe structurée bien au-delà du langage humain. Les éditeurs de texte aident à accomplir toutes ces tâches. Les plus populaires historiquement sont Vim et Emacs. Vous pouvez choisir n'importe quel éditeur de texte, mais il est recommandé de bien apprendre comment il fonctionne.

Vim

$ sudo apt install vim
$ vimtutor

Pour plus d'informations : https://missing.csail.mit.edu/2020/editors/

Emacs

$ sudo apt install emacs

https://www.emacswiki.org/emacs/LearningEmacs

Atom
https://atom.io/

Visual Studio
https://code.visualstudio.com/
Notez que le code VS dispose d'un mode interactif spécifique comme les notebooks Jupyter: https://code.visualstudio.com/docs/python/jupyter-support-py
