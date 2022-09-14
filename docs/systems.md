# Systems CTF

This class is a week long Capture the Flag event to get to know with the basics of systems usage, specifically linux, git, ssh. There is also a large section on python, with an emphasis on data science scripting practices using numpy and pandas in jupyter notebooks.

This is a self-guided exercise with resources and questions on this site. You, the participant, must look for the answer to the questions through reading documentation, discussing with others, and trying things. Try to avoid searching for answers online in a search engine; the answers can almost always be found in documentation.

Answers can be submitted through an API with the CTF server. Resources to answer different sections will be made available throughout the week; for example, some python questions require data which won't be available until the halfway point. Responding correctly to a question gives 1 point, and an additional 0.5 points are awarded for being the first to submit the correct answer to a question. That half point is the flag - be the first to capture it!

However, if you're speeding through the questions, consider helping others learn the material. Depending on your background, you may have varied experience with these tools. Get to know the other participants by helping them capture a flag too.

The CTF server's IP address is [`13.39.51.160`](http://13.39.51.160/). You can see a leaderboard there and it is the address for submitting answers. The first way we'll look at submitting answers is with `curl` in Linux.

## Linux

Linux is an open-source operating system based on Unix. It is a standard choice for development and is the most dominant operating system for web servers, cloud computing, and high performance computing at 80% of global public servers. There are many different [distributions](https://en.wikipedia.org/wiki/List_of_Linux_distributions) but they share a common set of tools, notably [GNU](https://en.wikipedia.org/wiki/GNU) software. A very common Linux distribution is Android, at [73% of all mobile devices](https://en.wikipedia.org/wiki/Usage_share_of_operating_systems), so you might be a Linux user already without realizing it!

You most likely don't use Linux as the operating system of your personal computer, however. If you **are** using one the 2.5 % of personal computers with Linux, you can skip straight to the Submission section

MacOS is also based on Unix, so if you're using MacOS, most things should work just as in Linux! A few commands will be different from the course instructions, and the questions will always refer to Linux resources, for example documentation. It is highly recommended to install homebrew (https://brew.sh/) which will allow for package installation via the command line.

### Installation on Windows

The easiest way to use Linux on Windows is through the Windows Subsystem for Linux. Installation instructions are here: [https://docs.microsoft.com/en-us/windows/wsl/install](https://docs.microsoft.com/en-us/windows/wsl/install). Make sure to follow all instructions carefully. If asked to join a "Windows Insiders Program", ignore this. By default, this installs Ubuntu, which is good for this systems class and for all of SDD.

The WSL is similar to a virtual machine inside of Windows, but it integrates with some existing components of Windows. You can access your Windows files from Linux at `/mnt/`, but you should make sure you're familiar with Linux first.

+ [About the WSL](https://docs.microsoft.com/en-us/windows/wsl/about)
+ [WSL FAQ](https://docs.microsoft.com/en-us/windows/wsl/faq)
+ [How to Access WSL Linux Files from Windows](https://www.howtogeek.com/426749/how-to-access-your-linux-wsl-files-in-windows-10/)

### Submission

Once you have a Unix-type environment, either native Linux or macOS, or through the WSL, you're ready to submit to the CTF. You will use the `curl` command; you can verify that you have `curl` by running `which curl` in the command line. `curl` is a tool for transferring data from or to a server. How do you know that? By checking the documentation of `curl` using `man curl`. Try it out!

To respond to a question, send a POST request with the data of the question `number` and `answer`, and your username as `user` (your username should be your ISAE login, but you can also check on the leaderboard). For example, the first question asks where the `curl` executable is (hint: use `which`). Then use `curl`:

```bash
curl -X POST 'http://13.39.51.160/' \
    -d 'number=1' \
    -d 'answer=your answer here' \
    -d 'user=your username here'
```

Some of the questions will require access to some files, called `file_a.txt`, `file_b.txt`, and `file_c.txt`. Here are three different ways to download using `curl` and `wget`:

```bash
curl http://13.39.51.160/files/file_a.txt -o file_a.txt
curl http://13.39.51.160/files/file_b.txt > file_b.txt
wget http://13.39.51.160/files/file_c.txt
```

Be sure to download all three files, using whichever method. You are ready to start answering questions! If you don't know an answer, check the resources below and read documentation using `man`.

You can see which questions you have answered by sending a GET request:

```bash
curl 'http://13.39.51.160/user/d.wilson'
```

You can also see which questions have remaining flags, the bonus points associated with answering the question for the first time, with a GET request:

```bash
curl 'http://13.39.51.160/answers/'
```

### Questions

1 | Where is the `curl` executable located? Some systems vary, if your answer is incorrect, try a common alternative.

2 | Where is the `wget` executable located?

3 | What is the linux command used for reading manuals?

4 | What is the longer name of the `-K` flag to `curl`? Answer with just the name, without `--`

5 | What is the `ls` command flag used for human-readable output? Answer with just the letter, without `-`

6 | What is the `cp` command flag allowing for copying directories? Answer with just the letter, without `-`

7 | What is the `mv` command flag which will interactively prompt before overwriting files? Answer with just the letter, without `-`

8 | If the variable `STRING` is set to `banana`, what does the command `echo ${STRING:4}$` return?

9 | If the variable `STRING` is set to `to be or not to be`, what does the command `echo ${STRING[@]/be/eat}` return?

10 | If the variable `a` is set to 3 and `b` is set to 4, what does the command `if [[ $a -le $b ]]; then echo $a; else echo $b; fi` return?

11 | If the variable `p` is set to `(3 1 4 1 5 9)`, what does the command `echo $((${p[0]} * ${p[2]}))` return?

12 | Where is the `grep` executable located?

13 | What is the `grep` command flag used to select *non-matching* lines? Answer with just the letter, without `-`

14 | What is the longer name of the `-c` flag to `grep`? Answer with just the name, without `--`

15 | What is the `cat` command flag which shows line numbers? Answer with just the letter, without `-`

16 | What does the command `head -n 10 file_a.txt | wc -l` return?

17 | How many lines are in `file_a.txt`?

18 | How many characters are in `file_c.txt`?

19 | How many words in `file_a.txt` start with the letter "d"?

20 | How many words are in `file_a.txt` that contain only 4 lowercase (English) letters? (Hint: the answer is 3459. 3470 is also good!)

21 | What is the last word in `file_b.txt`?

22 | How many words contain "ello" inside them in `file_b.txt`?

23 | What is the line number of the word "helicopter" in `file_b.txt`?

24 | What is the line number of the word "croissant" in `file_c.txt`?

25 | How many words contain "croissant" inside them in `file_c.txt`?

26 | How many words start with the letter "c" in `file_c.txt`?

27 | How many words end with the letter "t" in `file_c.txt`?

28 | How many words have the letter "o" directly followed by either "u" or another "o" in `file_c.txt`?

29 | What word is at the same line in `file_c.txt` as the word sheep is in `file_a.txt`?

30 | What is the second word in `file_c.txt` which contains the letter `x`?

### Resources

+ [ISAE class on CLI, Linux, and Bash](https://lms.isae.fr/course/view.php?id=1111)
+ [Shell class from MIT](https://missing.csail.mit.edu/2020/course-shell/)
+ [Bash exercises](https://www.learnshell.org)
+ [More bash exercises](https://exercism.io/tracks/bash)
+ [Short exercises in regular expressions](https://regexone.com/)

## Git

Git is a version control system used worldwide for maintaining code, documents, video games, and much more. It has seen wide adoption with servers like Github and Gitlab while being an open-source tool that anyone can install as a client or server. In this class, we will look at repositories hosted on Github, but git is much larger than that and many organizations like ISAE have their own private [git server](https://iris.isae-supaero.fr/git).

### Installation

If you're using Ubuntu, chances are you already have `git`. If not, simply do:

`sudo apt install git`

These questions concern two repositories: the Machine Learning class in SDD ([https://github.com/SupaeroDataScience/machine-learning](https://github.com/SupaeroDataScience/machine-learning)) and the Seaborn library, a popular graphing library ([https://github.com/mwaskom/seaborn](https://github.com/mwaskom/seaborn)). You will need to download both repositories. First choose a directory to host them in, for example `~/cours/SD/FSD319`:

```bash
mkdir -p cours/SD/FSD319
cd cours/SD/FSD319
```

and then download them using git clone:

```bash
git clone https://github.com/SupaeroDataScience/machine-learning.git
git clone https://github.com/mwaskom/seaborn.git
```

The commit for the `seaborn` repository is `1e6739` :

```bash
git checkout 1e6739
```

### Questions


31 | How many directories are there in the root directory of the `machine-learning` repository?

32 | How many total files are there in the `machine-learning` repository and all subdirectories? Not counting directories or hidden files like the `.git` repository

33 How many python or numpy files are in the `machine-learning` repository and subdirectories?

34 | What is the short version of the commit ID of the first commit of the `machine-learning` repository?

35 | What is the long version of the commit ID of the most recent commit of the `machine-learning` repository?

36 | What is the most recent commit message of the `machine-learning` repository?

37 | How many branches are in the `machine-learning` repository? Don't double count references to the same branch.

38 | What is the name of the branch which isn't `main` in the `machine-learning` repository?

39 | How many different unique user addresses have pushed commits to the `machine-learning` repository?

40 | What is the name of the LICENSE of the `machine-learning` repository? Hint: it is also the full first line of the LICENSE file

41 | What is the git remote "origin" url of the seaborn repository?

42 | What is the full version of the commit ID of the version 0.12 of seaborn?

43 | How many commits are in the `master` branch of seaborn?

44 | What is the last item of the seaborn repository's gitignore?

45 | How many tagged commits are there in the seaborn repository?

46 | How many "version" branches are there (ie, branches with a name starting in v)?

47 | What is the first line of the `setup.cfg` file in the seaborn repository?

48 | How many such key fields are in the `setup.cfg` file in the seaborn repository?

49 | How many files are in the seaborn repository? Not counting hidden files like the `.git` repository

50 | How many files directly use numpy in the seaborn repository?

### Resources

+ [Git course](https://www.youtube.com/playlist?list=PLjwdMgw5TTLXuY5i7RW0QqGdW0NZntqiP)
+ [Introduction to github](https://lab.github.com/githubtraining/introduction-to-github)
+ [Github video course](https://www.youtube.com/playlist?list=PL0lo9MOBetEHhfG9vJzVCTiDYcbhAiEqL)
+ [Learn git branching](https://learngitbranching.js.org/)
+ [Git SCM book](https://git-scm.com/book/en/v2)
+ [Git cheat sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)

### Git Exercise

In order to access the server for the next parts of the CTF, you will need to provide your public ssh key. The SSH section has references explaining [public-key cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography), but in general you will make a key pair with a private side and public side. You will give the public side to services like this class or Github to perform secure communication, keeping your private key secret to prove that it is you. 

First, start by making a key pair and uploading your public key to Github. This will allow you use to SSH to make push requests, instead of using a personal access token. [Create an SSH key and add it to your Github account](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

Then, we will use git as a way for you to transfer your public key to the class. We could use another means, like a USB key, email, or a very large QR code, but for this exercise we will use git. First [make a fork](https://docs.github.com/en/get-started/quickstart/fork-a-repo) of the [https://github.com/SupaeroDataScience/ctf2022](https://github.com/SupaeroDataScience/ctf2022) repository. Then, [make a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) with your key as a file in `keys/`. Please name your key with your name, like the example `keys/dennis-wilson.pub`. Be sure to upload **only your public key**. Do not ever upload your private key to public servers.

Once your key is in the repository, you are ready for the SSH and Python portions of the CTF.

## SSH

Starting on Wednesday, you will connect to the CTF server to answer questions about the remote environment. Your public key must be uploaded to the git repository above to get access to the server. You will use the corresponding private key to access the server. Your user on the server is `ctf` and the IP is the same as the CTF webserver: `13.39.51.160`.

Please note that *ISAE-EDU and ethernet block ssh to most servers*, including this one and `github.com`. In order to ssh to the server, you will need to either use the eduroam network or a different network like a mobile hotspot.

### Questions

51 | What is the name of the linux command used to generate SSH keys?

52 | What is the letter of the flag to specify the number of bits when generating an ssh key?

53 | What is the letter of the `ssh` flag that denotes the private key to use for authentification?

54 | What is the letter of the `ssh` flag to specify the user to log in as on the remote machine?

55 | What is the default port for `ssh`?

56 | What is the first default private key file used by `ssh`?

57 | What is the escape command to disconnect from an `ssh` pseudoterminal?

58 | What is the standard location of the per-user ssh configuation file in Linux?

59 | What is the keyword to specify the private key file in an ssh configuration file?

The following questions pertain to the remote server.

60 | How many files (excluding directories) are there in `~/`?

61 | What are the directories with binary executables accessible to the user (ie PATH)?

62 | How many binary executables are available to the user?

63 | What is the hostname of the server?

64 | What is the kernel name of the server?

65 | What is the release of the kernel of the server?

66 | What is the MAC address of the ethernet device of the server?

67 | What is the internal IP address of the server?

68 | What is the timezone of the server?

69 | What is the remote origin url of the git repository at `~/repo/`?

70 | What is the name of the file (without the path) that has been removed in the git repository?

71 | How many lines are in the file `~/repo/data/dogc.txt`?

72 | What is the last line of the file `~/repo/data/muni-cat.txt`?

73 | What is the filename and line number of the 100th instance of "ee" in all of the files in `~/repo/data/`? Answer in "filename:number" format

74 | How many `.txt` files are on the whole server?

75 | How many `.txt` files are in the home directory or its subdirectories?

### Resources

+ [Ubuntu ssh manual](https://doc.ubuntu-fr.org/ssh)
+ [Guide in French](https://openclassrooms.com/en/courses/43538-reprenez-le-controle-a-laide-de-linux/41773-la-connexion-securisee-a-distance-avec-ssh)
+ [Cryptographie Asymétrique](https://www.youtube.com/watch?v=MuNyEoU5tSo)
+ [How SSH works](https://www.youtube.com/watch?v=ORcvSkgdA58)

## Linux tools

Now that you're an expert in Linux, let's quickly look at some useful tools. You may need to install some of these, either using `apt`, `brew`, `yum`, `pacman`, or whichever package manager you use. Linux comes with many programs installed by default, especially distributions like Ubuntu, however the tools in this section will be more useful than the base Linux tools. We'll cover four: `apt` for package management, `top` for system monitoring, `tmux` for terminal management, and `vim` for file editing. There are alternatives to all of these programs that are great, but it is worth being familiar with these four.

### Questions

76 | What is the `apt` command used to install available updates?

77 | What is the letter of the `apt-get` command flag to perform a test run of the installation that does not actually change the system?

78 | What is the file which lists locations that `apt` fetches packages from?

79 | What is the name of the first column in `top` by default?

80 | What is the letter of the command in `top` to kill a process?

81 | What is the `tmux` command to list all running sessions?

82 | What is the `tmux` command to use an existing session?

83 | What is the letter of the tmux key binding to create a new window inside `tmux`?

84 | What is the letter of the tmux key binding to leave the current client without stopping it?

85 | If you run `tmux` on a remote server and then disconnect, will the `tmux` session end? "yes" or "no"

86 | What is the name for the tutorial command to learn `vim`?

87 | What is the name of the mode `vim` starts in by default?

88 | What is the command to quit vim, without saving changes?

89 | What is the letter used to navigate up in `vim`?

90 | What is the file used for a user's `vim` configuration?

### Resources

+ [apt manual](https://manpages.ubuntu.com/manpages/xenial/man8/apt.8.html)
+ [Alternatives to top](https://itsfoss.com/linux-system-monitoring-tools/)
+ [Guide to tmux](https://www.hamvocke.com/blog/a-quick-and-easy-guide-to-tmux/)
+ [tmux cheat sheet](https://tmuxcheatsheet.com/)
+ [Editors from MIT class](https://missing.csail.mit.edu/2020/editors/)
+ [Vim adventures](https://vim-adventures.com/)
+ [tldr, short man pages](https://tldr.sh/)

## Python

An overview and reminder of the python programming language, with a focus on numpy and pandas manipulation using Jupyter.

### Installation

You most likely have python installed on your Linux system, but it is worthwhile to make sure and to upgrade. Python 3.8, 3.9, or 3.10 are all supported.

```
sudo apt install python3
```

It is highly recommended to make a `virtual environment` to manage your python packages. There are three main libraries for virtual environments: 

+ [Virtualenv](https://docs.python.org/3/tutorial/venv.html)
+ [Pipenv](https://pipenv.pypa.io/en/latest/)
+ [Conda](https://docs.conda.io/en/latest/)

`Virtualenv` is recommended for new users on Linux. Conda, or the platform Anaconda, can be useful on Windows as many packages are built specifically for windows, but not all packages are available via conda. `Pipenv` is an exciting project aimed at Python developers, but it adds additional complexity.

Once you have a virtual environment created, please install the following packages for the rest of the Seminars class:

```
numpy
pandas
scipy
matplotlib
jupyter
```

The following packages will also be used in SDD and some in SD:

```
seaborn
scikit-learn
keras
torch
geos
graphviz
nltk
networkx
statsmodels
pyspark
cython
cma
gym
```

### Jupyter

[Jupyter](https://jupyter.org/) (stands for the three original languages in the project: Julia, Python, and R) is a way to use and develop code interactively in the browser. Once you've installed the jupyter package, you can run a Jupyter notebook by simply running `jupyter notebook`.

For Windows users, you can run Jupyter in the WSL. As explained in [this blog post](https://harshityadav95.medium.com/jupyter-notebook-in-windows-subsystem-for-linux-wsl-8b46fdf0a536), you simply need to execute `jupyter notebook --no-browser` on the WSL and then copy and paste the URL and token generated into a Windows browser.

Some additional packages for improving Jupyter are `nbopen nbdime RISE`. Be sure to read their documentation before installing to verify if these are relevant to you.

### Questions

91 | What is the name of the standard python library module for creating virtual environments?

92 | What is the name of the command used for activating an environment when using virtualenv?

93 | What is the name of the `pip` command used to display all currently installed packages, in a format that can be used to install them using `pip`?

94 | What is the URL of the Python Package Index?

95 | What is the `jupyter` command to convert a notebook to a different file type?

96 | In what year did Python first appear?

97 | What is the latest major stable version of Python?

98 | What was the end-of-life date for Python 3.6? Use YYYY-MM-DD format.

99 | According to [PEP 8](https://peps.python.org/pep-0008/), how many spaces should be used as indentation?

100 | According to [PEP 8](https://peps.python.org/pep-0008/), what is the name of the convention used for naming classes?

Questions 101 - 120 are the responses to the exercises in the Jupyter notebook `python_intro.ipynb`, which is in the `ctf2022` github repository. Some exercises can be solved by running the code in them; try to figure them out before running the code to get the solution.

Questions on Numpy and Pandas will be released on Thursday morning. If you have reached question 120 before then, congratulations! Take a look at the resources to prepare for Thursday or help out any friends who haven't reached 120 yet.

### Resources

+ [Python 3.10 Documentation](https://docs.python.org/3/index.html)
+ [Pip documentation](https://pypi.org/project/pip/)
+ [Stanford Python and Numpy tutorial](https://cs231n.github.io/python-numpy-tutorial/)
+ [Python seminar](https://github.com/xoolive/pyseminar)
+ [Google Colab](https://colab.research.google.com/): Jupyter notebooks on the cloud
+ [Binder](https://mybinder.org/): Also Jupyter notebooks on the cloud, not hosted by Google
