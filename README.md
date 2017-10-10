# session-6

Les frameworks CSS

# Get started

Position et appliquer des styles à chaque élément peut prendre beaucoup de temps. Un framework CSS permet d'appliquer des styles pour chaque élément plus modernes que ceux par défaut, et d'ajouter quelques utilitaires pour designer plus facilement un site responsif.

La plupart du temps, tout se passe en ajoutant des classes à ses éléments HTML.

Le plus connu des frameworks CSS s'appelle [Bootstrap](https://getbootstrap.com/). Pour débuter, vous pouvez suivre les instructions disponibles sur leur page [Get started](https://getbootstrap.com/docs/4.0/getting-started/introduction/). Vous y trouverez l'url des fichiers à inclure à votre page, et même un template de base tout fait que vous pouvez utiliser pour commencer votre code.

De plus, Bootstrap inclut également du code Javascript, pour rendre vos composants interactifs. Ainsi il est possible de créer un site web complet sans maitriser les subtilités du code Javascript.

Les frameworks facilitent la vie du développeur, mais ils ont deux inconvénients. Il faut bien lire la documentation pour les utiliser au mieux (il est impossible de deviner quelle classe utiliser et il est souvent hasardeux de modifier leur code), et les sites faits avec le même frameworks se ressemblent beaucoup. Heureusement il est possible de personnaliser Bootstrap avec vos propres styles.

## La grille

Bootstrap, comme d'autres frameworks, fonctionne sur le principe d'une grille. Imaginez que votre page est divisée en 12 colonnes virtuelles. Vous allez définir la largeur de vos blocs par un nombre de colonnes. Lorsqu'un bloc de 5 colonnes et suivi d'un bloc de 4 colonnes, ils se mettent côte à côte. Si vous ajouter un bloc de 4 colonnes, le total de colonnes (5 + 4 + 4 = 13) dépasse 12, donc ce bloc ira à la ligne. Comme les colonnes sont relatives à la largeur de la page, votre site est responsif. Bien entendu, vous pouvez définir pour chaque bloc un nombre de colonnes différent en fonction de la largeur réelle de l'écran. De cette manière, votre site prendra l'aspect optimal sur tous les écrans.

![la grille](http://www.geeksforgeeks.org/wp-content/uploads/boot.png)

## Les conteneurs

Pour commencer à utiliser le système de grille, vous devez définir deux blocs parents. Le premier est unique dans votre site. Il définit le cadre général du site. Soit largeur-fixe (.container), soit pleine-largeur (.container-fluid).

Dans ce bloc, vous pouvez créer des lignes (.row), qui définissent des ensembles de blocs qui seront toujours superposés verticalement.

Puis dans ces lignes, vous pouvez enfin définir vos colonnes. Un bloc "automatique" aura la classe "col". Un bloc de deux colonnes aura la classe "col-2". Si ce même bloc doit prendre 4 colonnes sur un écran plus large, il aura en plus la classe "col-md-4".

Tip : Il est bien sur possible d'ajouter plusieurs classes à un même élement. Celles-ci s'écrivent dans le même attribut class="", et sont séparées par des espaces.

Dans chaque colonne, il est ensuite possible de refaire une grille, avec un bloc ".row", qui contiendra également 12 colonnes.

```html
<main class="container">
  
  <section class="row>
    <article class="col-6"></article>
    <article class="col-4"></article>
    <article class="col-2"></article>
    <article class="col-6"></article>
    <article class="col-4"></article>
  </section>
  
  <section class="row>
    <article class="col-6"></article>
    <article class="col-4"></article>
    <article class="col-2"></article>
    <article class="col-6"></article>
    <article class="col-4"></article>
  </section>
</main>
```

### Le contenu

Bootstrap vous aide avec des règles de mise en forme pour presque chaque élement dont vous aurez besoin. Vous pouvez les retrouver sur [cette page](https://getbootstrap.com/docs/4.0/content/reboot/), accompagnées d'exemples (aperçu et code).

Une jolie citation avec sa source s'écrira donc : 

```html
<blockquote class="blockquote">
  <p class="mb-0">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
  <footer class="blockquote-footer">Someone famous in <cite title="Source Title">Source Title</cite></footer>
</blockquote>
```

### Les composants

Au delà des blocs de texte simple, un site est souvent composé de composants tels que des boutons, des formulaires, des alertes, des onglets, des infobulles, etc...

Bootstrap propose des configurations par défaut très pratiques, que vous pouvez retrouver [ici](https://getbootstrap.com/docs/4.0/components/buttons/). Regardez la liste à gauche.

Un petit bouton avec liste déroulante s'écrira donc : 

```html
<div class="dropdown">
  <button class="btn btn-secondary dropdown-toggle" type="button" id="dropdownMenuButton" data-toggle="dropdown" aria-haspopup="true" aria-expanded="false">
    Dropdown button
  </button>
  <div class="dropdown-menu" aria-labelledby="dropdownMenuButton">
    <a class="dropdown-item" href="#">Action</a>
    <a class="dropdown-item" href="#">Another action</a>
    <a class="dropdown-item" href="#">Something else here</a>
  </div>
</div>
```
# Exercice

A l'aide de Bootstrap, créez un diaporama défilant ([Caroussel](https://getbootstrap.com/docs/4.0/components/carousel/)) pour montrer les caractéristiques de 9 espèces de penguins. Votre page devra contenir : 

- un titre : Reconnaitre un manchot
- un sous-titre : Neuf espèces parmi les 18 existantes

Puis les caractéristiques de chaque manchot avec leur photo (elles sont dans le dossier /assets) : 

```yaml
image: megellanic.svg
Nom: Manchot de Magellan
Nom latin: Spheniscus magellanicus
Originaire de: Argentine, Brésil, Chili, Pérou, Uruguay
Observé: Antarctique, Australie, Nouvelle-Zélande
Statut: Presque menacé

image: humboldt.svg
Nom: Manchot de Humboldt
Nom latin: Spheniscus humboldti
Originaire de: Chili, Pérou, Uruguay
Observé: Colombie, Équateur
Statut: Vulnérable

image: emperor.svg
Nom: Manchot empereur
Nom latin: Aptenodytes forsteri
Originaire de: Antarctique
Observé: Argentine, Chili, Nouvelle-Zélande
Statut: Presque menacé

image: king.svg
Nom: Manchot royal
Nom latin: Aptenodytes patagonicus
Originaire de: Argentine, Chili, Afrique-du-Sud
Observé: Antarctique, Australie, Brésil, Nouvelle-Zélande, Uruguay
Statut: Préoccupation mineure

image: african.svg
Nom: Manchot du Cap
Nom latin: Spheniscus demersus
Originaire de: Angola, Namibie, Afrique-du-Sud
Observé: Congo, Gabon
Statut: En danger

image: chinstrap.svg
Nom: Manchot à jugulaire
Nom latin: Pygoscelis antarcticus
Originaire de: Antarctique, Argentine, Chili
Observé: Australie, Nouvelle-Zélande, Afrique-du-Sud
Statut: Préoccupation mineure

image: gentoo.svg
Nom: Manchot papou
Nom latin: Pygoscelis papua
Originaire de: Antarctique, Argentine, Australie (île Macquarie), Chili
Observé: Nouvelle-Zélande
Statut: Préoccupation mineure

image: rockhopper.svg
Nom: Gorfou de Moseley
Nom latin: Eudyptes moseleyi
Originaire de: Îles de l'Atlantique-sud et Océan indien
Observé: Îles Malouines, Afrique-du-Sud
Statut: En danger

image: adelie.svg
Nom: Manchot Adélie
Nom latin: Pygoscelis adeliae
Originaire de: Antarctique
Observé: Argentine, Australie, Nouvelle-Zélande
Statut: Préoccupation mineure

```

Pour ceux qui aura fini, adaptez votre code pour que ce ne soit plus un caroussel, mais [un système d'onglets verticaux](https://getbootstrap.com/docs/4.0/components/navs/#javascript-behavior)
