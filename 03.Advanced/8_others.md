# Liste des Challenges Avancés en PHP

## Challenge 1 : **Surcharge de méthodes (Method Overloading) en PHP**

### Description du projet :
Tu dois implémenter une classe qui utilise la surcharge de méthodes pour gérer des propriétés dynamiques. La classe devra permettre de définir et d’accéder à des propriétés de manière flexible, même si elles n’ont pas été explicitement définies dans la classe.

### À faire :
1. Crée une classe `DynamicProperties` qui utilise les méthodes magiques `__set()` et `__get()` pour gérer dynamiquement les propriétés non définies.
2. Implémente la méthode `__call()` pour permettre la surcharge des méthodes et effectuer des actions spécifiques en fonction des méthodes appelées.
3. Teste ton système avec l'ajout et la récupération de propriétés dynamiques et l’appel de méthodes non définies.
4. Pense à ajouter une méthode pour lister toutes les propriétés dynamiques définies dans l’objet.

---

## Challenge 2 : **Générateurs et itérateurs en PHP**

### Description du projet :
Les générateurs permettent de créer des itérateurs sans avoir à implémenter l’interface `Iterator`. Dans ce challenge, tu devras créer un générateur pour parcourir une collection d’éléments.

### À faire :
1. Crée une classe `RangeIterator` qui génère une séquence de nombres entre deux valeurs.
2. Implémente un générateur avec la méthode `yield` pour retourner les éléments un par un.
3. Teste le générateur en itérant sur une séquence d’entiers.
4. Étends le générateur pour qu’il puisse aussi accepter des pas personnalisés (par exemple, sauter de 2 en 2).
5. Ajoute des fonctionnalités comme le calcul du total de la séquence générée ou le filtrage de certains éléments avant de les retourner.

---

## Challenge 3 : **Gestion des Exceptions dans un Setter avec des Exceptions Personnalisées**

### Description du projet :
Dans ce challenge, tu dois implémenter une gestion d'exception robuste dans un setter. Si une valeur invalide est assignée à une propriété, une exception personnalisée doit être lancée.

### À faire :
1. Crée une classe `Person` avec un attribut privé `age`.
2. Implémente un setter pour `age` qui vérifie si l'âge est positif et inférieur à 120, sinon il doit lancer une exception personnalisée `InvalidAgeException`.
3. Crée la classe `InvalidAgeException` qui étend `Exception` et qui affiche un message d'erreur spécifique.
4. Gère cette exception dans ton code principal et affiche un message approprié lorsque l'exception est levée.

---

## Challenge 4 : **Redéfinition d'une Classe `Array` pour Simuler une `HashMap`**

### Description du projet :
PHP offre un tableau associatif natif, mais dans ce challenge, tu devras créer une classe qui imite le comportement d’une `HashMap` en utilisant des méthodes personnalisées pour ajouter, récupérer et supprimer des clés.

### À faire :
1. Crée une classe `MyHashMap` qui contient un tableau privé pour stocker les paires clé-valeur.
2. Implémente une méthode `put($key, $value)` pour ajouter une nouvelle paire clé-valeur.
3. Implémente une méthode `get($key)` pour récupérer la valeur associée à une clé donnée.
4. Implémente une méthode `remove($key)` pour supprimer une paire clé-valeur.
5. Ajoute une méthode `containsKey($key)` pour vérifier si une clé existe dans la map.
6. Étends la classe pour permettre l’itération sur les clés et les valeurs de la `HashMap`.

---

## Challenge 5 : **Utilisation des Annotations en PHP**

### Description du projet :
Les annotations permettent de lier des métadonnées aux classes, méthodes et propriétés. Dans ce challenge, tu vas implémenter un système d'annotations personnalisées.

### À faire :
1. Crée une classe `Product` avec des annotations pour décrire les propriétés comme le nom, la description et le prix.
2. Implémente une classe `AnnotationReader` qui analyse les annotations de la classe `Product` et les affiche.
3. Crée une annotation personnalisée `@Required` qui marque une propriété comme obligatoire.
4. Crée une méthode dans `AnnotationReader` qui vérifie si les propriétés annotées avec `@Required` ont bien été définies.
5. Implémente un mécanisme qui génère un message d'erreur si une propriété marquée comme `@Required` est manquante ou invalide.
6. Teste ce mécanisme en créant une instance de la classe `Product` sans définir toutes les propriétés annotées comme `@Required`.

---

## Challenge 6 : **Classe et Objet `Singleton`**

### Description du projet :
Le patron de conception Singleton garantit qu'une classe n'a qu'une seule instance et fournit un point d'accès global à cette instance. Tu dois implémenter ce patron dans un cas concret.

### À faire :
1. Crée une classe `Logger` qui écrit des messages dans un fichier de log.
2. Implémente le patron Singleton en utilisant une méthode statique `getInstance()` pour garantir qu'une seule instance de la classe `Logger` existe.
3. Dans la classe `Logger`, implémente une méthode `log($message)` qui écrit le message dans un fichier `log.txt`.
4. Teste ton système en appelant la méthode `log()` plusieurs fois et en vérifiant que toutes les entrées sont ajoutées au même fichier sans créer de nouvelles instances.

---

## Challenge 7 : **Utilisation de Traits pour Ajouter des Comportements à une Classe**

### Description du projet :
Les traits permettent de réutiliser des comportements communs dans plusieurs classes. Dans ce challenge, tu devras utiliser un trait pour ajouter des méthodes communes à différentes classes.

### À faire :
1. Crée un trait `Timestampable` avec des méthodes pour ajouter des timestamps `createdAt` et `updatedAt` à une classe.
2. Crée une classe `Post` qui utilise ce trait pour gérer les dates de création et de modification.
3. Crée une classe `User` qui utilise également ce trait pour gérer les dates de création et de modification.
4. Implémente une méthode `setCreatedAt($date)` et `setUpdatedAt($date)` dans chaque classe pour permettre de mettre à jour ces timestamps.
5. Teste le comportement du trait en créant des instances des classes `Post` et `User` et en affichant leurs dates.

---

## Challenge 8 : **Mécanisme de Clonage d'Objet**

### Description du projet :
Tu dois implémenter un mécanisme de clonage personnalisé pour une classe en PHP, ce qui te permettra de créer une copie exacte de l'objet tout en modifiant certains attributs après le clonage.

### À faire :
1. Crée une classe `User` avec des propriétés `name`, `email` et `role`.
2. Implémente la méthode `__clone()` pour permettre de cloner l’objet tout en modifiant certaines propriétés du clone, comme le `role`.
3. Teste ton mécanisme de clonage en créant une instance de la classe `User`, en la clonant et en modifiant les propriétés du clone.

---
