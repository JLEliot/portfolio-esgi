# 📁 Portfolio ESGI - Gestion complète de portfolios en PHP & MySQL

Projet web développé dans le cadre du cursus **ESGI 2024/2025**, permettant la gestion complète de portfolios utilisateurs avec système de rôles, sécurité renforcée, et interface d’administration moderne.

---

## ✨ Fonctionnalités principales

### 🔐 Authentification & Sécurité
- Connexion sécurisée avec `password_hash()`
- Gestion des rôles (admin / utilisateur)
- Option "se souvenir de moi" via cookies sécurisés
- Requêtes préparées et protection contre :
  - XSS
  - Injections SQL
  - CSRF (avec expiration)
- Sessions sécurisées avec nettoyage automatique

### 👤 Gestion des utilisateurs
- Profils complets : avatar, biographie, projets, compétences
- Page **profile.php** avec suppression et modification d’image de profil
- Accès à un **tableau de bord** personnalisé

### 🛠️ Gestion des compétences
- Interface admin : CRUD complet
- Affectation personnalisée par utilisateur avec niveaux
- Tri alphabétique et pagination dynamique

### 📂 Gestion des projets
- CRUD complet : ajout, édition, suppression, image
- Aperçu par modal dynamique avec navigation fluide
- Tri dynamique, champ de recherche en JS
- **Validation sécurisée** pour suppression (phrase obligatoire)
- Affichage responsive

---

## 🖼️ Aperçu du projet

![Aperçu Dashboard](assets/screenshots/dashboard.png)
![Aperçu Modal](assets/screenshots/modal-projet.png)

---

## 🚀 Installation locale

### Prérequis
- PHP 7.4+
- MySQL 5.7+ ou MariaDB
- Serveur local : Apache/Nginx (ou XAMPP/WAMP)

### Étapes

1. **Cloner le projet**

```bash
git clone [URL_DU_REPO]
cd portfolio-esgi
```

2. **Base de données**

```sql
CREATE DATABASE projetb2;
CREATE USER 'projetb2'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON projetb2.* TO 'projetb2'@'localhost';
FLUSH PRIVILEGES;
```

Importer les données :

```bash
mysql -u projetb2 -p projetb2 < config/database.sql
```

3. **Configuration**

- Modifier les identifiants dans `config/database.php`
- Créer le dossier d’uploads :

```bash
mkdir uploads
chmod 755 uploads
```

4. **Lancer le projet**

```bash
php -S localhost:8000
```

Accès : http://localhost:8000

---

## 👤 Comptes de test

| Rôle          | Email               | Mot de passe |
|---------------|---------------------|--------------|
| Administrateur| admin@example.com   | password     |
| Utilisateur 1 | user@example.com    | password     |
| Utilisateur 2 | marie@example.com   | password     |

---

## 🧭 Arborescence du projet

```
portfolio-esgi/
├── admin/
│   ├── add-skill.php
│   ├── edit-user.php
│   ├── edit-project.php
│   ├── delete-skill.php
│   ├── delete-project.php
│   ├── projects.php
│   ├── skills.php
│   ├── users.php
│   └── get-project.php
├── assets/
│   ├── css/style.css
│   └── js/script.js
├── config/
│   └── database.php
├── includes/
│   ├── header.php
│   ├── footer.php
│   └── functions.php
├── uploads/ (images utilisateurs/projets)
├── portfolio.php
├── profile.php
├── dashboard.php
├── index.php
├── login.php / register.php
├── manage-projects.php / manage-skills.php
└── README.md
```

---

## 🛡️ Sécurité intégrée

- `password_hash()` + cookies HttpOnly
- Requêtes préparées PDO
- Anti-CSRF avec tokens jetables
- Uploads sécurisés (format / poids / type)
- Vérifications côté client & serveur

---

## 📊 Base de données

Tables principales :
- `users` : Utilisateurs avec rôles
- `projects` : Projets liés à chaque user
- `skills` : Compétences disponibles
- `user_skills` : Table pivot avec niveaux

---

## 📱 Responsive & UI

- Design mobile-first
- Animations légères CSS
- Compatibilité avec tous les navigateurs modernes
- Affichage fluide avec modals dynamiques

---

## 📮 Idées d'amélioration (futures versions)

- ✅ Recherche AJAX / filtrage instantané
- ✅ Suppression avec validation textuelle anti-copie
- ⏳ Édition rapide en ligne (inline edit)
- ⏳ Support multilingue
- ⏳ Ajout d’un système de tags sur projets

---

## 🧑‍💻 Auteur

- **Nom** : *[À compléter]*
- **Email** : *[email@example.com]*
- **GitHub** : *[github.com/...]*
- Projet réalisé dans le cadre **pédagogique** ESGI 2024/2025.

---

## 📝 Licence

Projet libre de droits à usage **pédagogique uniquement** – réutilisable pour formation, devoirs ou démonstrations.