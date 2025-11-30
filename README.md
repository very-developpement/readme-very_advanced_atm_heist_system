# Store : https://very-developpement.tebex.io/

# 🏧 ATM Robbery Script - FiveM

<div align="center">

**A professional and optimized script to rob ATMs with an immersive alert system**

[🇫🇷 Version Française](README-FR.md) | [📖 Notification Guide EN](NOTIFICATION-EN.md)

</div>

---

## 📋 Table of Contents

- [Features](#-features)
- [Requirements](#-requirements)
- [Installation](#-installation)
- [Configuration](#️-configuration)
- [Usage](#-usage)
- [Compatibility](#-compatibility)
- [Security](#-security)
- [Support](#-support)

---

## ✨ Features

### 🎮 Immersive Gameplay
- ✅ **Realistic robbery** with ATM animation
- ✅ **Smart cooldown system** per ATM
- ✅ **Police check** - Minimum number of officers required
- ✅ **Required item** - USB drive needed to hack
- ✅ **Optional minigame** - mhacking support
- ✅ **Random rewards** - Between min and max configurable
- ✅ **Customizable key** - Default: G

### 👮 Advanced Police System
- 🚨 **Instant notifications** for all on-duty officers
- 📍 **Temporary blip** on map with configurable duration
- 📺 **"Breaking News" alert** news channel style
- 🎯 **Automatic street name** in alert

### 🎨 Modern Interface
- 💬 **Clean interaction notification** (top left)
- 📰 **Scrolling "Breaking News" banner** at bottom
- 🖼️ **Customizable logo** - Easy to replace
- 📱 **Responsive design** - Adapts to all resolutions
- 🎨 **100% NUI** - Works even with custom HUDs

### 🌍 Multilingual System
- 🇫🇷 **French** - Complete translation
- 🇬🇧 **English** - Complete translation
- ➕ **Easily extensible** - Add your own languages
- 🔄 **Hot swap** - Change language in config

### 🔔 Notification Compatibility (9+ systems)
- ✅ **ESX Notification** (native)
- ✅ **QBCore Notification** (native)
- ✅ **ox_lib** (modern)
- ✅ **okokNotify** (popular)
- ✅ **mythic_notify** (lightweight)
- ✅ **t-notify** (customizable)
- ✅ **pNotify** (classic)
- ✅ **Chat** (fallback)
- ✅ **Custom system** (yours)

> 📖 [See complete notification guide](NOTIFICATION-EN.md)

### 🛠️ Multi-Framework & Multi-Inventory

**Supported frameworks:**
- ✅ **ESX Legacy** (all versions)
- ✅ **QBCore** (all versions)

**Supported inventory systems:**
- ✅ **ESX Inventory** (native)
- ✅ **QBCore Inventory** (native)
- ✅ **ox_inventory** (modern)
- ✅ **Standalone** (no dependencies)

---

## 📦 Requirements

### Required
- ✅ **FiveM Server** (latest version recommended)
- ✅ **ESX Legacy** OR **QBCore** (your choice)
- ✅ **MySQL** (for database)

### Optional
- 🎮 **mhacking** - To enable hack minigame
- 🔔 **Notification system** - See list above

---

## 📥 Installation

### Step 1: Script Installation

1. **Download** the script from your store
2. **Extract** the archive in your `resources/[scripts]/` folder
3. **Rename** the folder to `very_advanced_atm_heist_system` (if needed)

```
your-server/
└── resources/
    └── [scripts]/
        └── very_advanced_atm_heist_system/
            ├── client/ (encrypted)
            ├── server/ (encrypted)
            ├── config/
            │   ├── config.lua ← EDITABLE
            │   └── locales/ (encrypted)
            ├── html/
            └── fxmanifest.lua (encrypted)
```

### Step 2: Add Item

#### For ESX:
```sql
INSERT INTO `items` (`name`, `label`, `weight`, `rare`, `can_remove`) VALUES
('usb_drive', 'USB Drive', 1, 0, 1);
```

#### For QBCore:
Add in `qb-core/shared/items.lua`:
```lua
['usb_drive'] = {
    ['name'] = 'usb_drive',
    ['label'] = 'USB Drive',
    ['weight'] = 100,
    ['type'] = 'item',
    ['image'] = 'usb_drive.png',
    ['unique'] = false,
    ['useable'] = true,
    ['shouldClose'] = true,
    ['combinable'] = nil,
    ['description'] = 'A USB drive to hack ATMs'
}
```
#### For ox_inventory
Add in `ox_inventory/data/items.lua` :
```lua
['usb_drive'] = {
	label = "USB Drive",
	weight = 100,
}
```

> 💡 **Note:** Add a `usb_drive.png` image in your inventory images folder

### Step 3: server.cfg Configuration

Add in your `server.cfg`:
```cfg
# Dependencies (choose according to your server)
ensure es_extended  # For ESX
# OR
ensure qb-core      # For QBCore

# ATM Robbery Script
ensure very_advanced_atm_heist_system
```

> ⚠️ **Important:** Make sure the script starts **AFTER** your framework

### Step 4: Configuration

Edit `config/config.lua` according to your needs (see Configuration section below)

### Step 5: Restart

```bash
restart very_advanced_atm_heist_system
# OR restart the entire server
```

---

## ⚙️ Configuration

> 📝 **Note:** Only `config/config.lua` is editable. The rest of the script is encrypted for your protection.

### Basic Configuration

```lua
-- Framework used
Config.Framework = 'esx' -- 'esx' or 'qb'

-- Inventory system
Config.Inventory = 'esx' -- 'esx', 'qb', 'ox' or 'standalone'

-- Script language
Config.Locale = 'en' -- 'fr' or 'en'

-- Notification system (see NOTIFICATION-EN.md)
Config.NotificationSystem = 'esx'
```

### Robbery Settings

```lua
-- Item required to hack
Config.RequiredItem = 'usb_drive'

-- Time before being able to rob the same ATM again (seconds)
Config.ATMResetTime = 600 -- 10 minutes

-- Hack duration (seconds)
Config.HackTime = 45

-- Hack minigame ('mhacking' or 'none')
Config.Minigame = 'none'
```

### Rewards

```lua
-- Minimum reward
Config.MinReward = 500

-- Maximum reward
Config.MaxReward = 5000

-- Reward type
Config.RewardType = 'cash' -- 'cash', 'money' or 'black_money'
```

> 💡 **Tip:** 
> - `cash` / `money` = Clean money
> - `black_money` = Dirty money (requires laundering)

### Police Configuration

```lua
-- Jobs considered as police
Config.PoliceJobs = {
    'police',
    'sheriff',
    -- Add other jobs here
}

-- Minimum number of online officers
Config.MinPolice = 1

-- Show blip for police
Config.UseBlipForPolice = true

-- Blip duration in milliseconds
Config.BlipDuration = 60000 -- 1 minute
```

### Breaking News Alert System

```lua
-- Enable "Breaking News" alert
Config.UseNUIAlert = true

-- Alert duration in milliseconds
Config.NUIDuration = 15000 -- 15 seconds
```

### ATM Locations

```lua
Config.ATMLocations = {
    vector3(146.97, -1035.2, 29.34),   -- Legion Square
    vector3(-386.7, 6045.95, 31.5),    -- Paleto Bay
    vector3(-132.46, 6366.92, 31.48),  -- Paleto Bay 2
    
    -- Add as many locations as you want
    -- vector3(x, y, z),
}
```

> 💡 **Tip:** Use `/getcoords` or similar to get coordinates

---

## 🎯 Usage

### For Players

1. **Get** a USB drive (configurable item)
2. **Approach** an ATM
3. **Wait** for the notification "Press [G]" to appear
4. **Press G** to start hacking
5. **Wait** for the hack to finish (or complete the minigame)
6. **Collect** your reward!

> ⏱️ The ATM will be on cooldown for the configured time

### For Police

When a robbery starts:
- 📱 You receive an instant notification
- 📍 A blip appears on your map (if enabled)
- 📺 A "Breaking News" alert is displayed
- 🗺️ The street name is indicated

---

## 🔄 Compatibility

### Tested Frameworks ✅
- ESX Legacy 1.8+
- ESX Legacy 1.9+
- QBCore

### Tested Inventories ✅
- ESX Default Inventory
- QBCore Inventory
- ox_inventory
- Standalone (no inventory)

### Tested Notification Systems ✅
- All systems listed in [NOTIFICATION-EN.md](NOTIFICATION-EN.md)

---

## 🔒 Security

### Script Protection
- 🔐 **Full encryption** - Only config.lua is editable
- 🛡️ **Anti-leak** - Protection against copying
- ✅ **Server validation** - All important actions
- ⏱️ **Anti-spam** - Cooldown system
- 🚫 **Anti-exploit** - Multiple checks

### Best Practices
- ✅ Police count verification (server-side)
- ✅ Required item verification (server-side)
- ✅ Cooldown managed server-side
- ✅ No client-side trust
- ✅ Protection against modifications

---

## 🐛 Troubleshooting

### Notifications don't appear
**Solution:**
1. Check that `Config.NotificationSystem` matches your system
2. Consult [NOTIFICATION-EN.md](NOTIFICATION-EN.md)
3. Test with `Config.NotificationSystem = 'chat'`
5. Contact our support

### Money not received
**Solution:**
1. Check `Config.Framework` (esx or qb)
2. Check `Config.Inventory` (esx, qb, ox, standalone)
3. Check `Config.RewardType` (cash, money, black_money)
4. Check server logs (F8)
5. Contact our support

### Interaction text doesn't appear
**Solution:**
- This is normal if you have a custom HUD blocking native displays
- The script now uses a NUI system that always works
- The notification appears at the top left of the screen

### "Not enough police"
**Solution:**
- Check `Config.MinPolice` (reduce to test)
- Check that your police jobs are in `Config.PoliceJobs`
- Make sure a police officer is online
- Contact our support

### Script doesn't start
**Solution:**
1. Check that the folder is named `very_advanced_atm_heist_system`
2. Check that your framework starts before
3. Check server logs for errors
4. Contact our support

---

## 📞 Support

### Included Support
- ✅ Installation and configuration
- ✅ Technical issues
- ✅ Feature questions
- ✅ Updates (if available)

### How to Get Support
1. **Discord:** https://discord.gg/WZXVMz9WuU
2. **Email:** very.developpement@gmail.com

> ⚠️ **Note:** Support does not cover custom modifications and will not provide support if the script has been decrypted.

---

## 📜 License & Terms

### ❌ FORBIDDEN
- ❌ Resell or redistribute this script
- ❌ Share your license with others
- ❌ Modify encrypted files
- ❌ Bypass encryption system

### ✅ ALLOWED
- ✅ Freely modify `config/config.lua`
- ✅ Customize `html/ledejinfo.png` (logo)
- ✅ Use on your server (1 license = 1 server)
- ✅ Request support
- ✅ Suggest improvements

### 🔐 Protection
This script is protected by encryption. Any attempt to:
- Decrypt
- Reverse engineer
- Unauthorized sharing

Will result in **being blacklisted from our shop and community servers** without a refund.

---

## 🎁 Credits

**Developed with ❤️ by Very Development**

Version: 2.0.0  
Last update: 29/11/2025

---

<div align="center">

### Thank you for choosing our script! 🎉

**Have fun and happy robbing! 🏧💰**

[⬆️ Back to top](#-atm-robbery-script---fivem)

</div>
