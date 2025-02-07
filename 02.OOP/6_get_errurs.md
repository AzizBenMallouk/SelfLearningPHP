# Challenge : Gestion des Employés

## Objectif
Corriger un système de gestion d'employés en utilisant la Programmation Orientée Objet (POO) en PHP. Le code contient plusieurs erreurs qu'il faut résoudre.

## Code

```php
<?php

// Définition de la classe Employe
class Employe {
    private $nom;
    private $prenom;
    private $age;
    private $salaireBase;

    // Constructeur
    public function __construct($nom, $prenom, $age, $salaireBase) {
        $this->nom = $nom;
        $this->prenom = $prenom;
        $this->$age = $age;
        $this->salaireBase = $salaireBase;
    }

    // Méthode pour afficher les détails de l'employé
    public function afficherDetails() {
        echo "Nom : $this->nom\n";
        echo "Prénom : $this->prenom\n";
        echo "Âge : $this->age\n";
        echo "Salaire de base : $this->salaireBase\n";
    }

    // Méthode pour calculer le salaire
    public function calculerSalaire() {
        $primeAnciennete = 1000;
        return $this->salaireBase + $primeAnciennete;
    }
}

// Définition de la classe Manager (hérite de Employe)
class Manager extends Employe {
    private $equipe;

    // Constructeur de Manager
    public function __construct($nom, $prenom, $age, $salaireBase, $equipe = []) {
        parent::__construct($nom, $prenom, $age, $salaireBase);
        $this->equipe = $equipe;
    }

    // Méthode pour afficher les employés de l'équipe
    public function afficherEquipe() {
        echo "Équipe du manager $this->nom $this->prenom : \n";
        foreach ($this->equipe as $employe) {
            echo $employe->afficherDetails() . "\n";
        }
    }
}

// Création d'un Employé
$employe1 = new Employe("Dupont", "Jean", 35, 2500);
$employe2 = new Employe("Martin", "Claire", 28, 2200);

// Création d'un Manager et ajout d'employés dans son équipe
$manager = new Manager("Lemoine", "Paul", 45, 4000);
$manager->equipe[] = $employe1;
$manager->equipe[] = $employe2;

// Affichage des détails de l'employé
$employe1->afficherDetails();

// Affichage des employés sous la supervision du manager
$manager->afficherEquipe();

// Calcul du salaire du manager
echo "Salaire du manager : " . $manager->calculerSalaire() . "\n";

?>
```




---


# Challenge : Gestion des Commandes dans un Système E-commerce

## Objectif
Corriger un système de gestion des commandes dans un e-commerce en utilisant la Programmation Orientée Objet (POO) en PHP. Le code contient plusieurs erreurs qu'il faut résoudre.

## Code

```php
<?php

// Définition de la classe Produit
class Produit {
    private $nom;
    private $prix;

    // Constructeur
    public function __construct($nom, $prix) {
        $this->nom = $nom;
        $this->$prix = $prix;
    }

    // Méthode pour afficher le détail du produit
    public function afficherDetails() {
        echo "Produit : $this->nom\n";
        echo "Prix : $this->prix\n";
    }

    // Méthode pour récupérer le prix
    public function getPrix() {
        return $this->$prix;  // Erreur : il faut utiliser $this->prix et non $this->$prix
    }
}

// Définition de la classe Commande
class Commande {
    private $produits = [];
    private $status; 

    // Constructeur
    public function __construct($status = 'en attente') {
        $this->status = $status;
    }

    // Méthode pour ajouter un produit à la commande
    public function ajouterProduit(Produit $produit) {
        $this->produits[] = $produit;
    }

    // Méthode pour afficher le détail de la commande
    public function afficherDetails() {
        echo "Statut de la commande : $this->status\n";
        foreach ($this->produits as $produit) {
            echo $produit->afficherDetails();
        }
    }

    // Méthode pour calculer le total de la commande
    public function calculerTotal() {
        $total = 0;
        foreach ($this->produits as $produit) {
            $total += $produit->getPrix();
        }
        return $total;
    }

    // Méthode pour changer le statut de la commande
    public function changerStatut($nouveauStatut) {
        $this->status = $nouveauStatut;
    }
}

// Création de produits
$produit1 = new Produit("Smartphone", 699);
$produit2 = new Produit("Casque audio", 199);

// Création d'une commande
$commande = new Commande();

// Ajout des produits à la commande
$commande->ajouterProduit($produit1);
$commande->ajouterProduit($produit2);

// Affichage des détails de la commande
$commande->afficherDetails();

// Calcul du total de la commande
echo "Total de la commande : " . $commande->calculerTotal() . "\n";

// Changer le statut de la commande
$commande->changerStatut("expédiée");

// Afficher les nouveaux détails de la commande
$commande->afficherDetails();

?>
```


---

# Challenge : Système de Paiement avec Interfaces

## Objectif
Implémenter un système de paiement en ligne en utilisant des **interfaces** et la **programmation orientée objet (POO)** en PHP. Le code contient des erreurs liées à l'utilisation des interfaces et de l'implémentation de méthodes. Il faut résoudre ces erreurs pour que le système fonctionne correctement.

## Code

```php
<?php

// Définition de l'interface Paiement
interface Paiement {
    public function effectuerPaiement($montant);
    public function annulerPaiement();
}

// Définition de la classe PaiementCarte qui implémente l'interface Paiement
class PaiementCarte implements Paiement {
    private $numeroCarte;
    private $nomCarte;
    private $dateExpiration;

    // Constructeur
    public function __construct($numeroCarte, $nomCarte, $dateExpiration) {
        $this->numeroCarte = $numeroCarte;
        $this->nomCarte = $nomCarte;
        $this->dateExpiration = $dateExpiration;
    }

    // Implémentation de la méthode effectuerPaiement
    public function effectuerPaiement($montant) {
        echo "Paiement de $montant effectué avec la carte $this->nomCarte\n";
    }

    // Implémentation de la méthode annulerPaiement
    public function annulerPaiement() {
        echo "Le paiement a été annulé avec la carte $this->nomCarte\n";
    }
}

// Définition de la classe PaiementPayPal qui implémente l'interface Paiement
class PaiementPayPal implements Paiement {
    private $emailPayPal;

    // Constructeur
    public function __construct($emailPayPal) {
        $this->emailPayPal = $emailPayPal;
    }

    // Implémentation de la méthode effectuerPaiement
    public function effectuerPaiement($montant) {
        echo "Paiement de $montant effectué avec PayPal ($this->emailPayPal)\n";
    }

    // Implémentation de la méthode annulerPaiement
    public function annulerPaiement() {
        echo "Le paiement a été annulé via PayPal ($this->emailPayPal)\n";
    }
}

// Classe Commande qui utilise une interface Paiement
class Commande {
    private $paiement;

    // Constructeur
    public function __construct(Paiement $paiement) {
        $this->paiement = $paiement;
    }

    // Méthode pour effectuer le paiement
    public function effectuerCommande($montant) {
        $this->paiement->effectuerPaiement($montant);
    }

    // Méthode pour annuler le paiement
    public function annulerCommande() {
        $this->paiement->annulerPaiement();
    }
}

// Création d'une commande avec paiement par carte
$commandeCarte = new Commande(new PaiementCarte("1234-5678-9876-5432", "John Doe", "12/24"));
$commandeCarte->effectuerCommande(150);
$commandeCarte->annulerCommande();

// Création d'une commande avec paiement PayPal
$commandePayPal = new Commande(new PaiementPayPal("johndoe@example.com"));
$commandePayPal->effectuerCommande(200);
$commandePayPal->annulerCommande();

?>
