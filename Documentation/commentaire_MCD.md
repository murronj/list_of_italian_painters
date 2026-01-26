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
La table "Person" entretient des relations avec les tables: "Training" par voie de "Studies", "Occupation" par voie de "Pursuit", "Geographical Place", "Organisation" par voie de "Membership", "Artwork", "Social Status", et "Movement" par voie de "Affiliation".

Les relations qu'entretient la class "Person" avec d'autres classes sont les suivantes:
- relation person-geographical place : ceci sera généralement un lieu de naissance ou de décès.
- relation person-organisation : si l'individu fait partie d'une organisation  en particulier comme une académie ou un institut par exemple. Cette relation se fait par la table "Membership" afin de montrer une appartenance.
- relation person-occupation : comme nous nous intéressons aux peintres, le métier sera généralement le même pour tout individu, mais il est inclus dans le cas où l'individu pratique plusieurs métiers. Par exemple, certains sont aussi écrivains. Cette relation se fait par la table "Pursuit" afin de montrer l'exercice de ce métier.
- relation person-social-status : l'inclusion de la cette classe sur le statut social à la naissance est nécessaire car nous nous intéressons à la prévalence du métier de peintre selon la classe sociale est issus l'artiste. 
- relation person-training : nous souhaitons voir si tous les peintres possèdent une formation artistique ou si d'autres formations ont aussi été effectuée. Cette relation se fait par la table "Studies" afin de montrer l'acquisition de cette/ces formations.
- relation person-artwork : il s'agit ici de lier les peintres et leurs oeuvres. Selon le style et le mouvement auquel appartiennent les oeuvres et leur peintre, nous espérons pouvoir faire d'éventuel parallèle entre les individus.
- relation person-movement : afin de définir une affiliation à un courant artistique. Cela est particulièrement pertinent dans le cadre de notre sujet car la liste employée concerne tous les peintres italiens, peu importe la période. Cette relation se fait au travers de la table "Affiliation" afin de montrer l'affiliation à un mouvement artistique, sachant qu'un seul artiste peut être relier à plusieurs mouvements.

## Training
La classe "Training" désigne la formation qu'a effectué l'individu. On la prend en compte car nous souhaitons tout d'abord savoir si les peintres traités dans ce projet possèdent une formation artistique, et s'ils ont potentiellement effectués d'autres formations.

### Propriétés
- le nom de la formation (ex. peintre, verrier, marchand, etc.)
- la date 

### Relations
La table "Training" fait lien avec la table "Studies" afin de montrer la relation avec "Person" et montrer la formation qu'a effectué la personne. 

## Occupation
La classe "Occupation" s'intéresse aux métiers exercés par les individus étudiés. Il s'agit de voir si les peintres étudiés exercent une autre profession ou non. Comme nous l'avons déjà mentionné, certains peintres étaient également écrivains.

### Propriétés
- le nom de la profession
- la définition

### Relations
La table "Occupation" a une relation avec la table "Person" au travers de "Pursuit" comme il s'agit d'individu exerçant un/des métier(s).

## Organisation
Cette classe désigne une groupe organisé de personne partageant des intérêts similaires. La nature de l'organisation peut varier: il peut s'agir d'académies, d'instituts, d'un groupe politique/philosophique/littéraire/artistique, etc. pour autant que cette affiliation soit formelle.

### Propriétés
- le nom
- la définition (institut, académie, etc.)
- start_date (la date de fondation)

### Relations
La table "Organisation" possède une relation avec "Geographical Place" car les organisations sont généralement basée dans une ville précise. De plus, elle est liée à la table relationnelle "Membership" qui fait le lien avec la "Person" et signifie une appartenance.

## Membership
La table "Membership" est une table relationnelle, un classe temporelle qui désigne l'appartenance formelle.

### Propriétés
- fk_person
- fk_organisation
- date_begin
- date_end

### Relations
Comme son nom (table relationnelle) l'indique, "Membership" fait office de lien tangible entre les tables "Person" et "Organisation". 

## Geographical place
Cette classe englobe tous les lieux importants. Il peut désigner un lieu de: naissance, de décès, le siège d'une organisation, conservation d'une oeuvre, etc. 

### Propriétés
- le nom
- le type (c'est-à-dire s'il s'agit d'un lieu de naissance (birth), de décès (death), de conservation (conservation), ou le siège d'une organisation (establishment))

### Relations
Cette table entretient plusieurs relations avec les autres classes mentionnées ("Person", "Organisation" et "Artwork"). Concernant nos questions de recherche, le lieu est important car nous espérons trouver un impact entre le lieu de résidence d'un peintre et les relations qu'il entretient (ou non) avec d'autres individus ayant vécu au même endroit, ou alors une organisation qui siège dans la même ville, etc.

## Artwork
Cette table désigne les oeuvres des peintres étudiés. 

### Propriétés
- le nom (à savoir le titre)
- la date 

### Relations
Cette table est liée à "Person" et désigne donc le créateur de l'oeuvre et à "Geographical Place" désignant son lieu de conservation ce qui est pertinent car peut donner des indications sur la circulation d'oeuvres italiennes.

## Movement
Cette classe désigne le courant artistique auquel appartient l'artiste. Elle est nécessaire car nous désirons savoir si les peintres d'un même courant entretiennent des relations plus étroites ou s'ils partagent plus de caractéristique que deux peintres n'appartenant pas au même courant. De plus, nous espérons remarquer une évolution selon les périodes historiques.

### Propriétés
- le nom (ex. baroque)
- la définition (une brève description du courant et ses caractéristiques)
- date_start
- date_end

### Relations
Cette table est liée à la table "Person" (par la table "Affiliation") afin d'identifier à quel courant artisitque le peintre appartenait. Nous l'avons également liée à la table "Period" afin de spécifier la période à laquelle le courant artistique appartient.

## Period
Comme la liste étudiée concerne tous les peintres italiens, toutes périodes confondues, nous avons juger nécessaire d'ajouter cette table afin d'avoir une vue chronologique. Nous espérons voir émerger une évolution et les éventuels chevauchements des courants artistique dans l'histoire de la peinture italienne.

### Propriétés
- le nom (p. ex. siècle)
- date de début
- date de fin
- la définition

### Relations
Au vue de nos intérêts, nous avons liée cette table à "Movement" afin d'établir une chronologie plus claire.

## Social Status
Le statut social semble important lorsque l'on considère que la profession de peintre n'a pas toujours été accessible à tous. Ainsi, nous espérons découvrir certains parrallèles ou certaines divergences selon le statut social des peintres étudiés. Comme nous étudions un large pan historique, il est nécessaire de normaliser la nomenclature afin d'éviter l'usage de termes anachroniques. Ainsi, nous proposons d'utiliser les termes suivants: milieu défavorisé (très peu de moyens financiers), milieu modeste (marchands, commerçants, classe moyenne), milieu privilégié (aristocratie, bourgeoisie, noblesse). Comme nous nous intéressons particulièrement au statut social dont sont issus les individus, nous ne prenons que le contexte de base/familial et écartons les fluctuations du statut durant la vie de l'individu (p. ex. un peintre issu d'un milieu défavorisé, mais qui meurt riche = nous prenons en compte le milieu défavorisé). Nous justifions cela par le fait que nos questions de recherche s'intéressent notamment à l'accessibilité à la profession selon le statut social initial de l'individu.

### Propriétés
- le nom (défavorisé, modeste, privilégié)
- la définition (brève explication)

### Relations
La table "Social Status" possède un lien avec la table "Person" afin de montrer une appartenance à un groupe spécifique.

## Affiliation
La table relationnelle "Affiliation" relie les tables "Person" et "Movement". Elle marque le lien d'appartenance entre une personne et un mouvement artistique. Il a été jugé nécessaire de la créer car un artiste peut appartenir à plusieurs mouvements et un mouvement contient plusieurs artistes.

### Propriétés
- fk_person
- fk_movement
- start_date
- end_date

### Relations
Il s'agit d'une table associative donc nous avons intégré les clés étrangères nécessaires, comme pour toutes les autres tables. "Affiliation" relie "Person" et "Movement".

## Pursuit
Il s'agit d'une table relationnelle/associative qui désigne l'exercice d'une métier. Il a été jugé nécessaire de l'inclure car une personne peut exercer plusieurs métiers et un métier peut être exercé par plusieurs personnes.

### Propriétés
- fk_person
- fk_occupation
- start_date
- end_date

### Relations
"Pursuit" fait le lien entre les tables "Person" et "Occupation", nous avons donc créer les clés étrangères nécessaires. Les classes relationnelles de ce type ("Membership", "Affiliation", "Pursuit", et "Studies") désigne un lien entre une personne et une entité (organisation, mouvement, métier, formation, etc.).

## Studies
La table "Studies" désigne l'acte d'acquérir une formation spécifique.

### Propriétés
- fk_person
- fk_training
- start_date
- end_date

### Relations
Cette classe relie les tables "Person" à "Training" en montrant l'acquisition de connaissances qui mène à une formation concrète. Il a été jugé nécessaire de créer cette table car une personne peut avoir plusieurs formations et une formation regroupe plusieurs personnes. Ainsi, nous montrons un lien entre une personne et une formation. 