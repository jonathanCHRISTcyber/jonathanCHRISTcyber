# 🌐 DFS Namespace

> Mise en place d'un espace de noms DFS (Distributed File System)
> permettant de fournir un point d'accès centralisé aux partages
> de fichiers de l'infrastructure.

---

## 🎯 Objectif

L'objectif de cette partie est de mettre en place un
**DFS Namespace** afin de fournir aux utilisateurs un chemin
centralisé permettant d'accéder aux ressources partagées.

Au lieu d'accéder directement à un serveur de fichiers, les
utilisateurs peuvent utiliser un chemin DFS.

Exemple :

```text
\\fotsing.local\DFS

Le namespace permet ainsi d'abstraire l'emplacement physique
des ressources

🖥️ Environnement
```
Windows Server
Active Directory
DFS Namespace
Serveur de fichiers
Windows 10
DNS
Partages réseau
Domaine fotsing.local
```
🏗️ Architecture

```
                    fotsing.local
                          │
                          ▼
                    DFS Namespace
                          │
                    \\fotsing.local\DFS
                          │
             ┌────────────┴────────────┐
             │                         │
             ▼                         ▼
       Serveur principal          Autre serveur
             │                         │
             ▼                         ▼
       Dossiers partagés         Dossiers partagés
```

⚙️ Configuration

1️⃣ Installation du rôle DFS Namespace

Nous commençons par installer le rôle nécessaire à la mise en
place du namespace DFS.

<p align="center"> <img src="./images/installation-du-espace-de-nom-dfs.png" width="850"> </p>

2️⃣ Configuration de l'espace de noms

Nous configurons ensuite le nouvel espace de noms DFS.

<p align="center"> <img src="./images/installation-du-espace-du-nom-dfs.png" width="850"> </p>

Cette étape permet de définir les paramètres nécessaires à la
création du namespace.

3️⃣ Création de l'espace DFS

Nous créons l'espace de noms qui servira de point d'accès
centralisé aux ressources.

<p align="center"> <img src="./images/creation-un-nouveau-espace-DFS.png" width="850"> </p>

4️⃣ Définition du chemin

Nous définissons le chemin du partage qui sera utilisé par
l'espace de noms DFS.

<p align="center"> <img src="./images/chemin-du-partage-a-ajouter.png" width="850"> </p>

5️⃣ Finalisation de l'installation

Une fois les paramètres définis, nous terminons la création
du namespace DFS.

<p align="center"> <img src="./images/installation-terminer.png" width="850"> </p>

📂 Gestion des dossiers DFS

6️⃣ Ajout des dossiers

Nous ajoutons ensuite les dossiers qui seront accessibles
depuis le namespace.

<p align="center"> <img src="./images/nous-ajoutons-nos-dossiers.png" width="850"> </p>

L'utilisateur pourra ainsi accéder aux ressources à partir
d'un chemin logique commun.

7️⃣ Vérification du partage

Nous vérifions que le partage est correctement créé et
accessible.

<p align="center"> <img src="./images/nous-pouvons-voir-que-le-nom-du-partage-est-cache.png" width="850"> </p>

🧪 Tests

8️⃣ Test depuis un poste Windows 10

Nous réalisons ensuite des tests depuis un poste client
Windows 10.

<p align="center"> <img src="./images/la-nous-faisons-des-tests-sur-notre-windows-10-avec-notre-nom-de.png" width="850"> </p>

L'objectif est de vérifier que le poste client peut accéder
correctement à l'espace DFS.

9️⃣ Vérification du namespace

Nous vérifions également que notre namespace DFS est
correctement créé.

<p align="center"> <img src="./images/notre-dfs-est-creer.png" width="850"> </p>

🧪 Scénario de test

```
Création du namespace
        │
        ▼
Définition du partage
        │
        ▼
Ajout des dossiers
        │
        ▼
Création du chemin DFS
        │
        ▼
Test depuis Windows 10
        │
        ▼
Vérification de l'accès
```

✅ Résultat

Le DFS Namespace fournit désormais un point d'accès logique
aux ressources partagées.

Les utilisateurs peuvent accéder aux ressources via le
namespace sans avoir besoin de connaître directement
l'emplacement physique des fichiers.

Exemple :

\\fotsing.local\DFS

** Compétences démontrées **
```
Administration Windows Server
DFS Namespace
Gestion des partages réseau
Active Directory
DNS
Gestion des ressources partagées
Windows 10
Administration des systèmes de fichiers
Dépannage réseau
```

# 🔄 DFS Replication

> Mise en place de la réplication DFS afin de maintenir une copie
> synchronisée des données entre plusieurs serveurs de fichiers.

---

## 🎯 Objectif

L'objectif de cette partie est de mettre en place **DFS Replication
(DFSR)** afin de répliquer automatiquement les données entre
plusieurs serveurs.

La réplication permet de maintenir plusieurs copies synchronisées
d'un même ensemble de données.

---

# 🖥️ Environnement

- Windows Server
- Active Directory
- DFS Replication
- DFS Namespace
- Serveur principal
- Serveur secondaire
- Dossiers partagés
- Windows 10
- Domaine `fotsing.local`

---

# 🏗️ Architecture

```text
                     Active Directory
                            │
                            ▼
                       DFS Replication
                            │
                 ┌──────────┴──────────┐
                 │                     │
                 ▼                     ▼
          Serveur principal      Serveur secondaire
                 │                     │
                 ▼                     ▼
          Dossier partagé        Dossier répliqué
                 │                     │
                 └──────────┬──────────┘
                            │
                            ▼
                    Données synchronisées

⚙️ Configuration

1️⃣ Ajout du deuxième serveur

Nous commençons par ajouter un deuxième serveur qui participera
à la réplication.

<p align="center"> <img src="./images/ajout-du-2ieme-serveur.png" width="850"> </p>

Le deuxième serveur permettra de disposer d'une seconde copie
des données.

2️⃣ Définition du chemin du membre

Nous définissons ensuite le chemin utilisé par le membre du
groupe de réplication.

<p align="center"> <img src="./images/chemin-du-membre.png" width="850"> </p>

3️⃣ Sélection du serveur

Nous sélectionnons le serveur qui participera à la réplication.

<p align="center"> <img src="./images/choisit-notre-serveur.png" width="850"> </p>

4️⃣ Sélection du dossier

Nous sélectionnons ensuite le dossier qui devra être répliqué.

<p align="center"> <img src="./images/choix-du-dossier.png" width="850"> </p>

🔁 Création du groupe de réplication

5️⃣ Création du groupe

Nous créons maintenant le groupe de réplication DFS.

<p align="center"> <img src="./images/creons-notre-replication.png" width="850"> </p>

Le groupe permet de définir les serveurs et les dossiers
participant à la réplication.

6️⃣ Vérification de la réplication

Une fois la configuration terminée, nous vérifions que le
groupe de réplication a bien été créé.

<p align="center"> <img src="./images/il-est-creer-notre-replication.png" width="850"> </p>

7️⃣ Installation de DFS Replication

Nous installons ensuite le rôle DFS Replication sur les serveurs
concernés.

<p align="center"> <img src="./images/installation-du-dfs-replication.png" width="850"> </p>

📁 Configuration du dossier répliqué

8️⃣ Définition du nom du dossier

Nous définissons le nom du dossier utilisé pour la réplication.

<p align="center"> <img src="./images/nom-du-dossier-de-replication.png" width="850"> </p>

9️⃣ Configuration du groupe de réplication

Nous configurons le groupe qui permettra aux serveurs
d'échanger et de synchroniser les données.

<p align="center"> <img src="./images/nous-installons-notre-groupe-de-replication.png" width="850"> </p>

🖥️ Serveur principal

🔟 Définition du serveur principal

Nous définissons le serveur principal utilisé dans notre
topologie de réplication.

<p align="center"> <img src="./images/serveur-principale.png" width="850"> </p>

🌐 Topologie de réplication

1️⃣1️⃣ Choix de la topologie

Nous sélectionnons la topologie utilisée pour la réplication
entre les différents serveurs.

<p align="center"> <img src="./images/topologie-choisit-pour-la-replication.png" width="850"> </p>

La topologie détermine la manière dont les serveurs vont
communiquer entre eux pour synchroniser les données.

🧪 Scénario de test

Le scénario de test est le suivant :

Serveur principal
       │
       │
       ▼
Modification d'un fichier
       │
       ▼
DFS Replication
       │
       ▼
Synchronisation
       │
       ▼
Serveur secondaire
       │
       ▼
Vérification du fichier

🧪 Tests

Nous pouvons vérifier la réplication en :

créant un fichier sur le serveur principal ;
modifiant le fichier ;
vérifiant sa présence sur le serveur secondaire ;
comparant les données entre les deux serveurs.

Exemple :

Serveur principal
       │
       ▼
Test.txt
       │
       ▼
DFS Replication
       │
       ▼
Serveur secondaire
       │
       ▼

Test.txt

✅ Résultat

DFS Replication permet de maintenir une copie synchronisée des
données entre plusieurs serveurs.

Cette configuration permet notamment d'améliorer la disponibilité
des données et de disposer de plusieurs serveurs contenant une
copie des ressources répliquées.

🧠 Compétences démontrées
---
Administration Windows Server
DFS Replication
DFS Namespace
Active Directory
Gestion des serveurs de fichiers
Réplication de données
Synchronisation de fichiers
Gestion des partages
Architecture multi-serveurs
Dépannage
---
🔗 Navigation

[⬅️ Retour au projet principal](../../README.md)
[📁 dhcp →](../dhcp/readme.md)                                                                                                                                                                                                                                                                                        