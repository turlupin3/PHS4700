# Chapitre 1: Introduction
[Diapositives](https://moodle.polymtl.ca/pluginfile.php/38725/mod_folder/content/0/Diapositives/Chapitre01.pdf?forcedownload=1)
## Physique
### Branches de la physique:
- mécanique classique (Newtonienne)
- mécanique quantique
  - La matière et l'énergie se fondent sur une nouvelle définition
  - dualité onde/particule
  - principe d'incertitue de heiseinberg
- relativité
  - Le temps et l'espace se fondent sur une nouvelle définition

### Moteur de simulation physique: 
Environement numérique représentant une scene dynamique en reproduissant aussi fidèlement que possibve les effets d'ombre et les effets sonnores

### Contraintes:
-   Réponse/Rapidité du moteur
-   Utilisation de mémoire et de stockage
-   Précision de la réponse

Il existe deux méthodologie opposée: Déterministe/Monté-Carlo

### Étapes pour la conception d'une application
1. Identifier les phénomènes physique
2. Traduire en équations
3. Choisir les méthodes numériques en respectant les contraintes
4. Programmer et valider les méthodes

## Applications multimédias
### Exemples d'application multimédia
1. **Billard (Dynamique)**

   Hypothèses:
   - Surface uniformément illuminée.
   - Effet d'ombre et bruits négligeable
   - Mouvements restent en 2D

   1. Phénomènes physiques
      1. Mouvement de la queue jusqu'à collisions avec la boule blanche

      2. Traitement de la collision
         - Vitesse angulaire
         - Vitesse linéaire

      3. Trajectoire de la boule blanche (4 sous-cas)
         1. Collision avec un côté
         2. Collision avec une boule
         3. entre dans une poche
         4. S'arrête sans collisions
               
           Si 3.3 ou 3.4 on reprend la simulation.
      
      4. Si 3.1 on calcule les nouvelles vitesses de la boule blanche

      5. Si on calcule les nouvelles vitesses des deux boules

      6. Tracer la trajectoire de toutes les boules en mouvement jusqu'à ce qu'une des boules entre en collision avec un côté (aller à 7) ou une autre boule (aller à 8), entre dans une poche (arret de la simulation pour cette boule) ou s'arrête (arret de la simulation pour cette boule). Si toutes les boules sont au repos ou dans une poche, On retourne à 1

      7. Déterminer les nouvelles vitesses initiales linéaire et angulaire de la boule ayant subi la collision et retourner à 6
      8.  Déterminer les nouvelles vitesses initiales linéaire et angulaire des boules impliquées retourner à 6

   2. Équation de la cinétique pour toutes étapes
   3. Acquisition des données (principales caractéristiques du jeu) 
   4. Méthode de résolution numérique
   5. Construire l'algorithme
   6. Validation des résultats
   7. Construire l'interface graphique

2. Images de synthèse (mécanique des fluides, physique ondulatoire, etc...)
- Objet
- Lumière
- Observateur

3. Environnements sonore

Son: Série de vibrations mécanique d'un fluide déformable

## Modélisation des solides
Il s'agit d'un solide si pour toute force externe, la densité reste constante. Un solide possède un volume et une masse.
$$V=\int_Vd^3r$$
$$m=\int_v\rho(\vec{r})d^3r$$

## Modélisation de la lumière
La lumière est constituée de particules de masse nulle appelées
photons. Ces particules interagissent peu entre elles par
collisions directes. Les photons véhiculent aussi une
combinaison de champs électriques et magnétiques qui sont
couplés sous la forme d’une onde électromagnétique

## Modélisation des fluides
Les forces interatomiques sont beaucoup plus faibles que dans les solides. Em l'absence de forces externes, les liquides maintiennent leur forme et occupe un volume $V$. L'application d'une force peut agir sur la densité. On utilise la notion de champ $\rho(\vec{r}, t)$, soit la distribution en temps et en espace de la matière.

$V=\int_{V_0}{d^3\vec{r}(t_0)} = \int_{V_f}{d^3\vec{r}(t_f)}$

$m=\int_{V_0}{\rho(\vec{r}, t_0)d^3\vec{r}(t_0)} = \int_{V_f}{\rho(\vec{r}, t_f)d^3\vec{r}(t_f)}$

### Liquides
Si on veut étudier l'ensemble du millieu (eau et surface), on utilisera la mécanique des fluides. Si on veut étudier le comportement de la surface, on utilisera la physique ondulatoire

Les équations de Navier-Stokes permmettent de simuler les fluides

### Gaz
Deux méthodes de traitement:
- traitement déterministe
  - mécanique des fluides couplée de la thermodinamique
  - puisqu'ils tranportent les ondes de compressions on utiliser l'accoustique
- Traitement stochastique/monte-carlo
  
