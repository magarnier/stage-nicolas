03 - VueJS
==========

Tout ce qu'on a fait est sympa, mais:
 - si il faut dupliquer toutes les cartes pour avoir notre mopedex complet, ça va être chaint
 - si on choisi de changer complètement l'affichage (comme quand on est passé d'un affichage sous forme de tableau à un affichage sous forme de div) et qu'on integère toutes les générations et qu'on veut afficher les 893 ça va être très très chiant
 
 Une solution pour ça, ça va être de faire des pages "dynamiques".
 Accorches toi c'ets pas simple.
 
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
 
 si ça marche pas sur windows essaies:
  npx @vue/cli create pokedex
  
 - il va te poser des question, appuies sur entrée à chaque fois.
 
 Recharge ton dossier (click droit sur 03 - VueJS et "Reload from Disk").
 
 Il va t'avoir crée plein de choses 
   - un dossier `node_modules`, t'auras pas y toucher ignore le
   - un dossier `public`, pareil t'auras pas y toucher ignore le
   - un dossier `src` c'est là ou tu vas bosser, dedans il y a
      - un fichier `App.vue`
      - un fichier `components/HelloWorld.vue`
      
 Dans ton terminal lances la commande suivante:
  `vue-cli-service serve`
  
 Il va t'afficher des choes comme
  >  - Local:   http://localhost:8080/ 
  >  - Network: http://192.168.0.12:8080/

  Cliques sur l'url `http://localhost:8080/`
  
C'est fini pour l'init :)

Tu peux comparer le code de HelloWorld.vue par rapport au rendu de la page 
Il y a des subtilités, mais tu devrais retrouver ce que tu as fait sur les premiers TP.

Un petit détail de ce qu'est un fichier .vue
 - entre les balises `<template>` tu vas avoir la partie `HTML`, un peu comme ce que tu as fais précédement.
 - entre les balises `<script>` tu peux avoir du code, tu vas avoir besoin d'y toucher pour faire de l'affichage
 - entre les balises `<style>` tu vas avoir ton `css`

 
 Les débuts en VueJS
 -------------------
 
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

à la place du to do, nous on aurait une liste de pokemon tu peux la copier/coller depuis le fichier`pokemon.json`.

Le but du TP va être de crée une `App.vue`
qui aura un composant `Card.vue` (à la place du `HelloWorld.vue`)

On va se servir de `v-for` pour afficher la liste de tous les pokemons sous forme de carte.

 Pour l'instant affiche "juste" la liste des numéros et des noms de pokemon.
 (On verra pour faire les cartes plus tard).
 sers toi bien de l'exemple https://fr.vuejs.org/v2/guide/#Conditions-et-boucles et adapte le à ton cas.
 
  Architecture en composants - aller plus loin
  ------------------------------------------

Pour aller plus loin, ce serais quand même cool qu'on fasse le même rendu par carte que ce qu'on a fait à l'étape 2.

Pré-requis, copie/colle le contenu du dossier `images` dans ton dossier `src\assets`

Alors tu vas être obligé de créer un nouveau composant qui se sera inclus par `Card.vue`. En fait ça va te permettre de donner au sous composant uniquement 1 seul pokemon.
Dans ton composant `Card.vue` tu vas avoir la liste des 151 pokemon.
Si tu crée un composant `CardContent.vue` tu vas pouvoir définir l'affichage d'un seul et unique pokemon.

ce qui va pouvoir te permettre 
 - de définir des urls qui dépendent du pokemon affiché (regardes v-bind:href)
 - de d'afficher l'image du pokemon (je te donne la syntaxe parce que c'est chelou v-bind:src="require(`../assets/${pokemon.id}.jpg`)")
 - d'afficher un contneu dédié pour le alt (regardes `v-bind:alt`)


Comme j'ai eu la flegme de chercher à télécharger l'intégralité des images de pokemon, il se peut que certains pokemon n'aient pas d'image associée.
Du coup si un pokemon n'a pas d'image associée, à la place on va afficher la pokeball (`v-if`). Pour pas se prendre la tete pour savoir si l'image existe,
je te propose de te baser sur l'id du pokemon, si il est inférieur à 6 on affiche son image, sinon on affiche la pokeball.

Si t'arrives jusqu'ici c'est déjà bien comme initiation au code :)

J'espère que ça t'a plu.