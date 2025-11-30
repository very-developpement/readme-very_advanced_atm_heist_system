# 📢 Notification Configuration Guide

<div align="center">

**Complete guide to configure the ATM Robbery script notification system**

[🇫🇷 Version Française](NOTIFICATION-FR.md) | [📖 README](README-EN.md)

</div>

---

## 📋 Table of Contents

- [Introduction](#-introduction)
- [Quick Setup](#-quick-setup)
- [Supported Systems](#-supported-systems)
- [Troubleshooting](#-troubleshooting)

---

## 🎯 Introduction

The ATM Robbery script supports **9+ different notification systems**. You can choose the one you already use on your server for perfect integration.

### Where to configure?

In `config/config.lua`, modify this line:

```lua
Config.NotificationSystem = 'esx'
```

Replace `'esx'` with the system you use (see list below).

---

## ⚡ Quick Setup

### Step 1: Identify your system

Which notification system are you currently using on your server?

| You use | Value to set |
|---------|--------------|
| ESX default | `'esx'` |
| QBCore default | `'qb'` |
| ox_lib | `'ox_lib'` |
| very_notify | `'very_notify'` |
| okokNotify | `'okokNotify'` |
| Mythic Notify | `'mythic_notify'` |
| T-Notify | `'t-notify'` |
| pNotify | `'pNotify'` |
| No system / Chat | `'chat'` |

### Step 2: Modify config

```lua
Config.NotificationSystem = 'your_choice'
```

### Step 3: Restart

```bash
restart very_advanced_atm_heist_system
```

✅ Done!

---

## 📚 Supported Systems

### 1️⃣ ESX Notification (Native)

**System name:** `'esx'`

```lua
Config.NotificationSystem = 'esx'
```

**Required:**
- ✅ ESX Legacy installed
- ✅ No additional dependencies

**Appearance:**
- Native ESX notification top right
- Classic GTA V style

**Advantages:**
- ✅ No installation required
- ✅ Works directly with ESX
- ✅ Lightweight and fast

---

### 2️⃣ QBCore Notification (Native)

**System name:** `'qb'`

```lua
Config.NotificationSystem = 'qb'
```

**Required:**
- ✅ QBCore installed
- ✅ No additional dependencies

**Appearance:**
- Native QBCore notification at top
- Colors according to type (success/error/info)

**Advantages:**
- ✅ No installation required
- ✅ Works directly with QBCore
- ✅ Notification type support

---

### 3️⃣ ox_lib (Modern)

**System name:** `'ox_lib'`

```lua
Config.NotificationSystem = 'ox_lib'
```

**Required:**
- ✅ ox_lib installed and started

**ox_lib Installation:**
```cfg
ensure ox_lib
ensure very_advanced_atm_heist_system
```

**Appearance:**
- Modern notifications top right
- Clean and professional design
- Icons and colors

**Advantages:**
- ✅ Beautiful design
- ✅ Smooth animations
- ✅ Lightweight and optimized

---

### 4️⃣ Very Notify (Our System)

**System Name:** `'very_notify'`

```lua
Config.NotificationSystem = 'very_notify'
```

**Requirements:**
- ✅ very_notify installed and running (our notification script)

**very_notify Installation:**
```cfg
ensure very_notify
ensure very_advanced_atm_heist_system
```

**Appearance:**
- Modern and custom design
- Clean and elegant notifications
- Optimized for our scripts
- Notification sounds
- Color-coded by type:
   - 🟢 Success = Green
   - 🔴 Error = Red
   - 🟠 Warning = Orange
   - 🔵 Info = Blue

**Advantages:**
- ✅ Fully integrated with our scripts
- ✅ Consistent design
- ✅ Guaranteed support

**Where to get it:**
- Available on our GitHub (Free)
- Compatible with all our Very Development scripts

---

### 5️⃣ okokNotify (Popular)

**System name:** `'okokNotify'`

```lua
Config.NotificationSystem = 'okokNotify'
```

**Required:**
- ✅ okokNotify installed and started

**okokNotify Installation:**
```cfg
ensure okokNotify
ensure very_advanced_atm_heist_system
```

**Appearance:**
- Customizable notifications
- Title and description
- 5 seconds duration

**Advantages:**
- ✅ Very popular
- ✅ Beautiful design
- ✅ Highly customizable

**Link:** [okokNotify on GitHub](https://github.com/okok-dev/okokNotify)

---

### 6️⃣ Mythic Notify (Lightweight)

**System name:** `'mythic_notify'`

```lua
Config.NotificationSystem = 'mythic_notify'
```

**Required:**
- ✅ mythic_notify installed and started

**mythic_notify Installation:**
```cfg
ensure mythic_notify
ensure very_advanced_atm_heist_system
```

**Appearance:**
- Notifications at top of screen
- Minimalist style
- Colors according to type

**Advantages:**
- ✅ Very lightweight
- ✅ Optimal performance
- ✅ Simple and effective

---

### 7️⃣ T-Notify (Customizable)

**System name:** `'t-notify'`

```lua
Config.NotificationSystem = 't-notify'
```

**Required:**
- ✅ t-notify installed and started

**t-notify Installation:**
```cfg
ensure t-notify
ensure very_advanced_atm_heist_system
```

**Appearance:**
- Customizable notifications
- Configurable position
- Various styles

**Advantages:**
- ✅ Very flexible
- ✅ Many options
- ✅ Customizable animations

---

### 8️⃣ pNotify (Classic)

**System name:** `'pNotify'`

```lua
Config.NotificationSystem = 'pNotify'
```

**Required:**
- ✅ pNotify installed and started

**pNotify Installation:**
```cfg
ensure pNotify
ensure very_advanced_atm_heist_system
```

**Appearance:**
- Notifications top right (centerRight)
- Classic style
- 5 seconds duration

**Advantages:**
- ✅ Stable and reliable
- ✅ Widely used
- ✅ Legacy system compatible

---

### 9️⃣ Chat (Fallback)

**System name:** `'chat'`

```lua
Config.NotificationSystem = 'chat'
```

**Required:**
- ✅ No dependencies

**Appearance:**
- Messages in chat
- Colors according to type:
  - 🟢 Success = Green
  - 🔴 Error = Red
  - ⚪ Info = White

**Advantages:**
- ✅ Always works
- ✅ No installation
- ✅ Universal fallback solution

**When to use:**
- If no notification system is installed
- To test quickly
- As temporary solution

---

## 🔧 Troubleshooting

### ❌ Notifications don't appear

**Problem:** You see no notifications

**Solutions:**

1. **Check configuration**
   ```lua
   -- In config/config.lua
   Config.NotificationSystem = 'esx' -- Check value
   ```

2. **Check system is installed**
   ```bash
   # In your server console
   restart your_notification_system
   restart very_advanced_atm_heist_system
   ```

3. **Test with chat**
   ```lua
   Config.NotificationSystem = 'chat'
   ```
   If it works, the problem is with your notification system.

4. **Check logs**
   - Press F8 in game
   - Look for errors

5. **Check start order**
   ```cfg
   # In server.cfg
   ensure your_notification_system  # BEFORE
   ensure very_advanced_atm_heist_system         # AFTER
   ```

6. **Contact Our Support**
    - Discord: https://discord.gg/WZXVMz9WuU
    - Email: very.developpement@gmail.com

---

### ❌ Wrong notification type

**Problem:** Notifications appear but with wrong style

**Solution:**

Some systems use different names for types:
- `success` = success
- `error` = error
- `info` = information
- `warning` = warning

The script converts automatically, but if it doesn't work, change the notification system.

---

### ❌ Double notifications

**Problem:** You receive 2 notifications (one ESX + another)

**Solution:**

This should **NOT** happen with this script. If it does:
1. Check you haven't modified the script (it's encrypted)
2. Check no other script intercepts notifications
3. Contact support (No support will be accepted if the script has been decrypted) :
    - Discord: https://discord.gg/WZXVMz9WuU
    - Email: very.developpement@gmail.com

---

### ❌ "Module not found" / "Export not found"

**Problem:** Error in server logs

**Solution:**

The configured notification system is not installed or not started.

```cfg
# Add in server.cfg BEFORE very_advanced_atm_heist_system
ensure ox_lib           # For example
ensure okokNotify       # Or the one you use
```

---

## 💡 Tips & Recommendations

### Which system to choose?

| Priority | Recommended System | Why |
|----------|-------------------|-----|
| **Simplicity** | `'esx'` or `'qb'` | Already installed with framework |
| **Modern and Aesthetic** | `'very_notify'` | Modern design with sound, optimized for our scripts |
| **Aesthetics** | `'ox_lib'` or `'okokNotify'` | Modern and beautiful design |
| **Performance** | `'mythic_notify'` | Very lightweight |
| **Compatibility** | `'chat'` | Works everywhere |

### Performance

All systems are lightweight and optimized. Performance difference is negligible.

### Visual Consistency

**Recommendation:** Use the same notification system as your other scripts for consistent user experience.

---

## 📞 Need Help?

If you have problems with notifications:

1. **Reread this guide** entirely
2. **Test with `'chat'`** to isolate the problem
3. **Check logs** (F8 in game)
4. **Contact support** with this information:
   - Notification system used
   - Framework version
   - Error messages (screenshot)
   - Excerpt from your config.lua

**Support:**
- Discord : https://discord.gg/WZXVMz9WuU
- Email : very.developpement@gmail.com

---

<div align="center">

### Happy Robbing! 🏧💰

[⬆️ Back to top](#-notification-configuration-guide) | [📖 Back to README](README-EN.md)

</div>