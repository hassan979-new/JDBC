
# 🧮 JDBC

## 📘 Description

Ces projets illustrent l’utilisation de JDBC en Java pour interagir avec une base de données MySQL, en appliquant les principes de la programmation orientée objet :

- Connexion JDBC avec gestion centralisée via une classe singleton

- Création et manipulation de tables SQL avec requêtes dynamiques

- DAO générique pour l’abstraction des opérations CRUD

- Services métiers pour encapsuler la logique applicative

- Tests unitaires pour valider les opérations sur les entités

- Agrégation d’objets (ex. une machine liée à un employé)

## 📂 Project Structure
````
projets/
├── JavaApplication1/
│   └── Source Packages/
│      └── javaapplication1/
│          └── ExoJDBC.java
├── GestionEmployeMachine/
│   └── Source Packages/
│       ├── app/
│       │   ├── TestEmploye.java
│       │   └── TestMachine.java
│       ├── dao/
│       │   ├── IDao.java
│       │   ├── EmployeDao.java
│       │   └── MachineDao.java
│       ├── entities/
│       │   ├── Employe.java
│       │   └── Machine.java
│       ├── service/
│       │   ├── EmployeService.java
│       │   └── MachineService.java
│       └── util/
│           └── Connexion.java
└── README.md
````


## ⚙️ Features

### **1.** ExoJDBC – Requêtes SQL avec JDBC et statistiques 
Classe ExoJDBC

Méthodes :

- Connexion à la base atelier via DriverManager

- Création de la table DevData avec colonnes : Developpeurs, Jour, NbScripts

- Insertion de données manuelles

Requêtes :

- MAX(NbScripts) par jour

- Classement des développeurs par total de scripts

- Total hebdomadaire

- Total pour un développeur donné via PreparedStatement

### **2.** GestionEmployeMachine – DAO, services et entités liées 
Classe Employe

- Attributs privés : id, nom, poste

Méthodes :

- Getters/setters pour chaque attribut

- Constructeurs avec ou sans identifiant

Classe Machine

- Attributs privés : id, nom, type, employe (objet Employe)

Méthodes :

- Getters/setters pour chaque attribut

- Constructeurs avec ou sans identifiant

Interface IDao<T>

Méthodes :

- findById(id)

- findAll()

- insert(obj)

- update(obj)

- delete(id)

Classe EmployeDao (implémente IDao<Employe>)

Méthodes :

- Requêtes SQL pour gérer les employés (CRUD)

- Utilisation de PreparedStatement et Statement

Classe MachineDao (implémente IDao<Machine>)

Méthodes :

- Requêtes SQL pour gérer les machines (CRUD)

- Appels à EmployeDao pour récupérer l’employé lié

Classe EmployeService

Méthodes :

- createEmploye(e)

- listEmployes()

- updateEmploye(e)

- deleteEmploye(e)

- getEmploye(e)

Classe MachineService

Méthodes :

- createMachine(m)

- listMachines()

- updateMachine(m)

- deleteMachine(m)

- getMachine(m)

Classe Connexion

- Attributs privés : conn (objet Connection)

Méthodes :

- getInstance() : singleton JDBC

- getConnection() : retourne la connexion active
## 🖥️ Example Execution


### Suivi des Scripts des Développeurs :

### Gestion des Machines et Employés (JDBC en Couches) : 



## 💡 Concepts Practiced

- Utiliser JDBC pour interagir avec une base MySQL

- Implémenter un DAO générique pour factoriser les opérations CRUD

- Créer des services métiers pour isoler la logique applicative

- Manipuler des relations entre entités (ex. machine → employé)

- Organiser les projets en packages modulaires

- Gérer les connexions avec un singleton sécurisé
## 🧑‍💻 Author

- 👤 Agouram Hassan
- 🏫 Programmation orientée objet : java
- 🎓 Instructor	Mr.LACHGAR
- 📅 10	novembre 2025
