# ♞ Familienschach

Online-Schach für zwei Tablets – z. B. für Enkel und Opa.
Figur antippen, dann Zielfeld antippen. Der **Hilfsmodus** zeigt mit grünen Punkten,
wohin eine Figur ziehen darf.

## Auf GitHub veröffentlichen (einmalig, ca. 5 Minuten)

1. Auf <https://github.com> anmelden (oder kostenlos registrieren).
2. Oben rechts **+ → New repository** wählen.
   - Name z. B. `familienschach`
   - **Public** auswählen (für kostenloses GitHub Pages nötig)
   - **Create repository** klicken.
3. Auf der neuen Seite **„uploading an existing file“** anklicken,
   die Dateien `index.html` und `README.md` hineinziehen und **Commit changes** klicken.
4. Im Repository auf **Settings → Pages** gehen.
   - Bei *Source*: **Deploy from a branch**
   - Bei *Branch*: **main** und **/ (root)** wählen → **Save**
5. Nach 1–2 Minuten ist das Spiel erreichbar unter
   `https://DEIN-BENUTZERNAME.github.io/familienschach/`

Tipp: Die Adresse auf beiden Tablets öffnen und über „Teilen → Zum Home-Bildschirm“
als App-Symbol ablegen.

## So wird gespielt

1. **Tablet 1:** „Neues Spiel starten“ → Farbe und Namen wählen.
   Es erscheint ein **6-stelliger Spielcode** und ein Einladungslink.
2. **Tablet 2:** Den Link öffnen **oder** „Einem Spiel beitreten“ wählen und den Code eingeben.
3. Sobald oben „verbunden“ steht, kann es losgehen. Weiß beginnt.

- Jedes Tablet sieht seine eigenen Figuren unten.
- Hat der andere gezogen, ertönt ein leiser Ton.
- „Zug zurück“ und „Neue Partie“ wirken auf beiden Tablets.
- Wird die Seite geschlossen, bleibt die Partie gespeichert. Beim nächsten Öffnen
  verbindet sich das Tablet automatisch wieder. Dafür muss das Tablet, das das Spiel
  gestartet hat, ebenfalls geöffnet sein.
- „Zu zweit an diesem Tablet“ funktioniert auch ganz ohne Internet.

## Technik

- Eine einzige Datei (`index.html`), kein Server und kein Konto nötig.
- Die Tablets verbinden sich direkt miteinander (WebRTC über die freie Bibliothek
  [PeerJS](https://peerjs.com) und deren kostenlosen Vermittlungsserver).
- Es werden nur die Züge und die Namen übertragen.
- Vollständige Schachregeln: Rochade, en passant, Bauernumwandlung, Schach, Matt, Patt,
  50-Züge-Regel, dreifache Stellungswiederholung.
