# Challenges sur les Classes et Objets avec PHP (Gestion d’une Bibliothèque)

## 🔹 Niveau 1 : Débutant (Classes, objets et instances)

1. **Créer une classe `Livre`**
   - Définir une classe `Livre` avec les attributs `$titre`, `$auteur`, `$anneePublication`.
   - Ajouter un constructeur pour initialiser ces valeurs.
   - Créer une méthode `afficherDetails()` qui affiche les informations du livre.

2. **Créer et manipuler des objets `Livre`**
   - Instancier plusieurs objets `Livre`.
   - Afficher leurs détails avec `afficherDetails()`.

3. **Gérer le statut du livre (Disponible / Emprunté)**
   - Ajouter un attribut `$disponible` (booléen).
   - Ajouter des méthodes `emprunter()` et `retourner()`.
   - Empêcher l’emprunt si le livre est déjà emprunté.

---

## 🔹 Niveau 2 : Intermédiaire (Static, self, class)

4. **Créer une classe `Bibliotheque` pour gérer plusieurs livres**
   - Ajouter un attribut `private static $livres` pour stocker les livres.
   - Ajouter une méthode `ajouterLivre(Livre $livre)`.
   - Ajouter une méthode `afficherTousLesLivres()`.

5. **Utiliser `self` et `static` dans `Bibliotheque`**
   - Accéder à `$livres` en utilisant `self::$livres`.
   - Tester en ajoutant et en affichant plusieurs livres.

6. **Compter le nombre total de livres**
   - Ajouter une propriété `private static $nombreLivres` qui s'incrémente à chaque ajout.
   - Créer une méthode `getNombreLivres()` pour retourner cette valeur.

---
