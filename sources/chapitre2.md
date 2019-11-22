# Chapitre 2: Dynamique des solides
[Diapositives](https://moodle.polymtl.ca/pluginfile.php/38725/mod_folder/content/0/Diapositives/Chapitre02.pdf?forcedownload=1)

## Sommaire
2. Chapitre 2
   1. Objets ponctuels et étendus
      1. Objets ponctuels
      2. Objets étendus
         1. Déplacement sans rotation
         2. Déplacement avec rotation
   2. Matrices de rotation
      1. Axes originaux
      2. Angles d'euler
      3. Évaluation directe 

## 2.1 Objets ponctuels et étendus
### Objets ponctuels
caractérisé par:
- sa masse $m_p$
- sa charge électrique $e_p$
- sa position $\vec{r}(t)$
$$
\vec{r}(t)= \begin{pmatrix}
            x(t) \\
            y(t) \\
            z(t) \\
            \end{pmatrix}
$$
- sa vitesse
$$
\vec{r}(t)= \begin{pmatrix}
            v_x(t) \\
            v_y(t) \\
            v_z(t) \\
            \end{pmatrix}
$$
- son accélération
$$
\vec{r}(t)= \begin{pmatrix}
            a_x(t) \\
            a_y(t) \\
            a_z(t) \\
            \end{pmatrix}
$$

### Objets Étendus
$$
V= \int_{V(t)}{d^3}r=\int_{V(t)} dxdydz
$$
$$
m = \int_{V(t)} \rho(\vec{r}) d^3r=\int_{V(t)} \rho(x,y,z) dxdydz
$$

comment décrire $v(t)$:

$\vec{r_j}$: position occupée par la particule $j$ à $t$

$\vec{r_i}$: position occupée par la particule $i$ à $t$

La distance qui les sépare est :
$$
d_{ji} = |\vec{r_j}(t) - \vec{r_i}(t)| = \sqrt {(x_j(t) - x_i(t)^2 + (y_j(t) - y_i(t)^2 + (z_j(t) - z_i(t)^2}
$$

Est-ce que $d_{ji}$ varie dans le temps:

**Mouvement de translation:**

Pour que l'objet ne se déforme pas, $d_{ji}$ n'est pas une fonction du temps => $d_{ji}$ constante

Est-ce que $v_j(t)= v_i(t)$ :

Oui, leur vitesse relative est nulle car leur distance est constante.

Si on applique une force constante sur un objet, elle est ressentie de la même manière par toutes les particules:
$$
\sum_k \vec{F_{j_k}} = \sum_k \vec{F_{i_k}} \newline
m\vec{a_j} = m\vec{a_i}
$$
Ce qui implique:
$$
\vec{r_j}(t) = \vec{r_i}(t) + \vec{r_{ji}}(t_0) \newline
\vec{v_j}(t) = \vec{v_i}(t) 
    $$

**Mouvement avec rotation:**

$$
\vec{v_j}(t) \not = \vec{v_i}(t) 
$$

Mais $\vec{v_{jy}}(t)$ doit avoir une commposant nulle suivant $\vec{r_{jy}}(t)$ pour que l'objet de se déforme pas.

Si le solide est en rotation, alors toutes les particules tourner autour du même point $\vec{r_c}$ avec la même vitesse angulaire $\vec\omega_c$
$$
\vec{\omega_c} = \frac{d\vec{\Omega}_i(t)}{dt}
$$

La position angulaire de i par rapport à j est indépendante du temps
$$
\vec{\Omega_j}(t) - \vec{\Omega_i}(t) = \vec{\Omega_j}(t_0) - \vec{\Omega_i}(t_0) = \Delta  \vec{\Omega_{ji}}
$$
Donc suivre la position angulaire d'une seule particule est suffisant pour déterminer la position angulaire des autres paticules:

Le centre de masse (CM) tourne sur lui même, sa position $\vec{r_c}$ et sa vitesse $\vec{v_c}$ sont independand de $\vec\omega_c$

On peut conclure que:
$$
\vec{r_i}(t) = \vec{r_c}(t) + \vec{r_{c,i}}(t) \newline 
\vec{v_i}(t) = \vec{v_c}(t) + \vec{v_{c,i}}(t) \newline
\vec{r_{c,i}}(t) = R(t)\vec{r_{c,i}}(t) \newline
\vec{v_{c,i}}(t) = \vec{\omega_c}(t) \wedge \vec{r_{c,i}}(t) \newline
$$

R(t) étant une matrice décrivant l'impact de cangement de la position angulaire sur un point arbitraire du solide

## 2.2 Matrices de rotation

Si un vecteur $\vec v_1$ subit une rotation pour la ramener dans un autre état 
$$
\vec v_2 = R^{2<-1} \vec v_1
\vec v_1 = {(R^{2<-1})}^{-1} \vec v_2
$$

**Rotation directe autour des axes originaux:**
On fait une rotation d'un angle $\theta_x$ autour le l'axe $x$, $\theta_y$ autour le l'axe $y$, $\theta_z$ autour le l'axe $z$,

La matrice de rotaion du systeme 1->2:
$$
R^{2<-1} = R_z(\theta_z)R_y(\theta_y)R_x(\theta_x) \\
R_x(\theta_x) = \begin{pmatrix}
            1 & 0 & 0 \\
            0 & cos(\theta_x) & -sin(\theta_x) \\
            0 & sin(\theta_x) & cos(\theta_x) \\
            \end{pmatrix}
\\
R_x(\theta_x) = \begin{pmatrix}
            cos(\theta_y) & 0 & sin(\theta_y) \\
            0 & 1 & 0 \\
            -sin(\theta_y) & 0 & cos(\theta_y) \\
            \end{pmatrix} 
\\
R_x(\theta_x) = \begin{pmatrix}
            1 & 0 & 0 \\
            0 & cos(\theta_x) & -sin(\theta_x) \\
            0 & sin(\theta_x) & cos(\theta_x) \\
            \end{pmatrix}
$$
note:
$$
R^{1<-2} = R_x(-\theta_x)R_y(-\theta_y)R_z(-\theta_z)
$$
note:
$$
R_y(-\theta_y) =
$$

**Rotation autour d'un axe quelconque**
Soit l'ae decrit par le vecteur unitaire $\hat u$ tel que $\theta_{\hat u} = \Delta \vec \Omega_i(t)$

**Angles d'Euler**
On definit les angles d'Euler en faisant trois rotations successives:
- angle $\psi: (x,y,z) -> (u,v,z)$
- angle $\theta: (u,v,z) -> (u,w,z)$
- angle $\psi: (u,w,z) -> (x,y,z)$

## 2.3 Quaternions
Quaternion:
$$
H = \{(a,b,c,d) \epsilon R^4 | (a',b',c',d') \star(a,b,c,d) \not= (a,b,c,d) \star(a',b',c',d')\}
$$

tranformons $\vec v = (v_x, v_y, v_z)^T$ en quaternion.

=> $\vec{\vec v} = (0, v_x, v_y, v_z)^T$

**Operations sur les quaternions**
$$
\vec{\vec q} + \vec{\vec q} =  
$$
Produit de hamilton:

important: non commutatif ni associatif

Conjugaision:
$$
(\vec{\vec q})^* = (q_0, -q_x, -q_y, -q_z)^T \\
= ((q_0, -\vec q^T)^T)
$$
Inversion:
$$
(\vec{\vec q})^{-1} = \frac{(\vec{\vec q})^* }{||\vec{\vec q}||^2}
$$

**Qauternions de rotation:**

il est possible d'utiliser les quaternions pour former les matrices de rotation

Def quaternion unitaire: $\vec{\vec r} = (cos(\frac{\theta}{2}), sin(\frac{\theta}{2})\hat{u}^T)^T$

$||\vec{\vec r}|| = \sqrt{cos^2(\theta/2)+sin^2(\theta/2)\hat{u}^2} = 1$

on peut utiliser ce quaternion r pour effectuer une rotation d'un angle $\theta$ transformant $\vec{\vec q} -> \vec{\vec q}'$
$$
\vec{\vec q}' = (0, \vec v'^T)^T = \vec{\vec r}(0, \vec v^T)^T\vec{\vec r}^*
$$
Donc:
$$
\vec{\vec q}'= \vec{\vec r}\vec{\vec q}\vec{\vec r}
$$
Exemple: on fait une rotation d'un angle $\theta=\frac{\pi}{2}$ de $\vec v = (1, 1, 1)^T$ autour de $\hat u = \hat z$
$$
\vec{\vec q} = \begin{pmatrix}
            1 \\
            1 \\
            1 \\
            \end{pmatrix} \\
\vec{\vec r}
$$

### Mouvement avec rotation 
$$
\vec r_i(t) = \vec r_c(t) + R(t) \vec r_{c,i}(t_0) \\
\vec v_i(t) = \vec v_c(t) + \vec \omega_c(t) \wedge (R(t) \vec r_{c,i}(t_0))
$$

## 2.4 Equations de la dynamique:
### 2.4.1 Mouvement de translation

**Lois de Newton:**
1. $\forall \vec{F_{ext}} = 0$ => $\vec a = 0$ ; $\vec v$ constante
2. $\forall \vec{F_{ext}} \not = 0$ => $\vec a \alpha F$

**Exemple fusée:**

la masse ejectée de la fisée a une vitesse différente de celle de la fusée, sinon elle restrait attachée. À ce momment lè, il faut augmenter la 3ieme loi de Newton stipulant que pour la fa foce exercé des moteurs, il y a une force égale mais de sens contraire qui prendra naissance.