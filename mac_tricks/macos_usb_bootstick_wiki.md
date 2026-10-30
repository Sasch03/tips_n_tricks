# Bootfähiges macOS-Installationsmedium erstellen

Diese Anleitung beschreibt, wie du mithilfe des Terminal-Befehls `createinstallmedia` einen bootfähigen USB-Stick für die Installation von macOS / OS X erstellst.

## 📋 Vorbereitung

1. **USB-Stick formatieren:** 
   * Format: **Mac OS Extended (Journaled)**
   * Schema: **GUID-Partitionskarte**
   * Name des Volumes: **`MyVolume`** *(Falls ein anderer Name gewählt wird, muss der Pfad im Befehl angepasst werden)*.
2. **macOS-Installer herunterladen:** 
   * Der Installer muss sich im Ordner `/Applications` (**Programme**) befinden.

> ⚠️ **Hinweis:** Das Ziel-Volume (`MyVolume`) wird während des Vorgangs vollständig gelöscht.

---

## 🚀 Befehle nach macOS / OS X Version

### macOS Sequoia (15)

```
sudo /Applications/Install\ macOS\ Sequoia.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

```

### macOS Sonoma (14)

```
sudo /Applications/Install\ macOS\ Sonoma.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

```

### macOS Ventura (13)

```
sudo /Applications/Install\ macOS\ Ventura.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

```

### macOS Monterey (12)

```
sudo /Applications/Install\ macOS\ Monterey.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

```

### macOS Big Sur (11)

```
sudo /Applications/Install\ macOS\ Big\ Sur.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

```

### macOS Catalina (10.15)

```
sudo /Applications/Install\ macOS\ Catalina.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

```

### macOS Mojave (10.14)

```
sudo /Applications/Install\ macOS\ Mojave.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

```

### macOS High Sierra (10.13)

```
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume

```

### macOS Sierra (10.12)

```
sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ macOS\ Sierra.app

```

### OS X El Capitan (10.11)

```
sudo /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ El\ Capitan.app

```

### OS X Yosemite (10.10)

```
sudo /Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ Yosemite.app

```

### OS X Mavericks (10.9)

```
sudo /Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ Mavericks.app

```

---

## 🛠 Ablauf & Fehlerbehebung

1. Führe den passenden Befehl im **Terminal** aus.
2. Gib dein **Administrator-Passwort** ein, wenn du dazu aufgefordert wirst *(Tastatureingaben werden nicht angezeigt)*.
3. Bestätige das Löschen des USB-Sticks mit `Y` und drücke `Enter`.
4. Warte, bis der Vorgang mit der Meldung `Install media now available at "/Volumes/Install macOS..."` abgeschlossen ist.