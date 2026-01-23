# Documentation pour le Modèle Conceptuel

## Person
La classe (persistent item) "Person" s'intéresse aux individus qui seront étudiés, c'est-à-dire les peintres italiens, mais elle désigne plus globalement tout êtres humains. 

### Propriétés
Pour la classe "Person", les propriétés suivantes seront inclues:
- leur nom
- leur date de naissance
- leur date de décès
- leur genre 
L'inclusion de la propriété "genre" est nécessaire car l'une des questions de recherche s'intéresse à la prévalence des femmes peintre et si elles partagent des caractéristiques ou des relations particulières.

### Relations
La table "Person" entretient des relations avec les tables: "Training", "Relationship", "Occupation", "Geographical Place", "Membership", "Social Status" et "Movement".

Les relations qu'entretient la class "Person" avec d'autres classes sont les suivantes:
- relation person-geographical place : ceci sera généralement un lieu de naissance ou de décès.
- relation person-organisation : si l'individu fait partie d'une organisation  en particulier comme une académie ou un institut par exemple. Cette relation se fait par la table "Membership" afin de montrer une appartenance.
- relation person-occupation : comme nous nous intéressons aux peintres, le métier sera généralement le même pour tout individu, mais il est inclus dans le cas où l'individu pratique plusieurs métiers. Par exemple, certains sont aussi écrivains.
- relation person-social-status : l'inclusion de la cette classe sur le statut social est nécessaire car nous nous intéressons à la prévalence du métier de peintre selon la classe sociale de l'artiste.
- relation person-training : nous souhaitons voir si tous les peintres possèdent une formation artistique ou si d'autres formations ont aussi été effectuée.
- relation person-artwork : il s'agit ici de lier les peintres et leurs oeuvres. Selon le style et le mouvement auquel appartiennent les oeuvres et leur peintre, nous espérons pouvoir faire d'éventuel parallèle entre les individus.
- relation person-realtionship : afin de mettre en lumière les éventuel relation entre artiste et voir s'ils partagent d'autres caractéristiques.
- relation person-movement : afin de définir une affiliation à un courant artistique. Cela est particulièrement pertinent dans le cadre de notre sujet car la liste employée concerne tous les peintres italiens, peu importe la période.

## Training
La classe "Training" désigne la formation qu'a effectué l'individu. On la prend en compte car nous souhaitons tout d'abord savoir si les peintres traités dans ce projet possèdent une formation artistique, et s'ils ont potentiellement effectués d'autres formations.

### Propriétés
- le nom de la formation (ex. peintre, verrier, marchand, etc.)
- la définition (p. ex. formation artisitque = quel atelier)

### Relations
La table "Training" fait lien avec la table "Person" afin de montrer la formation qu'a effectué la personne. 

## Occupation
La classe "Occupation" s'intéresse aux métiers exercés par les individus étudiés. Il s'agit de voir si les peintres étudiés exercent une autre profession ou non. Comme nous l'avons déjà mentionné, certains peintres étaient également écrivains.

### Propriétés
- le nom de la profession
- la définition

### Relations
La table "Occupation" a une relation avec la table "Person" comme il s'agit d'individu exerçant un/des métier(s).

## Organisation
Cette classe désigne une groupe organisé de personne partageant des intérêts similaires. La nature de l'organisation peut varier: il peut s'agir d'académies, d'institut, d'un groupe politique/philosophique/littéraire/artistique, etc. pour autant que cette affiliation soit formelle.

### Propriétés
- le nom
- la définition (la nature)

### Relations
La table "Organisation" possède une relation avec "Geographical Place" car les organisations sont généralement basée dans une ville précise. De plus, elle est liée à la table relationnelle "Membership" qui fait le lien avec la "Person" et signifie une appartenance.

## Membership
La table "Membership" est une table relationnelle qui désigne l'appartenance formelle.

### Propriétés
- fk_person
- fk_organisation
- notes

### Relations
Comme son nom (table relationnelle) l'indique, "Membership" fait office de lien tangible entre les tables "Person" et "Organisation". 

## Geographical place
Cette classe englobe tous les lieux importants. Il peut désigner un lieu de: naissance, de décès, le siège d'une organisation, conservation d'une oeuvre, etc. 

### Propriétés
- le nom
- la définition (village, ville, région, pays, etc.)

### Relations
Cette table entretient plusieurs relations avec les autres classes mentionnées ("Person", "Organisation" et "Artwork"). Concernant nos questions de recherche, le lieu est important car nous espérons trouver un impact entre le lieu de résidence d'un peintre et les relations qu'il entretient (ou non) avec d'autres individus ayant vécu au même endroit, ou alors une organisation qui siège dans la même ville, etc.

## Artwork
Cette table désigne les oeuvres des peintres étudiés. 

### Propriétés
- le nom (à savoir le titre)
- la date 

### Relations
Cette table est liée à "Person" et désigne donc le créateur de l'oeuvre, à "Geographical Place" désignant son lieu de conservation ce qui est pertinent car peut donner des indications sur la circulation d'oeuvres italiennes, et à "ArtworkType" pour en définir le type.

## ArtworkType
Cette classe se réfère au type artistique d'une oeuvre, à savoir: portrait, nature morte, scène historique, marine, paysage, etc. Attention à ne pas confondre avec la classe "Movement" qui désigne le courant artistique auquel appartient l'artiste. Nous souhaitons connaître le type car nous pourrons ainsi potentiellement voir à combien de types différents l'artiste s'est adonné. 

### Propriétés
- le nom (ex. marine, paysage, etc.)
- la définition (une courte description du type)

### Relations
Cette table a un lien uniquement avec "Artwork" car il s'agit d'un lien persistant avec une oeuvre.

## Movement
Cette classe désigne le courant artistique auquel appartient l'artiste. Elle est nécessaire car nous désirons savoir si les peintres d'un même courant entretiennent des relations plus étroites ou s'ils partagent plus de caractéristique que deux peintres n'appartenant pas au même courant. De plus, nous espérons remarquer une évolution selon les périodes historiques.

### Propriétés
- le nom (ex. baroque)
- la définition (une brève description du courant et ses caractéristiques)

### Relations
Cette table est liée à la table "Person" afin d'identifier à quel courant artisitque le peintre appartenait. Nous l'avons également liée à la table "Period" afin de spécifier la période à laquelle le courant artistique appartient.

## Period
Comme la liste étudiée concerne tous les peintres italiens, toutes périodes confondues, nous avons juger nécessaire d'ajouter cette table afin d'avoir une vue chronologique. Nous espérons voir émerger une évolution et les éventuels chevauchements des courants artistique dans l'histoire de la peinture italienne.

### Propriétés
- le nom (p. ex. Quattrocento, Renaissance, Baroque, ec.)
- date de début
- date de fin
- la définition (une brève définition du courant et de ses caractéristiques)

### Relations
Au vue de nos intérêts, nous avons liée cette table à "Movement" afin d'établir une chronologie plus claire.

## Social Status
Le statut social semble important lorsque l'on considère que la profession de peintre n'a pas toujours été accessible à tous. Ainsi, nous espérons découvrir certains parrallèles ou certaines divergences selon le statut social des peintres étudiés. Comme nous étudions un large pan historique, il est nécessaire de normaliser la nomenclature afin d'éviter l'usage de termes anachroniques. Ainsi, nous proposons d'utiliser les termes suivants: milieu défavorisé (très peu de moyens financiers), milieu modeste (marchands, commerçants, classe moyenne), milieu privilégié (aristocratie, bourgeoisie, noblesse). Comme nous nous intéressons particulièrement au statut social dont sont issus les individus, nous ne prenons que le contexte de base/familial et écartons les fluctuations du statut durant la vie de l'individu (p. ex. un peintre issu d'un milieu défavorisé, mais qui meurt riche = nous prenons en compte le milieu défavorisé). Nous justifions cela par le fait que nos questions de recherche s'intéressent notamment à l'accessibilité à la profession selon le statut social initial de l'individu.

### Propriétés
- le nom (défavorisé, modeste, privilégié)
- la définition (brève explication)

### Relation
La table "Social Status" possède un lien avec la table "Person" afin de montrer une appartenance à un groupe spécifique.

## Relationship
C'est une classe (sémantique) qui relie ici une personne à une autre personne. La nature de la relation peut varier. Comme il s'agit de deux personnes différentes nous avons décidé d'inclure les clés: fk_person_source et fk_person_target.

### Propriétés
- le nom (ex. amitié, mécène, commanditaire, père, mère, maître, etc.)
- la définition (pour toutes autres informations)

### Relations
Cette table est reliée à "Person" car il s'agit d'une relation entre deux individus. Elle est notamment liée à la table "Type" qui vise à définir la nature de la relation.