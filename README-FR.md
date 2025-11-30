# Boutique : https://very-developpement.tebex.io/

# 🏧 Script de Braquage d'ATM - FiveM

<div align="center">

![Version](https://img.shields.io/badge/version-2.0.0-blue.svg)
![FiveM](https://img.shields.io/badge/FiveM-Ready-green.svg)
![License](https://img.shields.io/badge/license-Commercial-red.svg)

**Un script professionnel et optimisé pour braquer les distributeurs automatiques avec un système d'alerte immersif**

[🇬🇧 English Version](README-EN.md) | [📖 Guide Notifications FR](NOTIFICATION-FR.md)

</div>

---

## 📋 Table des matières

- [Caractéristiques](#-caractéristiques)
- [Prérequis](#-prérequis)
- [Installation](#-installation)
- [Configuration](#️-configuration)
- [Utilisation](#-utilisation)
- [Compatibilité](#-compatibilité)
- [Sécurité](#-sécurité)
- [Support](#-support)

---

## ✨ Caractéristiques

### 🎮 Gameplay Immersif
- ✅ **Braquage réaliste** avec animation ATM
- ✅ **Système de cooldown intelligent** par distributeur
- ✅ **Vérification policière** - Nombre minimum de policiers requis
- ✅ **Item requis** - Clé USB nécessaire pour pirater
- ✅ **Mini-jeu optionnel** - Support mhacking
- ✅ **Récompenses aléatoires** - Entre min et max configurables

### 👮 Système Police Avancé
- 🚨 **Notifications instantanées** pour tous les policiers en service
- 📍 **Blip temporaire** sur la carte avec durée configurable
- 📺 **Alerte "Breaking News"** style chaîne d'info en continu
- 🎯 **Nom de rue automatique** dans l'alerte

### 🎨 Interface Moderne
- 💬 **Notification d'interaction** propre et discrète (haut gauche)
- 📰 **Bande défilante "Breaking News"** en bas d'écran
- 🖼️ **Logo personnalisable** - Remplacez facilement le logo
- 📱 **Design responsive** - S'adapte à toutes les résolutions
- 🎨 **100% NUI** - Fonctionne même avec des HUD custom

### 🌍 Système Multilingue
- 🇫🇷 **Français** - Traduction complète
- 🇬🇧 **Anglais** - Traduction complète
- 🔄 **Changement à chaud** - Modifiez la langue dans la config (fr ou en)

### 🔔 Compatibilité Notifications (9+ systèmes)
- ✅ **ESX Notification** (natif)
- ✅ **QBCore Notification** (natif)
- ✅ **ox_lib** (moderne)
- ✅ **very_notify** (Notre system de notification. Moderne avec sons et optimisé pour nos scripts)
- ✅ **okokNotify** (populaire)
- ✅ **mythic_notify** (léger)
- ✅ **t-notify** (personnalisable)
- ✅ **pNotify** (classique)
- ✅ **Chat** (fallback)

> 📖 [Voir le guide complet des notifications](NOTIFICATION-FR.md)

### 🛠️ Multi-Framework & Multi-Inventaire

**Frameworks supportés :**
- ✅ **ESX Legacy** (toutes versions)
- ✅ **QBCore** (toutes versions)

**Systèmes d'inventaire supportés :**
- ✅ **ESX Inventory** (natif)
- ✅ **QBCore Inventory** (natif)
- ✅ **ox_inventory** (moderne)
- ✅ **Standalone** (sans dépendances)

---

## 📦 Prérequis

### Obligatoire
- ✅ **FiveM Server** (dernière version recommandée)
- ✅ **ESX Legacy** OU **QBCore** (au choix)
- ✅ **MySQL or oxmysql** (pour la base de données)

### Optionnel
- 🎮 **mhacking** - Pour activer le mini-jeu de hack
- 🔔 **Système de notification** - Voir liste ci-dessus

---

## 📥 Installation

### Étape 1 : Installation du script

1. **Téléchargez** le script depuis votre keymaster après achat
2. **Extrayez** l'archive dans votre dossier `resources/[scripts]/`
3. **Renommez** le dossier en `very_advanced_atm_heist_system` (si nécessaire)

```
votre-serveur/
└── resources/
    └── [scripts]/
        └── very_advanced_atm_heist_system/
            ├── client/ (crypté)
            ├── server/ (crypté)
            ├── config/
            │   ├── config.lua ← MODIFIABLE
            │   └── locales/ (crypté)
            ├── html/
            └── fxmanifest.lua
```

### Étape 2 : Ajout de l'item

#### Pour ESX :
```sql
INSERT INTO `items` (`name`, `label`, `weight`, `rare`, `can_remove`) VALUES
('usb_drive', 'Clé USB', 1, 0, 1);
```

#### Pour QBCore :
Ajoutez dans `qb-core/shared/items.lua` :
```lua
['usb_drive'] = {
    ['name'] = 'usb_drive',
    ['label'] = 'Clé USB',
    ['weight'] = 100,
    ['type'] = 'item',
    ['image'] = 'usb_drive.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'Une clé USB pour pirater les distributeurs'
}
```
#### For ox_inventory
Ajoutez dans `ox_inventory/data/items.lua` :
```lua
['usb_drive'] = {
	label = "USB Drive",
	weight = 100,
}
```

> 💡 **Note :** Ajoutez une image `usb_drive.png` dans votre dossier d'images d'inventaire

### Étape 3 : Configuration du server.cfg

Ajoutez dans votre `server.cfg` :
```cfg
# Dépendances (choisir selon votre serveur)
ensure es_extended  # Pour ESX
# OU
ensure qb-core      # Pour QBCore

# Script ATM Robbery
ensure very_advanced_atm_heist_system
```

> ⚠️ **Important :** Assurez-vous que le script démarre **APRÈS** votre framework

### Étape 4 : Configuration

Éditez `config/config.lua` selon vos besoins (voir section Configuration ci-dessous)

### Étape 5 : Redémarrage

```bash
restart very_advanced_atm_heist_system
# OU redémarrez complètement le serveur
```

---

## ⚙️ Configuration

> 📝 **Note :** Seul le fichier `config/config.lua` est modifiable. Le reste du script est crypté pour votre protection.

### Configuration de base

```lua
-- Framework utilisé
Config.Framework = 'esx' -- 'esx' ou 'qb'

-- Système d'inventaire
Config.Inventory = 'esx' -- 'esx', 'qb', 'ox' ou 'standalone'

-- Langue du script
Config.Locale = 'fr' -- 'fr' ou 'en'

-- Système de notifications (voir NOTIFICATION-FR.md)
Config.NotificationSystem = 'esx'
```

### Paramètres du braquage

```lua
-- Item requis pour pirater
Config.RequiredItem = 'usb_drive'

-- Temps avant de pouvoir braquer à nouveau le même ATM (secondes)
Config.ATMResetTime = 600 -- 10 minutes

-- Durée du hack (secondes)
Config.HackTime = 45

-- Mini-jeu de hack ('mhacking' ou 'none')
Config.Minigame = 'none'
```

### Récompenses

```lua
-- Récompense minimum
Config.MinReward = 500

-- Récompense maximum
Config.MaxReward = 5000

-- Type de récompense
Config.RewardType = 'cash' -- 'cash', 'money' ou 'black_money'
```

> 💡 **Astuce :** 
> - `cash` / `money` = Argent propre
> - `black_money` = Argent sale (nécessite blanchiment)

### Configuration Police

```lua
-- Jobs considérés comme police
Config.PoliceJobs = {
    'police',
    'sheriff',
    -- Ajoutez d'autres jobs ici
}

-- Nombre minimum de policiers en ligne
Config.MinPolice = 1

-- Afficher un blip pour la police
Config.UseBlipForPolice = true

-- Durée du blip en millisecondes
Config.BlipDuration = 60000 -- 1 minute
```

### Système d'alerte BFM

```lua
-- Activer l'alerte "Breaking News"
Config.UseNUIAlert = true

-- Durée de l'alerte en millisecondes
Config.NUIDuration = 15000 -- 15 secondes
```

### Emplacements des ATM

```lua
Config.ATMLocations = {
    vector3(146.97, -1035.2, 29.34),   -- Legion Square
    vector3(-386.7, 6045.95, 31.5),    -- Paleto Bay
    vector3(-132.46, 6366.92, 31.48),  -- Paleto Bay 2
    
    -- Ajoutez autant d'emplacements que vous voulez
    -- vector3(x, y, z),
}
```

> 💡 **Astuce :** Utilisez `/getcoords` ou similar pour obtenir les coordonnées

---

## 🎯 Utilisation

### Pour les joueurs

1. **Obtenez** une clé USB (item configurable)
2. **Approchez-vous** d'un distributeur ATM
3. **Attendez** que la notification "Appuyez sur [G]" apparaisse
4. **Appuyez sur G** pour commencer le hack
5. **Attendez** la fin du hack (ou complétez le mini-jeu)
6. **Récupérez** votre récompense !

> ⏱️ L'ATM sera en cooldown pendant le temps configuré

### Pour la police

Lorsqu'un braquage commence :
- 📱 Vous recevez une notification instantanée
- 📍 Un blip apparaît sur votre carte (si activé)
- 📺 Une alerte "Breaking News" s'affiche
- 🗺️ Le nom de la rue est indiqué

---

## 🔄 Compatibilité

### Frameworks testés ✅
- ESX Legacy 1.8+
- ESX Legacy 1.9+
- QBCore

### Inventaires testés ✅
- ESX Default Inventory
- QBCore Inventory
- ox_inventory
- Standalone (aucun inventaire)

### Systèmes de notifications testés ✅
- Tous les systèmes listés dans [NOTIFICATION-FR.md](NOTIFICATION-FR.md)

---

## 🔒 Sécurité

### Protection du script
- 🔐 **Cryptage complet** - Seul config.lua est modifiable
- 🛡️ **Anti-leak** - Protection contre la copie
- ✅ **Validation serveur** - Toutes les actions importantes
- ⏱️ **Anti-spam** - Système de cooldown
- 🚫 **Anti-exploit** - Vérifications multiples

### Bonnes pratiques
- ✅ Vérification du nombre de policiers (côté serveur)
- ✅ Vérification de l'item requis (côté serveur)
- ✅ Cooldown géré côté serveur
- ✅ Pas de trust client-side
- ✅ Protection contre les modifications

---

## 🐛 Dépannage

### Les notifications ne s'affichent pas
**Solution :**
1. Vérifiez que `Config.NotificationSystem` correspond à votre système
2. Consultez [NOTIFICATION-FR.md](NOTIFICATION-FR.md)
3. Testez avec `Config.NotificationSystem = 'chat'`
4. Contacter notre support

### L'argent n'est pas reçu
**Solution :**
1. Vérifiez `Config.Framework` (esx ou qb)
2. Vérifiez `Config.Inventory` (esx, qb, ox, standalone)
3. Vérifiez `Config.RewardType` (cash, money, black_money)
4. Regardez les logs serveur (F8)
4. Contacter notre support

### Le texte d'interaction ne s'affiche pas
**Solution :**
- C'est normal si vous avez un HUD custom qui bloque les affichages natifs
- Le script utilise maintenant un système NUI qui fonctionne toujours
- La notification apparaît en haut à gauche de l'écran

### "Pas assez de policiers"
**Solution :**
- Vérifiez `Config.MinPolice` (réduisez pour tester)
- Vérifiez que vos jobs police sont dans `Config.PoliceJobs`
- Assurez-vous qu'un policier est bien connecté
- Contacter notre support

### Le script ne démarre pas
**Solution :**
1. Vérifiez que le dossier s'appelle `very_advanced_atm_heist_system`
2. Vérifiez que votre framework est démarré avant
3. Regardez les logs serveur pour les erreurs
4. Contacter notre support

---

## 📞 Support

### Support inclus
- ✅ Installation et configuration
- ✅ Problèmes techniques
- ✅ Questions sur les fonctionnalités
- ✅ Mises à jour (si disponibles)

### Comment obtenir du support
1. **Discord:** https://discord.gg/WZXVMz9WuU
2. **Email:** very.developpement@gmail.com

> ⚠️ **Note :** L'assistance ne couvre pas les modifications personnalisées et ne sera pas fournie si le script a été décrypté.

---

## 📜 Licence & Conditions

### ❌ INTERDIT
- ❌ Revendre ou redistribuer ce script
- ❌ Partager votre licence avec d'autres
- ❌ Modifier les fichiers cryptés
- ❌ Contourner le système de cryptage

### ✅ AUTORISÉ
- ✅ Modifier `config/config.lua` librement
- ✅ Personnaliser `html/ledejinfo.png` (logo)
- ✅ Utiliser sur votre serveur (1 licence = 1 serveur)
- ✅ Demander du support
- ✅ Suggérer des améliorations

### 🔐 Protection
Ce script est protégé par cryptage. Toute tentative de :
- Décryptage
- Reverse engineering
- Partage non autorisé

Entraînera **Un blackliste de notre boutique et de nos serveur communautaire** sans remboursement.

---

## 🎁 Crédits

**Développé avec le ❤️ par Very Developpement**

Version : 2.0.0  
Dernière mise à jour : 29/11/2025

---

<div align="center">

### Merci d'avoir choisi notre script ! 🎉

**Bon jeu et bon braquage ! 🏧💰**

[⬆️ Retour en haut](#-script-de-braquage-datm---fivem)


</div>
