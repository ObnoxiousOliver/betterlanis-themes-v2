# Better LANiS Themes v2

**Table of Contents**
- [Better LANiS Themes v2](#better-lanis-themes-v2)
  - [Struktur](#struktur)
  - [manifest.json - Datei](#manifestjson---datei)
    - [preview - Eigenschaft](#preview---eigenschaft)
    - [Komplettes Beispiel](#komplettes-beispiel)
  - [CSS - Datei](#css---datei)
    - [Ein Thema schreiben](#ein-thema-schreiben)

## Struktur

Der Ordner des Themas muss mit `.bl-theme` enden, ansonsten wird das Theme in Better LANiS nicht angezeigt, z.B `my-theme.bl-theme`.

Der Name wird kleingeschiben und Wörter werden mit einem Minus getrennt.

Alle Dateien die zum Thema gehören kommen in den Themenordner

```
  my-theme.bl-theme
  |- icon.png
  |- manifest.json
  |- css
    |- main.css
```

## manifest.json - Datei

Ein Thema muss ein `manifest.json` beinhalten.
Alle Informationen bezüglich des Themes ist in diesem enthalten. Das `manifest.json` ist im [JSON](https://developer.mozilla.org/docs/Learn/JavaScript/Objects/JSON) format.

| Eigenschaft   | Typ             | Bescheibung                                                                                         | Verwengung                                                   |
| ------------- | --------------- | --------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| `name`        | `String`        | Der Angzeigename vom Thema.                                                                         | `"name": "My Theme"`                                         |
| `version`     | `String`        | Die Version vom Thema.<br>Der String muss von [SemVer](https://semver.org/) geparsed werden können. | `"version": "1.0.0"`                                           |
| `author`      | `String`        | Der Author vom Thema.                                                                               | `"author": "Oliver"`                                         |
| `authors`     | `Array[String]` | Zusätzliche Authoren vom Thema.                                                                     | `"authors": [ "Random Dude", "Another Random Dude" ]`        |
| `description` | `String`        | Die Beschreibung vom Thema.                                                                         | `"description": "This is my Theme"`                          |
| `css`         | `String`        | Der relative Pfad zur CSS-Datei.                                                                    | `"css": "css/main.css"`                                      |
| `preview`     | `Object`        | Drei Vorschaufarben vom Thema. [Mehr info](#preview---eigenschaft)                                    | `"preview": { "1": "#43fa76", "2": "#57da35", "3": "#222" }` |
| `icon`        | `String`        | Der relative Pfad zur Bild-Datei für das Icon vom Thema.                                            | `"icon": "icon.png"`                                         |

### preview - Eigenschaft

| Eigenschaft | Typ      | Bescheibung                                                                                                    | Verwengung                      |
| ----------- | -------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------- |
| `1`         | `String` | Vorschaufarbe 1. in Hex. Wird auch als Icon farbe verwendet, falls keine Bild-Datei für das Icon angegeben ist. | `"1": "#43fa76"`                |
| `2`         | `String` | Vorschaufarbe 2. in Hex.                                                                                       | `"3": "#57da35"`                |
| `3`         | `String` | Vorschaufarbe 3. in Hex.                                                                                       | `"2": "#222"` funktioniert auch |

### Komplettes Beispiel

```json
{
  "name": "My Theme",
  "version": "1.0.0",
  "author": "Oliver",
  "authors": [
    "Random Dude",
    "Another Random Dude" 
  ],
  "description": "This is my Theme",
  "css": "css/main.css",
  "preview": {
    "1": "#43fa76",
    "2": "#57da35",
    "3": "#222"
  },
  "icon": "icon.png"
}
```

## CSS - Datei

In der CSS wird das Thema geschrieben. Der Syntax ist [CSS](https://developer.mozilla.org/de/docs/Learn/Getting_started_with_the_web/CSS_basics). Dadurch können komplexere Themen geschrieben werden die Better LANiS komplett ändern können. Mit den DevTools und wissen in CSS kann Better LANiS wie alles aussehen.

### Ein Thema schreiben

Das Theme was wir hier schreiben wird nur die Variablen des Aussehens von Better LANiS ersetzten. Alle Farben sind auf dem `:root` Element gesetzt. Das Element folgt dann zwei geschweifte Klammen `{}`.

```css
:root {

}
```

Zwischen den Klammern können dann die Variablen gesetzt werden.
Eine Variable in CSS ist dekläriert mit `--`. Da diese Variablen schon existieren werden die Werte ersetzt.

```css
:root {
  /* Colors */
  --red: #f44;
  --green: #6f6;
  --blue: #35f;
  --yellow: #fc3;
  --diamond: #75dfff;

  /* Background Colors  */
  --primary-background: #e5e5e5;
  --secondary-background: #f5f5f5;
  --tertiary-background: #efefef;
  
  /* Background Modifiers  */
  --background-modifier-unfocused: #0006;
  --background-modifier-selected: #0000000a;
  --background-modifier-hover: #00000015;
  --background-modifier-active: #0003;

  /* Popup */
  --popup-background: #fff;
  --popup-foreground: #000;

  /* Foreground Colors  */
  --primary-foreground: #000;
  --secondary-foreground: #555;
  --muted-foreground: #999;

  /* Warning */
  --warning: #fc4;
  --warning-background: #221808;
  --warning-foreground: #000;

  /* Error */
  --error: #f44;
  --error-background: #220808;
  --error-foreground: #fff;

  /* Button */
  --button: #d7d7d7;
  --button-foreground: #000;
  --button-highlight: #222;
  --button-highlight-foreground: #fff;

  /* Scrollbar */
  --scrollbar-track: #e5e5e5;
  --scrollbar-thumb: #d1d1d1;

  /* Drop Shadow */
  --elevation-high: #0002 0 5px 10px;
  --elevation-medium: #0002 0 2px 5px;
  --elevation-low: #0002 0 1px 2px;

  /* Typography */
  --font: Heebo, "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  --header-font: Poppins, "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
}
```

Alle CSS-Variablen können in den **DevTools > Elements > Styles > :root** eingesehen werden.
