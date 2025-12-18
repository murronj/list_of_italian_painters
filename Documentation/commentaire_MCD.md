# Documentation pour le Modèle Conceptuel
## Person
La classe "Person" s'intéresse aux individus qui seront étudiés, c'est-à-dire les peintres du VIIe siècle, mais elle inclut notamment tout autre personne pertinente à nos recherches. 
### Propriétés
Pour la classe "Person", les propriétés suivantes seront inclues:
- leur nom
- leur date de naissance
- leur date de décès
- leur genre 
L'inclusion de la propriété "genre" est nécessaire car l'une des questions de recherche s'intéresse à la prévalence des femmes peintre au XVIIe siècle et si elles partagent des caractéristiques ou des relations particulières.

## Training
La classe "Training" désigne la formation qu'a effectué l'individu. On la prend en compte car nous souhaitons tout d'abord savoir si tous les peintres traités dans ce projet possèdent une formation artistique, et s'ils ont potentiellement effectués d'autres formations.
### Propriétés
- le nom de la formation (ex. peintre, verrier, marchand, etc.)
- la définition (ex. formation artisitque = quel atelier)

## Occupation
La classe "Occupation" s'intéresse aux métiers exercés par les individus étudiés. Il s'agit de voir si les peintres étudiés exercent une autre profession ou non. Cette classe peut être aussi utile afin de savoir quel métier est exercé par les autres individus qui seront mentionnés.
### Propriétés
- le nom de la profession
- la définition

## Organisation
Cette classe désigne une groupe organisé de personne partageant des intérêts similaires. La nature de l'organisation peut varier: littéraire, artistique, politique, philosophique, etc.
### Propriétés
- le nom
- la définition (la nature)

## Geographical place
Cette classe englobe tous les lieux importants. Il peut désigner un lieu de: naissance, de décès, de résidence, le siège d'une organisation, conservation d'une oeuvre, etc. Ainsi, cette classe entretient plusieurs relations avec les autres classes mentionnées. Concernant nos questions de recherche, le lieu est important car nous espérons trouver un impact entre le lieu de résidence d'un peintre et les relations qu'il entretient (ou non) avec d'autres individus ayant vécu au même endroit, ou alors une organisation qui siège dans la même ville, etc.
### Propriétés
- le nom
- le type (village, ville, région, pays, etc.)
- la latitude
- la longitude

## Type
Cette classe se réfère au type artistique d'une oeuvre, à savoir: portrait, nature morte, scène historique, marine, paysage, etc. Attention à ne pas confondre avec la classe "Movement" qui désigne le courant artistique auquel appartient l'artiste.
Il est possible que cette classe soit transformée en propriété de la classe "Artwork". 
### Propriétés
- le nom (ex. marine, paysage, etc.)
- la définition (une courte description du type)

## Movement
Cette classe désigne le courant artistique auquel appartient l'artiste. Elle est nécessaire car nous désirons savoir si les peintres d'un même courant entretiennent des relations plus étroites ou s'ils partagent plus de caractéristique que deux peintres n'appartenant pas au même courant.
### Propriétés
- le nom (ex. baroque)
- la définition (une brève description du courant et ses caractéristiques)
- la période de pertinance (période à laquelle on trouve ce courant)

## Religion
Nous souhaitons prendre en compte l'affiliation religieuse des individus mentionnés. Cela paraît important surtout lorsque l'on prend en compte le contexte historique et politique, particulièrement la Guerre de Trent Ans ainsi que les conséquences de la Réforme protestante et des Guerres de Religion au XVIe siècle. Cette classe est utile car nous souhaitons déterminer si une division existe entre les peintres de différentes religions.
### Propriétés
- le nom (ex. catholicisme, protestantisme)
- la définition 

## Social Status
Le statut social semble important lorsque l'on considère que la profession de peintre n'était pas forcément accessible à tous. Ainsi, nous espérons découvrir certains parrallèles ou certaines divergences selon le statut social des peintres étudiés.
Attention: au fil des recherches, le vocabulaire sera peut-être modifié au fil des recherches afin d'éviter l'usage d'une nomenclature anachronique.
### Propriétés
- le nom (ex. noblesse, aristocratie, bourgeoisie, etc.)
- la définition (brève explication)

## Relationship
C'est une classe (sémantique) qui relie ici une personne à une autre personne. La nature de la relation peut varier.
### Propriétés
- le nom (ex. amitié, mécène, commanditaire, père, mère, maître, etc.)
- la définition (pour toute autre informations)

## Relations
Les relations qu'entretient la class "Person" avec d'autres classes sont les suivantes:
- relation person-lieu : ceci pouvant être un lieu de naissance, de résidence, de décès, ou simplement un lieu important dans la vie de l'individu pour une autre raison.
- relation person-organisation : si l'individu fait partie d'une organisation en particulier
- relation person-occupation : comme nous nous intéressons aux peintres, le métier sera généralement le même pour tout individu, mais il est inclus dans le cas où l'individu pratique plusieurs métier.
- relation person-social-status : l'inclusion de la cette classe sur le statut social est nécessaire car nous nous intéressons à la prévalence du métier de peintre selon la classe sociale de l'artiste.
- relation person-training : nous souhaitons voir si tous les peintres possèdent une formation artistique ou si d'autres formations ont aussi été effectuée.
- relation person-artwork : il s'agit ici de lier les peintres et leurs oeuvres. Selon le style et le mouvement auquel appartiennent les oeuvres et leur peintre, nous espérons pouvoir faire d'éventuel parallèle entre les individus.
- relation person-person : afin de mettre en lumière les éventuel relation entre artiste et voir s'ils partagent d'autres caractéristiques.
- relation person-religion : permet de voir si les peintres ayant les mêmes croyances religieuses partagent plus de caractéristiques que les peintres qui ne partagent pas les mêmes croyances. Potentiellement intéressant étant donné le contexte historique (Guerre de Trente Ans) et si l'on prend aussi en compte les emplacements géographiques.
- relation person-movement : afin de définir une affiliation à un courant artistique.