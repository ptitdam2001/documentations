# Adaptive et Responsive design

## Définitions

Le **Responsive Webdesign** est une partie d’un plus grand concept que l’on appelle **Adaptive Design** (Design Adaptatif ou Design Adaptif). Lorsque l’on parle de Responsive Webdesign, on fait uniquement référence à la mise en page (Ethan Marcotte – NDT auteur du livre Responsive Webdesign – des grilles fluides, des images flexibles et des media-queries).

Le **Design Adaptatif** quant à lui va bien au delà d’une simple fluidité dans la mise en page. En pratique ce terme signifie la même chose qu’Amélioration Progressive, à savoir pour faire simple, essayer d’apporter la meilleur expérience utilisateur à la plus large audience possible (NDT par audience il faut entendre différents appareils et situations de navigation). **De plus le terme “Adaptive Design” ne devrait pas être confondu avec le terme “mise en page adaptative” (Adaptive layout) qui n’a strictement rien à voir**.
 
Enfin le terme **Adaptive layout**, ou Mise en page Adaptative désigne un type de mise en page obtenu en *combinant plusieurs largeurs fixes*. 

![adaptivetrad1Ataptative Responsive](http://www.inpixelitrust.fr/blog/wp-content/uploads/2013/06/adaptivetrad1.jpg)


En conclusion, le Responsive Webdesign est une partie du Design Adaptatif. Responsive Webdesign = uniquement les mises en page fluide, alors que Design Adaptatif = mise en page fluide + amélioration progressive.

### Liens / Ressources :
- [Responsive Design. I don’t think that word means what you think it means](http://www.zeldman.com/2011/07/06/responsive-design-i-dont-think-that-word-means-what-you-think-it-means/)
- [On Adaptive vs. Responsive Web Design](http://blog.easy-designs.net/archives/2011/11/16/on-adaptive-vs-responsive-web-design/)
- [Responsive & Adaptive Web Design](http://www.lullabot.com/articles/responsive-adaptive-web-design)
- [Brad Frost on Google+](https://plus.google.com/103751101313992876152/posts/ezi7gr6T1kR) 



## Adaptive design vs Responsive design

![Responsive design](https://blog.atolcd.com/wp-content/uploads/sites/2/2014/08/responsive-300x268.jpg)

Adaptive design, responsive design mais aussi amélioration progressive, mise en page adaptative, grilles fluides…autant de termes que l’on trouve maintenant partout sur Internet mais souvent utilisés à tort car au final, quelle est la différence entre ces deux notions ?

La création d’interfaces s’adaptant aux différents terminaux ( tablettes, smartphones, phabletes (tiré du mot phablet en anglais), écrans d’ordinateurs,…) est devenu un incontournable, plus question de développer des interfaces spécifiques à chaque taille d’écran pour des questions évidentes de coûts de conception et de maintenance. La manière de « designer » pour le Web a donc évoluée avec pour but principal, l’amélioration de l’expérience utilisateur c’est à dire faciliter la lecture, rendre simple et intuitive la navigation, s’assurer que la présentation des informations sera toujours propre, agréable quel que soit le terminal.

### Adaptive et responsive, une confusion répandue
Le terme général décrivant l’ensemble des méthodes permettant d’adapter une interface au terminal utilisé est Adaptive Design ou Design adaptatif. La notion de Responsive Design ou plus précisément Responsive Web Design  fait partie du Design adaptatif et regroupe deux types de mise en page :

- la mise en page responsive (en anglais responsive layout)
- la mise en page adaptative  (en anglais adaptive layout)

C’est là que la confusion se crée car le responsive design, faisant partie de la grande famille du design adaptatif regroupe lui même les notions de responsive et d’adaptative design à ceci près, et la nuance est importante, qu’on ne parlera dans ce cas que de la mise en page responsive ou adaptative (ou layout en anglais).

### Notions de grilles fluides, fixes et media-queries
La conception des pages adaptative s’articule autour de deux axes principaux :

- les grilles fluides et fixes
- les media-queries

Il faut donc imaginer une page Web comme une succession d’éléments posée sur une grille comme un architecte poserait des tracés sur du papier millimétré.

**La grille fixe** permet de séparer la page en x colonnes dont la largeur est fixe. Au fur et à mesure que la largeur d’affichage diminue, les éléments placés sur les colonnes vont se placer les uns en dessous des autres.

**La grille fluide** assure aussi une séparation de la page en colonnes mais ces dernières ont une largeur établie en pourcentage. Avec ce type de grilles, non seulement les éléments de contenus vont pouvoir se placer les uns en dessous des autres au fur et à mesure de la diminution de la largeur, mais aussi s’adapter en largeur car ils sont positionnés sur des colonnes dont la largeur est exprimée en pourcentage.

Malgré tout, l’utilisation des grilles ne pourrait pas fonctionner correctement. L’utilisation d’une grille fluide permet d’adapter à elle seule la largeur de la page mais, sur les petits écrans, les éléments se retrouvent vite étriqués et donc peu lisibles. Ce sont les media-queries, appelés aussi points de bascule ou encore points de rupture, qui permettent d’indiquer au navigateur quand un élément doit changer de place voire disparaître.

### Au final, quelle différence entre mise en page adaptive et responsive ?

La mise en page adaptive utilise plutôt des grilles fixes et s’adapte par « à coup », c’est à dire qu’à chaque point de rupture défini dans un media-querie, l’interface change d’organisation. Visuellement, en diminuant la taille de la fenêtre de son navigateur, tant que l’on a pas passé un point de rupture, rien ne change.

La mise en page responsive, quant à elle, assure une adaptation permanente en plus des points de rupture. Visuellement, quand on diminue la taille de la fenêtre du navigateur, la largeur des blocs de contenus diminue proportionnellement de façon fluide avec par moment des changements dans l’organisation de la page quand on passe un point de rupture.

### Choix entre adaptive et responsive ?

De prime abord, on pourrait penser que le responsive est un meilleur choix, l’espace complet de la page est exploité, les blocs s’adaptent en permanence sans à coup quelle que soit la taille de l’écran. Mais ce n’est pas si simple, car une interface entièrement fluide et responsive nécessite souvent un design très épuré pas toujours souhaité par le client et ne permet pas de préserver la taille des blocs quand c’est voulu. **Le bon compromis est donc souvent une mise en page adaptive combinant des grilles fluides et fixes**.