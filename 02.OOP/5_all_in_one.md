# Gestion d'une Bibliothèque en POO avec Concepts Avancés

## Objectif
Créer un système de gestion d'une bibliothèque en utilisant la Programmation Orientée Objet (POO) en PHP, avec l’application des concepts suivants :
- Encapsulation
- Héritage
- Abstraction
- Polymorphisme
- Traits
- Méthodes Magiques
- Constantes de Classe
- Typage Strict
- Sérialisation
- Clonage
- Exceptions

## Spécifications

### 1. Classe abstraite : **Personne**
#### Propriétés :
- **nom** (*string*) : Le nom de la personne.
- **age** (*int*) : L'âge de la personne.

#### Méthodes abstraites :
- **sePresenter()** : Chaque sous-classe doit implémenter cette méthode pour afficher un message unique, par exemple :  
  - Lecteur : "Je suis [nom], un lecteur de [âge] ans."
  - Bibliothécaire : "Je suis [nom], un bibliothécaire qui gère la bibliothèque."

---

### 2. Classe **Lecteur** (Hérite de *Personne*)
#### Propriétés :
- **livresEmpruntes** (*array*) : Contient les titres des livres empruntés.

#### Méthodes :
- **emprunterLivre(livre)** : Ajoute un livre à la liste si le lecteur n'a pas dépassé le nombre maximal d'emprunts.
- **retournerLivre(livre)** : Retire un livre de la liste.
- **afficherEmprunts()** : Affiche les livres empruntés.
- **__toString()** : Redéfinir cette méthode pour retourner une chaîne représentant le lecteur (ex. : "Lecteur [nom], [âge] ans").

---

### 3. Classe **Bibliothecaire** (Hérite de *Personne*)
#### Propriétés :
- **specialite** (*string*) : La spécialité du bibliothécaire (ex: gestion, conservation, animation).
- **listeLecteurs** (*array*) : Liste des lecteurs enregistrés.
- **nombreLecteurs** (*statique*) : Nombre total de lecteurs inscrits.

#### Méthodes :
- **inscrireLecteur(lecteur)** : Ajoute un lecteur à la bibliothèque, évite les doublons.
- **afficherLecteurs()** : Affiche tous les lecteurs enregistrés.
- **__get()** et **__set()** : Utiliser ces méthodes magiques pour gérer les accès aux propriétés privées.
- **__serialize()** : Sérialiser les informations du bibliothécaire et de la liste des lecteurs.

---

### 4. Classe **ResponsableBibliotheque** (Hérite de *Bibliothecaire*)
#### Méthodes :
- **sePresenter()** : Redéfinir cette méthode pour afficher "[nom], le responsable de la bibliothèque, supervise toute la gestion." et appeler la méthode **sePresenter()** de la classe parente pour ajouter l'information sur la spécialité.
- **__clone()** : Implémenter la méthode pour personnaliser le clonage d'un responsable de bibliothèque.

---

### 5. Trait **FormatAffichage**
#### Méthodes :
- **afficherLivreFormatJson()** : Méthode pour afficher les détails du livre au format JSON. 
- Ajouter ce trait à la classe **Livre** et tester son utilisation pour afficher des livres au format JSON.

---

### 6. Classe **Livre**
#### Propriétés :
- **titre** (*string*) : Le titre du livre.
- **auteur** (*string*) : L'auteur du livre.
- **datePublication** (*readonly string*) : La date de publication du livre.

#### Méthodes :
- **emprunter()** : Marquer un livre comme emprunté.
- **retourner()** : Marquer un livre comme retourné.
- **__toString()** : Redéfinir la méthode pour afficher les détails du livre sous forme de chaîne.

---

### 7. Exception Personnalisée : **LivreNonDisponibleException**
#### Description :
- Lancer cette exception lorsque un lecteur essaie d’emprunter un livre déjà emprunté.

---

## Contraintes Techniques
- Utiliser l'**encapsulation** pour les propriétés privées.
- Valider les données dans les **setters** (ex. : l'âge doit être positif, un livre ne peut être emprunté deux fois).
- Utiliser `self` pour gérer la propriété statique **nombreLecteurs**.
- Utiliser `$this` pour accéder aux propriétés et méthodes internes.
- Appliquer **Late Static Binding** pour la gestion des instances de classe.
- Utiliser les méthodes magiques **__get**, **__set**, **__toString**, et **__serialize**.
- Utiliser le **typage strict** et la **déclaration de type** pour toutes les méthodes.

---

## Mise en pratique
1. Créer quelques **Lecteurs** et leur ajouter des livres empruntés.
2. Créer un **Bibliothécaire** et inscrire des lecteurs.
3. Créer un **ResponsableBibliotheque** et afficher la liste des lecteurs.
4. Tester les **emprunts et retours de livres** avec gestion des exceptions.
5. Cloner un **ResponsableBibliotheque** et tester le clonage.
6. Sérialiser un **Bibliothécaire** et ses **Lecteurs**.

---

🔍 **Bonus** : Ajouter une fonctionnalité de **recherche de livre** parmi les livres empruntés par un lecteur et limiter le nombre total d'emprunts à **MAX_EMPRUNTS**.


---


# Gestion d'un Système de Commandes en POO

## Objectif
Créer un système de gestion de commandes dans une boutique en ligne en utilisant la Programmation Orientée Objet (POO) en PHP, avec des concepts avancés comme les **traits**, **exceptions**, **interfaces**, **constantes de classe**, **serialisation**, **clonage**, **late static binding**, et **méthodes magiques**.

## Spécifications

### 1. Interface **CommandeInterface**
#### Méthodes :
- **calculerTotal()** : Méthode pour calculer le montant total de la commande.
- **appliquerRemise()** : Méthode pour appliquer une remise sur la commande (ex : code promo).

---

### 2. Classe **Commande** (Implémente l'interface `CommandeInterface`)
#### Propriétés :
- **produits** (*array*) : Tableau contenant les produits dans la commande.
- **remise** (*float*) : Remise appliquée sur la commande.
- **status** (*string*) : Le statut de la commande (ex : "en attente", "expédiée").

#### Méthodes :
- **ajouterProduit(produit, prix)** : Ajouter un produit à la commande avec son prix.
- **calculerTotal()** : Calculer le total de la commande en prenant en compte la remise.
- **appliquerRemise(remise)** : Appliquer une remise à la commande.
- **__toString()** : Retourner les détails de la commande sous forme de chaîne (produits, total, remise).

---

### 3. Classe **Produit**
#### Propriétés :
- **nom** (*string*) : Nom du produit.
- **prix** (*float*) : Prix du produit.

#### Méthodes :
- **afficherDetails()** : Affiche les détails du produit (nom et prix).

---

### 4. Classe **CommandeEnLigne** (Hérite de `Commande`)
#### Méthodes :
- **calculerTotal()** : Redéfinir cette méthode pour appliquer des frais de livraison dans le calcul du total.
- **__serialize()** : Sérialiser les informations de la commande en ligne.
- **__clone()** : Permettre de cloner une commande en ligne.

---

### 5. Trait **GestionStock**
#### Méthodes :
- **mettreAJourStock()** : Réduire le stock d’un produit lors de la validation d’une commande.
- Ajouter ce trait à la classe **Commande** pour gérer la mise à jour du stock des produits lorsque la commande est finalisée.

---

### 6. Exception Personnalisée : **StockInsuffisantException**
#### Description :
- Lancer cette exception lorsque le stock d’un produit est insuffisant pour satisfaire une commande.

---

### 7. Constantes de Classe
#### Dans la classe **Commande** :
- Définir une constante `MAX_COMMANDES_PAR_UTILISATEUR` pour limiter le nombre de commandes qu’un utilisateur peut passer.

---

### 8. Utiliser Late Static Binding pour la gestion des commandes
#### Méthodes :
- Dans la classe `Commande`, utiliser `static::class` pour enregistrer dynamiquement le type de commande créée (Commande, CommandeEnLigne, etc.).

---

### 9. Interface **LivraisonInterface**
#### Méthodes :
- **expedier()** : Méthode pour expédier la commande (changer son statut).
- **suiviLivraison()** : Méthode pour récupérer le statut de la livraison de la commande.

---

### 10. Classe **CommandeLivraison** (Implémente `LivraisonInterface`)
#### Méthodes :
- **expedier()** : Mettre à jour le statut de la commande à "expédiée".
- **suiviLivraison()** : Afficher le statut actuel de la livraison (ex : "En cours", "Livré").

---

## Contraintes Techniques
- Utiliser l'**encapsulation** pour les propriétés privées et protéger les données.
- Valider les données dans les **setters** (ex. : un produit doit avoir un prix positif).
- Appliquer le **typage strict** et les **types de retour** pour toutes les méthodes.
- Utiliser les **méthodes magiques** telles que **__toString**, **__clone**, **__serialize**.
- Appliquer les bonnes pratiques de POO (inheritance, abstraction, interfaces).

---

## Mise en pratique
1. Créer des **Produits** et une **Commande** avec plusieurs produits.
2. Appliquer des **remises** à la commande et calculer le total.
3. Implémenter un **traitement de stock** pour mettre à jour le stock lors de la commande.
4. Tester la gestion des exceptions avec une commande dont le stock est insuffisant.
5. Utiliser **late static binding** pour dynamiser la création de commandes.
6. Créer des **Commandes en ligne** et appliquer des **frais de livraison**.
7. Implémenter et tester le **suivi de livraison** d’une commande.

---

🔍 **Bonus** : Ajouter une fonctionnalité de **recommandation de produits** basée sur les commandes passées par un utilisateur (enregistrer l'historique des commandes).



---


# Système de Gestion d'Entreprise (ERP) en POO

## Objectif
Créer un système ERP (Enterprise Resource Planning) pour une entreprise qui gère les employés, les départements, les projets, les finances et les rapports. Ce système met en œuvre des concepts avancés de la Programmation Orientée Objet (POO) en PHP, y compris les **interfaces**, **traits**, **exceptions personnalisées**, **constantes de classe**, **clonage**, **serialisation**, **late static binding**, **méthodes magiques**, et plus encore.

## Spécifications

### 1. Interface **EmployeInterface**
#### Méthodes :
- **afficherDetails()** : Méthode pour afficher les informations d'un employé.
- **calculerSalaire()** : Méthode pour calculer le salaire d’un employé.

---

### 2. Classe **Employe**
#### Propriétés :
- **nom** (*string*) : Le nom de l'employé.
- **prenom** (*string*) : Le prénom de l'employé.
- **dateEmbauche** (*DateTime*) : La date d'embauche de l'employé.
- **departement** (*string*) : Le département auquel l'employé appartient.
- **salaireBase** (*float*) : Le salaire de base de l'employé.

#### Méthodes :
- **afficherDetails()** : Affiche les informations de l'employé (nom, prénom, département).
- **calculerSalaire()** : Calcule le salaire de base de l'employé. Ajoute une prime selon l'ancienneté.
- **__toString()** : Redéfinir cette méthode pour afficher le nom complet et le salaire.

---

### 3. Classe **Manager** (Hérite de `Employe` et Implémente `EmployeInterface`)
#### Propriétés :
- **equipe** (*array*) : Liste des employés supervisés par le manager.

#### Méthodes :
- **ajouterEmploye(Employe $employe)** : Ajouter un employé à l’équipe du manager.
- **afficherEquipe()** : Afficher tous les employés de l’équipe.
- **calculerSalaire()** : Redéfinir cette méthode pour ajouter une prime de gestion à son salaire.
- **__clone()** : Cloner un manager, tout en clonant également son équipe.

---

### 4. Classe **Departement**
#### Propriétés :
- **nom** (*string*) : Le nom du département.
- **budget** (*float*) : Le budget alloué à ce département.
- **responsable** (*Manager*) : Le manager responsable de ce département.

#### Méthodes :
- **afficherDepartement()** : Afficher les détails du département (nom, budget, responsable).
- **ajouterBudget($montant)** : Ajouter un montant au budget du département.
- **__get()** et **__set()** : Utiliser ces méthodes magiques pour gérer dynamiquement les attributs de département.

---

### 5. Trait **GestionProjets**
#### Méthodes :
- **demarrerProjet()** : Démarre un projet en définissant son état à "En cours".
- **terminerProjet()** : Termine un projet et met à jour son statut à "Terminé".
- Ajouter ce trait à la classe **Departement** pour gérer les projets du département.

---

### 6. Exception Personnalisée : **BudgetInsuffisantException**
#### Description :
- Lancer cette exception si un département tente de dépasser son budget alloué.

---

### 7. Constantes de Classe
#### Dans la classe **Manager** :
- Définir une constante `PRIME_DE_GESTION` pour la prime que chaque manager reçoit sur son salaire de base.

#### Dans la classe **Departement** :
- Définir une constante `BUDGET_MINIMUM` qui détermine le budget minimal qu'un département doit avoir pour pouvoir démarrer un projet.

---

### 8. Late Static Binding
#### Méthodes :
- Dans la classe **Employe**, utiliser `static::class` pour enregistrer dynamiquement les employés créés, afin de tracer leur nombre par type d'employé (Manager, etc.).

---

### 9. Classe **RapportFinancier**
#### Propriétés :
- **montantTotal** (*float*) : Le montant total des finances de l’entreprise.
- **departements** (*array*) : Liste des départements de l'entreprise.

#### Méthodes :
- **genererRapport()** : Générer un rapport financier avec la somme des budgets des départements.
- **__toString()** : Retourner une chaîne représentant le rapport financier (montant total et départements associés).

---

### 10. Méthodes Magiques
#### Dans la classe **Employe** :
- **__get()** et **__set()** : Utiliser ces méthodes pour accéder et définir dynamiquement les propriétés comme le salaire ou le département.

#### Dans la classe **Manager** :
- **__call()** : Permet de traiter les appels à des méthodes inexistantes (ex : `ajouterEmploye()`) et de rediriger vers la méthode appropriée.

---

## Contraintes Techniques
- Utiliser l'**encapsulation** pour les propriétés privées et protéger les données.
- Valider les données dans les **setters** (ex. : un employé ne peut pas être ajouté à une équipe s'il est déjà dans une autre équipe).
- Appliquer le **typage strict** et les **types de retour** pour toutes les méthodes.
- Utiliser **Late Static Binding** pour gérer dynamiquement les sous-classes (Managers, Employés).
- Appliquer les **méthodes magiques** telles que **__toString**, **__clone**, **__get**, **__set**, et **__call** pour personnaliser le comportement des objets.
- Gérer les exceptions avec des **Exceptions personnalisées** (BudgetInsuffisantException).
- Implémenter des **constantes de classe** pour les valeurs constantes comme les primes et les budgets.

---

## Mise en pratique
1. Créer des **Employés** et des **Managers** avec des informations personnelles et des salaires calculés.
2. Créer des **Départements** et y ajouter des **Managers**.
3. Ajouter des **Employés** dans des départements et gérer les budgets avec des **exceptions personnalisées** si le budget est dépassé.
4. Cloner des **Managers** avec leurs équipes et afficher les équipes clonées.
5. Générer des **rapports financiers** avec les budgets des départements.
6. Tester la gestion des **projets** dans les départements avec le trait **GestionProjets**.
7. Tester les **méthodes magiques** pour l'accès dynamique aux propriétés et la gestion des appels de méthode.

---

🔍 **Bonus** : Ajouter une fonctionnalité de **gestion de congés** pour les employés, avec un suivi des jours de congés pris et disponibles.
