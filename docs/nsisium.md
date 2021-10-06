# Mini-Projet **nsisium**

## Contexte :

Une équipe de chercheurs de l'université de Balnave vient de découvrir un nouvel élément : le **nsisium**.  

Dans la classification de Mendeleïev, il s'agit de l'élément 119, un métalloïde aux propriétés étonnantes puisqu'il permettrait, selon le professeur Kefa PIPO, de tripler les performances des panneaux photovoltaïques actuels !

Ce métalloïde ne se trouve sur terre que dans les régions naturellement radioactives et donc dangereuses pour l'exploration humaine. Plus précisément, on le trouve dans le sous-sol de grottes où une fumée épaisse empêche l’utilisation de caméra traditionnelle.

L’idée serait donc de piloter à distance un robot d’exploration équipé d'un capteur de nsisium pour cartographier une zone donnée.  
Il serait aussi équipé d’un capteur ultra-son pour visualiser son environnement comme ce que peuvent faire les chauves souris (les ultra-sons sont utilisables dans les épaisses fumées contrairement aux ondes lumineuses).

L'accès des grottes peut être limité à une largeur de 250 mm et une hauteur de 120 mm. Le robot doit être capable de gravir une rampe de 60%.

Il faut prévoir une surveillance de l'autonomie énergétique du robot afin d'assurer sa récupération...


## Ressources :

Le robot utilisé sera un EV3 de chez LEGO équipé d'un système d'exploitation Linux (EV3 MicroPython version v2.0).

Le robot portera un capteur de nsisium.  
Ce capteur envoie un signal spécial dans le sol. Si celui-ci revient à 100 % c'est qu'il n'y a pas de nsisium en dessous.  
Si le signal ne revient que faiblement par exemple à 10 %, c'est que du nsisium se trouve en dessous et qu'il a absorbé une grande partie de l'énergie du signal d'origine. Son taux serait alors de 90%.

Le robot utilisera également un capteur ultrason. Ce dernier permettra de mesurer la distance entre d’éventuels obstacles et le robot. Le pilote à l’instar d’une chauve souris pourra ainsi éviter les obstacles présents sur la zone de recherche.

Pour le positionnement, plusieurs capteurs pourront être utilisés dont le capteur gyroscopique et le capteur tachymétrique intégré aux moteurs.

Plus d’informations dans la documentation [pybricks ev3-micropython/](https://pybricks.github.io/ev3-micropython/)


## Démarche :

Vous travaillerez en mode agile par équipes de 3 élèves (1 SI et 2 NSI) + 1 professeur qui jouera le role de [Product Owner](https://www.orientation.com/metiers/product-owner).

Les équipes seront donc misent en concurrences pour ce projet.

Dans chaque équipe vous désignerez un volontaires pour être [Scrum Master](https://www.clementine.jobs/fiches-metiers/metiers-techniques-du-web/scrum-master/#:~:text=Le%20Scrum%20Master%20est%20avant,en%20suivant%20la%20m%C3%A9thode%20Scrum.).

Tout le monde participe activement au développement du code y compris le [Product Owner](https://www.orientation.com/metiers/product-owner) en cas de besoin (mais pas trop parce qu'il n'a pas que ça à faire !;) ).

Ce projet sera donc aussi l'occasion de découvrir et d'expérimenter les rudiments d'une méthode agile que présente les vidéos suivantes...

<center>
    <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/VpdFpZ_w5x8?start=30" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

<center>
    <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/-HV_MW5KgVk" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

<center>
    <iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/WNYcSxbJvsc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</center>

Le développement du projet va donc se décomposer en plusieurs sprints...


## Un peu d'aide et quelques conseils :

### Mise en réseau par wifi :

- Créer un réseau LAN avec un routeur Wifi.

- Installer un dongle Wifi sur le port USB-A de la brique Lego EV3.

- Après démarrage du système, configurer le réseau WiFi depuis le menu de la brique...

> Si la connexion Wifi est valide, l'adresse IP du robot s'affiche sur l'écran (en haut)

- Pour tester le bon fonctionnement du robot, on peut se connecter via SSH. Les identifiants sont :
  * utilisateur : robot
  * mot de passe : maker
```
$ ssh robot@192.168.1.101
```

- Pour lancer un script micropython depuis la console du robot par SSH : 
```
$ brickrun pybricks-micropython /home/robot/hello.py
```

- Pour lancer un interpréteur depuis la console du robot par SSH afin d'exécuter une des fonctions de votre programme :
```
$ cd monProjet # aller dans le dossier du projet
$ brickrun pybricks-micropython # démarrer l'interpréteur Pybricks MicroPython
Pybricks MicroPython v1.11 on 2020-05-06; linux version
Use Ctrl-D to exit, Ctrl-E for paste mode
>>> from monProgramme import *
>>> maFonction()
```

### Modularité :

Développer petit à petit de façon modulaire, par fonctionnalité...

```python
#!/usr/bin/env pybricks-micropython

# Dépendances
from machin import bidule, truc

# Définitions
    
bar = 'titi'

def foo() :
    '''
        Docstring de foo()
    '''
    pass

# Tests
if __name__ == '__main__': 
    # appel à la fonction foo() pour un test
    foo()
    # affichage en console d'une variable
    print(bar)
```
## Autres ressources :

- Le module Pybricks MicroPython pour EV3 est basé sur [ev3dev](https://www.ev3dev.org/news/2019/04/13/ev3-micropython/) ;
- [Tutoriel EV3 Python par Raphael Holzer](https://ev3-tutorial.readthedocs.io/en/latest/index.html) ;

- [https://sites.google.com/site/ev3devpython/](https://sites.google.com/site/ev3devpython/) ;

- [Instructions de construction de différents modèles](https://education.lego.com/en-us/product-resources/mindstorms-ev3/downloads/building-instructions#building-core)


