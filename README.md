# TUTORIEL VUE.JS

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


# Ressource initiale pour comprendre le fonctionnement interne de vue.js
Lien : https://medium.com/js-imaginea/the-vue-js-internals-7b76f76813e3

    # Phase de compilation
    Le compilateur Vue lit le modèle d'un composant, le fait passer par des étapes telles que l'analyse(Parsing stage), l'optimisation(Optimization stage), le codegen(CodeGen Stage) et crée finalement une fonction de rendu. Cette fonction est responsable de la création d'un VNode qui est utilisé par le processus de correctif du DOM virtuel pour créer le DOM actuel.

    - Parsing stage : Cette étape de compilation joue avec le balisage envoyé comme modèle pour un composant particulier. Tout d'abord l'analyseur analyse le modèle en analyseur HTML et le convertit à son tour en AST (arbre de syntaxe abstraite). L'AST contient les informations telles que les attributs, le parent, les enfants, les balises, etc. Le processus d'analyse analysera les directives similaires aux éléments. Les directives structurelles telles que v-for , v-if, v-once seront représentées sous forme de paires clé-valeur dans l'AST pour un élément particulier.
    - Optimization stage : L'objectif de l'optimiseur est de parcourir l'AST généré et de détecter les sous-arbres qui sont purement statiques, c'est-à-dire les parties du DOM qui n'ont jamais besoin d'être modifiées. Une fois qu'il a détecté les sous-arbres statiques, Vue les hissera dans des constantes, de sorte que Vue ne créera pas de nouveaux nœuds pour eux à chaque nouveau rendu. Ces nœuds seront complètement ignorés pendant le processus de correction du DOM virtuel.
    - CodeGen Stage : La dernière étape du compilateur est l'étape codegen, une étape où la fonction de rendu réelle sera créée et sera utilisée dans le processus de patch. Sur la base de l'indicateur statique fourni par l'optimiseur, le codegen divisera la fonction de rendu en 2 fonctions distinctes. L'une est une fonction de rendu simple et l'autre est une fonction de rendu statique. À la fin, les fonctions de rendu seront utilisées pour créer un VNode tout en déclenchant le processus de rendu réel.

    # The observer and watcher - react component

    - Observer : Sous le capot, Vue parcourt toutes les propriétés que nous définissons dans les données et les convertit en getter/setters à l'aide de Object.defineProperty. Lorsqu'une propriété de données obtient une nouvelle valeur, la fonction set en informe les Watchers .
    - Watcher : Un observateur est créé pour chaque composant lorsqu'une application Vue est initialisée. Il analyse une expression, collecte les abonnés et déclenche un rappel lorsque la valeur de l'expression change. Ceci est utilisé à la fois pour l' API $watch et les directives. Chaque instance de composant a une instance d'observateur correspondante, qui enregistre toutes les propriétés comme "touchées" lors du rendu du composant en tant que dépendances. Plus tard, lorsque le setter d'une dépendance est déclenché, il en informe l'observateur, ce qui déclenchera finalement le processus de correctif. Chaque fois qu'un changement de données est observé, il ouvre une file d'attente et met en mémoire tampon tous les changements de données qui se produisent dans la même boucle d'événements. Tous les observateurs sont ajoutés à la file d'attente. Chaque observateur a un identifiant unique dans un ordre incrémentiel, donc si le même observateur est déclenché plusieurs fois, il ne sera poussé dans la file d'attente qu'une seule fois et avant de le consommer, la file d'attente sera triée car l'observateur doit s'exécuter du parent à l'enfant.

    # The patch process

    Le processus de patch est essentiellement un processus qui interagit efficacement avec le DOM réel à l'aide du DOM virtuel. Un DOM virtuel est juste un objet JavaScript qui représente un modèle d'objet de document (DOM). Vue.js utilise en interne la bibliothèque snabbdom. Le processus concerne le jeu de l'ancien VNode (Virtual DOM Node) et du nouveau VNode. En fin de compte, les deux seront comparés les uns aux autres. L'algorithme fonctionnera de la manière suivante :
        - 1 : Il vérifiera d'abord si l'ancien VNode est présent ou non et, si ce n'est pas le cas, créera l'élément DOM pour chaque VNode. Lorsque vous atterrissez pour la première fois dans l'application et que le premier processus de rendu démarre, dans ce cas, l'ancien VNode ne sera pas là.
        - 2 : Dans l'autre cas, si l'ancien VNode est présent, le processus de comparaison des enfants des deux commencera - Le nœud commun restera tel qu'il est dans DOM et le nouveau nœud sera ajouté et l'ancien nœud sans correspondance sera également supprimé de Virtual DOM. à partir du DOM réel.
        - 3 : De plus, les styles, la classe, l'ensemble de données et l'écouteur d'événements pour le nœud correspondant seront mis à jour (la nouvelle chose sera ajoutée ou les choses qui ne sont pas nécessaires seront supprimées) si nécessaire.
    Le même processus aura lieu récursivement pour tous les nœuds.

    # Life cycle hooks
    Le cycle de vie du composant peut être séparé en quatre sections :
        - La création
        - Le montage
        - La mise à jour
        - La destruction
    
# a) ressource pour comprendre comment créer de nouveaux éléments HTML personnalisés
Lien : https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_custom_elements

    Le controller qui permet de réaliser des éléments custom se nomme CustomElementRegistry object, cet objet vous permet d'enregistrer un élément personnalisé sur la page, de renvoyer des informations sur les éléments personnalisés qui sont enregistrés.
    Pour enregistrer un éléments customiser sur la page il faut utiliser la méthode CustomElementRegistry.define(), celle-ci prend 3 arguments :
        - DOMString : représente le nom donné à l'élément. Les noms d'éléments nécessite un tirets, ils ne peuvent pas être des mots simples. 
        - Class object  : définit le comportement de l'élément.
        - Optional : contient une propriété extends, qui spécifie l'élément intégré dont l'élément hérite, le cas échéant.
    Ainsi par exemple nous avons : "customElements.define('word-count', WordCount, { extends: 'p' });"
    Il est possible de définir des rappels de cycle de vie spécifiques à l'intérieur de la classe, qui s'exécutent à des points spécifiques du cycle de vie de l'élément. 
    Il existe 2 types d'éléments personnalisés :
        - Les éléments personnalisés autonomes : ils n'héritent pas des éléments HTML standard. On peut les utiliser sur une page en les écrivant littéralement comme un élément HTML. Par exemple <popup-info>, ou document.createElement("popup-info").
        - Les éléments intégrés personnalisés héritent des éléments HTML de base. Pour en créer un, on peut spécifier quel élément ils étendent, et ils sont utilisés en écrivant l'élément de base mais en spécifiant le nom de l'élément personnalisé dans l' attribut is. Par exemple <p is="word-count">, ou document.createElement("p", { is: "word-count" }).
    
# b) faites des recherches supplémentaires sur le sujet et en lien avec le DOM et la manière dont il est manipulé par le framework Vue.js
# c) en complément, rajouter dans le compte-rendu, ce que vous avez retenu de vos recherches
Lien :  - https://fr.wikipedia.org/wiki/Document_Object_Model
        - https://blog.logrocket.com/how-the-virtual-dom-works-in-vue-js/#:~:text=Vue%20uses%20a%20virtual%20DOM,and%20so%20is%20very%20efficient.

    Le Document Object Model (DOM) est une interface de programmation normalisée par le W3C, qui permet à des scripts d'examiner et de modifier le contenu du navigateur web. Par le DOM, la composition d'un document HTML ou XML est représentée sous forme d'un jeu d'objets, lesquels peuvent représenter une fenêtre, une phrase ou un style. À l'aide du DOM, un script peut modifier le document présent dans le navigateur en ajoutant ou en supprimant des nœuds de l'arbre.
        - Modèle : Un modèle sert à représenter quelque chose, comme le plan d'une ville. Le DOM représente le document qui se trouve dans le navigateur.
        - Objet : En programmation, un objet est un conteneur qui comporte des propriétés et des méthodes qui sont des variables et des actions concernant ce qu'il   représente. Les objets du DOM peuvent représenter une fenêtre, un document, une phrase, un style…
        - Document : Le DOM concerne un document, tel qu'une page web affichée dans un navigateur. Une page web commence par une balise !DOCTYPE suivi de la balise <html>dans laquelle se trouve le reste du document. Le DOM représente le document affiché par une structure en arbre, comportant des nœuds (branches et feuilles).

    Autre description du DOM :
        - Le Document Object Model, ou DOM, est une sorte d'interface qui traite tout le langage de balisage (votre HTML) comme des nœuds connectés. Il peut être vu comme une interface d'objets pour les éléments de balisage stockés dans une structure arborescente. Le DOM est ce qui nous permet d'écrire et de changer les styles des éléments, et même de changer les éléments eux-mêmes. Cela se fait en ajoutant, modifiant ou supprimant des balises d'élément ou des styles CSS dans l'en-tête et le corps d'un document, car ils sont représentés sous forme de nœuds et d'objets. C'est ainsi que fonctionne le DOM HTML.

    Donc tout va bien avec le DOM. Cependant, à mesure que les applications se développent - ce qui signifie plus de nœuds à traverser, plus d'éléments et plus de scripts pour communiquer avec ces éléments - le DOM se développe plus lentement et coûte beaucoup de puissance de traitement. Essayer d'effectuer une recherche ou même de mettre à jour un DOM devient une tâche difficile, affectant finalement les performances de l'application. C'est pourquoi le DOM virtuel a été créé.

    L'équipe Vue.js a construit le DOM virtuel pour être une sorte d'abstraction du DOM traditionnel ; c'est une version "allégée" du DOM HTML, mais avec des super pouvoirs. Le DOM virtuel est plus intelligent et trouve donc un moyen d'être plus efficace que le DOM traditionnel. Pour ce faire, il utilise principalement divers algorithmes de différenciation pour éviter de restituer l'intégralité du DOM après toute nouvelle modification ou mise à jour du document. Cela seul améliore considérablement l'efficacité et la gestion des ressources car l'API DOM est appelée moins souvent. Le DOM virtuel par cette explication est situé entre le DOM réel et l'instance de Vue.
    exemple : 
        new Vue ({ 
            el : '#app' , 
            data : { 
                text : 'hi LogRocket' }, 
            render ( createElement ) { return createElement ( 'h1' , { attrs : { id : 'headers' } }, this . text
            ) ; } });   
    Va renvoyer :
        < div id = 'app' > < h1 id = 'headers' > salut LogRocket </ h1 > </ div > 

    Le DOM virtuel Vue est donc constitué de composants Vue, qui sont des objets JavaScript qui étendent l'instance Vue. Vue utilise un DOM virtuel en raison de la différence de vitesse et d'efficacité par rapport au DOM réel. Le DOM virtuel est également plus petit que le DOM réel et est donc très efficace.

    