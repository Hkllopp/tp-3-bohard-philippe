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

Ils ne retournent pas le même nombre de paquets car

