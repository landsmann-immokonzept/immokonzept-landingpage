# ImmoKonzept Landingpage

Statische Landingpage für ImmoKonzept GbR.

## Deployment auf Netlify

### Option 1: Drag & Drop (schnellste)

1. Gehe zu [app.netlify.com](https://app.netlify.com)
2. Ziehe diesen Ordner in den Browser
3. Fertig - Website ist live!

### Option 2: Git-basiert

1. Erstelle ein Git Repository:
   ```bash
   cd immokonzept-landingpage
   git init
   git add .
   git commit -m "Initial commit"
   ```

2. Push zu GitHub/GitLab

3. Verbinde Repository mit Netlify

### Custom Domain einrichten

1. In Netlify: Site settings > Domain management
2. Add custom domain: `immokonzept.de` oder `portal.immokonzept.de`
3. DNS-Einträge beim Domain-Provider setzen:
   - CNAME: `@` oder `portal` → `[dein-site-name].netlify.app`
4. SSL wird automatisch aktiviert

## Struktur

```
immokonzept-landingpage/
├── index.html        # Hauptseite
├── impressum.html    # Impressum
├── datenschutz.html  # Datenschutzerklärung
├── netlify.toml      # Netlify-Konfiguration
└── README.md         # Diese Datei
```

## Webhook

Das Kontaktformular sendet an:
```
https://purple-storm-melbourne-frequency.trycloudflare.com/webhook/lead
```

**Wichtig:** Falls der Cloudflare Tunnel nicht mehr läuft, muss die URL im `index.html` aktualisiert werden (Zeile im JavaScript, suche nach `fetch(`).

## Anpassungen

### Texte ändern
Direkt in `index.html` bearbeiten.

### Farben ändern
In `index.html` im `<style>` Block die CSS-Variablen anpassen:
```css
:root {
  --primary: #1a5f6e;      /* Hauptfarbe (Petrol) */
  --primary-dark: #134a56;  /* Dunklere Variante */
  --secondary: #7B68EE;     /* Akzentfarbe (Lila) */
  --accent: #E07020;        /* Highlight (Orange) */
}
```

### Logo hinzufügen
Ersetze die `<div class="logo-icon">IK</div>` mit einem `<img>` Tag.

## TODO

- [ ] Impressum: Adresse eintragen
- [ ] Impressum: Telefonnummer eintragen
- [ ] Impressum: USt-IdNr. eintragen (falls vorhanden)
- [ ] Datenschutz: Adresse eintragen
- [ ] Logo als Bilddatei hinzufügen
- [ ] Fotos für Team-Sektion hinzufügen
- [ ] Webhook-URL aktualisieren (falls Tunnel neu)
