
# Liste des Challenges SOLID en PHP

## Challenge 1: **Single Responsibility Principle (SRP)**
### Objectif
Corriger une classe qui viole le principe de la responsabilité unique en PHP. La classe fait trop de choses, et tu dois la refactoriser pour qu’elle se concentre uniquement sur une seule responsabilité.

### Code Initial
```php
class Utilisateur {
    private $nom;
    private $email;
    
    public function __construct($nom, $email) {
        $this->nom = $nom;
        $this->email = $email;
    }

    public function envoyerEmail($message) {
        // Code pour envoyer un email
    }

    public function enregistrerUtilisateur() {
        // Code pour enregistrer l'utilisateur dans la base de données
    }
}
```

### Challenge
- Refactoriser cette classe pour respecter le SRP en séparant l’envoi d’e-mails et l’enregistrement en base de données dans des classes distinctes.

---

## Challenge 2: **Open/Closed Principle (OCP)**
### Objectif
Améliorer une classe qui viole le principe d’ouverture/fermeture. La classe doit être modifiable sans modification du code existant, uniquement en ajoutant de nouvelles fonctionnalités.

### Code Initial
```php
class Calculateur {
    public function calculer($type, $a, $b) {
        if ($type == 'addition') {
            return $a + $b;
        } elseif ($type == 'soustraction') {
            return $a - $b;
        }
    }
}
```

### Challenge
- Ajouter une nouvelle opération, comme la multiplication ou la division, sans modifier le code existant dans la classe `Calculateur`. Utiliser l’héritage ou l’interface pour appliquer le principe OCP.

---

## Challenge 3: **Liskov Substitution Principle (LSP)**
### Objectif
Réparer une hiérarchie de classes qui viole le principe de substitution de Liskov.

### Code Initial
```php
class Oiseau {
    public function voler() {
        echo "Je vole !";
    }
}

class Pingouin extends Oiseau {
    public function voler() {
        throw new Exception("Je ne peux pas voler !");
    }
}
```

### Challenge
- Modifier la classe `Pingouin` pour ne pas violer le LSP. Les sous-classes devraient pouvoir être utilisées de manière interchangeable avec la classe parente sans modifier le comportement attendu.

---

## Challenge 4: **Interface Segregation Principle (ISP)**
### Objectif
Refactoriser une interface trop générale en plusieurs interfaces spécifiques pour respecter le principe de séparation des interfaces.

### Code Initial
```php
interface Machine {
    public function imprimer();
    public function scanner();
    public function faxer();
}

class Imprimante implements Machine {
    public function imprimer() {
        echo "Impression en cours";
    }

    public function scanner() {
        throw new Exception("Impression ne peut pas scanner");
    }

    public function faxer() {
        throw new Exception("Impression ne peut pas faxer");
    }
}
```

### Challenge
- Refactoriser l'interface `Machine` en plusieurs interfaces spécifiques comme `ImprimanteInterface`, `ScannerInterface`, et `FaxInterface`, et faire en sorte que la classe `Imprimante` implémente uniquement les interfaces pertinentes.

---

## Challenge 5: **Dependency Inversion Principle (DIP)**
### Objectif
Appliquer le principe d'inversion de dépendance pour résoudre les problèmes de dépendance entre les classes.

### Code Initial
```php
class Commande {
    private $paiement;

    public function __construct() {
        $this->paiement = new PaiementCarte();
    }

    public function traiterPaiement() {
        $this->paiement->effectuerPaiement(100);
    }
}

class PaiementCarte {
    public function effectuerPaiement($montant) {
        echo "Paiement de $montant effectué avec carte";
    }
}
```

### Challenge
- Refactoriser la classe `Commande` pour qu'elle ne crée pas directement une instance de `PaiementCarte` mais reçoive une dépendance via le constructeur ou un setter. Appliquer le principe DIP pour inverser la dépendance.

---

## Challenge 6: **SOLID Combiné - Refactoring complet**
### Objectif
Refactoriser un projet complet en appliquant l’ensemble des principes SOLID à un code qui viole ces principes.

### Code Initial
```php
class GestionnaireEmploye {
    public function calculerSalaire($type, $salaire) {
        if ($type == 'contrat') {
            return $salaire * 1.1; // augmentation de 10%
        } elseif ($type == 'freelance') {
            return $salaire * 1.2; // augmentation de 20%
        }
    }

    public function envoyerMessage($email, $message) {
        // Code d'envoi d'email
    }
}
```

### Challenge
- Refactoriser la classe `GestionnaireEmploye` pour respecter tous les principes SOLID : appliquer l’Open/Closed Principle, le Single Responsibility Principle, et d’autres principes en divisant cette classe en plusieurs classes ou interfaces.
---

## Challenge Bonus : **Refactorisation d'un Projet PHP**
### Objectif
Prendre un projet existant en PHP et refactoriser son code en utilisant les principes SOLID pour améliorer la maintenabilité et la testabilité.
