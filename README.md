# 🔐 Infrastructure IT & Cybersecurity Lab

 > Lab personnel d'administration systèmes, réseaux et cybersécurité
 > basé sur Windows Server, Active Directory, Linux, pfSense et Wazuh.

---

## 🎯 Objectif du projet

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

## 🏗️ Architecture

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

