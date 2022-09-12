# Systems CTF

This class is a week long Capture the Flag event to get to know with the basics of systems usage, specifically linux, git, ssh. There is also a large section on python, with an emphasis on data science scripting practices using numpy and pandas in jupyter notebooks.

This is a self-guided exercise with resources and questions on this site. You, the participant, must look for the answer to the questions through reading documentation, discussing with others, and trying things. Try to avoid searching for answers online in a search engine; the answers can almost always be found in documentation.

Answers can be submitted through an API with the CTF server. Resources to answer different sections will be made available throughout the week; for example, some python questions require data which won't be available until the halfway point. Responding correctly to a question gives 1 point, and an additional 0.5 points are awarded for being the first to submit the correct answer to a question. That half point is the flag - be the first to capture it!

The CTF server's IP address is `13.39.51.160`. You can see a leaderboard there and it is the address for submitting answers. The first way we'll look at submitting answers is with `curl` in Linux.

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

### Questions

1. Where is the `curl` executable located?
2. Where is the `wget` executable located?
3. What is the linux command used for reading manuals?
4. What is the longer name of the `-K` flag to `curl`? Answer with just the name, without `--`
5. What is the `ls` command flag used for human-readable output? Answer with just the letter, without `-`
6. What is the `cp` command flag allowing for copying directories? Answer with just the letter, without `-`
7. What is the `mv` command flag which will interactively prompt before overwriting files? Answer with just the letter, without `-`
8. If the variable `STRING` is set to `banana`, what does the command `echo ${STRING:4}$` return?
9. If the variable `STRING` is set to `to be or not to be`, what does the command `echo ${STRING[@]/be/eat}` return?
10. If the variable `a` is set to 3 and `b` is set to 4, what does the command `$a <= $b` return?
11. If the variable `p` is set to `(3 1 4 1 5 9)`, what does the command `echo $((${p[0]} * ${p[2]}))` return?
12. Where is the `grep` executable located?
13. What is the `grep` command flag used to select *non-matching* lines? Answer with just the letter, without `-`
14. What is the longer name of the `-c` flag to `grep`? Answer with just the name, without `--`
15. What is the `cat` command flag which shows line numbers? Answer with just the letter, without `-`
16. What does the command `head -n 10 file_a.txt | wc -l` return?
17. How many lines are in `file_a.txt`?
18. How many characters are in `file_c.txt`?
19. How many words in `file_a.txt` start with the letter "d"?
20. How many four-letter words are in `file_a.txt`?
21. What is the last word in `file_b.txt`?
22. How many words contain "ello" inside them in `file_b.txt`?
23. What is the line number of the word "helicopter" in `file_b.txt`?
24. What is the line number of the word "croissant" in `file_c.txt`?
25. How many words contain "croissant" inside them in `file_c.txt`?
26. How many words start with the letter "c" in `file_c.txt`?
27. How many words end with the letter "t" in `file_c.txt`?
28. How many words have the letter "o" directly followed by either "u" or another "o" in `file_c.txt`?
29. What word is at the same line in `file_c.txt` as the word sheep is in `file_a.txt`?
30. What is the second word in `file_c.txt` which contains the letter `x`?

### Resources

+ [ISAE class on CLI, Linux, and Bash](https://lms.isae.fr/course/view.php?id=1111)
+ [Shell class from MIT](https://missing.csail.mit.edu/2020/course-shell/)
+ [Bash exercises](https://www.learnshell.org)
+ [More bash exercises](https://exercism.io/tracks/bash)
+ [Short exercises in regular expressions](https://regexone.com/)

## Git

[create an SSH key and add it to your account](https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)

    Créez un compte GitHub si ce n'est pas déjà fait.
    Créez un fork du dépôt https://github.com/SupaeroDataScience/etudiants-sdd-XXXXXX où XXXXXX est l'année scolaire en cours (par exemple 201819)
    Copiez votre clé publique dans un fichier avec le nom prénom-nom-login_github.pub (faites attention que vous copiez la partie publique et non la partie privée)
    Faites un commit en ajoutant ce fichier
    Faites un Pull Request au dépôt de base (https://github.com/SupaeroDataScience/etudiants-sdd-XXXXXX) pour que les modifications que vous avez faites soient intégrées dessus.

### Questions


### Resources

+ [Git course](https://www.youtube.com/playlist?list=PLjwdMgw5TTLXuY5i7RW0QqGdW0NZntqiP)
+ [Introduction to github](https://lab.github.com/githubtraining/introduction-to-github)
+ [Github video course](https://www.youtube.com/playlist?list=PL0lo9MOBetEHhfG9vJzVCTiDYcbhAiEqL)
+ [Learn git branching](https://learngitbranching.js.org/)
+ [Git SCM book](https://git-scm.com/book/en/v2)
+ [Git cheat sheet](https://github.github.com/training-kit/downloads/github-git-cheat-sheet.pdf)


## SSH

Starting on Wednesday, you will connect to the CTF server to answer questions about the remote environment. Your public key must be uploaded to the git repository above to get access to the server. You will use the corresponding private key to access the server.

### Questions

0. What is the hostname of the server?
1. What is the operating system of the server?
2. How many files (excluding directories) are there in ~/?
3. What are the directories with binary executables accessible to the user (ie PATH)?
4. How many binary executables are available to the user?
5. What is the MAC address of the ethernet device of the server?
6. What is the internal IP address of the server?

### Resources

+ [Ubuntu ssh manual](https://doc.ubuntu-fr.org/ssh)
+ [Guide in French](https://openclassrooms.com/en/courses/43538-reprenez-le-controle-a-laide-de-linux/41773-la-connexion-securisee-a-distance-avec-ssh)
+ [Cryptographie Asymétrique](https://www.youtube.com/watch?v=MuNyEoU5tSo)
+ [How SSH works](https://www.youtube.com/watch?v=ORcvSkgdA58)

## Python

An overview and reminder of the python programming language, with a focus on numpy and pandas manipulation using Jupyter.

### Installation

### Questions

Questions will be revealed on Wednesday

### Resources