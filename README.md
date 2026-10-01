# Komunikācijas moduļa prototips

CSP datu vākšanas sistēmas komunikācijas moduļa prototips: vēstuļu veidnes, respondenti, komunikācijas sagatavošana ar priekšskatījumu un simulēta nosūtīšana.

Viss ir vienā failā `index.html`, un serveris nav vajadzīgs. Failu var atvērt tieši pārlūkā vai publicēt ar GitHub Pages.

- Visi testa dati ir izdomāti. E-pasta adresēm ir rezervētais domēns `.example`, un e-adrešu numuri sākas ar `0000…`.
- Dati glabājas tikai pārlūka `localStorage`. Kājenē ir poga, ar kuru var atjaunot sākotnējos testa datus.
- Nosūtīšana ir simulācija. E-pasti uz domēnu `nepiegadajams.example` simulācijā "neizdodas", lai var redzēt kļūdas statusu.
- Krāsas ir definētas kā CSS mainīgie `index.html` faila sākumā (`:root`).

## GitHub Pages

1. Repozitorijā atveriet **Settings → Pages**.
2. Sadaļā **Build and deployment** pie **Source** izvēlieties **Deploy from a branch**.
3. Pie **Branch** izvēlieties `main` un mapi `/ (root)`, tad spiediet **Save**.
4. Pēc 1–2 minūtēm prototips būs pieejams adresē `https://<lietotājvārds>.github.io/<repozitorija-nosaukums>/`.
