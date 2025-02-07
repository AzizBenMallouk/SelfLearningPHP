# Challenges en Encapsulation avec PHP

## 🔹 Niveau 1 : Débutant (Bases de l'encapsulation)

1. **Créer une classe simple avec un attribut privé**  
   - Définir une classe `CompteBancaire` avec un attribut privé `$solde`.
   - Ajouter un constructeur pour l'initialisation du solde.
   - Créer une méthode `getSolde()` pour récupérer la valeur du solde.

2. **Ajouter des méthodes pour modifier l'attribut privé**  
   - Ajouter `deposer($montant)` et `retirer($montant)`.
   - Vérifier que le montant du retrait ne dépasse pas le solde disponible.

3. **Empêcher l'initialisation avec un solde négatif**  
   - Vérifier dans le constructeur que `$solde` ne peut pas être négatif.
   - Lever une exception (`throw new Exception`) si l’utilisateur tente d'initialiser un solde négatif.

---

## 🔹 Niveau 2 : Intermédiaire (Validation et sécurité)

4. **Validation des montants déposés et retirés**  
   - Empêcher les montants négatifs pour `deposer()` et `retirer()`.
   - Lever une exception en cas d'erreur.

5. **Rendre l'attribut privé immuable en dehors de la classe**  
   - Empêcher toute modification de `$solde` en dehors de la classe.

6. **Créer un système de logs**  
   - Ajouter un attribut privé `$historiqueTransactions` (tableau).
   - Enregistrer chaque dépôt et retrait dans `$historiqueTransactions`.
   - Ajouter une méthode `getHistorique()` pour afficher les transactions.

---

## 🔹 Niveau 3 : Avancé (POO et bonnes pratiques)

7. **Utiliser des `getter` et `setter` au lieu d'un accès direct**  
   - Créer `setSolde()` avec des règles métier strictes.
   - Ajouter un `getter` pour le solde et l’historique.

8. **Créer plusieurs types de comptes bancaires (Héritage et polymorphisme)**  
   - `CompteCourant` (avec découvert autorisé).
   - `CompteEpargne` (avec un taux d'intérêt et un retrait limité).

9. **Encapsuler les règles métier dans des méthodes privées**  
   - Créer une méthode privée `verifierMontant($montant)`.
   - Créer une méthode `estSolvable($montant)`.

10. **Protéger la modification du solde avec des constantes et des propriétés `readonly`**  
   - Ajouter `readonly` pour empêcher la modification du solde après création.

---

## 🔹 Niveau 4 : Expert (Design Patterns et bonnes pratiques avancées)

11. **Utiliser le pattern Factory pour instancier les comptes**  
   - Créer une classe `CompteFactory` qui génère un `CompteBancaire`.

12. **Utiliser le pattern Repository pour gérer plusieurs comptes**  
   - Créer une classe `CompteRepository` qui stocke et gère plusieurs comptes (sans communication avec la base de donnée, juste il faut represeter la liste des comptes comme un array dans le repository).

13. **Intégrer une classe Logger pour suivre toutes les actions**  
   - Enregistrer toutes les opérations (`depot`, `retrait`, `erreur`).

---

