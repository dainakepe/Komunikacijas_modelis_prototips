# Komunikācijas moduļa prototips

CSP datu vākšanas sistēmas komunikācijas moduļa prototips: vēstuļu veidnes, respondenti, komunikācijas sagatavošana ar priekšskatījumu un simulēta nosūtīšana.

Viss ir vienā failā `index.html`, un serveris nav vajadzīgs. Failu var atvērt tieši pārlūkā vai publicēt ar GitHub Pages.

- Visi testa dati ir izdomāti. E-pasta adresēm ir rezervētais domēns `.example`, un e-adrešu numuri sākas ar `0000…`.
- Dati glabājas tikai pārlūka `localStorage`. Kājenē ir poga, ar kuru var atjaunot sākotnējos testa datus.
- Nosūtīšana ir simulācija. E-pasti uz domēnu `nepiegadajams.example` simulācijā "neizdodas", lai var redzēt kļūdas statusu.
- Krāsas ir definētas kā CSS mainīgie `index.html` faila sākumā (`:root`).

## Vēstuļu veidnes

Veidnes var būt divu veidu:

- **E-pasta saturs.** Vēstule ir pats ziņojuma teksts ar noformējumu: virsraksti, treknraksts, saraksti, saites un poga. E-adresē tiek nosūtīta tā vienkārša teksta versija.
- **Vēstule pielikumā (PDF).** Katram adresātam tiek ģenerēts A4 dokuments. Ziņojumā ir tikai īss pavadteksts. Dokumentu var izdrukāt vai saglabāt kā PDF.

PDF dokuments sastāv no divām daļām:
- **pastāvīgās daļas:** veidlapas galva, apsekojuma baneris, konfidencialitātes sadaļa, plašāka informācija, paraksts un kājene. Tās rediģē sadaļā "Pastāvīgās daļas";
- **mainīgā daļa:** pats vēstules teksts, ko raksta katrā veidnē.

Abos veidos var lietot iepriekš definētus laukus. Tos ievieto ar izvēlni "+ Ievietot lauku":

| Grupa | Lauki |
|---|---|
| Respondents | `{vārds}`, `{uzņēmums}` |
| Apsekojums | `{apsekojums}`, `{sākums}`, `{termiņš}`, `{e-anketa}`, `{apsekojuma_epasts}`, `{apsekojuma_vietne}` |
| Dokuments | `{datums}`, `{dok_nr}`, `{tālrunis}`, `{parakstītājs}`, `{amats}` |

## Nosacījumi un vēstuļu varianti

Katram respondentam ir divas pazīmes:
- **dalības veids:** e-anketa, tikai telefonintervija vai klātienes intervija;
- **iepriekšējā dalība:** piedalījās, nepiedalījās vai izlasē pirmo reizi.

Redaktorā ar pogu **◇ Nosacījums** iezīmētās rindkopas kļūst par bloku, kas redzams tikai respondentiem ar izvēlēto pazīmes vērtību vai vērtībām. Tā vienā veidnē var būt vairāki varianti, piemēram, "Kā piedalīties aptaujā?" e-anketas un telefonintervijas respondentiem.

- **Veidnes priekšskatījumā** variantu var pārslēgt.
- **Sagatavošanā:**
  - respondentus var atlasīt pēc pazīmēm;
  - kopsavilkumā redzams, cik vēstuļu būs katrā variantā;
  - katras vēstules priekšskatījumā redzams tās variants.
- **CSV importā** pazīmes var norādīt kolonnās `dalības veids` un `iepriekšējā dalība`. Tās nav obligātas. Atpazīst arī saīsinājumus CAWI/CATI/CAPI un vērtības jā/nē.

## GitHub Pages

1. Repozitorijā atveriet **Settings → Pages**.
2. Sadaļā **Build and deployment** pie **Source** izvēlieties **Deploy from a branch**.
3. Pie **Branch** izvēlieties `main` un mapi `/ (root)`, tad spiediet **Save**.
4. Pēc 1–2 minūtēm prototips būs pieejams adresē `https://<lietotājvārds>.github.io/<repozitorija-nosaukums>/`.
