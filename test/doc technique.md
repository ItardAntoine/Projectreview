#Documentation technique : To-do List App

##Usage non technique.



##Usage technique.

L'application est basée sur la structure MVC (Modèle-Vue-Contrôleur).

###Storage (Store) 

Toutes les données sont stockées côté client via l'API Javascript WebStorage : window.localStorage.     

#####Méthodes
**store** créer un nouvel objet client et créer un nouvel espace de stockage si il n'y en a pas
**find** trouve un objet en fonction d'une requête donnée sous forme d'objet JavaScript ou via son ID.     
**findAll** retourne toutes les données en mémoire.     
**save** créé ou met à jour une tâche existante.     
**remove** enlève un Id du local storage.
**drop** enlève toutes les données du local storage et redémarre à zero. 
...


###Modèle (Model)

Le modèle contient la manipulation des données.

#####Méthodes
**model** créé une nouvelle instance du model et le connecte au storage
**create** créé un nouveau model TODO
**read** trouve et retourne un modèle dans le storage
**update** met à jour un modèle
**remove** enlève un modèle du storage
**removeAll** enlève toutes les données du storage
**getCount** retourne un total de TODO

...


###Vue (View)

La vue correspond à l'interface utilisateur.   

#####Méthodes
**view** Une vue qui supprime complètement le DOM du navigateur.
**_removeItem** enlève un objet de la page 
**_clearCompletedButton** permet d'initialiser le bouton après utilisation
**_setFilter** affichage des filtres
**_elementComplete** confirmation que l'id est complété
**_editItem** création de l'objet à afficher
**_editItemDone** fin de la création de l'objet
**render** rendu total à afficher sur la page
**_itemId** donne un id à l'objet
**_bindItemEditDone**  Suite d'évènement 'click'
**_bindItemEditCancel** Annule l'édition d'un Todo
**bind** routeur qui permet de savoir vers quel onglet afficher la view


...

####Template 

Permet d'alléger le code mais appartient directement à la partie "View" du MVC.

####Méthodes 
**Template** permet de mettre par défaut les méthodes du template
**show** créé un <li> en html et le retourne pour le placer dans l'APP
**itemCounter** Donne un total du nombre de dos restant à compléter
**clearCompletedButton** recharge le texte avec le nouveau bouton "nettoyage terminé"




###Contrôleur (Controller) 

Le contrôleur gère la logique de l'application, récupère les données du modèle (Model) et affiche le texte renvoyé par la partie vue (View).


#####Méthodes
**Controller** Prends le modèle et la view et fait le lien entre eux
**setView** charge et initalise la vue
**showAll** évènement qui déclenche le chargement. Va mettre tous les objets dans la Todo-list
**showActive** retourne toutes les tâches actives
**showCompleted** retourne toutes les tâches complètes
**addItem** évènement qui permet de créer un objet quand on le souhaite
**editItem** Déclenche le mode d'édition d'élément
**editItemSave** fin du mode d'édition par un succès
**editItemCancel** annule un objet du mode d'édition
**removeItem** En lui attribuant un ID, il trouvera l'élément DOM correspondant à cet ID, le supprimera du DOM et le supprimera également du stockage.
**removeCompletedItems** supprime tous les objets du DOM et du storage
**toggleComplete** Donne l'ID d'un modèle et une case à cocher et il mettra à jour l'élément stocké en fonction de l'état de la case à cocher.
**toggleAll** Permet d'activer / désactiver toutes les cases à cocher et de compléter les modèles
**_updateCount** met à jour les bout de page qui change en fonction du nombre de page qu'il reste 
**_filter** met à jour les objets TODO basé sur les routes actives ????????????
**_updateFilterState**  Met simplement à jour les états sélectionnés du filtre de navigation

...


##Audit de performance du site todolistme.net
Les valeurs sont estimées à l'aide des outils de développement de Google Chrome et peuvent varier.

Le site todolistme.net offre des performances satisfaisantes mais perfectibles, notamment le temps de chargement de la page et l'évaluation des scripts.

D'autre part l'application n'est pas suffisamment optimisée pour mobile et propose une accessibilité médiocre : la page n'est pas responsive, est non adaptée aux screen readers et autres outils d'accessibilité.


###Performance
#####Premier rendu du contenu
**1.1 ms** - Indique le moment où le premier texte / image est peint.     
#####Indice de vitesse
**3  ms** - Indique à quelle vitesse le contenu d'une page devient visible.
#####Temps d'interactivité
**5.2  ms** - Marque à quel moment la page est totalement interactive.
#####CPU Idle
**5 790 ms** - Marque la première fois que le thread principal de la page est libre pour gérer les inputs utilisateurs.
#####Input Latency
**134 ms** - Une estimation du temps requis pour répondre aux inputs utilisateur, en millisecondes, pendant la fenêtre de temps durant laquelle le processeur est le plus sollicité pendant le chargement. Si le temps de latence est supérieur à 50 ms, les utilisateurs peuvent percevoir l'application comme étant lente.


###Performance site concurrent
#####Premier rendu du contenu
**1.3 ms** - Indique le moment où le premier texte / image est peint.     
#####Indice de vitesse
**3.6  ms** - Indique à quelle vitesse le contenu d'une page devient visible.
#####Temps d'interactivité
**5.7  ms** - Marque à quel moment la page est totalement interactive.
#####CPU Idle
**5 120 ms** - Marque la première fois que le thread principal de la page est libre pour gérer les inputs utilisateurs.
#####Input Latency
**60.1 ms** - Une estimation du temps requis pour répondre aux inputs utilisateur, en millisecondes, pendant la fenêtre de temps durant laquelle le processeur est le plus sollicité pendant le chargement. Si le temps de latence est supérieur à 50 ms, les utilisateurs peuvent percevoir l'application comme étant lente.

Nous pouvons également noter quelques points importants :  

* Le texte est invisible pendant le chargement des webfonts.
* Le temps de démarrage de JavaScript est trop élevé (5 270 ms).
* Le fichier jQuery n'est pas minifié.

###Différences avec notre application



###Possibilités d'amélioration de notre application basées sur les performances du site


