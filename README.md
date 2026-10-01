# Komunikācijas moduļa prototips

CSP datu vākšanas sistēmas komunikācijas moduļa prototips: vēstuļu veidnes, respondenti, komunikācijas sagatavošana ar priekšskatījumu un simulēta nosūtīšana.

Viss ir vienā failā `index.html`, un serveris nav vajadzīgs. Failu var atvērt tieši pārlūkā vai publicēt ar GitHub Pages.

- Visi testa dati ir izdomāti. E-pasta adresēm ir rezervētais domēns `.example`, un e-adrešu numuri sākas ar `0000…`.
- Dati glabājas tikai pārlūka `localStorage`. Kājenē ir poga, ar kuru var atjaunot sākotnējos testa datus.
- Nosūtīšana ir simulācija. E-pasti uz domēnu `nepiegadajams.example` simulācijā "neizdodas", lai var redzēt kļūdas statusu.
- Krāsas ir definētas kā CSS mainīgie `index.html` faila sākumā (`:root`).

## Veidņu grupēšana

Lapā "Veidnes" veidnes ir sagrupētas divos līmeņos:

1. **Adresāts.** Cilnes "Komunikācija ar fiziskām personām" un "Komunikācija ar juridiskām personām", katrai ar veidņu skaitu. Pēc noklusējuma atvērta cilne fiziskajām personām.
2. **Kategorija.** Katrā cilnē ir četri bloki: "Uzaicinājumi", "Atgādinājumi", "Informatīvie ziņojumi" un "Citi". Katram blokam ir veidņu skaits, poga "+ Pievienot veidni" un iespēja to sakļaut. Sakļautie bloki pārlūkā saglabājas.

Papildus:
- **Lauki veidnē.** Katrai veidnei ir lauki "Adresāts" un "Kategorija". Ja veidni pievieno no konkrēta bloka, abi lauki jau ir aizpildīti.
- **Meklēšana.** Meklēšanas lauks filtrē aktīvās cilnes veidnes pēc nosaukuma un temata.
- **Informācija par veidnēm.** Paskaidrojums par laukiem, nosacījumiem un valodām atveras, uzklikšķinot uz ikonas "i" blakus virsrakstam.
- **Sagatavošana.** Veidņu izvēlne ir sagrupēta pēc adresāta un kategorijas. Ja atzīmētie respondenti neatbilst veidnes adresātam, sistēma par to brīdina, un ar vienu klikšķi var atlasīt tikai atbilstošos.

## Vēstuļu veidnes

Veidnes var būt divu veidu:

- **E-pasta saturs.** Vēstule ir pats ziņojuma teksts ar noformējumu: virsraksti, treknraksts, saraksti, saites un poga. E-adresē tiek nosūtīta tā vienkārša teksta versija.
- **Vēstule pielikumā (PDF).** Katram adresātam tiek ģenerēts A4 dokuments. Ziņojumā ir tikai īss pavadteksts. Dokumentu var izdrukāt vai saglabāt kā PDF.

Veidnēm ar veidu "E-pasta saturs" redaktorā var pievienot:
- **attēlus** (poga **Attēls**). Attēlu var augšupielādēt no datora (PNG, JPG vai GIF, ne lielāku par 1 MB) vai norādīt `https://` saiti. Obligāti jānorāda alternatīvais teksts, un var izvēlēties platumu (mazs, vidējs, pilns) un novietojumu (pa kreisi vai centrā). Augšupielādētie attēli glabājas pārlūkā kā data URL;
- **pogas ar saiti** (poga **Poga**). Pogai norāda tekstu un saiti, kurai jāsākas ar `https://` vai jābūt laukam, piem., `{e-anketa}`.

Uzklikšķinot uz attēla vai pogas redaktorā, to var rediģēt vai dzēst. Priekšskatījumā attēli un pogas izskatās tā, kā tos redzēs saņēmējs, un poga atver saiti jaunā cilnē.

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

Nosacījumus var veidot pēc trim respondenta pazīmēm:
- **respondenta veids:** uzņēmums vai privātpersona. Ja tas nav norādīts, to nosaka pēc e-adreses: `_DEFAULT@` nozīmē uzņēmumu, `_PRIVATE@` nozīmē privātpersonu. Ja e-adreses nav, skatās, vai norādīta kontaktpersona;
- **dalības veids:** e-anketa, tikai telefonintervija vai klātienes intervija;
- **iepriekšējā dalība:** piedalījās, nepiedalījās vai izlasē pirmo reizi.

Redaktorā ar pogu **◇ Nosacījums** iezīmētās rindkopas kļūst par bloku, kas redzams tikai respondentiem ar izvēlēto pazīmes vērtību vai vērtībām. Tā vienā veidnē var būt vairāki varianti, piemēram, "Kā piedalīties aptaujā?" e-anketas un telefonintervijas respondentiem.

- **Veidnes priekšskatījumā** variantu var pārslēgt.
- **Sagatavošanā:**
  - respondentus var atlasīt pēc pazīmēm;
  - kopsavilkumā redzams, cik vēstuļu būs katrā variantā;
  - katras vēstules priekšskatījumā redzams tās variants.
- **CSV importā** pazīmes var norādīt kolonnās `respondenta veids`, `dalības veids`, `iepriekšējā dalība` un `valoda`. Tās nav obligātas. Atpazīst arī saīsinājumus CAWI/CATI/CAPI un vērtības jā/nē.

## Valodas

Katram respondentam ir norādīta **valoda**: latviešu, krievu vai angļu.

- **Valodu versijas.** Veidnes redaktorā ar pogām **LV / RU / EN** pārslēdz valodas versiju. Katrai versijai ir savs temats, teksts un PDF dokuments. Jaunu versiju var izveidot no latviešu teksta vai tukšu.
- **Kopīgie iestatījumi.** Vēstules veids, pastāvīgo daļu izvēle un papildu pielikumi ir kopīgi visām valodām.
- **Pastāvīgās daļas.** Tām ir tulkojumi: iestādes nosaukums, vieta, amats, noslēguma frāze, konfidencialitātes un plašākas informācijas sadaļas, e-paraksta atzīme un e-pasta kājene. Ja tulkojuma lauks ir tukšs, tiek lietots latviešu teksts.
- **Apsekojuma nosaukums.** Tam var norādīt arī angļu un krievu nosaukumu. Lauks `{apsekojums}` tiek aizpildīts respondenta valodā.
- **Sagatavošana.**
  - Katrs respondents saņem vēstuli savā valodā.
  - Ja veidnei tās valodas versijas nav, tiek sūtīta latviešu versija, un sistēma par to brīdina.
  - Kopsavilkumā redzams, cik vēstuļu būs katrā valodā.

## GitHub Pages

1. Repozitorijā atveriet **Settings → Pages**.
2. Sadaļā **Build and deployment** pie **Source** izvēlieties **Deploy from a branch**.
3. Pie **Branch** izvēlieties `main` un mapi `/ (root)`, tad spiediet **Save**.
4. Pēc 1–2 minūtēm prototips būs pieejams adresē `https://<lietotājvārds>.github.io/<repozitorija-nosaukums>/`.
