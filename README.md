# symlinx.github.io
## Description
Ce repos contient les données du blog symlinx.github.io. Il est géré avec Jekyll, un générateur de sites et de blogs statiques.

## Prérequis

Pour éditer ce site, on aura besoin de :

- git
- ruby
- gem
- jekyll



## Installer son envrionnement 

Installer les différents composants. Ci-dessous un exemple pour les distributions basées sur Debian, à adapter selon votre OS
```
apt install -y git ruby rubygems
``` 
Ajouter votre clé publique SSH dans votre compte GitHub et configurer le client git
```
git config --global user.name "github_username"
git config --global user.email "my@email.com"
```
Installer les gems Ruby
```
gem install jekyll minima bundler
```

## Comment éditer le blog

Cloner le projet
```
git clone git@github.com:symlinx/blog.git
cd blog/
```
Jekyll se base sur un fichier de configuration _config.yml et des fichiers markdown, qu'il va builder en un site html statique 

Créer un un nouveau post à partir d'un post existantet l'éditer avec votre contenu
```
cp -p _posts/2019-01-26-welcome-to-jekyll.markdown _posts/2019-01-27-mon-premier-billet.markdown
vim _posts/2019-01-27-mon-premier-billet.markdown
```

Builder une nouvelle version du site vers le répertoire docs/ utilisé par GitHub pour servir les fichiers statiques
```
$ bundle exec jekyll build -d docs
Configuration file: /home/mint/github/blog/_config.yml
            Source: /home/mint/github/blog
       Destination: docs
 Incremental build: disabled. Enable with --incremental
      Generating... 
       Jekyll Feed: Generating feed for posts
                    done in 0.374 seconds.
 Auto-regeneration: disabled. Use --watch to enable.
 ```
Commiter et pusher la nouvelle version
 ```
 $ git add -A
 $ git commit -a -m 'mon premier billet'
 $ git push
 Counting objects: 10, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (7/7), done.
Writing objects: 100% (10/10), 3.12 KiB | 0 bytes/s, done.
Total 10 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
To git@github.com:symlinx/blog.git
   ddb06f8..6e9ff4f  master -> master
```
 
