<div align="center">

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   HERO BANNER                                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0a,30:111827,60:1e3a5f,100:22c55e&height=250&section=header&text=🔐%20SecureGate&fontSize=56&fontColor=e2e8f0&fontAlignY=32&desc=Multi-Room%20Zutrittskontrollsystem%20auf%20Raspberry%20Pi%20Basis&descSize=18&descColor=94a3b8&descAlignY=52&animation=fadeIn" width="100%"/>

<br/>

<!-- Status Badges -->
![Version](https://img.shields.io/badge/Version-2.0.0-22c55e?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Raspberry%20Pi-A22846?style=for-the-badge&logo=raspberry-pi&logoColor=white)
![License](https://img.shields.io/badge/License-Apache%202.0-3b82f6?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Production%20Ready-22c55e?style=for-the-badge)

<br/>

<p>
<strong>SecureGate</strong> ist ein vollständiges, selbst gehostetes Zutrittskontrollsystem<br/>
mit NFC/Smartcard-Authentifizierung, Multi-Room-Verwaltung, Admin-Dashboard, mobiler Scanner-App und automatisiertem Reporting.<br/>
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

### 🏢 Multi-Room-Architektur

<p align="center">
  <img src="https://img.shields.io/badge/Bis%20zu-4%20Räume-22c55e?style=for-the-badge"/>
</p>

- Jeder Raum läuft als **eigene Flask-Instanz** (`app.py`)
- Konfigurierbare Ports: `5000`, `5100`, `5200`, `5300`
- CLI-Steuerung: `--port`, `--room`, `--no-reader` (für Räume ohne Hardware)
- **Per-Room Pairing** über eigene Pairing-Dateien (`pairing_5000.json`, etc.)
- Jeder Monitor zeigt seinen eigenen **Raumnamen** an
- Systemd-Services: `sicherheit-raum1` bis `sicherheit-raum4`

</td>
<td width="50%" valign="top">

### 🔑 NFC / Smartcard Zutrittskontrolle

<p align="center">
  <img src="https://img.shields.io/badge/NFC-Lesen%20%26%20Schreiben-3b82f6?style=for-the-badge"/>
</p>

- Unterstützt **NFC-Tags & Smartcards** zur Authentifizierung
- **NDEF-Schreibfunktion** — Tags erhalten automatisch eine Zugangs-URL
- Kartenleser-Verwaltung über eigenes Admin-Panel (`webseite-e.py`)
- Echtzeit-Validierung über REST-API
- **Pairingprotokoll** mit pulsierendem Pairing-Code auf dem Monitor

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🖥️ Admin-Dashboard & Benutzerverwaltung

<p align="center">
  <img src="https://img.shields.io/badge/Dashboard-Multi--User%20System-f59e0b?style=for-the-badge"/>
</p>

- **Rollenbasiertes Login-System** — Level 1–10+
- Administratoren (Level 10+) → vollständiges Dashboard
- Mitarbeiter → personalisierte QR-Code-Seite
- **Gruppen-Verwaltung** mit individueller Farbzuordnung
- **Broadcast-Tab** mit Per-Room-Steuerung und Live-Countdown (HH:MM:SS)
- **Lockdown-Modus** — Räume einzeln sperren
- **Zugangszeiten** mit Mittagspause und 5-Minuten-Override-Button
- **QR-Karten Drucktool** — Benutzer wählen, Layout 1/2/4/6/8/9 pro A4-Seite

</td>
<td width="50%" valign="top">

### 📱 QR-Code Scanner (Android APK)

<p align="center">
  <img src="https://img.shields.io/badge/APK-Android%20Scanner-34A853?style=for-the-badge"/>
</p>

- Native **Android-App** (WebView-basiert) für mobiles Scannen
- Unterstützt **QR-Code & NFC-Scan** über Kamera bzw. NFC-Chip
- Auto-Login via URL-Parameter (`?auto=UID`)
- NFC-Bridge über `nfcScanned()` und `nfcReady()`
- **Glassmorphism-Toast-Benachrichtigungen**
- Dark/Light-Mode Umschaltung
- NFC-Patch via `patch-nfc.py` (dynamische `MainActivity.java`-Erkennung)

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 📊 Excel-Reports & Statistiken

<p align="center">
  <img src="https://img.shields.io/badge/Reports-7%20Sheet%20Excel-ef4444?style=for-the-badge"/>
</p>

- Automatische Generierung von **umfassenden Excel-Reports**
- **7 Tabellenblätter** mit Auswertungen und Diagrammen
- Erstellt über `report.php` mit **PhpSpreadsheet**
- Zugangsstatistiken, Benutzeraktivitäten & Zeitauswertungen
- Exportierbar für Compliance- und Sicherheitsaudits

</td>
<td width="50%" valign="top">

### ⚡ Setup-Wizard & Deployment

<p align="center">
  <img src="https://img.shields.io/badge/Setup-One--Click%20Install-a855f7?style=for-the-badge"/>
</p>

- **`setup.sh`** — Automatische Systeminstallation
- **`setup.php`** — Web-Wizard für Ersteinrichtung
- Admin-Erstellung und Raum-Konfiguration mit Auto-Pairing
- **`reset-deploy.sh`** — Kompletter System-Reset & Neuinstallation
- Setzt Datenbank zurück, löscht alle Dateien, deployt mit korrekten Rechten

</td>
</tr>
</table>

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   ARCHITEKTUR                                                  -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🏗️ Systemarchitektur

```
┌─────────────────────────────────────────────────────────────────────────┐
│                          🔐 SecureGate System                          │
│                        main-max.local (HTTPS)                          │
├─────────────────────────────────────────────────────────────────────────┤
│                                                                         │
│   🏢 Multi-Room Flask Instanzen                                         │
│   ┌─────────────┐ ┌─────────────┐ ┌─────────────┐ ┌─────────────┐     │
│   │  Raum 1     │ │  Raum 2     │ │  Raum 3     │ │  Raum 4     │     │
│   │  app.py     │ │  app.py     │ │  app.py     │ │  app.py     │     │
│   │  :5000      │ │  :5100      │ │  :5200      │ │  :5300      │     │
│   └──────┬──────┘ └──────┬──────┘ └──────┬──────┘ └──────┬──────┘     │
│          │               │               │               │             │
│          └───────────────┴───────┬───────┴───────────────┘             │
│                                  │                                     │
│   ┌──────────────┐    ┌──────────┴──────────┐    ┌──────────────────┐  │
│   │ 🔑 webseite  │    │  🗄️ MariaDB         │    │ 🌐 Apache + PHP  │  │
│   │   -e.py      │    │  (sicherheit)       │    │  (/admin/)       │  │
│   │  :5001       │    │                     │    │                  │  │
│   │              │    │  • benutzer         │    │  • index.php     │  │
│   │  • Reader-UI │    │  • karten           │    │  • scan.php      │  │
│   │  • NFC/NDEF  │    │  • gruppen          │    │  • report.php    │  │
│   │  • Pairing   │    │  • einstellungen    │    │  • setup.php     │  │
│   └──────────────┘    │  • logs             │    │  • app_proxy     │  │
│                       └─────────────────────┘    └──────────────────┘  │
│                                                                         │
│   📱 Android APK (QR + NFC)           🖨️ QR-Karten Drucktool            │
│   • WebView → scan.php               • Layouts: 1/2/4/6/8/9 pro A4    │
│   • NFC Bridge Functions             • QR enthält Raw-ATR              │
│   • Auto-Login (?auto=UID)                                             │
│                                                                         │
└─────────────────────────────────────────────────────────────────────────┘
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
<!--   DATENBANK                                                    -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🗄️ Datenbank-Schema

| Tabelle | Beschreibung |
|:--|:--|
| `benutzer` | Benutzerdaten, Berechtigungslevel (1–10+), Avatare |
| `karten` | NFC/Smartcard UIDs und Benutzerzuordnungen |
| `gruppen` | Gruppenstruktur mit individueller Farbzuordnung |
| `einstellungen` | Systemkonfiguration, Zugangszeiten, Tagesrhythmus |
| `logs` | Zugangs-Protokolle und Audit-Trail pro Raum |

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
| PHP | 8.0+ | Admin-Dashboard & Reports |
| NFC-Reader | USB / I²C | Kartenleser (optional pro Raum) |

### Automatische Installation

```bash
# 1. Repository klonen
git clone https://github.com/Max6025/SecureGate.git

# 2. Setup-Script ausführen
cd SecureGate
sudo bash setup.sh
```

Anschließend im Browser `https://main-max.local/admin/setup.php` öffnen, um den **Setup-Wizard** zu starten — dieser führt durch Admin-Erstellung und Raum-Konfiguration mit Auto-Pairing.

### Manuelle Installation

```bash
# 1. Dateien kopieren
sudo cp -r . /opt/sicherheitssystem/
cd /opt/sicherheitssystem/

# 2. Python-Abhängigkeiten
pip install -r requirements.txt

# 3. Datenbank einrichten
sudo mysql -u root < sql/setup.sql

# 4. PHP-Dateien deployen
sudo cp -r web/* /var/www/html/admin/
sudo chown -R www-data:www-data /var/www/html/admin/

# 5. Raum-Services starten
python3 app.py --port 5000 --room "Eingang" &
python3 app.py --port 5100 --room "Büro" &
python3 app.py --port 5200 --room "Lager" --no-reader &
python3 webseite-e.py &
```

### Schnell-Reset

```bash
sudo bash reset-deploy.sh
```

> ⚠️ **Achtung:** Löscht alle Daten (inkl. Avatare), setzt die Datenbank komplett zurück und deployt alle Dateien neu mit korrekten Berechtigungen.

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   MULTI-ROOM                                                   -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 🏢 Multi-Room Konfiguration

Jeder Raum wird als eigenständiger Service betrieben:

| Service | Port | CLI-Befehl |
|:--|:--|:--|
| `sicherheit-raum1` | 5000 | `python3 app.py --port 5000 --room "Eingang"` |
| `sicherheit-raum2` | 5100 | `python3 app.py --port 5100 --room "Büro"` |
| `sicherheit-raum3` | 5200 | `python3 app.py --port 5200 --room "Lager" --no-reader` |
| `sicherheit-raum4` | 5300 | `python3 app.py --port 5300 --room "Werkstatt"` |
| `admin-panel` | 5001 | `python3 webseite-e.py` |

**CLI-Parameter:**

| Parameter | Beschreibung |
|:--|:--|
| `--port` | Port für diese Raum-Instanz (5000, 5100, 5200, 5300) |
| `--room` | Anzeigename des Raums auf dem Monitor |
| `--no-reader` | Raum ohne angeschlossenen NFC-Reader starten |

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   PROJEKTSTRUKTUR                                              -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## 📁 Projektstruktur

```
/opt/sicherheitssystem/
├── app.py                  # ⚙️ Raum-Service (Flask, Multi-Instanz)
├── webseite-e.py           # 🔑 Kartenleser-Panel (Flask, Port 5001)
├── db_manager.py           # 🗄️ Gemeinsames Datenbankmodul (MariaDB)
├── requirements.txt        # 📦 Python-Abhängigkeiten
├── setup.sh                # 🚀 Automatisches Setup-Script
├── reset-deploy.sh         # 🔄 Kompletter System-Reset & Deploy
├── pairing_5000.json       # 🔗 Pairing-Datei Raum 1
├── pairing_5100.json       # 🔗 Pairing-Datei Raum 2
├── ...                     # 🔗 Weitere Pairing-Dateien
│
├── web/
│   ├── index.php           # 🖥️ Admin-Dashboard (Login + Verwaltung)
│   ├── scan.php            # 📱 Mobiler QR/NFC Scanner
│   ├── report.php          # 📊 Excel-Report-Generator (PhpSpreadsheet)
│   └── setup.php           # 🧙 Ersteinrichtungs-Wizard
│
├── apk/
│   ├── patch-nfc.py        # 🔧 NFC-Patch für Android-Build
│   └── ...                 # 📱 Android APK Quellen
│
├── sql/
│   └── setup.sql           # 🗄️ Datenbank-Schema
│
└── certs/
    └── ...                 # 🔒 Self-Signed HTTPS Zertifikate
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

<img src="https://via.placeholder.com/500x300/111827/22c55e?text=Admin+Dashboard" width="100%"/>

</td>
<td width="50%" align="center">

**Broadcast & Lockdown**

<img src="https://via.placeholder.com/500x300/111827/3b82f6?text=Broadcast+%26+Lockdown" width="100%"/>

</td>
</tr>
<tr>
<td width="50%" align="center">

**QR-Karten Drucktool**

<img src="https://via.placeholder.com/500x300/111827/a855f7?text=QR+Karten+Druck" width="100%"/>

</td>
<td width="50%" align="center">

**Setup-Wizard**

<img src="https://via.placeholder.com/500x300/111827/f59e0b?text=Setup+Wizard" width="100%"/>

</td>
</tr>
</table>

> 📌 **Tipp:** Ersetze die Platzhalter durch echte Screenshots deines Systems.

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
<td>Systemstatus eines Raums abfragen</td>
<td>app.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/POST-3b82f6?style=flat-square"/></td>
<td><code>/api/validate</code></td>
<td>Karte / UID validieren</td>
<td>app.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/POST-3b82f6?style=flat-square"/></td>
<td><code>/api/pair</code></td>
<td>Kartenleser an Raum koppeln</td>
<td>app.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/POST-3b82f6?style=flat-square"/></td>
<td><code>/api/broadcast</code></td>
<td>Broadcast an spezifischen Raum senden</td>
<td>app.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/GET-22c55e?style=flat-square"/></td>
<td><code>/api/settings</code></td>
<td>Einstellungen & Zugangszeiten</td>
<td>app.py</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/GET-22c55e?style=flat-square"/></td>
<td><code>/admin/?api=app_proxy&port=</code></td>
<td>PHP-Proxy für Per-Room API-Aufrufe (HTTPS→HTTP)</td>
<td>Apache/PHP</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/GET-22c55e?style=flat-square"/></td>
<td><code>/admin/scan.php?auto=UID</code></td>
<td>Mobiler Scanner mit Auto-Login</td>
<td>Apache/PHP</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/GET-22c55e?style=flat-square"/></td>
<td><code>/admin/report.php</code></td>
<td>Excel-Report generieren (7 Sheets)</td>
<td>Apache/PHP</td>
</tr>
<tr>
<td><img src="https://img.shields.io/badge/GET-22c55e?style=flat-square"/></td>
<td><code>/admin/setup.php</code></td>
<td>Ersteinrichtungs-Wizard</td>
<td>Apache/PHP</td>
</tr>
</table>

> **Hinweis:** Der `app_proxy` akzeptiert einen `&port=`-Parameter, um gezielt den richtigen Raum-Service anzusprechen.

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
<td>🏢</td>
<td><strong>Per-Room Lockdown</strong></td>
<td>Einzelne Räume können unabhängig gesperrt werden</td>
</tr>
<tr>
<td>⏰</td>
<td><strong>Zugangszeiten</strong></td>
<td>Zeitbasierte Zugangsbeschränkung mit Mittagspause & Override</td>
</tr>
<tr>
<td>🗄️</td>
<td><strong>Lokal</strong></td>
<td>Alle Daten auf dem eigenen Raspberry Pi — kein Cloud-Zwang</td>
</tr>
<tr>
<td>📋</td>
<td><strong>Audit-Logs</strong></td>
<td>Jeder Zugang wird protokolliert und ist über Reports einsehbar</td>
</tr>
<tr>
<td>🔄</td>
<td><strong>API-Proxy</strong></td>
<td>Mixed-Content-Schutz durch PHP-Proxy (HTTPS→HTTP)</td>
</tr>
</table>

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   EINSCHRÄNKUNGEN                                              -->
<!-- ═══════════════════════════════════════════════════════════════ -->

## ⚠️ Bekannte Einschränkungen

| Einschränkung | Grund |
|:--|:--|
| APK-Build nicht auf dem Pi möglich | ARM64 vs. x86 AAPT2 — Build auf separatem PC erforderlich |
| Web NFC API liest nur NDEF | Keine Raw-Card-UIDs über den Browser — nur über physischen Reader |
| Torch/Vibration im WebView deaktiviert | Android WebView unterstützt diese APIs nicht |
| PHP kann `main-max.local` nicht auflösen | Interne API-Aufrufe nutzen `127.0.0.1` statt Hostname |

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
- [x] Gruppen-Verwaltung mit Farbzuordnung
- [x] **Multi-Room-Architektur** (bis zu 4 Räume)
- [x] **Setup-Wizard** (setup.sh + setup.php)
- [x] **QR-Karten Drucktool** (Layouts 1–9 pro A4)
- [x] **Broadcast-Tab** mit Live-Countdown
- [x] **Per-Room Lockdown**
- [x] **Zugangszeiten** mit Mittagspause & Override
- [ ] iOS-Support (PWA)
- [ ] Biometrische Authentifizierung
- [ ] E-Mail-Benachrichtigungen

<br/>

<!-- ═══════════════════════════════════════════════════════════════ -->
<!--   LIZENZ                                                       -->
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

<strong>SecureGate</strong> — Professionelle Multi-Room Zutrittskontrolle. Selbst gehostet. Open Source.

<br/>

![Made with](https://img.shields.io/badge/Made%20with-❤️-ef4444?style=flat-square)
![Powered by](https://img.shields.io/badge/Powered%20by-Raspberry%20Pi-A22846?style=flat-square&logo=raspberry-pi&logoColor=white)
![Built in](https://img.shields.io/badge/Built%20in-🇩🇪%20Deutschland-000?style=flat-square)

<br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0a,30:111827,60:1e3a5f,100:22c55e&height=100&section=footer" width="100%"/>

</div>
