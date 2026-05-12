# Satz des Pythagoras

Eine interaktive Webseite zum Satz des Pythagoras — mit Dashboard zum Rechnen
**und** einer echten Animation, die den Beweis Schritt für Schritt visuell
herleitet.

> **a² + b² = c²**

## Inhalt

| Datei | Beschreibung |
|---|---|
| [`index.html`](index.html) | **Startseite** — Auswahl zwischen Animation und Dashboard. |
| [`animation.html`](animation.html) | **Animierter Beweis** — bewegte Herleitung von `a² + b² = c²` durch Flächenumlegung. Mit Play/Pause, Schritt-vor/zurück und Tempo-Regler. |
| [`dashboard.html`](dashboard.html) | **Dashboard** — Werte für `a`, `b` oder `c` eintragen, statische Flächendarstellung mit Schritt-für-Schritt-Herleitung. |

## Die Animation

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
