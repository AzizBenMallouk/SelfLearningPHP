# Challenges en Polymorphisme et Abstraction avec PHP (Gestion des Animaux)

## 🔹 Niveau 1 : Débutant (Introduction au polymorphisme)

1. **Créer une classe parent `Animal`**
   - Définir une classe `Animal` avec les attributs `$nom` et `$age`.
   - Ajouter un constructeur pour initialiser ces attributs.
   - Ajouter une méthode `seDeplacer()` qui affiche un message générique.

2. **Créer des classes enfants `Oiseau`, `Poisson`, `Mammifere`**
   - Faire hériter `Oiseau`, `Poisson` et `Mammifere` de `Animal`.
   - Redéfinir `seDeplacer()` dans chaque classe :
     - `Oiseau` → "Je vole dans le ciel."
     - `Poisson` → "Je nage dans l'eau."
     - `Mammifere` → "Je marche sur la terre."

---

## 🔹 Niveau 2 : Intermédiaire (Abstraction et méthodes abstraites)

3. **Créer une classe abstraite `Animal`**
   - Transformer `Animal` en `abstract Animal`.
   - Ajouter une méthode abstraite `communiquer()`.

4. **Implémenter `communiquer()` dans les classes enfants**
   - `Oiseau` → "Je chante."
   - `Poisson` → "Je fais des bulles."
   - `Mammifere` → "Je grogne ou rugis."

5. **Créer une interface `Carnivore` et `Herbivore`**
   - Ajouter une méthode `manger()`.
   - `Lion` implémente `Carnivore` et affiche "Je mange de la viande."
   - `Lapin` implémente `Herbivore` et affiche "Je mange des plantes."

---

## 🔹 Niveau 3 : Avancé (Polymorphisme dynamique)

6. **Créer une fonction `faireCrier(Animal $animal)`**
   - Cette fonction prend un `Animal` en paramètre et appelle `communiquer()`.
   - Tester avec des instances de `Oiseau`, `Poisson`, `Mammifere`.

7. **Créer une classe `Zoo` qui stocke plusieurs animaux**
   - Ajouter un attribut `$animaux` (tableau).
   - Ajouter une méthode `ajouterAnimal(Animal $animal)`.
   - Ajouter une méthode `afficherTousLesDeplacements()` qui appelle `seDeplacer()` pour chaque animal.

---

