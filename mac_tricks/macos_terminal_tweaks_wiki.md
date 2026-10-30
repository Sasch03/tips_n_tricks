# macOS Terminal Tweaks & Anpassungen

Eine Sammlung von nützlichen Terminal-Befehlen (`defaults write`), um macOS individuell anzupassen und die Benutzeroberfläche zu optimieren.

> **Hinweis:** Führe diese Befehle im **Terminal** aus. Einige Anpassungen erfordern Administratorrechte (`sudo`) oder ein Neustarten der entsprechenden Dienste (z. B. `killall Dock`).

---

## 📑 Inhaltsverzeichnis
- [Dock Anpassungen](#dock-anpassungen)
  - [Dock-Einblenden beschleunigen](#dock-einblenden-beschleunigen)
  - [Spacer (Platzhalter) zum Dock hinzufügen](#spacer-platzhalter-zum-dock-hinzufügen)
  - [Versteckte Apps transparent darstellen](#versteckte-apps-transparent-darstellen)
- [System & Benachrichtigungen](#system--benachrichtigungen)
  - [Disk-Auswurf-Warnung deaktivieren](#disk-auswurf-warnung-deaktivieren)
- [Screenshots](#screenshots)
  - [Standard-Dateiformat auf JPG ändern](#standard-dateiformat-auf-jpg-ändern)
- [Launchpad Layout](#launchpad-layout)
- [Sonstiges](#sonstiges)
  - [Bildschirmschoner als Hintergrundbild nutzen](#bildschirmschoner-als-hintergrundbild-nutzen)

---

## Dock Anpassungen

### Dock-Einblenden beschleunigen
Entfernt die Verzögerung und die Animation beim automatischen Ein- und Ausblenden des Docks.

**Aktivieren:**
```bash
defaults write com.apple.dock autohide-delay -float 0; defaults write com.apple.dock autohide-time-modifier -int 0; killall Dock
```

**Rückgängig machen (Standardwerte):**
```bash
defaults write com.apple.dock autohide-delay -float 0.5; defaults write com.apple.dock autohide-time-modifier -int 0.5; killall Dock
```

---

### Spacer (Platzhalter) zum Dock hinzufügen
Fügt leere Abstände im Dock ein, um Apps optisch zu gruppieren. Der Befehl kann mehrfach ausgeführt werden.

**Normaler Spacer:**
```bash
defaults write com.apple.dock persistent-apps -array-add '{tile-data={}; tile-type="spacer-tile";}' && killall Dock
```

**Kleiner Spacer (halbe Höhe):**
```bash
defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="small-spacer-tile";}' && killall Dock
```

> **Tipp:** Ein erstellter Spacer kann einfach per Drag-and-Drop aus dem Dock gezogen werden, um ihn wieder zu entfernen.

---

### Versteckte Apps transparent darstellen
Macht Symbole von ausgeblendeten Anwendungen (Cmd + H) im Dock halbtransparent.

```bash
defaults write com.apple.Dock showhidden -bool TRUE && killall Dock
```

---

## System & Benachrichtigungen

### Disk-Auswurf-Warnung deaktivieren
Deaktiviert die Warnmeldung *"Nicht ordnungsgemäß ausgeworfen"*, wenn ein Laufwerk ohne vorheriges Auswerfen getrennt wird.

> ⚠️ **Wichtig:** Erfordert einen Neustart des Macs, um vollständig wirksam zu werden.

**Deaktivieren:**
```bash
sudo defaults write /Library/Preferences/SystemConfiguration/com.apple.DiskArbitration.diskarbitrationd.plist DADisableEjectNotification -bool YES && sudo pkill diskarbitrationd
```

**Wieder aktivieren:**
```bash
sudo defaults delete /Library/Preferences/SystemConfiguration/com.apple.DiskArbitration.diskarbitrationd.plist DADisableEjectNotification && sudo pkill diskarbitrationd
```

*Alternativ:* Nutzung einer App wie [Ejectify](https://ejectify.app).

---

## Screenshots

### Standard-Dateiformat auf JPG ändern
Ändert das Dateiformat von Screenshots von PNG (Standard) auf JPG.

```bash
defaults write com.apple.screencapture type jpg
```

> **Rückgängig machen:** Ersetze `jpg` am Ende des Befehls durch `png`.

---

## Launchpad Layout

Passe die Anzahl der Spalten und Zeilen im Launchpad an. Ersetze `X` und `Y` durch die gewünschte Anzahl.

**Spaltenanzahl ändern (`X` anpassen):**
```bash
defaults write com.apple.dock springboard-columns -int X; killall Dock
```

**Zeilenanzahl ändern (`Y` anpassen):**
```bash
defaults write com.apple.dock springboard-rows -int Y; killall Dock
```

**Layout auf Standard zurücksetzen:**
```bash
defaults delete com.apple.dock springboard-rows; defaults delete com.apple.dock springboard-columns; defaults write com.apple.dock ResetLaunchPad -bool TRUE; killall Dock
```

---

## Sonstiges

### Bildschirmschoner als Hintergrundbild nutzen
Startet den aktuellen Bildschirmschoner direkt als animierten Schreibtisch-Hintergrund.

```bash
/System/Library/Frameworks/ScreenSaver.framework/Resources/ScreenSaverEngine.app/Contents/MacOS/ScreenSaverEngine -background
```

> **Hinweis:** Beende den Prozess im Terminal mit `Ctrl + C`, um den Bildschirmschoner wieder zu schließen.