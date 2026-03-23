<div align="center">

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   HERO BANNER                                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0a,30:111827,60:1e3a5f,100:22c55e&height=250&section=header&text=🔐%20SecureGate&fontSize=56&fontColor=e2e8f0&fontAlignY=32&desc=Professionelles%20Zutrittskontrollsystem%20auf%20Raspberry%20Pi%20Basis&descSize=18&descColor=94a3b8&descAlignY=52&animation=fadeIn" width="100%"/>

<br/>

<!-- Status Badges -->
![Version](https://img.shields.io/badge/Version-1.0.0-22c55e?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Raspberry%20Pi-A22846?style=for-the-badge&logo=raspberry-pi&logoColor=white)
![License](https://img.shields.io/badge/License-Apache%202.0-3b82f6?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Production%20Ready-22c55e?style=for-the-badge)

<br/>

<p>
<strong>SecureGate</strong> ist ein vollständiges, selbst gehostetes Zutrittskontrollsystem<br/>
mit NFC/Smartcard-Authentifizierung, Admin-Dashboard, mobiler Scanner-App und automatisiertem Reporting.<br/>
Entwickelt für den professionellen Einsatz — betrieben auf einem Raspberry Pi.
</p>

<br/>

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white)
![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)
![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Android](https://img.shields.io/badge/Android-34A853?style=flat-square&logo=android&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-A22846?style=flat-square&logo=raspberry-pi&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=flat-square&logo=apache&logoColor=white)

</div>

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   FEATURE CARDS                                                -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 📋 Features im Überblick

<table>
<tr>
<td width="50%" valign="top">

### 🔑 NFC / Smartcard Zutrittskontrolle

<p align="center">
  <img src="https://img.shields.io/badge/NFC-Lesen%20%26%20Schreiben-22c55e?style=for-the-badge"/>
</p>

- Unterstützt **NFC-Tags & Smartcards** zur Authentifizierung
- **NDEF-Schreibfunktion** — Tags werden automatisch mit einer Zugangs-URL beschrieben
- Kartenleser-Verwaltung über ein eigenes Admin-Panel (`webseite-e.py`)
- Echtzeit-Validierung über REST-API
- Pairingprotokoll zwischen Kartenleser und Hauptsystem mit visuellem Feedback

</td>
<td width="50%" valign="top">

### 🖥️ Admin-Dashboard & Benutzerverwaltung

<p align="center">
  <img src="https://img.shields.io/badge/Dashboard-Multi--User%20System-3b82f6?style=for-the-badge"/>
</p>

- **Rollenbasiertes Login-System** mit Berechtigungsstufen (Level 1–10+)
- Administratoren (Level 10+) erhalten Zugriff auf das vollständige Dashboard
- Mitarbeiter sehen eine personalisierte QR-Code-Seite mit ihrem Namen
- Benutzer anlegen, bearbeiten und Rechte verwalten
- **Broadcast-System** für systemweite Benachrichtigungen
- Professionelles Dark-Theme-Interface

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 📱 QR-Code Scanner (Android APK)

<p align="center">
  <img src="https://img.shields.io/badge/APK-Android%20Scanner-34A853?style=for-the-badge"/>
</p>

- Native **Android-App** (WebView-basiert) für mobiles Scannen
- Unterstützt **QR-Code & NFC-Scan** über die Kamera bzw. NFC-Chip
- Auto-Login via URL-Parameter (`?auto=UID`)
- NFC-Integration über `nfcScanned()` und `nfcReady()` Bridge-Funktionen
- Ergebnis-Anzeige als elegante Glassmorphism-Toast-Benachrichtigungen
- Dark/Light-Mode Umschaltung

</td>
<td width="50%" valign="top">

### 📊 Excel-Reports & Statistiken

<p align="center">
  <img src="https://img.shields.io/badge/Reports-7%20Sheet%20Excel-f59e0b?style=for-the-badge"/>
</p>

- Automatische Generierung von **umfassenden Excel-Reports**
- **7 Tabellenblätter** mit verschiedenen Auswertungen und Diagrammen
- Erstellt über `report.php` mit **PhpSpreadsheet**
- Zugangsstatistiken, Benutzeraktivitäten & Zeitauswertungen
- Exportierbar für Compliance- und Sicherheitsaudits
- Diagramme direkt in der Excel-Datei enthalten

</td>
</tr>
</table>

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   ARCHITEKTUR                                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🏗️ Systemarchitektur

```
┌──────────────────────────────────────────────────────────────────────┐
│                        🔐 SecureGate System                         │
│                      main-max.local (HTTPS)                         │
├──────────────────────┬───────────────────────┬───────────────────────┤
│                      │                       │                       │
│   ⚙️ master-code.py  │   🔑 webseite-e.py    │   🌐 Apache + PHP     │
│   (Flask :5000)      │   (Flask :5001)        │   (/admin/)           │
│                      │                       │                       │
│   • REST API         │   • Kartenleser-UI    │   • index.php         │
│   • Hauptlogik       │   • NFC Lesen/NDEF    │   • scan.php          │
│   • Pairing          │   • Reader-Verwaltung │   • report.php        │
│   • Broadcast        │                       │   • Login-System      │
│                      │                       │                       │
├──────────────────────┴───────────────────────┴───────────────────────┤
│                                                                      │
│   🗄️ MariaDB (sicherheit)        📱 Android APK (QR + NFC)          │
│   • db_manager.py                 • WebView → scan.php               │
│   • Benutzer, Karten, Logs        • NFC Bridge Functions             │
│                                                                      │
└──────────────────────────────────────────────────────────────────────┘
```

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   TECH STACK                                                   -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## ⚡ Tech Stack

<table>
<tr>
<td align="center" width="20%">

#### 🐍 Backend

![Python](https://img.shields.io/badge/Python%203-3776AB?style=flat-square&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000?style=flat-square&logo=flask)

</td>
<td align="center" width="20%">

#### 🌐 Web

![PHP](https://img.shields.io/badge/PHP%208-777BB4?style=flat-square&logo=php&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=flat-square&logo=apache&logoColor=white)

</td>
<td align="center" width="20%">

#### 🗄️ Datenbank

![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white)

</td>
<td align="center" width="20%">

#### 📱 Mobile

![Android](https://img.shields.io/badge/Android-34A853?style=flat-square&logo=android&logoColor=white)
![WebView](https://img.shields.io/badge/WebView-4285F4?style=flat-square&logo=google-chrome&logoColor=white)

</td>
<td align="center" width="20%">

#### 🔧 Hardware

![Raspberry Pi](https://img.shields.io/badge/RPi-A22846?style=flat-square&logo=raspberry-pi&logoColor=white)
![NFC](https://img.shields.io/badge/NFC-002E5F?style=flat-square)

</td>
</tr>
</table>

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   INSTALLATION                                                 -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🚀 Installation

### Voraussetzungen

| Komponente | Version | Zweck |
|:--|:--|:--|
| Raspberry Pi | 4B oder neuer | Systemhost |
| Python | 3.9+ | Backend-Services |
| MariaDB | 10.5+ | Datenbank |
| Apache | 2.4+ | Webserver für PHP |
| PHP | 8.0+ | Admin-Dashboard |
| NFC-Reader | USB / I²C | Kartenleser |

### Setup

```bash
# 1. Repository klonen
git clone https://github.com/Max6025/SecureGate.git
cd SecureGate

# 2. Python-Abhängigkeiten installieren
pip install -r requirements.txt

# 3. Datenbank einrichten
sudo mysql -u root < sql/setup.sql

# 4. PHP-Dateien deployen
sudo cp -r web/* /var/www/html/admin/
sudo chown -R www-data:www-data /var/www/html/admin/

# 5. Services starten
python3 master-code.py &    # Hauptsystem auf Port 5000
python3 webseite-e.py &     # Kartenleser auf Port 5001
```

### Schnell-Reset (Neuinstallation)

```bash
# Kompletter System-Reset inkl. Datenbank & Dateien
sudo bash reset-deploy.sh
```

> ⚠️ **Achtung:** `reset-deploy.sh` löscht alle Daten, setzt die Datenbank zurück und deployt alle Dateien neu.

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   PROJEKTSTRUKTUR                                              -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 📁 Projektstruktur

```
SecureGate/
├── master-code.py          # ⚙️ Haupt-API & Dashboard (Flask, Port 5000)
├── webseite-e.py           # 🔑 Kartenleser-Panel (Flask, Port 5001)
├── db_manager.py           # 🗄️ Gemeinsames Datenbankmodul (MariaDB)
├── requirements.txt        # 📦 Python-Abhängigkeiten
├── reset-deploy.sh         # 🔄 Kompletter System-Reset & Deploy
│
├── web/
│   ├── index.php           # 🖥️ Admin-Dashboard (Login + Verwaltung)
│   ├── scan.php            # 📱 Mobiler QR/NFC Scanner
│   └── report.php          # 📊 Excel-Report-Generator
│
├── apk/
│   ├── patch-nfc.py        # 🔧 NFC-Patch für Android-Build
│   └── ...                 # 📱 Android APK Quellen
│
├── sql/
│   └── setup.sql           # 🗄️ Datenbank-Schema
│
├── certs/
│   └── ...                 # 🔒 Self-Signed HTTPS Zertifikate
│
└── README.md
```

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   SCREENSHOTS                                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🖼️ Screenshots

<table>
<tr>
<td width="50%" align="center">

**Admin-Dashboard**

<!-- Screenshot hier einfügen -->
<img src="https://via.placeholder.com/500x300/111827/22c55e?text=Admin+Dashboard" width="100%"/>

</td>
<td width="50%" align="center">

**Kartenleser-Panel**

<!-- Screenshot hier einfügen -->
<img src="https://via.placeholder.com/500x300/111827/3b82f6?text=Kartenleser+Panel" width="100%"/>

</td>
</tr>
<tr>
<td width="50%" align="center">

**Mobiler Scanner**

<!-- Screenshot hier einfügen -->
<img src="https://via.placeholder.com/500x300/111827/34A853?text=QR+%2F+NFC+Scanner" width="100%"/>

</td>
<td width="50%" align="center">

**Excel-Reports**

<!-- Screenshot hier einfügen -->
<img src="https://via.placeholder.com/500x300/111827/f59e0b?text=Excel+Reports" width="100%"/>

</td>
</tr>
</table>

> 📌 **Hinweis:** Ersetze die Platzhalter durch echte Screenshots deines Systems.

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   API REFERENZ                                                 -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🔌 API-Endpunkte

<table>
<tr>
<th>Methode</th>
<th>Endpunkt</th>
<th>Beschreibung</th>
<th>Service</th>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/GET-22c55e?style=flat-square"/></td>
<td><code>/api/status</code></td>
<td>Systemstatus abfragen</td>
<td>master-code.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/POST-3b82f6?style=flat-square"/></td>
<td><code>/api/validate</code></td>
<td>Karte / UID validieren</td>
<td>master-code.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/POST-3b82f6?style=flat-square"/></td>
<td><code>/api/pair</code></td>
<td>Kartenleser koppeln</td>
<td>master-code.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/POST-3b82f6?style=flat-square"/></td>
<td><code>/api/broadcast</code></td>
<td>Nachricht an alle Clients</td>
<td>master-code.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/GET-22c55e?style=flat-square"/></td>
<td><code>/admin/scan.php</code></td>
<td>Mobiler Scanner</td>
<td>Apache/PHP</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/GET-22c55e?style=flat-square"/></td>
<td><code>/admin/report.php</code></td>
<td>Excel-Report generieren</td>
<td>Apache/PHP</td>
</tr>
</table>

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   SICHERHEIT                                                   -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🛡️ Sicherheit

<table>
<tr>
<td>🔒</td>
<td><strong>HTTPS</strong></td>
<td>Gesamte Kommunikation über TLS (Self-Signed Zertifikate)</td>
</tr>
<tr>
<td>👤</td>
<td><strong>Rollenbasiert</strong></td>
<td>Mehrstufiges Berechtigungssystem (Level 1–10+)</td>
</tr>
<tr>
<td>🗄️</td>
<td><strong>Lokal</strong></td>
<td>Alle Daten bleiben auf dem eigenen Raspberry Pi — kein Cloud-Zwang</td>
</tr>
<tr>
<td>📋</td>
<td><strong>Audit-Logs</strong></td>
<td>Jeder Zugang wird protokolliert und ist über Reports einsehbar</td>
</tr>
</table>

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   ROADMAP                                                      -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🗺️ Roadmap

- [x] NFC/Smartcard Zutrittskontrolle
- [x] Admin-Dashboard mit Multi-User Login
- [x] Android APK mit QR & NFC Support
- [x] Excel-Report Generator (7 Sheets)
- [x] Broadcast & Pairing System
- [x] NDEF-Schreibfunktion für NFC-Tags
- [ ] iOS-Support (PWA)
- [ ] Biometrische Authentifizierung
- [ ] Multi-Standort Verwaltung
- [ ] E-Mail-Benachrichtigungen

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   LIZENZ & KONTAKT                                             -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 📄 Lizenz

Dieses Projekt steht unter der [Apache License 2.0](LICENSE).

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   FOOTER                                                       -->
<!-- ═══════════════════════════════════════════════════════════════ -->

<div align="center">

---

<br/>

<strong>SecureGate</strong> — Professionelle Zutrittskontrolle. Selbst gehostet. Open Source.

<br/>

![Made with](https://img.shields.io/badge/Made%20with-❤️-ef4444?style=flat-square)
![Powered by](https://img.shields.io/badge/Powered%20by-Raspberry%20Pi-A22846?style=flat-square&logo=raspberry-pi&logoColor=white)
![Built in](https://img.shields.io/badge/Built%20in-🇩🇪%20Deutschland-000?style=flat-square)

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0a,30:111827,60:1e3a5f,100:22c55e&height=100&section=footer" width="100%"/>

</div>
