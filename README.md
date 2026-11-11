# ♞ Familienschach – Opa Walter gegen Marten

Online-Schach für zwei Tablets.
Figur antippen, dann Zielfeld antippen. Der **Hilfsmodus** zeigt mit grünen Punkten,
wohin eine Figur ziehen darf.

## Auf GitHub veröffentlichen (einmalig, ca. 5 Minuten)

1. Auf <https://github.com> anmelden (oder kostenlos registrieren).
2. Oben rechts **+ → New repository** wählen.
   - Name z. B. `familienschach`
   - **Public** auswählen (für kostenloses GitHub Pages nötig)
   - **Create repository** klicken.
3. Auf der neuen Seite **„uploading an existing file“** anklicken,
   **alle Dateien** hineinziehen (`index.html`, `README.md`, `manifest.webmanifest`,
   `favicon.png`, `apple-touch-icon.png`, `icon-192.png`, `icon-512.png`)
   und **Commit changes** klicken.
4. Im Repository auf **Settings → Pages** gehen.
   - Bei *Source*: **Deploy from a branch**
   - Bei *Branch*: **main** und **/ (root)** wählen → **Save**
5. Nach 1–2 Minuten ist das Spiel erreichbar unter
   `https://DEIN-BENUTZERNAME.github.io/familienschach/`

Tipp: Die Adresse auf beiden Tablets öffnen und über „Teilen → Zum Home-Bildschirm“
als App-Symbol ablegen – dann erscheint das Symbol mit Opa und Marten.

## So wird gespielt

1. Beim ersten Öffnen fragt jedes Tablet: **„Wer spielt auf diesem Tablet?“**
   → einmal **Opa Walter** bzw. **Marten** antippen. Das Tablet merkt sich die Auswahl.
2. Die Tablets finden sich automatisch. Oben rechts steht, ob der andere gerade
   online ist („Opa Walter ist online“ / „… ist offline“).
3. **Es müssen nicht beide gleichzeitig online sein:** Wer am Zug ist, zieht einfach –
   der andere sieht den Zug, sobald er das Spiel das nächste Mal öffnet.
4. Bei **„Neue Partie“** wird gefragt, wer mit Weiß spielt (und anfängt).

- Jeder sieht seine eigenen Figuren unten.
- Hat der andere gezogen, ertönt ein leiser Ton.
- „Zug zurück“ und „Neue Partie“ wirken auf beiden Tablets.
- Die Partie bleibt gespeichert, auch wenn die Seite geschlossen wird.
- Falsche Person gewählt? Unten auf **„Person wechseln“** tippen.

## Spielstand

Rechts steht für Opa Walter und Marten, wie viele Partien jeder **gewonnen**, **remis**
gespielt und **verloren** hat. Eine Partie zählt, sobald sie mit Matt oder Remis endet.
Wird der letzte Zug zurückgenommen, wird sie wieder herausgerechnet. Wer mitten in einer
Partie auf „Neue Partie“ tippt, beendet sie ohne Wertung. Der Spielstand ist auf beiden
Tablets gleich und bleibt gespeichert.

## Sprachchat

- Rechts im Spiel auf **„🎤 Sprechen“** tippen. Auf dem anderen Tablet erscheint
  „… ruft an!“ – dort auf **Annehmen** tippen.
- Beim ersten Mal fragt das Tablet, ob die Seite das **Mikrofon** benutzen darf → **Erlauben**.
- Während des Gesprächs: **Stumm** schaltet das eigene Mikrofon aus, **Auflegen** beendet das Gespräch.
  Ein grüner Ring um das Gesicht zeigt, wenn der andere gerade spricht.
- Tipp: Mit Kopfhörern gibt es kein Echo.
- Das Gespräch läuft direkt von Tablet zu Tablet und wird nirgends gespeichert.

## Technik

- Eine Webseite (`index.html`), kein eigener Server und kein Konto nötig.
- Die Züge laufen verschlüsselt über **zwei kostenlose öffentliche Nachrichtenserver**
  (EMQX und HiveMQ, MQTT über sichere WebSockets) gleichzeitig. Fällt einer aus, läuft
  alles über den anderen weiter. Der letzte Spielstand bleibt dort gespeichert.
- Der **Sprachchat** ist eine direkte Verbindung zwischen den Tablets (WebRTC). In sehr
  seltenen Netzen (z. B. manche Firmen- oder Hotel-WLANs) kommt er nicht zustande –
  das Spiel funktioniert dann trotzdem.
- Bei Problemen: unten auf **„Person wechseln“** tippen – dort steht, welcher Server
  erreichbar ist und ob der andere online ist.
- Vollständige Schachregeln: Rochade, en passant, Bauernumwandlung, Schach, Matt, Patt,
  50-Züge-Regel, dreifache Stellungswiederholung.
