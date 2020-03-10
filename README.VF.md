# ENS_DREEM_CHALLENGE

1 Présentation du projet

1.1 ENS Data Challenge : Entreprise Dreem
L’ensemble des éléments relatifs à notre sujet a été mis à disposition par la plateforme de challenge de données Challengedata.ens. 
A l’instar de la plateforme Kaggle, cette plateforme fournit un accès facile à des datasets de Machine Learning supervisés, ceci à
des ﬁns éducatives. Les ensembles de données étant suﬃsamment petits pour pouvoir être étudiés sur des machines standards, tout en 
conservant des caractéristiques intéressantes sur données réelles.

Nous avons choisi de nous intéresser, pour ce projet, à un challenge proposé par l’entreprise Dreem, une startup spécialisée dans les
problèmes de sommeil. Leur produit, le bandeau Dreem, vise à améliorer la qualité du sommeil des individus, en stimulant certaines
parties du cerveau lors des diﬀérentes phases de sommeil. L’objet d’étude de notre projet s’eﬀectue sur des enregistrements de 
10 secondes, de signaux cérébraux caractéristiques des phases de sommeil profond appelées "oscillation lente". La mesure ainsi que 
l’enregistrement de ces ondes, symbolisant une forte activité cérébrale, est réalisée par le bandeau dreem sous forme 
d’EEG (électroencéphalogramme).

Notre objectif est,à partir de la base de données à notre disposition,de prédire si uneoscillation lente sera suivie d’une autre lors de
la seconde suivant la ﬁn l’enregistrement, en condition sham (ie : sans stimulation du bandeau). On se place ici en condition sham aﬁn de
pouvoir déterminer avec exactitude le moment exact où il est utile de stimuler, ce qui ne sera pas le cas si on prédit une oscillation 
lente dans la seconde qui va suivre.

1.2 Principes du parallélisme

Le parallélisme est une technique informatique visant à utiliser plusieurs processeurs pour traiter des opérations de manière 
simultanée:Le but est que la réalisation de toutes ces opérations s’exécute en réduisant le plus possible le temps de traitement. 
Cette technique s’écarte de la méthode traditionnelle dite "séquen
tielle". Les opérations sont traitées de manière successive et
le temps d’exécution demeure plus élevé qu’avec du parallélisme.
Le parallélisme peut s’appliquer en utilisant plusieurs processeurs. Le problème en question se retrouve subdivisé en plusieurs parties 
qui peuvent être résolues de manières concurrentes. Chaque partie se retrouve alors transformée en une série d’instructions étant
exécutées par les diﬀérents processeurs. Le parallélisme permet : - un gain de temps - un traitement de problèmes plus complexes, 
dont on aurait du mal à faire face avec une simple approche séquentielle (traitement de grande données) - de ne pas forcément
utiliser des ressources locales

Un classement des diﬀérentes machines a été proposé par Flynn en 1966 : 

- SISD : Il y a une seule unité de calcul qui a accès à une seule donnée à la fois. C’est un exemple de l’approche séquentielle 
et il n’y a aucune parallélisation. 

- MISD : Plusieurs processeurs traitent une même donnée mais appliquent des instructions multiples et diﬀérentes. 

- SIMD : Une même instruction s’opère simultanément, grâce à plusieurs unités de calcul, sur plusieurs données pour avoir des résultats
diﬀérents. -

- MIMD : Plusieurs machines où les processeurs possèdent leur propre mémoire et n’ayant pas accès à celle des autres. Les processeurs
sont cependant reliés sur le même réseau. Les diﬀérentes machines peuvent coïncider avec le parallélisme sauf la première. S’ajoute à ça le choix du Multiprocessing ou du Multithreading (même si empiriquement les deux sont complémentaires).
Le Multiprocessing consiste à l’ajout de plusieurs processus pour augmenter la vitesse de réponse et de calcul du système. La séparation des processeurs permet une gestion des ressources conjointe plus eﬃcace dans la mesure où un processus, une fois subdivisé, est moins sujet à engorger l’appareil sur lequel il eﬀectue une tâche (Notion de CPU limité). Il existe 2 souscatégories de Multiprocessing que sont : Le Multiprocessing symétrique et le multiprocessing asymétrique. Le Multiprocessing symétrique est le fait que les processus fonctionnent de manière libre et non contrainte dans le système. Le Multiprocessing Asymétrique modélise une relation de subordination entre les processeurs. Un processeur peut interdire à un autre de réaliser certaines opérations : Il y a donc une répartition des tâches. Le Multithreading consiste à la multiplication des « threads », tâche, pour un processus. Cette création de thread est plus eﬃcace qu’une création supplémentaire de processus qui épuise les ressources et qui est chronophage. Augmenter le nombre de tâches permet d’augmenter le niveau deréponsedusystèmedanslamesureoùunetâchedevientpluslente,leprocessuspeutcontinuer de fonctionner.
Ensuite vient le choix du modèle. Le modèle synchrone ou le modèle asynchrone. Dans le modèle synchrone il existe une dépendance entre les tâches, de ce fait il faut attendre la ﬁn de réalisation d’une tâche avant de passer à la suivante (First-In-First-Out). Au contraire, le modèle asynchrone permet de passer à une autre tâche même si la tâche eﬀectuéeprécédemmentresteencoursderéalisation.Chaquemachinepossèdesapropremémoire et agit de manière indépendante.

1.3 Application sur des algorithmes de Machine Learning 

Pour pouvoir eﬀectuer des prédictions sur ce challenge, nous ferons appel à diﬀérents algorithmes de Machine Learning. Nous nous plaçons ici dans une problématique de classiﬁcation, nos labels en sortie pouvant prendre les valeurs :
Labels = 0,1,2
0 = Pas d’oscillation dans la sec qui suit 
1 = Une oscillation faible dans la sec qui suit
2 = une oscillation forte dans la seonde qui suit

Les algorithmes utilisés pour des applications de Machine Learning peuvent être "lourds" et avoir une forte empreinte mémoire 
pour des systèmes informatiques "standard". Encore plus lorsque que l’on est confronté à des données de grande dimension, comme c’est le
cas ici.
Nos données d’entrainements sont de :
Xtrain = 261,634 (obervations) pour 1261 variables soit 261.634 x 1261 
Ytrain = 261,634 (observations) soit 261634 x 1

Les 11 premières variables permettent de caractériser chacun de ces enregistrements (stade de sommeil, amplitude de l’oscillation 
actuelle, durée de l’oscillation actuelle etc.) . 
Les 1250 colonnes suivantes correspondent quant à elles aux 10 sec d’enregistrement EEG pour chaque observation (1250 points soit 
125 colonnes/sec). Notre Xtrain avant traitement préalable à une empreintre mémoire (à l’importation) de 2.4 go (2,408.14 mo) 
et de 2.13 mo pour notre Ytrain.
En outre, même si ces algorithmes restent relativement simples à implémenter, la méthode que nous utiliserons ici pour résoudre notre
problématique se montrera très gourmande en temps. La cross validation ainsi que le split entre données d’entrainements et données de
validation (ou test) vont augmenter considérablement le temps d’éxecution de notre programme. De même, il n’est pas recommandé 
d’entrainer nos données sur un seul modèle, ceci car si eﬀectivement un algorithme est performant sur un jeu de donnée, rien ne
dit qu’il le sera sur des données jamais rencontrées. Nous avons donc entrainé plusieurs modèles et leurs avons appliqué la méthode 
dîte de "cross validation".

Ici la parallélisation va se révéler déterminante aﬁn d’optimiser la vitesse d’éxecution de notre code. En eﬀet appliquer 
ces diﬀérentes procédures sur nos processeurs nous permet de gagner un temps considérable et de réduire l’empreinte mémoire de 
notre dataset initiale. Dans la suite de ce document nous montrerons l’importance du gain temps/mémoire réalisé en faisant appel à
ces méthodes de multiproccessing et de multhreading.
