# Proton Drive GUI (Unofficial) / واجهة Proton Drive (غير رسمية)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Bash](https://img.shields.io/badge/Language-Bash-4EAA25.svg)](https://www.gnu.org/software/bash/)

A lightweight, multi-language GUI/TUI wrapper written in Bash for the official [Proton Drive CLI](https://proton.me/download/drive/cli).

واجهة رسومية وتفاعلية خفيفة متعددة اللغات مكتوبة بلغة Bash لتسهيل التعامل مع أداة السطر البرمجي الرسمية **Proton Drive CLI**.

---

## 🌍 Languages Supported / اللغات المدعومة
- 🇬🇧 English
- 🇸🇦 العربية
- 🇫🇷 Français
- 🇪🇸 Español
- 🇩🇪 Deutsch

---

## ✨ Features / الميزات
- **Graphical User Interface (GUI)** using `zenity` or interactive **Terminal UI (TUI)** fallback if no display is available.
- **Easy Upload & Download** of files and directories.
- **Conflict Handling**: Choose how to handle filename conflicts (Keep both, replace, create new revision, or skip).
- **Desktop Integration**: Install as a desktop application with `.desktop` shortcuts and context actions.
- **Multi-language Support**: Automatically detects system language or allows manual selection.

---

## 📋 Prerequisites & Requirements / متطلبات التشغيل

Before running this script, ensure you have the following installed on your Linux system:

قبل تشغيل السكربت، تأكد من توفر المتطلبات التالية على نظام لينكس الخاص بك:

| Requirement / المتطلب | Description / الوصف |
| :--- | :--- |
| **Bash 4.0+** | Required for associative arrays and modern features. |
| **proton-drive CLI** | The official Proton Drive CLI binary. |
| **Python 3** | Required for JSON response parsing. |
| **Zenity** *(Optional)* | For the Graphical User Interface (GUI). |
| **notify-send** *(Optional)* | For desktop notifications during operations. |

### 1. Install Dependencies / تثبيت الاعتمادات

#### Debian/Ubuntu based:
```bash
sudo apt update
sudo apt install python3 zenity libnotify-bin desktop-file-utils
```

#### Arch Linux based:
```bash
sudo pacman -S python zenity libnotify desktop-file-utils
```

#### Fedora / RHEL:
```bash
sudo dnf install python3 zenity libnotify desktop-file-utils
```

### 2. Download and Authenticate Proton Drive CLI / إعداد أداة Proton Drive
1. Download the official `proton-drive` binary from [proton.me/download/drive/cli](https://proton.me/download/drive/cli).
2. Place it in `~/.local/bin/` and make it executable:
   ```bash
   mkdir -p ~/.local/bin
   mv /path/to/downloaded/proton-drive ~/.local/bin/
   chmod +x ~/.local/bin/proton-drive
   ```
3. Authenticate your Proton account:
   ```bash
   ~/.local/bin/proton-drive auth login
   ```

---

## 🚀 Installation & Usage / التثبيت والاستخدام

### Quick Start / التشغيل السريع
1. Clone this repository or download `pdrive-gui`:
   ```bash
   git clone https://github.com/your-username/pdrive-gui.git
   cd pdrive-gui
   ```
2. Grant execution permissions:
   ```bash
   chmod +x pdrive-gui
   ```
3. Run the menu:
   ```bash
   ./pdrive-gui
   ```

---

### System Installation / التثبيت في النظام

To add `pdrive-gui` to your system's application menu:

لتثبيت السكربت وإضافته إلى قائمة التطبيقات بالنظام:

```bash
./pdrive-gui install --desktop
```

#### Installing with a custom icon / التثبيت مع أيقونة مخصصة:
```bash
./pdrive-gui install --desktop --icon /path/to/icon.png
```

#### Uninstall / إلغاء التثبيت:
```bash
./pdrive-gui uninstall
```

---

## 💻 Command Line Interface (CLI) Commands / الأوامر المباشرة

```bash
pdrive-gui                      # Open the main interactive menu / فتح القائمة الرئيسية
pdrive-gui upload [FILE...]     # Upload files or folders / رفع ملفات أو مجلدات
pdrive-gui download [PATH...]   # Download items from Drive / تنزيل عنصر من السحابة
pdrive-gui lang [en|ar|fr|es|de]# Change interface language / تغيير اللغة
pdrive-gui --version            # Show version information / عرض رقم الإصدار
```

---

## 🎨 Changing Icon Post-Installation / تغيير الأيقونة بعد التثبيت

If you want to update the app icon manually:

إذا أردت استبدال الأيقونة يدوياً بعد التثبيت:

```bash
# For SVG icons:
cp /path/to/new-icon.svg ~/.local/share/icons/hicolor/scalable/apps/pdrive-gui.svg

# For PNG icons (256x256 recommended):
cp /path/to/new-icon.png ~/.local/share/icons/hicolor/256x256/apps/pdrive-gui.png

# Update system icon cache:
gtk-update-icon-cache -f -t ~/.local/share/icons/hicolor 2>/dev/null || true
```

---

## 📜 Disclaimer & License / الإخلاء القانوني والترخيص

- **Disclaimer**: This is an **unofficial** tool and is NOT affiliated with, endorsed by, or sponsored by Proton AG. "Proton" and "Proton Drive" are registered trademarks of Proton AG.
- **License**: Released under the [MIT License](LICENSE).