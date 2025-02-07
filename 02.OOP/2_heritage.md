# Challenges en Héritage avec PHP (Gestion des Véhicules)

## 🔹 Niveau 1 : Débutant (Bases de l'héritage)

1. **Créer une classe parent `Vehicule`**
   - Définir une classe `Vehicule` avec les attributs privés `$marque`, `$modele`, `$vitesseMax`.
   - Ajouter un constructeur pour initialiser ces attributs.
   - Ajouter une méthode `afficherInfos()` pour afficher les détails du véhicule.

2. **Créer une classe enfant `Voiture`**
   - Faire hériter `Voiture` de `Vehicule`.
   - Ajouter un attribut `$nombrePortes`.
   - Redéfinir `afficherInfos()` pour inclure le nombre de portes.

3. **Créer une classe enfant `Moto`**
   - Faire hériter `Moto` de `Vehicule`.
   - Ajouter un attribut `$typeGuidon`.
   - Ajouter une méthode `faireWheelie()` qui affiche un message lorsque la moto fait une roue arrière.

---

## 🔹 Niveau 2 : Intermédiaire (Surcharge et sécurité)

4. **Utiliser le constructeur parent dans les classes enfants**
   - Utiliser `parent::__construct($marque, $modele, $vitesseMax)` pour éviter la duplication de code.

5. **Surcharger `afficherInfos()` dans `Voiture` et `Moto`**
   - Ajouter des détails spécifiques à chaque type de véhicule.

6. **Rendre `$vitesseMax` accessible aux classes enfants**
   - Modifier la visibilité de `$vitesseMax` en `protected` pour permettre l'accès dans `Voiture` et `Moto`.

---

## 🔹 Niveau 3 : Avancé (Polymorphisme et abstraction)

7. **Créer une classe abstraite `VehiculeMotorise`**
   - Transformer `Vehicule` en `abstract VehiculeMotorise`.
   - Définir une méthode abstraite `demarrer()`.

8. **Implémenter la méthode `demarrer()` dans `Voiture` et `Moto`**
   - `Voiture` affiche "La voiture démarre avec un moteur silencieux".
   - `Moto` affiche "La moto démarre avec un bruit puissant".

9. **Utiliser des interfaces pour structurer le code**
   - Créer une interface `Transportable` avec la méthode `charger()`.
   - Implémenter cette interface dans une nouvelle classe `Camion`.

---

## 🔹 Niveau 4 : Expert (Bonnes pratiques et design patterns)

10. **Utiliser `final` pour empêcher l'héritage de certaines classes**
    - Ajouter `final` à `MotoSport` pour éviter d'autres sous-classes.

11. **Créer une Factory pour instancier les véhicules dynamiquement**
    - Définir une classe `VehiculeFactory` pour créer `Voiture`, `Moto` ou `Camion`.

---
