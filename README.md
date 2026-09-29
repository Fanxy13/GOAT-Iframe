# Ziegen-Buddy

<p align="center">
  <img src="docs/ziege.gif" alt="Pixel-Ziege mit Krone, die zum Gras läuft, frisst, hüpft und meckert" width="380">
</p>

Eine winzige Pixel-Ziege als Haustier für deine Website. Sie läuft herum, grast, klettert auf Felsen, meckert und lässt sich streicheln. Alles steckt in einer einzigen HTML-Datei, ohne Abhängigkeiten.

Inspiriert vom `/buddy`-Begleiter in Claude Code.

## Was sie kann

- **Eigenes Leben:** Sie läuft herum, grast, käut wieder, blinzelt, wedelt mit dem Schwanz, klettert auf Felsen, legt sich hin und schläft.
- **Streicheln:** Ein Klick auf die Ziege lässt Herzen aufsteigen. Wer übertreibt, kassiert einen Kopfstoss.
- **Füttern:** Ein Klick auf den Boden lässt Gras wachsen. Die Ziege trabt hin und frisst es.
- **Hochheben:** Packen, hochziehen und werfen. Sie landet auf allen vier Hufen.
- **Sprechblasen** mit frechen Sprüchen.
- **Acht Hüte**, von der Krone bis zur Schweizer Mütze.
- **Hunger, Laune und Energie.** Sterben kann sie nicht.
- **Schlüpft aus einem Ei.** Ja, Ziegen schlüpfen aus Eiern. Frag nicht.

## Zwei Modi

| Normaler Modus | Simpel-Modus |
|:---:|:---:|
| <img src="docs/normal.png" alt="Ziege auf einer Bergweide mit Chatverlauf, Eingabefeld und Knöpfen" width="400"> | <img src="docs/iframe.png" alt="Ziege mit Krone unten auf einer Beispiel-Website, Hintergrund durchsichtig" width="400"> |
| Bergweide mit Chat, Befehlen und Knöpfen | Nur die Ziege auf durchsichtigem Hintergrund, zum Einbetten |

## Loslegen

Lade [`ziegen-buddy.html`](ziegen-buddy.html) herunter und öffne sie im Browser. Mehr braucht es nicht: keine Installation, keine Bibliotheken, kein Build-Schritt.

## Auf deiner Website einbetten

Leg `ziegen-buddy.html` auf deinen Webserver und binde sie mit einem iframe ein:

```html
<iframe src="ziegen-buddy.html?modus=simpel&hut=krone"
        title="Ziegen-Buddy"
        style="width:100%; height:150px; border:0"
        loading="lazy"></iframe>
```

Mit `modus=simpel` erscheint nur die Ziege, der Hintergrund bleibt durchsichtig. Alles andere stellst du über weitere Parameter in der Adresse ein, jeweils mit `&` verbunden.

**Ohne eigenen Server:** Aktiviere GitHub Pages für dieses Repository (Settings → Pages → Branch `main`). Danach kannst du diese Adresse als `src` verwenden:

```text
https://<dein-name>.github.io/ziegen-buddy/ziegen-buddy.html?modus=simpel
```

### Einstellungen

| Parameter | Standard | Beschreibung |
|---|---|---|
| `modus` | – | `simpel`: nur die Ziege, durchsichtiger Hintergrund |
| `name` | zufällig | Name der Ziege |
| `hut` | `keiner` | `krone`, `zylinder`, `propeller`, `heiligenschein`, `zauberhut`, `muetze`, `entli`, `edelweiss` |
| `groesse` | `3` | Pixelgrösse 1 bis 8, oder `s`, `m`, `l` |
| `streicheln` | `ja` | Klick auf die Ziege zeigt Herzen |
| `fuettern` | `ja` | Klick auf den Boden lässt Gras wachsen |
| `hochheben` | `ja` | Ziege packen, hochziehen und werfen |
| `sprechblasen` | `ja` | Sprechblasen anzeigen |
| `plappern` | `ja` | redet ab und zu von selbst |
| `laufen` | `ja` | `nein`: bleibt an ihrem Platz |
| `schlafen` | `ja` | legt sich hin und schläft, wenn sie müde ist |
| `beduerfnisse` | `ja` | wird hungrig und müde |
| `gras` | `ja` | Gras und Blumen wachsen von selbst |
| `boden` | `nein`\* | Graslinie und Erde |
| `berge` | `nein`\* | Berge im Hintergrund |
| `felsen` | `nein`\* | Felsen zum Klettern |
| `ei` | `nein`\* | schlüpft beim ersten Besuch aus einem Ei |
| `ton` | `nein` | Geräusche, sobald jemand in den Rahmen geklickt hat |
| `speichern` | `ja` | merkt sich Name, Hut und Hunger im Browser |
| `tempo` | `1` | Laufgeschwindigkeit, 0.25 bis 3 |
| `start` | `mitte` | `links`, `mitte`, `rechts` oder 0 bis 100 |
| `farben` | `hell` | `dunkel` für dunkle Seiten (Berge, Boden, Sprechblase) |
| `blase` | wie `farben` | nur die Sprechblase: `hell` oder `dunkel` |
| `hintergrund` | durchsichtig | Farbe statt durchsichtig, z. B. `ffffff` |
| `schema` | – | `dunkel`, falls deine Seite `color-scheme: dark` setzt |

\* Im normalen Modus sind `boden`, `berge`, `felsen` und `ei` eingeschaltet. Statt `ja` und `nein` gehen auch `1` und `0` oder `an` und `aus`.

### Beispiele

```text
?modus=simpel&groesse=2&laufen=nein&hochheben=nein    kleine Ziege, die an ihrem Platz bleibt
?modus=simpel&boden=ja&felsen=ja                       mit Graslinie und Kletterfelsen
?modus=simpel&farben=dunkel&boden=ja&berge=ja          für eine dunkle Seite
?modus=simpel&plappern=nein                            redet nur, wenn man mit ihr spielt
```

### Gut zu wissen

- **Klicks:** Der durchsichtige Rahmen fängt trotzdem Klicks ab. Setz ihn dorthin, wo darunter nichts Klickbares liegt, zum Beispiel direkt über den Footer.
- **Dunkle Seiten:** `farben=dunkel` passt Berge, Boden und Sprechblase an. Setzt deine Seite selbst `color-scheme: dark`, braucht es zusätzlich `schema=dunkel`, sonst zeichnet der Browser einen weissen Hintergrund in den Rahmen.
- **Datenschutz:** Der Simpel-Modus lädt nichts von fremden Servern. Der normale Modus holt die Schriften DM Mono und Pixelify Sans von Google Fonts.
- **Speicher:** Name, Hut und Hunger landen im `localStorage` des Besuchers. Mit `speichern=nein` bleibt nichts im Browser.
- **Handy:** Wischen über die Wiese scrollt die Seite weiter. Nur die Ziege selbst lässt sich packen.

## Befehle im normalen Modus

Tipp `/` ins Eingabefeld, dann erscheint die Befehlsliste.

| Befehl | Wirkung |
|---|---|
| `/buddy pet` | streicheln |
| `/buddy feed` | Gras hinwerfen |
| `/buddy trick` | Kunststück |
| `/buddy mäh` | meckern |
| `/buddy sleep` | hinlegen oder wecken |
| `/buddy hat [name]` | Hut wechseln |
| `/buddy card` | Steckbrief mit Werten wie STURHEIT 99 |
| `/buddy name <name>` | umbenennen |
| `/buddy size s\|m\|l` | Grösse ändern |
| `/buddy sound` | Ton an oder aus |
| `/buddy mute` | Sprechblasen aus oder an |
| `/buddy off`, `/buddy on` | verstecken und zurückholen |
| `/buddy reset` | neue Ziege schlüpfen lassen |
| `/clear` | Verlauf leeren |

Normale Nachrichten beantwortet sie auch, und `Esc` unterbricht, was sie gerade tut. Ist sie hungrig, frisst sie deine Nachricht auf.

## Technik

- Eine einzige HTML-Datei mit rund 105 KB, reines JavaScript ohne Bibliotheken.
- Die Pixel-Art steckt als Text-Raster im Code und wird auf `<canvas>` in ganzzahligen Pixelgrössen gezeichnet, damit sie auf jedem Bildschirm scharf bleibt.
- 17 Posen, 8 Hüte und Partikel für Herzen, Zzz, Sterne und Eierschalen.
- Die Geräusche entstehen live mit der Web Audio API.
- Bei `prefers-reduced-motion` fallen Wackeln und Bildschirmschütteln weg.

## Lizenz

MIT
