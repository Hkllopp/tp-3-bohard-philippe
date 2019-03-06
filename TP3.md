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


**5.A quoi sert le paquet fortunes ? Installez-le.**

<h2> Exercice 3. </h2>

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
