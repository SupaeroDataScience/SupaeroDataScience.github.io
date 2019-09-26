# Information for current students

## Useful links

[Moodle (requires ISAE-SUPAERO authentication)](https://lms.isae.fr/course/index.php?categoryid=282)<br>
The [Operations Research MS](http://m2rit-ro.recherche.enac.fr/)<br>
The [Applied Math MS](https://perso.math.univ-toulouse.fr/m2r/)<br>
The [alumni Linkedin group](https://perso.math.univ-toulouse.fr/m2r/)

## Software (in French, updated Sept. 2019)

Votre boîte à outils sur votre ordi perso, tout au long de l'année !

### Une machine virtuelle ?

Auto-formation virtual-box : [http://lms.isae.fr/course/view.php?id=1111](http://lms.isae.fr/course/view.php?id=1111)

### Distribution GNU/Linux
On vous recommande d'installer une distribution Linux Ubuntu-like (ou Debian-like) pour trouver facilement de l'aide si besoin.

### Pilotes GPU

Installation de drivers CUDA :
[https://developer.nvidia.com/cuda-downloads](https://developer.nvidia.com/cuda-downloads)

Installation de drivers OpenCL :
- Si le PC a une carte graphique NVIDIA, les drivers OpenCL et CUDA sont [là](http://www.nvidia.com/Download/index.aspx?lang=en-us)
- Si le PC a une carte graphique AMD, les drivers OpenCL sont [là](https://www.amd.com/en-us/solutions/professional/hpc/opencl)
- Si le PC a seulement un processeur Intel, les drivers OpenCL sont [là](https://software.intel.com/en-us/articles/opencl-drivers)
- Sur Mac, [OpenCL est déjà installé](https://support.apple.com/fr-fr/HT202823)

Compilateurs possibles :
- gcc/g++, Clang/xCode, Visual Studio, ...

Librairies / d’interfaces pour la programmation :
- Librairie [pycuda en Python](https://mathema.tician.de/software/pycuda/)
~~~~
> pip install pycuda
~~~~
- Librairie [pyopencl en Python](https://mathema.tician.de/software/pyopencl/)
~~~~
> pip install pyopencl
~~~~
→ Interface [Boost en C++](http://www.boost.org/doc/libs/1_63_0/libs/compute)

### Le langage R
- L'interpréteur du langage R
~~~~
> sudo apt install r-base
~~~~
- L'environnement de développement R-studio Desktop
[https://www.rstudio.com/products/rstudio/download/](https://www.rstudio.com/products/rstudio/download/)

### Le langage Scala
- L'interpréteur du langage Scala et le Scala Build Tool
~~~~
> echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
> sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
> sudo apt-get update
> sudo apt-get install sbt
~~~~

### Le couteau suisse de Python 3 (le plus récent) via Anaconda (https://www.anaconda.com/download)
- Une [distribution anaconda pour Python 3 (le plus récent)](https://www.anaconda.com/distribution/#download-section)
- En principe par défaut vous avez déjà les paquets de base (numpy, pandas, scipy, matplotlib, scikit-learn) sinon vous pouvez les ajouter avec la commande "conda install nom-du-paquet"
- Quelques paquets conda en plus
~~~~
> conda install tensorflow keras pytorch proj4 geos graphviz python-graphviz nltk networkx statsmodels pyspark
~~~~
- Pour ceux qui ont une carte graphique NVIDIA (à regarder après avoir fait la partie plus bas concernant votre carte graphique)
~~~~
> conda install tensorflow-gpu pytorch-gpu
~~~~
- Et quelques paquets pour lesquels il vaut mieux utiliser pip (si possible le pip de votre distribution conda qui devrait devenir la commande pip par défaut si vous n'avez pas fait une installation exotique)
~~~~
> pip install pulp facile cartopy altair ipyleaflet cython cma vispy gym gym[atari] gym[classic_control] gym[box2d] gym[algorithms] roboschool
~~~~

### La base de données PostgreSQL
~~~~
> sudo apt install postgresql-11 pgadmin3
~~~~

Il y aura sûrement d'autres choses à installer en cours d'année mais vous avez une base très complète avec ça.

Notez que vous avez également accès gratuitement (avec votre statut étudiant) au solver de programmation linéaire et programmation par contraintes [IBM ILOG CPLEX](https://www.ibm.com/products/ilog-cplex-optimization-studio). Il n'est pas nécessaire de l'installer mais ça peut être utile pour reproduire les BE joués au SI.

[Tableau software](https://www.tableau.com/academic/students) (à installer vers mars)

### Quelques outils utiles pour jupyter notebooks :
[Replier les cellules d'un notebook](https://stackoverflow.com/questions/33159518/collapse-cell-in-jupyter-notebook) :

~~~~
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --user

pip install jupyter_nbextensions_configurator
jupyter nbextensions_configurator enable --user
~~~~

[Ouvrir des notebooks en double-cliquant dessus](https://github.com/takluyver/nbopen) :

~~~~
pip install nbopen
python -m nbopen.install_xdg
~~~~

[Avoir des git diffs et des git merge lisibles sur les notebooks](https://github.com/jupyter/nbdime) :

~~~~
pip install nbdime
nbdime config-git –enable –global
~~~~

