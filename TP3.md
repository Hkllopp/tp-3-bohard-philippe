  <h1>TP3 </h1>
  <h2>Exercice 1 Commandes de Base </h2>

**1. Quels sont les 5 derniers paquets installés sur votre machine**
  dpkg -l | tail -5
  
  
 **2.  Utiliser dpkg et apt pour compter le nombre de paquets installés (ne pas hésiter à consulter le manuel !).
Comment explique-t-on la (petite) différence de comptage ?**

dpkg -l | wc -l
505

apt list --installed | wc -l 
501

Ils ne retournent pas le même nombre de paquets car il y a sur la première lignes des mots qui ne sont pas des paquets.

**3. Combien de paquets sont disponibles en téléchargement ?**

apt list | wc -l
62510


**4.Créer un alias ”maj” qui met à jour le système**

La commande pour obtenir les mises à jour est apt-get update.
Pour l'alias il suffait de faire alias maj='apt-get update' , pour executer notre commande nous devrons seuelement taper maj.


**5. A quoi sert le paquet fortunes ? Installez-le.**

Le paquet fortune permet d'afficher dans le terminal des citations proverbes ...
Pour l'installer il faut taper la commande : sudo apt install fortunes.
Pour l'executer il faut taper fortune.

<h2> Exercice 3. </h2>

**6.Quels paquets proposent de jouer au sudoku ?**

apt search soduku. Nous n'allons pas lister les paquets mais il y en a 35.

**7. Lister les derniers paquets installés explicitement avec la commande apt install**

grep "install" var/log/apt/history.log

<h2>Exercice 2</h2>
la commande :

   ```
  wich ls | xargs dpkg -S
  ```
le Script :
  ```
  #!/bin/bash

  which "$1" | xargs dpkg -S | cut -d':' -f1
  ```

<h2>Exercice 3</h2>

**Ecrire une commande qui affiche ”INSTALLÉ” ou ”NON INSTALLÉ” selon le nom et le statut du package
spécifié dans cette commande.**
```
#!/bin/bash

retour=$(apt list --installed | grep "$1" | wc -l)

if [ $retour -eq 1 ]; then
        echo INSTALLE
else
        echo NON INSTALLE 
fi
```

<h2>Exercice 4</h2>
option -L permet de lister les fichiers installés sur le système.
dpkg -L coreutils
[ permet de tester une expression ou une option

<h2>Exercice 5</h2>

Il faut tout d'abord installer aptitude. Aptitude est un gestionnaire de paquet graphique.
Sudo apt install aptitude
Il faut lancer aptitude : sudo aptitude
Nous avons notre interface graphique. Il faut faire CTRL+T pour accéder au menu en haut de l'écran.
Nous nous rendons dans upgradable package et nous allons dans le menu search pour rechercher emacs.
Une fois sur le paquet, il suffit d'appuyer sur la touche U pour effectuer l'upgrade.
Pour quitter nous allons dans le menu action et quit.
Pour conclure, depuis ce gestionnaire nous pouvons supprimer, installer et upgrader des paquets sur notre système.



<h2>Exercice 6</h2>

```
cd /etc/apt/sources.list.d
ls
cat linuxuprising-ubuntu-java-bionic.list
```
Le fichier contient l'URL du serveur

<h2>Exercice 7</h2>

<h2>Exercice 8</h2>
```
sudo apt install autoreconf
sudo apt install gettext
sudo apt install autopoint
autoreconf -o
sudo apt install checkinstall
sudo checkinstall
```
