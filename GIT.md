# GIT

Open Source Version Control System

## Github a Proje Yüklemek

1. Create Github account
2. Install Git
3. In your coding folder create .git file
~~~bash
git init
~~~
4. Commit your changes
~~~bash
git commit -m "commit message"
~~~~
5. Add to repository
~~~bash
git remote add origin <repository_url>
~~~
6. Push your changes
~~~bash
git push -u origin master
~~~

## GIT Workflow

![Git workflow chart](/Images/Git%20Workflow.png "Git Workdlow")

## Useful GIT Commands

### git config

~~~bash
git config --list

git config -- global user.name = '<user_name>'
~~~

### git init

~~~bash
git init
~~~
> To add .git file

### git status

~~~bash
git status
~~~
~~~bash
clear
~~~

### git add

~~~bash
git add <file_name>

git add .
~~~
> '.' adds all files

### git commit

~~~bash
git commit -m "<commit_comment>"
~~~~

### git restore

~~~bash
git restore --staged <file_name>
~~~
> Geçiş bölgesine gönderilen değişikliği geri almak için kullanılır

### git log

~~~bash
git log

# last to commits
git log -p -2

git log --since=10minutes
git log -n

git log --author=<author>
git log --oneline
~~~

### git checkout

~~~bash
git checkout <commit_id>
~~~

### git revert

~~~bash
git revert <commit_id>
~~~

### git reset

~~~bash
git reset --soft <commit>
git reset --mix <commit>
git reset --hard <commit>
~~~
> Dangerous command
~~~bash
.gitignore
~~~
> İstemediğimiz dosyların isimlerini bu dosyaya yazıyoruz

### git rm

~~~bash
git rm -r --cached
~~~

### git branch

~~~bash
git branch <branch_name>

git branch -a
~~~
> -a tüm bracnhleri görmek için kullanılır

### git merge

~~~bash
git merge <branch_name>
~~~

### git clone

~~~bash
git clone <repository>
~~~