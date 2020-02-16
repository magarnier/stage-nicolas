03 - VueJS
==========

Tout ce qu'on a fait est sympa, mais:
 - si il faut dupliquer toutes les cartes pour avoir notre mopedex complet, ça va être chaint
 - si on choisi de changer complètement l'affichage (comme quand on est passé d'un affichage sous forme de tableau à un affichage sous forme de div) et qu'on integère toutes les générations et qu'on veut afficher les 893 ça va être très très chiant
 
 Une solution pour ça, ça va être de faire des pages "dynamiques".
 
 Boostraper l'app
 ----------------
 Boostraper === joli terme pour dire mettre en place la structure de base.
 
 Mettre en place une nouvelle application, ça demande de savoir comment son build fonctionne.
 Comme c'est une partie assez chiante, il y a des gens qui ont fait des outils pour nous :). On va les installer et les exécuter.
 
 Appelles moi pour cette étape, c'est pas compliqué, mais faut savoir ou chercher.
 
 https://blog.elao.com/fr/dev/realisez-une-application-vue-js-avec-vue-cli/
 
 dans ton IDE, ouvre le terminal
 
 va dans to workspace (cd D:\foldername)
 npm install -g @vue/cli @vue/cli-service-global
 
 vue create <pokedex>
 => <pokedex> est un nom libre, c'est le nom de ton project
 
 Lances ton App
 --------------
 Pour lancer ton app, fais
 
 
 Architecture en composant
 -------------------------
 
 Commence par lire :
 https://fr.vuejs.org/v2/guide/
 et comprends ce qui se passe dans "Conditions et boucles"
 
 Plus haut je disais que dupliquer les cartes pour afficher des informations de pokemon c'est chiant, je sais pas si tu vois ou je veux en venir,
 mais si on compare leur exemple:
 
 ```js
 data: {
     todos: [
       { text: 'Apprendre JavaScript' },
       { text: 'Apprendre Vue' },
       { text: 'Créer quelque chose de génial' }
     ]
   }
```

à la place du to do, nous on aurait une liste de pokemon dans le ficher `pokemon.json`.

Le but du TP va être de crée une `App.vue`
qui aura un composant `Card.vue`

On va se servir de `v-for` pour afficher la liste de tous les pokemons sous forme de carte.

Comme j'ai eu la flegme de chercher à télécharger l'intégralité des images de pokemon, il se peut que certains pokemon n'aient pas d'image associée.
Du coup si un pokemon n'a pas d'image associée, à la place on va afficher la pokeball (`v-if`).

Si t'arrives jusqu'ici c'est déjà bien comme initiation au code :)

J'espère que ça t'a plu.