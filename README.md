# Bauablaufplan-Tool · Pure Energy Germany

Eigenständiges, browserbasiertes Tool zur Erstellung von Bauablaufplänen für
WEESS-PowerTower-Installationen. Dient als **Schnittstelle für Elektrofachfirmen**:
Felder ausfüllen → als PDF (A4 quer) speichern → ausgefülltes PDF an Pure Energy
zurücksenden.

## Eigenschaften

- **Vollständig offline / unabhängig** – eine einzige `index.html`, keine externen
  Abrufe (Schriften sind eingebettet). Kein Build, kein Server, keine Datenbank nötig.
- **Editierbar im Browser** – alle Kopf-, Kontakt- und Hinweisfelder direkt anklickbar.
- **Phasen-Editor** – Bezeichnung, Strang (AC/DC), Haus, Startdatum und Dauer in
  **Werktagen**.
- **Automatische Terminübersicht (Gantt)** – Wochenenden und gesetzliche
  **Feiertage in NRW** werden nicht als Arbeitstage gezählt; Balken laufen im
  Kalender entsprechend länger. Feiertage werden je Jahr automatisch berechnet
  (inkl. beweglicher Feiertage wie Karfreitag, Christi Himmelfahrt, Fronleichnam).
- **Meilensteine** – z. B. zugesicherte Baufreiheit.
- **PDF-Export** – über die Druckfunktion des Browsers (Ziel: „Als PDF speichern").

## Nutzung

1. `index.html` im Browser öffnen.
2. Felder ausfüllen / anpassen, Phasen und Meilensteine eintragen.
3. Button **„Als PDF speichern (A4 quer)"** → im Druckdialog **„Als PDF speichern"** wählen.

Die Hilfe-Box und der Editor werden im PDF automatisch ausgeblendet.

## Einbindung in die Plattform

Die Datei kann per `<iframe>` eingebettet werden:

```html
<iframe src="index.html" style="width:100%;height:100vh;border:0;"></iframe>
```

Die Zugangs-/Rechtesteuerung erfolgt zentral über die Plattform.

## Anpassen

- **Branding-Farben:** CSS-Variablen ganz oben im `<style>`-Block
  (`--teal #0F6E56`, `--dark #04342C`, `--dc #6BBF59`).
- **Vorbelegte Daten:** im `<script>`-Block in den Arrays `phases` und `milestones`.
- **Feiertage:** Funktion `holidaysNRW(year)` – bei Bedarf um weitere Bundesländer erweiterbar.

---
Pure Energy Germany · Oskomera GmbH · Debbingstraße 16a, 46286 Dorsten · USt-IdNr. DE293182720
