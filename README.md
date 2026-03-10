# Test d'Admission MSc Cybersécurité - La Plateforme_
**Candidat :** Maxime CHAPMAN

Ce dépôt contient les solutions techniques pour les trois exercices du test d'entrée.

---

## Exercice 01 : Architecture Réseau (Packet Tracer)

### Objectif
Conception et configuration d'un réseau segmenté (MiniLab) pour trois bureaux avec isolation des flux et accès Internet.

### Processus réalisé
1. **Segmentation L2 (VLANs) :** Création des VLANs 1 (VoIP), 10 (Wi-Fi), 20 (PC Fixes) et 30 (Administration) sur trois commutateurs Cisco 2960.
2. **Configuration des accès :** Assignation rigoureuse des ports selon le cahier des charges.
3. **Interconnexion (Trunks) :** Mise en place de liaisons Trunk (dot1Q) sur les ports 1 et 9 pour permettre le passage multi-VLAN entre les équipements.
4. **Routage Inter-VLAN (L3) :** Configuration d'un routeur 1941 via des sous-interfaces (Router-on-a-stick).
5. **Automatisation IP :** Mise en place de pools DHCP dédiés sur le routeur pour chaque segment réseau.



## Exercice 02 : Automatisation Active Directory (PowerShell)

### Objectif
Automatiser la création de comptes utilisateurs dans le domaine `laplateforme.local` à partir d'un export RH au format CSV.

### Processus réalisé
1. **Analyse des données :** Structuration d'un fichier `utilisateurs.csv` incluant Nom, Prénom, Fonction et Service.
2. **Développement du script :** - Importation dynamique des données via `Import-Csv`.
    - Génération automatique des comptes (format `prenom.nom`).
    - Assignation aux Unités d'Organisation (OU) correspondantes au service de l'employé.
3. **Sécurisation :** Définition d'un mot de passe complexe par défaut (`Azerty_2025!`) avec activation de l'attribut `ChangePasswordAtLogon` pour forcer le renouvellement dès la première connexion.



## Exercice 03 : Conteneurisation (Docker)

### Objectif
Déploiement d'une stack LEMP complète pour héberger un site WordPress fonctionnel.

### Processus réalisé
1. **Architecture Micro-services :** Utilisation de `docker-compose` pour orchestrer trois conteneurs distincts :
    - **Nginx :** Serveur web faisant office de Reverse Proxy.
    - **MariaDB :** Base de données SQL isolée.
    - **WordPress (PHP-FPM) :** Moteur applicatif.
2. **Gestion des volumes :** Mise en place de volumes nommés (`db_data`, `wp_data`) pour assurer la persistance des données et le partage de configuration entre PHP et Nginx.
3. **Réseau :** Les conteneurs communiquent via un réseau interne Docker, sécurisant ainsi la base de données qui n'est pas exposée sur le port public.
