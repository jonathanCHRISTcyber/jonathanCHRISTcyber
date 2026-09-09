# Infrastructure IT & Cybersecurity Lab

 > Lab personnel d'administration systèmes, réseaux et cybersécurité
 > basé sur Windows Server, Active Directory, Linux, pfSense et Wazuh.

---

## Objectif du projet

Ce projet consiste à construire et administrer une infrastructure
informatique complète dans un environnement de laboratoire.

L'objectif est de mettre en pratique des compétences en :

- Administration Windows Server
- Active Directory
- DNS
- Gestion des utilisateurs et groupes
- Gestion des permissions NTFS
- Partage de fichiers
- Sauvegarde et restauration
- Réplication
- Administration Linux
- Pare-feu et réseau
- Supervision et détection de sécurité
- SIEM avec Wazuh
- Journalisation et audit

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

fotsing.local
│
├── OU-Utilisateurs
│   ├── RH
│   ├── Direction
│   ├── Informatique
│   ├── Comptabilité
│   └── Stagiaire
│
├── OU-Groupe
│   ├── OU-DL
│   └── OU-GG
│
├── OU-Ordinateurs
│
└── OU-Serveurs
🔹 Serveurs
Serveur |	Rôle |	Adresse IP
Serveur1 |	Active Directory / DNS / DHCP / fichiers |	192.168.1.5
DC02	Contrôleur de domaine secondaire |	192.168.1.11
Ubuntu-SOC |	Wazuh / supervision sécurité |	192.168.1.10
pfSense |	Routage / pare-feu |	192.168.1.254

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

