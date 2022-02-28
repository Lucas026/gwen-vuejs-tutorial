# product-and-cart

# 1ère partie :

    étape What is Vuejs :
        - C'est un framework léger
        - Il est flexible et peu s'adapter très facilement

    étape Vue 3 Setup : 
        - On peut l'utiliser juste en appelant un CDN dans un script
        - On peut déclarer des variables dans le script et les appeller avec {{ nom_variable }} dans l'html

    étape Vue js directives :
        - Il existe des irectives custom dans Vuejs qui peuvent être appelée dans la page html
        - On peut leur fournir divers arguments comme par exemple "isVisible"

    étapes Methods : 
        - dans Vue.createApp on peut déclarer autre chose que data c'est a dire methods. Dedans on peut implémenter nos propre méthode ainsi que leurs arguments et leur mettre ce que l'on veut dedans
        - Les méthodes que l'on crée peuvent ensuite être appelé grâce à des directives

    étape Components : 
        - Un component peut-être appelé comme une balise html
        - Le component doit porter le nom de la balise en premier argument et le second argument est un argument qui n'est pas obligatoire
        - On peut coder de l'html dedans afin de faire comme dans la viéo un formulaire et on peut lui ajouter des data comme avec le {{title}}
        - On peut aussi lui intégrer des methods que l'on peut directement mettre dans le code html du components

    étape Components Props :
        - On peut appeller un autre components dans un components afin de le customiser
        - Pour appeller un autre components il suffit juste de mettre component['nom'] dans le components souhaité afin de l'utilisé derrière
        - On peut aussi faire du passage de data, par exemple on a une balise <label> dans un components 1 on peut déclarer/ modifier ses datas dans un components 2, dans le component 1 il suffira juste de l'appelé par le nom par lequelle on l'a nommé dans le component 2
        - On peut aussi créer un props sur une propriété html ou encore sur un model, après ça on peut appelé une méthode d'objet appelé computed qui permé de transformé des variables en clé, a l'intérieur ce ces variables ont met un get() et un set() que l'on customise en fonction de ce que l'on veut faire

    étape Loops :
        - Grâce au loop eu lieu de tout afficher ans un seul templates et répéter plusieurs foi le components enfant par exemple, on peut boucler tout ça dans le components parents et les données voulue sont stockées en tant que data et son donc récupéré grâce au loop en fonction du nom que l'on leur a attribuer.

    étape LifeCycle Hooks :
        - Les hook permettent de faire des appelle a une API, ou encore de créer ou enlever des evenements
        - Ceux-ci sont a utilisés sur les components en fonction du cas dans lequel on en a besoin

# 2ème partie :

    - On peut afficher/cacher des templates grâce a des components et des methods très facilement. Par exemple dans la vidéo on implémente toggleSidebar qui nous permet d'ouvrir et fermer le panier mais comme on ne peut pas l'utiliser tel qu'elle dans le template on utilise un props dans la balise custom sidebar afin de passer la méthode et de pvr l'utiliser dans le template a l'intérieur du component.

    - De même on peut passer les paramètres/attributs de nos méthodes dans le template en le passant a la balise sidebar par un props, qui est aussi déclaré dans le component, on peut ensuite recupérer les infos des méthodes en utilisant ceci {{ nom_méthodes.attributs }}.

    - Grâce au loop on peut facilement afficher les données que l'on dispose dans un JSON par exemple via un LifeCycle Hook qui appelle ce JSON et les afficher dynamiquement. Puis ensuite les utiliser afin de les utliser dans différente méthode afin de les traiter et de ressortir autre chose. On peut déclarer un loop comme ceci <div v-for="(product, i) in inventory.slice(0,3)" :key="product.id" class="card">, le v-for représente la boucle dans laquelle on va faire passer les données et la :key représente la clé par laquelle on va faire passer les données que l'on veut par exemple si on veut recuperer un type on va faire {{ product.type }} dans l'exemple de la vidéo.

# Partie Vue CLI :

    - Tout seul Vuejs n'est pas très utile car a s'il faut travailler sur plusieurs page ça devient vite gênant. Pour cela on peut utiliser un projet Vue CLI qui permettre de réaliser un projet front end beaucoup plus simplement qu'en important seulement le CDN. On peut lancer un server un peu a la manière de symfony avec un npm serve. 

    - Il ajoute aussi un système de routing dans lequel on peut passer le chemin donc le path, le nom de ce chemin ainsi que le component qui y correspond

    - La navbar peut etre mis dans le fichier App.vue car celui-ci est accesible sur l'ensemble des vue que l'on va créer, ensuite en fonction des routes que l'on utilise on doit les déclarer dans le fichier index.js dans le dossier router et il faut aussi importer les vue afin qu'il puisse les connaitre.

    - Afin d'utiliser SASS on doit installer un SASS loader qui va nous permettre d'utiliser les fichiers scss. Le SASS nous permet de customiser dynamiquement nos pages sans passer par un fichier de style de spécifique, on peut importer tout les fichiers sass dans un seul fichier scss afin de tout utiliser sans avoir a les appelé un par un.

    - Au lieu d'avoir un template a l'intérieur d'un component, ce que l'on va faire c'est que l'on va déclarer un une fichier Sidebar.vue a l'intérieur du dossier components et on va y apporter le code tu template. Ensuite on doit l'importer et le déclarer en tant que component dans App.vue afin de pouvoir l'utiliser. On doit aussi réutiliser celle-ci dans la balise custom <sidebar /> afin de faire appelle au methods que nous avons utliser et donc on doit déclarer ces meme méthodes dans App.vue.

    - Au lieu de déclarer 2 fois la les meme data ce que l'on peut faire c'est passé par le router-view. Par exemple dans la vidéo ce que l'on peut faire c'est passé les data inventory dans le router-view depuis App.vue et les récupéré en tant que props dans Home.vue.




    


