# 🎲 Würfel Roller

Eine mobile Würfel-App für EveryApp mit Schüttel-Funktion und Historie.

## Features

- **1-6 Würfel wählen**: Wähle, mit wie vielen Würfeln du gleichzeitig würfeln möchtest
- **Schöne Animationen**: Flüssige Roll-Animationen bei jedem Wurf
- **Schüttel-Erkennung**: Schüttle dein Gerät zum Würfeln (über Beschleunigungssensor)
- **Summen-Anzeige**: Automatische Berechnung der Gesamt-Summe
- **Wurf-Historie**: Speichert die letzten 20 Würfe mit Zeitstempel
- **Vibration**: Haptisches Feedback bei jedem Wurf
- **Mobil-optimiert**: Responsives Design für Smartphones
- **Offline-fähig**: Funktioniert auch im Browser ohne Bridge (Fallback-Modus)

## Installation in EveryApp

1. Öffne die **EveryApp** auf deinem Android-Gerät
2. Tippe auf "App hinzufügen" oder das ➕-Symbol
3. Füge diese URL ein:

```
https://github.com/Krust3nKaese3/EveryRollDice
```

4. Bestätige die angeforderten Berechtigungen:
   - **Storage**: Zum Speichern der Wurf-Historie
   - **Sensors**: Für die Schüttel-Erkennung (Beschleunigungssensor)
   - **Vibration**: Für haptisches Feedback beim Würfeln

5. Die App wird heruntergeladen und ist sofort einsatzbereit!

## Benutzung

### Würfel-Anzahl wählen
Tippe oben auf eine der Zahlen (1-6), um die Anzahl der Würfel festzulegen.

### Würfeln
Es gibt drei Möglichkeiten zu würfeln:
1. **Würfeln-Button**: Tippe auf den großen "🎲 Würfeln"-Button
2. **Schüttel-Funktion**: Aktiviere die Schüttel-Erkennung und schüttle dein Gerät
3. Beide Methoden zeigen eine schöne Animation und vibrieren kurz

### Historie ansehen
Deine letzten 20 Würfe werden unten in der Historie angezeigt, inklusive:
- Einzelne Würfel-Werte
- Gesamt-Summe
- Uhrzeit des Wurfs

Die Historie kannst du mit dem "Löschen"-Button zurücksetzen.

## Technische Details

- **Benötigte Berechtigungen**: `storage`, `sensors`, `vibration`
- **Manifest**: `everyapp.json`
- **Entry Point**: `index.html`
- **Alle Ressourcen inline**: CSS und JavaScript sind direkt in der HTML-Datei eingebettet

## Entwicklung

Die App ist als Single-Page-HTML-Datei entwickelt und nutzt die EveryApp-Bridge-API:
- `window.EveryAppBridge.storage.*` für persistente Datenspeicherung
- `window.EveryAppBridge.sensors.getAccelerometer()` für Schüttel-Erkennung
- `window.EveryAppBridge.vibration.vibrate()` für haptisches Feedback

### Graceful Degradation
Die App erkennt automatisch, ob sie innerhalb von EveryApp oder in einem normalen Browser läuft. Im Browser-Modus:
- Wird eine Warnung angezeigt
- LocalStorage wird statt Bridge-Storage verwendet
- DeviceMotion API wird für Schüttel-Erkennung genutzt
- Vibration wird übersprungen

## Repository-Struktur

```
EveryRollDice/
├── everyapp.json    # Manifest mit App-Metadaten
├── index.html       # Vollständige App (HTML/CSS/JS)
└── README.md        # Diese Datei
```

## Lizenz

Open Source - frei nutzbar

---

**Viel Spaß beim Würfeln! 🎲**
