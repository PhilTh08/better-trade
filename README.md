# Better Trade

Fabric-Client-Mod für Minecraft Java **26.3**, **Java 25** und Fabric Loader **0.19.5 oder neuer**. Fabric API wird nicht benötigt.

## Installation

Die JAR aus einem veröffentlichten [Release](https://github.com/PhilTh08/better-trade/releases) in den `mods`-Ordner legen. Vorhandene ältere Better-Trade-JARs ersetzen, damit nur eine Version geladen wird.

## Funktionen und Standardtasten

- **Shift halten:** freigegebene Materialverkäufe wiederholen.
- **G:** ausgewähltes Angebot beim Öffnen des Villagers vollständig abarbeiten.
- **B:** Einstellungen; dort auch der Bereich **Updates**.
- **J:** Villager-Statistiken, Preisvergleich und Einstellungen.
- **M:** anvisierte oder gerade geöffnete Kiste markieren/freigeben.
- Kompakte Item-Buttons oben links: Lager-Menü, Sortieren, einblendbare Suche und Markierung.
- Grün markierte Kisten, mehrere erlaubte Itemarten pro Kiste, gemeinsamer Lagerverbund.
- Bewegung im normalen Kistenfenster; während Suche und Einstellungen wird keine Bewegung ausgelöst.
- Villager-Symbole: hellgrüner Farbstoff für einen bezahlbaren, zuletzt verfügbaren Trade; Redstone bei ausverkauften Angeboten oder fehlendem Material; Papier bei unbekannten Angeboten. Die Vanilla-Server übertragen Angebote erst beim Öffnen des Handelsfensters. Außerhalb des Fensters wird deshalb der zuletzt geprüfte Bestand verwendet; vorhandene eigene Items werden aktuell berücksichtigt.

## Updates als Besitzer freigeben

1. Die neue Version prüfen. `fabric.mod.json` muss die neue Versionsnummer enthalten, z.B. `5.0.1`.
2. Die Datei exakt `Better-Trade-5.0.1-Minecraft-26.3-Fabric.jar` nennen.
3. Unter **Releases → Draft a new release** den Tag `v5.0.1` wählen und die JAR anhängen.
4. Zunächst **Save draft** wählen. Entwürfe und Vorabversionen werden vom Updater nicht angeboten.
5. Wenn du die Version freigeben möchtest, den Entwurf öffnen und **Publish release** wählen. Das Release als neueste stabile Version kennzeichnen.

GitHub liefert die SHA-256-Prüfsumme des hochgeladenen Assets. Der Updater akzeptiert ausschließlich eine passende, veröffentlichte stabile JAR dieses Repositories und prüft Prüfsumme, Dateigröße, Mod-ID, Minecraft-Version und Mod-Version. Eine neue Mod-Version kann nicht aus einer Beschreibung oder einem Versions-Tag allein erzeugt werden: Die gebaute JAR muss hochgeladen werden.

## Installation eines angebotenen Updates

Der Client prüft asynchron beim Start und danach alle sechs Stunden. In **B → Updates** lässt sich jederzeit manuell prüfen. **Update laden & nach Beenden installieren** lädt und prüft die Datei; ein separater Helfer wartet auf das Beenden von Minecraft. Danach wird die vorhandene Mod-Datei ersetzt und eine Sicherung mit der Endung `.bettertrade-backup` behalten. Beim nächsten Spielstart ist die neue Version aktiv. Der Updater beendet das Spiel nicht selbst und benötigt kein GitHub-Passwort oder Token.

Bei einer fehlgeschlagenen Prüfung bleibt die bisherige Mod unverändert. Weitere Details und die vollständige Anleitung befinden sich als `BETTER_TRADE_LIESMICH.txt` in der JAR.

## Prüfung

Gegen die tatsächlichen 26.3-Klassen kompiliert. Automatisierte Tests verwenden reale Minecraft-Container mit simulierten Netzwerkantworten. Installation und Prozess-Warten des Updaters werden mit echten separaten Java-Prozessen geprüft; sämtliche Mixins werden durch Fabric geladen. Ein manueller Test in einer gerenderten Spielwelt ersetzt diese Prüfungen nicht und wurde bei der Erstellung nicht durchgeführt.
