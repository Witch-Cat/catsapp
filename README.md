# CatsApp

CatsApp est une application de messagerie sécurisée permettant aux utilisateurs de communiquer de manière chiffrée.
Elle utilise Flask pour le backend et MySQL comme base de données. Les utilisateurs peuvent créer un compte avec un nom d'utilisateur unique, ajouter des contacts grâce aux noms d'utilisateurs et échanger par message. Le statut en ligne est affiché lorsque l'utilisateur est connecté. Si aucun mouvement de curseur ou clic pendant 5 minutes, alors le statut passe inactif. Si l'utilisateur se déconnecte, le statut change.

## Table des matières

- [Installation](#installation)
- [Configuration](#configuration)
- [Utilisation](#utilisation)
- [Structure du projet](#structure-du-projet)
- [Sécurité](#sécurité)
- [Améliorations futures](#améliorations-futures)
- [Crédits](#crédits)

## Installation

1. **Cloner le dépôt :**
   ```bash
   git clone https://github.com/Witch-Cat/catsapp.git
   cd catsapp
   ```

2. **Installer les dépendances :**
   ```bash
   pip install -r requirements.txt
   ```

3. **Initialiser la base de données :**
   Assurez-vous que MySQL est installé et en cours d'exécution. Ensuite, exécutez :
   ```bash
   python db.py
   ```

## Configuration

- **Configuration de la base de données :**
  Modifiez le fichier `db.py` pour correspondre à votre configuration MySQL (hôte, utilisateur, mot de passe).

- **Clé secrète de l'application :**
  Changez la valeur de `app.secret_key` dans `app.py` pour une valeur sécurisée en production.

## Utilisation

Pour lancer l'application, exécutez :
```bash
python app.py
```
Ou, si vous utilisez Python 3 :
```bash
python3 app.py
```

Accédez à l'application via votre navigateur à l'adresse `http://127.0.0.1:5000/`.

## Structure du projet

```
database/
│
├── __pycache__/
├── db.py
└── init.sql
static/
│
├── css/
└── img/
templates/
│
├── admin/
│   └── admin_dashboard.html
├── user/
│   ├── base.html
│   ├── chat.html
│   ├── index.html
│   ├── register.html
│   └── settings.html
├── add_user.py
├── app.py
├── encryption.py
├── requirements.txt
├── reset_db.py
├── run.py
└── server.py
```

## Sécurité

- **Chiffrement :** Les messages sont chiffrés à l'aide de clés RSA et AES. Chaque utilisateur possède une paire de clés RSA pour le chiffrement des clés symétriques AES utilisées pour chiffrer les messages.
- **Authentification :** Les mots de passe sont hachés en SHA256 avec `werkzeug.security`.

## Améliorations futures

1. **Restrictions sur les mots de passe :**
   - Implémenter des règles de complexité pour les mots de passe (longueur minimale, caractères spéciaux, chiffres, etc.).

2. **Chiffrement côté frontend :**
   - Ajouter une couche de chiffrement côté client pour protéger les données envoyées au serveur.

3. **Ajout de groupes de conversation :**
   - Ajouter la possibilité de discuter à plus de 2 personnes.

4. **Suppression de contacts :**
   - Ajouter la possibilité de supprimer un contact et les conversations associées.

5. **Photo de profil :**
   - Possibilité de changer de photo de profil dans les paramètres (actuellement non fonctionnel mais présent).

6. **Amélioration de la structure de la page admin :**
   - Repenser la structure de la page d'administration pour une meilleure ergonomie et une gestion plus efficace des utilisateurs.

---

N'hésitez pas à contribuer en améliorant le projet ! Faute de temps, je ne pourrai continuer ce projet, mais je pense que certains auront le temps/courage de le faire ;)

## Crédits
- [rTielemans](https://github.com/rTielemans)
- [sloghult](https://github.com/sloghult)
