# 📢 Guide de Configuration des Notifications

<div align="center">

**Guide complet pour configurer le système de notifications du script ATM Robbery**

[🇬🇧 English Version](NOTIFICATION-EN.md) | [📖 README](README-FR.md)

</div>

---

## 📋 Table des matières

- [Introduction](#-introduction)
- [Configuration rapide](#-configuration-rapide)
- [Systèmes supportés](#-systèmes-supportés)
- [Dépannage](#-dépannage)

---

## 🎯 Introduction

Le script ATM Robbery supporte **9+ systèmes de notifications différents**. Vous pouvez choisir celui que vous utilisez déjà sur votre serveur pour une intégration parfaite.

### Où configurer ?

Dans `config/config.lua`, modifiez cette ligne :

```lua
Config.NotificationSystem = 'esx'
```

Remplacez `'esx'` par le système que vous utilisez (voir liste ci-dessous).

---

## ⚡ Configuration Rapide

### Étape 1 : Identifier votre système

Quel système de notification utilisez-vous actuellement sur votre serveur ?

| Vous utilisez | Valeur à mettre |
|---------------|-----------------|
| ESX par défaut | `'esx'` |
| QBCore par défaut | `'qb'` |
| ox_lib | `'ox_lib'` |
| very_notify | `'very_notify'` |
| okokNotify | `'okokNotify'` |
| Mythic Notify | `'mythic_notify'` |
| T-Notify | `'t-notify'` |
| pNotify | `'pNotify'` |
| Aucun système / Chat | `'chat'` |

### Étape 2 : Modifier la config

```lua
Config.NotificationSystem = 'votre_choix'
```

### Étape 3 : Redémarrer

```bash
restart very_advanced_atm_heist_system
```

✅ C'est fait !

---

## 📚 Systèmes Supportés

### 1️⃣ ESX Notification (Natif)

**Nom du système :** `'esx'`

```lua
Config.NotificationSystem = 'esx'
```

**Requis :**
- ✅ ESX Legacy installé
- ✅ Aucune dépendance supplémentaire

**Apparence :**
- Notification native ESX en haut à droite
- Style GTA V classique

**Avantages :**
- ✅ Aucune installation requise
- ✅ Fonctionne directement avec ESX
- ✅ Léger et rapide

---

### 2️⃣ QBCore Notification (Natif)

**Nom du système :** `'qb'`

```lua
Config.NotificationSystem = 'qb'
```

**Requis :**
- ✅ QBCore installé
- ✅ Aucune dépendance supplémentaire

**Apparence :**
- Notification native QBCore en haut
- Couleurs selon le type (succès/erreur/info)

**Avantages :**
- ✅ Aucune installation requise
- ✅ Fonctionne directement avec QBCore
- ✅ Support des types de notifications

---

### 3️⃣ ox_lib (Moderne)

**Nom du système :** `'ox_lib'`

```lua
Config.NotificationSystem = 'ox_lib'
```

**Requis :**
- ✅ ox_lib installé et démarré

**Installation ox_lib :**
```cfg
ensure ox_lib
ensure very_advanced_atm_heist_system
```

**Apparence :**
- Notifications modernes en haut à droite
- Design épuré et professionnel
- Icônes et couleurs

**Avantages :**
- ✅ Très beau design
- ✅ Animations fluides
- ✅ Léger et optimisé

---

---

### 4️⃣ Very Notify (Notre Système)

**Nom du système :** `'very_notify'`

```lua
Config.NotificationSystem = 'very_notify'
```

**Requis :**
- ✅ very_notify installé et démarré (notre script de notifications)

**Installation very_notify :**
```cfg
ensure very_notify
ensure very_advanced_atm_heist_system
```

**Apparence :**
- Design moderne et personnalisé
- Notifications élégantes
- Optimisé pour nos scripts
- Sons avec notification
- Couleurs selon le type :
  - 🟢 Succès = Vert
  - 🔴 Erreur = Rouge
  - 🟠​ Avertissement = Orange
  - 🔵​ Info = Bleu

**Avantages :**
- ✅ Parfaitement intégré avec nos scripts
- ✅ Design cohérent
- ✅ Support garanti

**Où l'obtenir :**
- Disponible sur notre Github (Free)
- Compatible avec tous nos scripts Very Developpement

---

### 5️⃣ okokNotify (Populaire)

**Nom du système :** `'okokNotify'`

```lua
Config.NotificationSystem = 'okokNotify'
```

**Requis :**
- ✅ okokNotify installé et démarré

**Installation okokNotify :**
```cfg
ensure okokNotify
ensure very_advanced_atm_heist_system
```

**Apparence :**
- Notifications personnalisables
- Titre et description
- Durée de 5 secondes

**Avantages :**
- ✅ Très populaire
- ✅ Beau design
- ✅ Hautement personnalisable

**Lien :** [okokNotify sur GitHub](https://github.com/okok-dev/okokNotify)

---

### 6️⃣ Mythic Notify (Léger)

**Nom du système :** `'mythic_notify'`

```lua
Config.NotificationSystem = 'mythic_notify'
```

**Requis :**
- ✅ mythic_notify installé et démarré

**Installation mythic_notify :**
```cfg
ensure mythic_notify
ensure very_advanced_atm_heist_system
```

**Apparence :**
- Notifications en haut de l'écran
- Style minimaliste
- Couleurs selon le type

**Avantages :**
- ✅ Très léger
- ✅ Performance optimale
- ✅ Simple et efficace

---

### 7️⃣ T-Notify (Personnalisable)

**Nom du système :** `'t-notify'`

```lua
Config.NotificationSystem = 't-notify'
```

**Requis :**
- ✅ t-notify installé et démarré

**Installation t-notify :**
```cfg
ensure t-notify
ensure very_advanced_atm_heist_system
```

**Apparence :**
- Notifications personnalisables
- Position configurable
- Styles variés

**Avantages :**
- ✅ Très flexible
- ✅ Nombreuses options
- ✅ Animations personnalisables

---

### 8️⃣ pNotify (Classique)

**Nom du système :** `'pNotify'`

```lua
Config.NotificationSystem = 'pNotify'
```

**Requis :**
- ✅ pNotify installé et démarré

**Installation pNotify :**
```cfg
ensure pNotify
ensure very_advanced_atm_heist_system
```

**Apparence :**
- Notifications en haut à droite (centerRight)
- Style classique
- Durée de 5 secondes

**Avantages :**
- ✅ Stable et fiable
- ✅ Largement utilisé
- ✅ Compatible ancien système

---

### 9️⃣ Chat (Fallback)

**Nom du système :** `'chat'`

```lua
Config.NotificationSystem = 'chat'
```

**Requis :**
- ✅ Aucune dépendance

**Apparence :**
- Messages dans le chat
- Couleurs selon le type :
  - 🟢 Succès = Vert
  - 🔴 Erreur = Rouge
  - ⚪ Info = Blanc

**Avantages :**
- ✅ Fonctionne toujours
- ✅ Aucune installation
- ✅ Solution de secours universelle

**Quand l'utiliser :**
- Si aucun système de notification n'est installé
- Pour tester rapidement
- Comme solution temporaire

---

## 🔧 Dépannage

### ❌ Les notifications ne s'affichent pas

**Problème :** Vous ne voyez aucune notification

**Solutions :**

1. **Vérifiez la configuration**
   ```lua
   -- Dans config/config.lua
   Config.NotificationSystem = 'esx' -- Vérifiez la valeur
   ```

2. **Vérifiez que le système est installé**
   ```bash
   # Dans votre console serveur
   restart votre_systeme_notification
   restart very_advanced_atm_heist_system
   ```

3. **Testez avec le chat**
   ```lua
   Config.NotificationSystem = 'chat'
   ```
   Si ça fonctionne, le problème vient de votre système de notification.

4. **Vérifiez les logs**
   - Appuyez sur F8 dans le jeu
   - Regardez s'il y a des erreurs

5. **Vérifiez l'ordre de démarrage**
   ```cfg
   # Dans server.cfg
   ensure votre_systeme_notification  # AVANT
   ensure very_advanced_atm_heist_system           # APRÈS
   ```

6. **Contacter notre support**
   - Discord : https://discord.gg/WZXVMz9WuU
   - Email : very.developpement@gmail.com

---

### ❌ Mauvais type de notification

**Problème :** Les notifications apparaissent mais avec le mauvais style

**Solution :**

Certains systèmes utilisent des noms différents pour les types :
- `success` = succès
- `error` = erreur  
- `info` = information
- `warning` = avertissement

Le script convertit automatiquement, mais si ça ne fonctionne pas, changez de système de notification.

---

### ❌ Notifications en double

**Problème :** Vous recevez 2 notifications (une ESX + une autre)

**Solution :**

Cela ne devrait **pas** arriver avec ce script. Si c'est le cas :
1. Vérifiez que vous n'avez pas modifié le script (il est crypté)
2. Vérifiez qu'aucun autre script n'intercepte les notifications
3. Contactez le support (Aucun support ne sera accepter en cas de décryptage du script) :
    - Discord: https://discord.gg/WZXVMz9WuU
    - Email: very.developpement@gmail.com

---

### ❌ "Module not found" / "Export not found"

**Problème :** Erreur dans les logs serveur

**Solution :**

Le système de notification configuré n'est pas installé ou pas démarré.

```cfg
# Ajoutez dans server.cfg AVANT very_advanced_atm_heist_system
ensure ox_lib           # Par exemple
ensure okokNotify       # Ou celui que vous utilisez
```

---

## 💡 Conseils & Recommandations

### Quel système choisir ?

| Priorité | Système recommandé | Pourquoi |
|----------|-------------------|----------|
| **Simplicité** | `'esx'` ou `'qb'` | Déjà installé avec le framework |
| **Moderne et Esthétique** | `'very_notify'` | Design moderne avec son et optimisé pour nos scripts |
| **Esthétique** | `'ox_lib'` ou `'okokNotify'` | Design moderne et beau |
| **Performance** | `'mythic_notify'` | Très léger |
| **Compatibilité** | `'chat'` | Fonctionne partout |

### Performances

Tous les systèmes sont légers et optimisés. La différence de performance est négligeable.

### Cohérence visuelle

**Recommandation :** Utilisez le même système de notification que vos autres scripts pour une expérience utilisateur cohérente.

---

## 📞 Besoin d'aide ?

Si vous avez des problèmes avec les notifications :

1. **Relisez ce guide** en entier
2. **Testez avec `'chat'`** pour isoler le problème
3. **Vérifiez les logs** (F8 en jeu)
4. **Contactez le support** avec ces informations :
   - Système de notification utilisé
   - Version de votre framework
   - Messages d'erreur (screenshot)
   - Extrait de votre config.lua

   **!!! IMPORTANT !!!** - Aucun demande de support ne sera traiter en cas de décryptage de notre script !

**Support :**
- Discord : https://discord.gg/WZXVMz9WuU
- Email : very.developpement@gmail.com

---

<div align="center">

### Bon braquage ! 🏧💰

[⬆️ Retour en haut](#-guide-de-configuration-des-notifications) | [📖 Retour au README](README-FR.md)

</div>