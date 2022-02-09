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

    étape 


    


