# 🕐 Shadow Copy / VSS

> Mise en place de Shadow Copy sur un serveur de fichiers
> Windows Server afin de permettre la restauration de versions
> précédentes des fichiers.

---

## 🎯 Objectif

L'objectif est de mettre en place Shadow Copy afin de permettre
aux utilisateurs de récupérer une version précédente d'un fichier
sans devoir restaurer l'intégralité du serveur.

---

## 🖥️ Environnement

- Windows Server
- NTFS
- Serveur de fichiers
- Volume de données
- Shadow Copy / VSS
- Active Directory

---

# ⚙️ Configuration

## 1️⃣ Configuration de Shadow Copy

Nous commençons par accéder aux propriétés du volume contenant
les données et configurons les clichés instantanés.

<p align="center">
  <img src="images/01-configurer-les-fichiers-instantanée-pour-la-restauration.png" width="850">
</p>

---

## 2️⃣ Création du dossier de test

Nous créons un dossier permettant de vérifier le fonctionnement
de Shadow Copy.

<p align="center">
  <img src="images/02-ici-nous-avons-notre-dossier-tests-creer.png" width="850">
</p>

---

## 3️⃣ Définition de l'espace disque

Nous définissons l'espace maximal pouvant être utilisé pour
les clichés instantanés.

<p align="center">
  <img src="images/03-ici-on-definit-une-taille.png" width="850">
</p>

---

## 4️⃣ Planification

Nous configurons la planification des clichés instantanés.

<p align="center">
  <img src="images/04-ici-on-planifie.png" width="850">
</p>

---

# 🧪 Test de restauration

Nous effectuons ensuite une modification du fichier afin de
vérifier qu'une version précédente peut être récupérée.

<p align="center">
  <img src="images/05-la-nous-pouvons-voir-qu'il-possibiliter-de-revenir-à-la-version-precedenter.png" width="850">
</p>

---

## activation des clichés

Nous activons nos clichés instantané

<p align="center">
  <img src="06-nous-activons-les-clichés-instantanée.png" width="850">
</p>

---
## 🔄 Restauration
ici nous validons les clichés instantanés, Nous pouvons voir qu'il y'a eu une action
<p align="center">
  <img src="docs/shadow-copy/images/09-validons-les-cliches-instantane-pour-la-retauration.png" width="850">
</p> 
<p align="center">
  <img src="images/08-nous-pouvons-voir-qu'il-y'a-eu-une-action-a15-nous-allons-cliquer-sur-creer.png" width="850">
</p>

---
# ✅ Résultat

La fonctionnalité Shadow Copy permet de conserver des versions
précédentes des fichiers et de restaurer rapidement une donnée
modifiée ou supprimée.

---

# 🧠 Compétences démontrées

- Administration Windows Server
- NTFS
- VSS / Shadow Copy
- Serveur de fichiers
- Gestion des données
- Sauvegarde et restauration
- Dépannage

---

## 🔗 Navigation

[⬅️ Retour au projet principal](../../README.md)

[📁 Serveur de fichiers →](../serveur-fichiers/README.md)