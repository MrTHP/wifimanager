# wifimanager
# WiFi Manager - Ncurses based WiFi connection tool # For Debian Trixie Linux
# 📶 WiFi Manager TUI

[![Bash](https://img.shields.io/badge/Shell-Bash-green.svg)](https://www.gnu.org/software/bash/)
[![Debian](https://img.shields.io/badge/OS-Debian_Trixie-red.svg)](https://www.debian.org/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

Un outil léger en interface texte (TUI) basé sur **ncurses/dialog** pour gérer les connexions WiFi sous Linux. Conçu pour **Debian Trixie**, il permet de scanner, se connecter et administrer les réseaux sans interface graphique (X11/Wayland).

Parfait pour les installations minimales, les serveurs avec carte WiFi, ou simplement pour les amoureux du terminal comme moi. 🐧

---

## ✨ Fonctionnalités

- **📡 Scan WiFi** : Liste les réseaux disponibles avec signal et sécurité.
- **🔐 Connexion** : Gestion automatique des réseaux ouverts et sécurisés (WPA).
- **📊 État actuel** : Affiche la connexion active et la puissance du signal.
- **❌ Déconnexion** : Quitte le réseau actuel proprement.
- **💾 Réseaux sauvegardés** : Liste les profils WiFi connus.
- **🔘 Toggle WiFi** : Active ou désactive la carte radio WiFi.
- **🛠️ Installation auto** : Vérifie et installe les dépendances manquantes (`nmcli`, `dialog`, etc.).

---

## 📋 Prérequis

- **Système** : Debian Trixie (ou toute distro utilisant **NetworkManager**).
- **Privilèges** : Accès **root** requis (via `sudo`).
- **Dépendances** :
  - `network-manager` (nmcli)
  - `dialog`
  - `iw`
  - `wpasupplicant`

> **Note** : Le script tente d'installer automatiquement les paquets manquants au premier lancement.

---

## 🚀 Installation & Utilisation

### 1. Cloner le dépôt

```bash
git clone https://github.com/MrTHP/wifimanager.git
cd wifimanager
```

### 2. Rendre le script exécutable

```bash
chmod +x wifimanager.sh
```

### 3. Lancer le script

```bash
sudo ./wifimanager.sh
```

### 4. Navigation

Utilisez les flèches du clavier pour naviguer dans le menu et `Entrée` pour valider. Les mots de passe sont masqués lors de la saisie.

---

## 🖼️ Aperçu

*(Insérer ici une capture d'écran du menu principal ou du scan WiFi)*

```text
┌──────────────────────────────────────────────────────────────┐
│                      WiFi Manager                            │
├──────────────────────────────────────────────────────────────┤
│  Choose an option:                                           │
│                                                              │
│    1  Scan and Connect to WiFi                               │
│    2  Show Current Connection                                │
│    3  Disconnect from WiFi                                   │
│    4  Show Saved Networks                                    │
│    5  Toggle WiFi (On/Off)                                   │
│    6  Show WiFi Status                                       │
│    7  Exit                                                   │
│                                                              │
│                <  Ok  >         <  Cancel  >                 │
└──────────────────────────────────────────────────────────────┘
```

---

## ⚙️ Détails Techniques

- **Backend** : Utilise `nmcli` (NetworkManager Command Line Interface) pour toutes les opérations réseau.
- **UI** : Utilise `dialog` pour une interface ncurses propre et compatible avec tous les terminaux.
- **Sécurité** : Les mots de passe ne sont pas stockés en clair dans les logs temporaires (utilisation de `--insecure` pour l'affichage maské, mais transmission sécurisée via nmcli).
- **Nettoyage** : Les fichiers temporaires (`/tmp/wifi_networks.tmp`) sont supprimés après chaque opération.

---


## 📄 Licence

Distribué sous la licence MIT. Voir `LICENSE` pour plus d'informations.

---

## 👤 À propos de l'auteur

**MrTHP**  
📍 Baie-Comeau, QC  
🐧 Passionné Linux & Gaming | 🛠️ Arch/NixOS/Debian | 🚀 Self-hosting (VPS, Nginx, SearXNG)

Je crée des scripts et configs pour optimiser mes setups. Checkez mes autres repos pour plus d'outils d'administration et de dotfiles !

[![GitHub](https://img.shields.io/badge/GitHub-MrTHP-black?style=for-the-badge&logo=github)](https://github.com/MrTHP)

---

> ⚠️ **Avertissement** : Ce script est fourni "tel quel". Assurez-vous de comprendre les commandes réseau avant de les exécuter sur des systèmes de production critiques.
