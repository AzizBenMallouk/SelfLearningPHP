# Liste des Challenges POO en PHP

## Challenge 1 : **Système de gestion de bibliothèque**

### Description du projet :
Tu dois développer un système de gestion d’une bibliothèque, qui permet de gérer les livres, les membres et les emprunts de livres. Le système doit comporter plusieurs fonctionnalités :  
- Ajouter un livre à la bibliothèque.
- Inscrire un membre.
- Effectuer un emprunt et un retour de livre.
- Afficher les livres disponibles et ceux empruntés.
- Afficher les informations des membres inscrits et leurs emprunts.

Le système doit être structuré de manière à pouvoir facilement ajouter de nouvelles fonctionnalités dans le futur, telles que la recherche de livres ou la gestion des réservations.

### À faire :
1. Identifier les entités principales dans ce système. Quelles classes seraient nécessaires pour représenter les livres, les membres et les emprunts ?  
2. Pour les interactions avec la bibliothèque, quelle interface ou classe devrait être utilisée pour gérer les emprunts et les retours ?  
3. Chaque entité (par exemple, livre, membre) devra-t-elle être une classe ou une interface ?
4. Quelles propriétés seraient nécessaires dans chaque classe ? Pense à des attributs comme le titre du livre, le nom du membre, la date de l’emprunt, etc.
5. Quelle méthode serait appropriée pour effectuer un emprunt de livre, et comment gérera-t-on le retour ?
6. Comment organiser l’ajout et la recherche des livres dans le système ?

---

## Challenge 2 : **Système de gestion des commandes**

### Description du projet :
Tu dois implémenter un système de gestion des commandes pour un magasin en ligne. Le système doit permettre de gérer :
- L’ajout d’articles au panier.
- La validation des commandes.
- L’affichage des détails de chaque commande (articles achetés, prix total, statut de la commande).
- La mise à jour du statut de la commande (par exemple, "en traitement", "expédiée", "livrée").

### À faire :
1. Quelles classes seraient nécessaires pour représenter une commande, un article et un panier ?  
2. Quelles interfaces, s'il y en a, seront nécessaires pour les actions de validation, d’ajout au panier, etc. ?
3. Quelles propriétés seront importantes dans la classe `Commande` ? Que faut-il stocker comme informations pour chaque commande ?
4. Quels types de méthodes seraient nécessaires pour calculer le total d’une commande, mettre à jour son statut ou ajouter des articles ?
5. Pour la gestion des articles et du panier, quelles relations devraient exister entre les classes ? Est-ce que le panier aura une classe dédiée ?  
6. Comment le système pourra-t-il être étendu pour ajouter un mode de paiement, des remises ou des coupons ?

---

## Challenge 3 : **Gestion des employés dans une entreprise**

### Description du projet :
Développe un système de gestion des employés dans une entreprise, qui permettra de gérer les informations suivantes :
- Le nom, l’âge, le poste et le salaire de chaque employé.
- La création et la mise à jour des informations d’un employé.
- Le calcul du salaire annuel de chaque employé.
- L’affichage des informations de tous les employés.

### À faire :
1. Quels types d’entités doivent être créés pour gérer les informations des employés ?
2. Devrait-il y avoir une interface pour la gestion des informations des employés ou une classe par défaut pour les employés ?
3. Quelles propriétés devront être présentes dans la classe `Employe` ?
4. Que doit-on inclure comme méthodes dans cette classe (par exemple, calcul du salaire annuel) ?
5. Comment organiser l'ajout et la gestion des employés dans l'entreprise ? Y a-t-il des sous-classes ou des interfaces spécifiques à créer pour certains types d'employés (par exemple, employés permanents et contractuels) ?
6. Quelles relations devraient exister entre les classes pour gérer l’organisation hiérarchique des employés dans l’entreprise ? Doit-il y avoir des classes spécialisées (par exemple, pour un manager ou un directeur) ?

---

## Challenge 4 : **Gestion des étudiants et des matières dans une école**

### Description du projet :
Tu dois créer un système de gestion pour une école, permettant de gérer les étudiants, leurs matières et leurs notes. Le système doit permettre :
- L’ajout d’étudiants.
- L’enregistrement des notes pour chaque étudiant dans différentes matières.
- La possibilité de calculer la moyenne générale de chaque étudiant.
- L’affichage des résultats d’un étudiant dans une matière spécifique.

### À faire :
1. Quelles entités devraient être créées dans ce système (par exemple, `Etudiant`, `Matiere`, `Note`) ?
2. Chaque entité doit-elle être une classe ou une interface ? Par exemple, la matière est-elle mieux représentée par une classe ou une interface ?
3. Quelles propriétés sont nécessaires pour la classe `Etudiant` ? Devrait-elle contenir une liste de matières et de notes ?
4. Quelles méthodes devraient être incluses pour gérer les notes, calculer la moyenne, ajouter une matière, etc. ?
5. Comment organiser l’ajout et l’affichage des matières pour un étudiant ? Devrait-il y avoir une relation entre la classe `Etudiant` et une autre classe pour gérer les matières ?
6. Le calcul de la moyenne générale d’un étudiant doit-il être une méthode de la classe `Etudiant` ou une fonction externe ?

---

## Challenge 5 : **Gestion des véhicules dans un parc automobile**

### Description du projet :
Tu dois implémenter un système de gestion d’un parc automobile, qui permet de gérer les véhicules, leur type et leur entretien. Les fonctionnalités du système doivent inclure :
- L’ajout de véhicules (voiture, camion, moto).
- La gestion des entretiens (pneus, vidange, etc.).
- Le calcul des coûts d’entretien pour chaque véhicule.
- L’affichage des véhicules dans le parc automobile.

### À faire :
1. Quelles classes et interfaces seront nécessaires pour gérer les différents types de véhicules (voiture, moto, camion) ?
2. Les véhicules doivent-ils être des classes ou des interfaces ? Quels détails doivent être stockés pour chaque type de véhicule ?
3. Quelles propriétés seront nécessaires dans les classes pour représenter les véhicules (par exemple, marque, modèle, type) ?
4. Comment organiser l’entretien des véhicules ? Les entretiens doivent-ils être des classes à part ou des méthodes dans la classe véhicule ?
5. Que faut-il comme méthode pour calculer le coût d’entretien d’un véhicule ? Cette méthode doit-elle être présente dans chaque type de véhicule ou dans une classe de gestion des entretiens ?
6. Comment gérer l’affichage des véhicules dans le parc ? Est-ce que chaque véhicule aura une méthode spécifique pour afficher ses informations ?

---

## Challenge Bonus : **Système de réservation de billets de cinéma**

### Description du projet :
Crée un système de réservation de billets pour un cinéma. Le système devra permettre :
- La gestion des films disponibles.
- La réservation de billets pour un film (avec le choix de la date et de l’heure).
- L’affichage des films programmés et des places disponibles.

### À faire :
1. Quelles entités devraient être créées (films, réservations, clients) ?
2. Devrait-il y avoir des interfaces pour la gestion des films et des réservations ?
3. Comment organiser la gestion des films, des horaires et des réservations ? Les classes doivent-elles être abstraites ou concrètes ?
4. Quelles propriétés et méthodes sont nécessaires pour chaque entité ?
5. Comment gérer les places disponibles et l’affichage des horaires des films ?
6. Que faire pour permettre d’ajouter des fonctionnalités supplémentaires, comme des promotions ou des films à venir ?

---
