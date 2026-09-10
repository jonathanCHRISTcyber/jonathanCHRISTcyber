# Infrastructure IT & Cybersecurity Lab

 > Lab personnel d'administration systèmes, réseaux et cybersécurité
 > basé sur Windows Server, Active Directory, Linux, pfSense et Wazuh.

---

## Objectif du projet

Ce projet consiste à construire et administrer une infrastructure
informatique complète dans un environnement de laboratoire.

L'objectif est de mettre en pratique des compétences en :

- Déployer une infrastructure Windows Server
- Mettre en place un domaine Active Directory
- Organiser les utilisateurs et les ordinateurs avec des OU
- Créer et gérer des groupes de sécurité
- Mettre en place un serveur de fichiers
- Sécuriser les accès aux données avec les permissions NTFS
- Mettre en place la réplication DFS
- Configurer les sauvegardes
- Mettre en place Shadow Copy / VSS
- Activer l'audit de sécurité Windows
- Déployer un serveur Wazuh
- Installer et connecter des agents Wazuh
- Mettre en place une infrastructure réseau avec pfSense
- Tester la connectivité et la résolution DNS

---

##  Architecture
Le projet repose sur une infrastructure virtualisée reproduisant un environnement
d'entreprise avec plusieurs services Windows et Linux.

###  Infrastructure

- **Active Directory** : gestion centralisée des utilisateurs, groupes et ordinateurs
- **DNS** : résolution de noms du domaine `fotsing.local`
- **DHCP** : attribution dynamique des adresses IP
- **Serveur de fichiers** : partage des données par service
- **Serveur de sauvegarde** : sauvegarde des données et restauration
- **DFS / réplication** : réplication des données entre serveurs
- **Audit Windows** : journalisation des accès aux fichiers
- **Wazuh** : supervision et détection des événements de sécurité
- **pfSense** : routage, filtrage réseau et segmentation
- **Ubuntu Server** : serveur Linux dédié à la supervision et à la sécurité

###  Organisation Active Directory

Le domaine `fotsing.local` est organisé avec plusieurs unités
d'organisation :

```text
fotsing.local
│
├── OU-Utilisateurs
│   ├── RH
│   ├── Direction
│   ├── Informatique
│   ├── Comptabilité
│   └── Stagiaire
│
├── OU-Groupes
│   ├── OU-DL
│   └── OU-GG
│
├── OU-Ordinateurs
│
└── OU-Serveurs
```

## Serveurs
|Serveur |	Rôle |	Adresse IP
|---|---|---|
|Serveur1 |	Active Directory / DNS / DHCP / fichiers |	192.168.1.5
|DC02 |	Contrôleur de domaine secondaire |	192.168.1.11
|Ubuntu-SOC |	Wazuh / supervision sécurité |	192.168.1.10
|pfSense |	Routage / pare-feu |	192.168.1.254

### Environnement

| Machine | Rôle | IP |
|---|---|---|
| Serveur1 | Windows Server / AD DS / DNS / fichiers | 192.168.1.5 |
| DC02 | Contrôleur de domaine secondaire | 192.168.1.11 |
| Ubuntu-SOC | Wazuh Manager / SOC | 192.168.1.10 |
| pfSense | Pare-feu / routage | Lab |

### Domaine

```text
Domaine : fotsing.local
NetBIOS : FOTSING

> Active Directory
Mise en place du domaine `fotsing.local`, des OU, des utilisateurs
et des groupes de sécurité.

## 📸 Architecture du laboratoire

![Architecture réseau](images/architecture.png)