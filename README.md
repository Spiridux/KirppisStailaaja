# KirppisStailaaja – Deployment ohje

## Tiedostorakenne
```
kirppisstailaaja/
├── index.html          ← Pääsivu
├── vercel.json         ← Vercel-konfiguraatio
├── api/
│   └── chat.js         ← Claude API serverless function
└── redirect-fi.html    ← .fi-domainin redirect (käytetään one.com:ssa)
```

## Vercel deployment (kirppisstailaaja.com)

### 1. GitHub-repo
Luo GitHub-repo ja pushaa tiedostot sinne.

### 2. Vercel
- Mene vercel.com → New Project
- Yhdistä GitHub-repo
- Vercel tunnistaa automaattisesti projektin

### 3. API Key (TÄRKEÄ)
Vercel Dashboardissa:
- Project → Settings → Environment Variables
- Lisää: `ANTHROPIC_API_KEY` = sinun Anthropic API -avaimesi
- Scope: Production + Preview + Development

### 4. Domain
- Vercel Dashboard → Project → Settings → Domains
- Lisää: `kirppisstailaaja.com`
- Seuraa Vercel-ohjeita DNS-konfiguraatiolle

## .fi-domain (one.com → kirppisstailaaja.com)

one.com:ssa lisää redirect:
- Kaikki liikenne kirppisstailaaja.fi → https://kirppisstailaaja.com
- Tyyppi: 301 Permanent Redirect

Vaihtoehtoisesti: voit hostata redirect-fi.html tiedoston one.com:ssa
ja asettaa sen index-sivuksi.

## Kuvien lisääminen

Korvaa index.html:ssä placeholder-kohdat:

```html
<!-- HERO kuva -->
<img src="/galina-hero.jpg" alt="Galina KirppisStailaaja"/>

<!-- Muotokuva -->
<img src="/galina-portrait.jpg" alt="Galina"/>
```

Lataa kuvat Vercelin Public-kansioon tai käytä Cloudinary/Vercel Blob -palvelua.

## Some-linkit

Päivitä index.html:ssä social-icon-linkit kun profiilit luotu:
- instagram.com/kirppisstailaaja
- tiktok.com/@kirppisstailaaja
- youtube.com/@kirppisstailaaja
- facebook.com/kirppisstailaaja
- threads.net/@kirppisstailaaja
 
