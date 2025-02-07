# Challenges PHP : Maîtriser les Concepts Avancés (Traits, Readonly, Typing, Méthodes Magiques, Sérialisation, etc.)

## 🔹 Niveau 1 : Débutant (Traits, Readonly, Typage)

### 1. Utiliser un Trait pour la gestion des formats d’affichage
- Créer un trait `AffichageFormat` avec une méthode `afficherFormat()` qui renvoie les détails du livre au format JSON.
- Ajouter ce trait à la classe `Livre` et tester son utilisation.

### 2. Attribut `readonly` pour la date de publication
- Déclarer l’attribut `$datePublication` de la classe `Livre` comme `readonly`.
- Initialiser cette valeur dans le constructeur et tenter de la modifier après l’instanciation.

### 3. Utiliser le typage strict
- Activer le typage strict au début du fichier PHP.
- Modifier la méthode `ajouterLivre` de `Bibliotheque` pour qu'elle accepte uniquement des objets de type `Livre`.

---

## 🔹 Niveau 2 : Intermédiaire (Méthodes Magiques, Constantes de Classe)

### 4. Méthode magique `__get` et `__set`
- Ajouter des méthodes `__get()` et `__set()` dans la classe `Livre` pour intercepter l’accès aux attributs privés.
- Tester l'accès à des propriétés non définies directement par ces méthodes.

### 5. Définir une constante de classe
- Créer une constante `MAX_LIVRES` dans la classe `Bibliotheque` pour limiter le nombre de livres qu’une bibliothèque peut contenir.
- Ajouter une logique pour vérifier avant d’ajouter un livre que la limite n’est pas atteinte.

### 6. Utiliser la méthode magique `__toString()`
- Ajouter une méthode `__toString()` à la classe `Livre` pour retourner une représentation sous forme de chaîne du livre.
- Tester en affichant un objet `Livre`.

---

## 🔹 Niveau 3 : Avancé (Sérialisation, Clonage, Comparaison, Late Static Binding, Exceptions)

### 7. Sérialisation d'un livre
- Ajouter la méthode `__serialize()` à la classe `Livre` pour personnaliser la sérialisation de l'objet.
- Tester la sérialisation et la désérialisation d’un livre.

### 8. Clonage d'un objet `Livre`
- Implémenter la méthode `__clone()` dans `Livre` pour personnaliser le clonage.
- Tester le clonage d'un livre et vérifier si les attributs sont copiés correctement.

### 9. Comparer deux livres
- Implémenter la méthode `compare()` dans `Livre` qui compare deux livres sur leur titre et auteur.
- Tester en comparant deux livres identiques et différents.

### 10. Late Static Binding avec `Bibliotheque`
- Créer une méthode statique `creerBibliotheque()` dans `Bibliotheque` qui utilise le late static binding pour retourner une instance de la classe `Bibliotheque`.
- Tester cette méthode dans une classe dérivée de `Bibliotheque`.

### 11. Gestion des exceptions
- Ajouter une exception `LivreNonDisponibleException` dans `Bibliotheque` pour signaler qu’un livre ne peut pas être emprunté.
- Tester cette exception lorsqu’un livre déjà emprunté est essayé d’être emprunté à nouveau.

---
