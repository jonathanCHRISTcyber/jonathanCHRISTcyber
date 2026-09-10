Objectif :DFS Namespace

Mettre en place un espace de noms DFS basé sur le domaine afin d'abstraire le nom physique du serveur de fichiers.

Technologie utilisée :

Windows Server 2022
DFS Namespace

Résultat :

Accès unifié via \\fotsing.local\Partages
Les utilisateurs ne dépendent plus du nom du serveur.
Préparation de l'infrastructure pour la haute disponibilité avec DFS Replication.

                        fotsing.local
                              │
                              │
                 \\fotsing.local\Partages
                              │
      ┌────────────┬────────────┬────────────┬────────────┐
      │            │            │            │
      RH           IT       Direction   Comptabilite   Public