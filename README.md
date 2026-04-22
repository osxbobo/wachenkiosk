# 🛒 Wachenkiosk

Eine webbasierte Kiosk-App für die Rettungswache — entwickelt zur einfachen Verwaltung von Snack- und Getränkekäufen, Guthaben und interner Kommunikation.

**Live:** [osxbobo.github.io/wachenkiosk](https://osxbobo.github.io/wachenkiosk/)

---

## ✨ Features

### 👤 Nutzer
- **Schnellwahl** — die zuletzt eingeloggten Nutzer erscheinen als Kacheln, PIN-Eingabe öffnet sich automatisch beim Antippen
- **Name + PIN Login** — alternativ manueller Login mit Name und 4-stelliger PIN
- **Eingeloggt bleiben** — Session bleibt nach Seiten-Reload erhalten
- **Produktkatalog** — alle Artikel mit Bild, Name und Preis auf einen Blick
- **Kauf einbuchen** — einfach Produkt antippen, wird sofort im Verlauf gespeichert
- **Storno** — Käufe können innerhalb von 10 Minuten storniert werden
- **Gutschrift einzahlen** — Schnellbeträge (5 / 10 / 20 / 50 €) oder eigener Betrag; Geld muss physisch in die Kasse eingelegt werden
- **Kontostand** — Übersicht über Ausgaben und Gutschriften inkl. Saldo
- **Monatsverlauf** — scrollbarer Verlauf mit Monatsauswahl
- **Nachrichten an Admin** — Feedback, Produktvorschläge oder Fragen direkt ans Admin-Team senden und Antworten lesen & beantworten
- **Zahlungserinnerung** — automatische Erinnerung bei negativem Kontostand (einstellbar: bei jedem Login, wöchentlich, monatlich oder nie)
- **Ankündigungen** — Infos und Angebote vom Admin werden prominent angezeigt und können weggeklickt werden

### 🔐 Admin
- **Nutzerverwaltung** — Nutzer anlegen, löschen, PIN zurücksetzen, Admin-Rechte vergeben/entziehen, Guthaben anpassen
- **Verkaufsübersicht** — monatliche Übersicht aller Nutzer mit Ausgaben, Eingezahltem und Saldo; Artikel-Statistik mit Verkaufszahlen und Umsatz pro Artikel
- **CSV-Export** — vollständiger Monatsexport für die Buchhaltung (Excel-kompatibel) mit User-Zusammenfassung, Artikel-Übersicht und Einzeltransaktionen
- **Produktverwaltung** — Produkte hinzufügen, bearbeiten (Name & Preis), entfernen
- **Ausverkauft** — Produkte als ausverkauft markieren (Kachel wird ausgegraut, nicht mehr buchbar)
- **Rabatte** — prozentualer Rabatt auf einzelne Produkte; durchgestrichener Originalpreis wird angezeigt, rabattierter Preis korrekt verbucht
- **Neue Produkte** — 3 Tage lang mit „NEU"-Badge gekennzeichnet
- **Nachrichten-Center** — alle eingehenden User-Nachrichten einsehen, beantworten und löschen
- **Direktnachricht** — gezielte Nachricht an einzelne Nutzer senden
- **Broadcast** — Info oder Angebot an alle Nutzer gleichzeitig senden

### 🔔 Benachrichtigungen
- **Nachrichten-Badge** — Symbol in der Leiste zeigt ungelesene Admin-Antworten, Direktnachrichten und Ankündigungen in Echtzeit
- **Monatserinnerung** — automatisches Banner am 1. jedes Monats

---

## 🛠 Technik

| | |
|---|---|
| **Frontend** | Vanilla HTML, CSS, JavaScript — keine Build-Tools, keine Frameworks |
| **Hosting** | GitHub Pages |
| **Datenbank** | Firebase Realtime Database (kostenloser Spark Plan) |
| **Auth** | PIN-basiert, Session-Persistenz via localStorage |
| **Echtzeit-Sync** | Firebase-Listener — alle Geräte synchronisiert ohne Seite neu laden |

---

## 🚀 Setup

### 1. Firebase einrichten
1. Gehe auf [console.firebase.google.com](https://console.firebase.google.com) und erstelle ein neues Projekt
2. Klicke auf das **`</>`**-Symbol um eine Web-App zu registrieren
3. Gehe zu **Build → Realtime Database** → Datenbank erstellen → Testmodus
4. Kopiere deinen `firebaseConfig`-Block

### 2. Datenbankregeln setzen
In der Firebase Console unter **Realtime Database → Regeln**:
```json
{
  "rules": {
    ".read": true,
    ".write": true
  }
}
```

### 3. `index.html` anpassen
Trage deinen eigenen `firebaseConfig`-Block in die `index.html` ein.

### 4. Auf GitHub Pages deployen
1. Repository erstellen und `index.html` + `README.md` hochladen
2. **Settings → Pages → Branch: main, Folder: / (root) → Save**
3. Nach 1–2 Minuten ist die App live unter `https://username.github.io/repository-name/`

---

## 📁 Projektstruktur

```
wachenkiosk/
├── index.html      # Die komplette App (eine einzige Datei)
└── README.md       # Diese Datei
```

---

*Idee Thomas B. · Erstellt vom Medien- & Kreativteam*
