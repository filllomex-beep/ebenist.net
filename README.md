# ebenist.net

Web Michala Řičici — ebenist a restaurátor historického nábytku, Spálená 9, Praha 1.
Vlastní restaurátorská živnost od roku 1988.

## Struktura

| Cesta | Obsah |
|---|---|
| `index.html` | Celý web — jeden soubor, ručně editovatelný (HTML + CSS + JS inline) |
| `assets/img/` | Fotografie prací a dílny |
| `design-system/MASTER.md` | Design systém — barvy, typografie, spacing, motion |
| `sitemap.xml` | Mapa webu pro vyhledávače (1 stránka + 93 fotografií) |
| `robots.txt` | Pravidla pro roboty + odkaz na sitemapu |

Statický web bez build kroku. `index.html` se otevře přímo v prohlížeči.

## Nasazení

Vercel, automaticky z větve `main`.

## Google Search Console

1. Doména musí ukazovat na Vercel (dnes na `ebenist.net` běží ještě starý WordPress).
2. V [Search Console](https://search.google.com/search-console) založit property:
   - **Doména** (doporučeno) — přidat TXT záznam do DNS u registrátora domény. Pokryje www i non-www.
   - nebo **Předpona adresy URL** `https://ebenist.net/` — pak odkomentovat řádek
     `<meta name="google-site-verification" …>` v hlavičce `index.html` a nasadit.
3. Odeslat sitemapu: *Sitemapy* → `sitemap.xml`.
4. *Kontrola URL* → `https://ebenist.net/` → **Požádat o indexaci**.

Po každé větší změně obsahu přegenerovat `lastmod` v `sitemap.xml` na aktuální datum.
