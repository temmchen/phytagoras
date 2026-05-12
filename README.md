# Mathe-Animationen — Pythagoras &amp; Trigonometrie

Interaktive Webseite mit animierten Visualisierungen für Schüler:

- **Satz des Pythagoras** — animierter Beweis und Dashboard zum Rechnen
- **Trigonometrie** — Sinus, Kosinus, Tangens am Einheitskreis
- **Umkehrfunktionen** — arcsin, arccos, arctan

## Inhalt

| Datei | Beschreibung |
|---|---|
| [`index.html`](index.html) | **Startseite** — Themen-Übersicht: Pythagoras &amp; Trigonometrie. |
| [`animation.html`](animation.html) | **Pythagoras-Animation** — bewegte Herleitung von `a² + b² = c²` durch Flächenumlegung. Mit Play/Pause, Schritt-Steuerung und Tempo-Regler. |
| [`dashboard.html`](dashboard.html) | **Pythagoras-Dashboard** — Werte für `a`, `b` oder `c` eintragen, Flächendarstellung mit Schritt-für-Schritt-Herleitung. |
| [`trigonometrie.html`](trigonometrie.html) | **Sinus / Kosinus / Tangens** — Einheitskreis-Animation mit gleichzeitig wachsenden Kurven. |
| [`umkehrfunktionen.html`](umkehrfunktionen.html) | **arcsin / arccos / arctan** — alle drei Umkehrfunktionen nebeneinander, Ergebnis in Grad UND Bogenmaß. |
| [`winkel-umrechnen.html`](winkel-umrechnen.html) | **Winkel umrechnen & rechnen** — Grad ↔ Bogenmaß, Referenztabelle, Beispiele für Komplement, Supplement, Reduzieren. |

## Die Pythagoras-Animation

`animation.html` zeigt den klassischen Beweis durch **Flächenumlegung** in
10 Phasen:

1. **Einführung** — Wir starten mit dem rechtwinkligen Dreieck.
2. **Dreieck zeichnen** — Katheten `a`, `b` und Hypotenuse `c` werden gezeichnet.
3. **Rechter Winkel** — Markierung des 90°-Winkels zwischen den Katheten.
4. **Quadrate errichten** — Auf jeder Seite wächst ein Quadrat: `a²`, `b²`, `c²`.
5. **Behauptung** — `a² + b² = c²`.
6. **Beweisaufbau** — Zwei identische Quadrate der Seite `(a+b)`.
7. **Aufteilung** — Beide enthalten dieselben 4 Dreiecke, aber unterschiedlich angeordnet.
8. **Umlegung** — Die Dreiecke gleiten in eine neue Position (animiert).
9. **Gleichheit** — `4·Dreiecke + c² = 4·Dreiecke + a² + b²`.
10. **Folgerung** — `c² = a² + b²` ✓.

### Steuerung

- **▶ Abspielen / ⏸ Pause** — Animation starten/anhalten
- **↻ Neustart** — von vorn beginnen
- **⟵ / ⟶** — einen Schritt zurück / vor
- **Tempo** — Wiedergabegeschwindigkeit von 0.3× bis 2.5×
- **a, b eingeben** — Die Geometrie passt sich an neue Werte an

## Trigonometrie-Seite

`trigonometrie.html` zeigt links den **Einheitskreis** mit einem rotierenden
Punkt und farblich markierten Strecken für sin α (rot, senkrecht), cos α
(blau, waagerecht) und tan α (grün, auf der Tangentenlinie). Rechts werden
die Kurven der drei Funktionen gleichzeitig gezeichnet, während der Winkel
wächst. Mit Schieberegler, Auto-Abspielen und Snap-Buttons für die typischen
Winkel 30°, 45°, 60°, 90°.

## Umkehrfunktionen-Seite

`umkehrfunktionen.html` zeigt **alle drei** Umkehrfunktionen **gleichzeitig**
nebeneinander: arcsin, arccos und arctan jeweils mit eigenem Schieberegler,
Mini-Einheitskreis (mit Hauptwertbereich), Graph der Umkehrfunktion und einer
Ergebnis-Anzeige in **Grad UND Bogenmaß** (mit exakter π-Darstellung wo
möglich, z. B. „π/6"). Auf schmalen Bildschirmen stapeln sich die drei Panels
vertikal.

## Winkel umrechnen

`winkel-umrechnen.html` enthält:

- **Interaktiver Umrechner** Grad ↔ Bogenmaß mit Einheitskreis-Darstellung
- **Referenztabelle** der typischen Winkel (0°, 30°, 45°, 60°, 90°, 120°, 135°,
  150°, 180°, 270°, 360°) mit Bogenmaß als π-Bruch und Dezimalwert,
  sin/cos/tan-Werten. Klick auf eine Zeile übernimmt den Wert.
- **Rechenbeispiele** zu Winkeln addieren, Komplement (90°−α),
  Supplement (180°−α), Reduzieren modulo 360°, Grad→Bogenmaß und zurück
- **Live-Rechner** für aktuellen Winkel: Komplement, Supplement,
  Vollwinkel-Reduktion, Quadrant

## Benutzung

Keine Build-Schritte nötig. Einfach öffnen:

```bash
# lokal
open index.html         # macOS
xdg-open index.html     # Linux
start index.html        # Windows
```

Oder einen einfachen lokalen Webserver starten:

```bash
python3 -m http.server 8000
# dann http://localhost:8000/ im Browser öffnen
```

## Technik

- Reines HTML, CSS und JavaScript — keine Abhängigkeiten, kein Build.
- SVG für Geometrie und Animation.
- Animation per `requestAnimationFrame` mit Ease-in/out-Interpolation der
  Polygon-Eckpunkte zwischen den beiden Konfigurationen.
