# Komunikācijas moduļa prototips

CSP datu vākšanas sistēmas komunikācijas moduļa prototips: vēstuļu veidnes, respondenti, komunikācijas sagatavošana ar priekšskatījumu un simulēta nosūtīšana.

Prototips ir vienā failā `index.html`, un serveris nav vajadzīgs. Failu var atvērt tieši pārlūkā vai publicēt ar GitHub Pages. Pielikumu bibliotēkas PDF faili atrodas mapē `pielikumi/` un tiek ielādēti ar relatīvu ceļu.

- Visi testa dati ir izdomāti. E-pasta adresēm ir rezervētais domēns `.example`, un e-adrešu numuri sākas ar `0000…`.
- Dati glabājas tikai pārlūka `localStorage`. Kājenē ir poga, ar kuru var atjaunot sākotnējos testa datus.
- Nosūtīšana ir simulācija. E-pasti uz domēnu `nepiegadajams.example` simulācijā "neizdodas", lai var redzēt kļūdas statusu.
- Krāsas ir definētas kā CSS mainīgie `index.html` faila sākumā (`:root`).

## Sākumlapa (DELTA)

Atverot prototipu, vispirms redzama DELTA sistēmas sākumlapa ar moduļu kartītēm.
- Visas moduļu kartītes ir vienāda izmēra un neaktīvas, ar birku "Nav pieejams prototipā". Pirmajā rindā ir "Metadatu pārvaldība", "Respondentu pārvaldība" un "Datu vākšana", otrajā – "Datu vākšanas pārraudzība", "Mikrodatu pārvaldība" un "Administrēšana".
- Kartītē **Respondentu pārvaldība** zem apraksta ir aktīva poga **Komunikācija** ("Vēstuļu veidnes un sūtīšana") CSP krāsā ar aploksnes ikonu un bultiņu →. Tā atver komunikācijas moduli ar cilni "Veidnes". Pārējā kartītes daļa nav klikšķināma – prototipā pieejama tikai komunikācija.
- **Navigācija.** Komunikācijas moduļa galvenē ir nosaukums "Komunikācija" ar apakšvirsrakstu "Respondentu pārvaldība" un navigācijas ceļš "DELTA › Respondentu pārvaldība › Komunikācija". Sākumlapā var atgriezties ar saitēm "DELTA" vai "Respondentu pārvaldība" ceļā, ar CSP logo vai ar saiti "← DELTA sākums".

## Veidņu grupēšana

Lapā "Veidnes" veidnes ir sagrupētas divos līmeņos:

1. **Adresāts.** Trīs kartītes ar veidņu skaitu: "Komunikācija ar fiziskām personām" (atvērta pēc noklusējuma), "Komunikācija ar juridiskām personām" un "Cita komunikācija" (jaukta komunikācija, piem., viena ziņa visiem). Jauktās komunikācijas veidnēm adresāts ir "Visi (jaukta komunikācija)", un tajās lieto lauku `{adresāts}`: uzņēmumam tas ir nosaukums, fiziskai personai – vārds. Šādu veidni var sūtīt reizē gan fiziskām, gan juridiskām personām.
2. **Kategorija.** Katrā cilnē ir četri bloki: "Uzaicinājumi", "Atgādinājumi", "Informatīvie ziņojumi" un "Citi". Katram blokam ir veidņu skaits un poga "+ Pievienot veidni".

Bloku sakļaušana:
- **Pēc noklusējuma visi bloki ir sakļauti**, atverot lapu "Veidnes" vai pārslēdzot adresātu grupu. Redzams tikai virsraksts, veidņu skaits un poga "+ Pievienot veidni".
- Uzklikšķinot uz bloka virsraksta, tas izvēršas, vēlreiz uzklikšķinot – sakļaujas. Bultiņa rāda stāvokli.
- Saite **"Izvērst visus / Sakļaut visus"** blakus meklēšanas laukam izvērš vai sakļauj visus aktīvās grupas blokus.
- Meklējot automātiski izvēršas bloki ar rezultātiem. Notīrot meklēšanu, visi bloki atkal ir sakļauti.
- Pēc veidnes pievienošanas vai rediģēšanas izvēršas bloks, kurā tā atrodas.

Papildus:
- **Lauki veidnē.** Katrai veidnei ir lauki "Adresāts" un "Kategorija". Ja veidni pievieno no konkrēta bloka, abi lauki jau ir aizpildīti.
- **Meklēšana.** Meklēšanas lauks filtrē aktīvās cilnes veidnes pēc nosaukuma un temata.
- **Sagatavošana.** Veidņu izvēlne ir sagrupēta pēc adresāta un kategorijas. Ja atzīmētie respondenti neatbilst veidnes adresātam, sistēma par to brīdina, un ar vienu klikšķi var atlasīt tikai atbilstošos.

## Vēstuļu veidnes

Veidnes var būt divu veidu:

- **E-pasta saturs.** Vēstule ir pats ziņojuma teksts ar noformējumu: virsraksti, treknraksts, krāsas, līdzināšana, saraksti, saites, attēli un pogas. E-adresē tiek nosūtīta tā vienkārša teksta versija.
- **Vēstule pielikumā.** Galvenā vēstule ir pielikumā, bet ziņojumā ir tikai īss pavadteksts. Pielikums var būt dokuments no pielikumu bibliotēkas (PDF vai DOCX) vai dokuments ar laukiem, kas katram adresātam tiek ģenerēts kā A4 PDF (to var izdrukāt vai saglabāt kā PDF).

### Veidnes izveide un rediģēšana

Veidne atveras gandrīz pilnekrāna logā ar pogu **"← Atpakaļ uz veidnēm"**.

- **Izkārtojums.** Kreisajā kolonnā (~45 %) ir forma, labajā (~55 %) – priekšskatījums, kas, ritinot formu, paliek redzams.
- **Kompakta forma.** "Adresāts", "Kategorija" un "Valodas versija" ir vienā rindā. Paskaidrojumi ir paslēpti aiz mazas **"i"** ikonas un parādās, uzbraucot ar peli vai fokusējot to.

**Vēstules veids** ir divas kompaktas pogas ar ikonu un nosaukumu. Zem izvēlētās pogas atveras apakšizvēlne; neizvēlētās pogas apakšizvēlne ir paslēpta.

- **E-pasta saturs:**
  - **"No sagataves"** atver logu ar e-pasta satura šabloniem no sadaļas "Sagataves", sagrupētiem pēc kategorijas un atlasītiem pēc izvēlētā adresāta. Izvēlētā šablona teksts un formatējums ielādējas redaktorā, un to var brīvi labot. Ja temats vēl nav aizpildīts, tiek ielādēts arī temats.
  - **"Veidot jaunu"** atver redaktoru tikai ar uzrunu un parakstu.
- **Vēstule pielikumā:**
  - **"No sagatavēm"** atver logu ar pielikumu sagatavēm (meklēšana, filtri, PDF priekšskatījums). Izvēlētais dokuments kļūst par veidnes galveno vēstuli.
  - **"Augšupielādēt failu"** – PDF vai DOCX, līdz 1 MB. Fails tiek pievienots arī pielikumu sagatavēm.
  - Saite **"vai veidot dokumentu redaktorā ar laukiem"** saglabā iespēju veidot ģenerētu PDF dokumentu ar laukiem un nosacījumiem.
  - Izvēlētais dokuments redzams kartītē ar pogām "Priekšskatīt", "Nomainīt" un "Noņemt". Zem tās ir pavadteksta redaktors ar pavadteksta sagatavēm.

Ja pēc satura ievadīšanas nomaina vēstules veidu, sistēma brīdina: "Mainot vēstules veidu, ievadītais saturs var tikt zaudēts. Turpināt?".

**Papildu pielikumi (neobligāti)** ir sakļaujama sadaļa formas apakšā (pēc noklusējuma sakļauta). Ar pogu "+ Pievienot pielikumu" var izvēlēties failu no sagatavēm vai no datora.

**Priekšskatījums:**
- Zem ziņojuma teksta ar saspraudes ikonu redzami pielikumi.
- Ja galvenā vēstule ir PDF dokuments, zem pavadteksta uzreiz redzams pats dokuments, kura lapas var ritināt. Telefonā redzama pirmās lapas sīkbilde.
- DOCX failam redzama faila kartīte ar nosaukumu, izmēru un pogu "Atvērt".
- Pielikumi redzami arī sadaļā "Sagatavot komunikāciju" un nosūtītajās vēstulēs.

Veidnēm ar veidu "E-pasta saturs" redaktorā var pievienot:
- **attēlus** (poga **Attēls**). Attēlu var augšupielādēt no datora (PNG, JPG vai GIF, ne lielāku par 1 MB) vai norādīt `https://` saiti. Obligāti jānorāda alternatīvais teksts, un var izvēlēties platumu (mazs, vidējs, pilns) un novietojumu (pa kreisi, centrā vai pa labi). Augšupielādētie attēli glabājas pārlūkā kā data URL;
- **pogas ar saiti** (poga **Poga**). Pogai norāda tekstu un saiti, kurai jāsākas ar `https://` vai jābūt laukam, piem., `{e-anketa}`.

Uzklikšķinot uz attēla vai pogas redaktorā, to var rediģēt vai dzēst. Priekšskatījumā attēli un pogas izskatās tā, kā tos redzēs saņēmējs, un poga atver saiti jaunā cilnē.

### Teksta formatēšana redaktorā

Rīkjosla ir sagrupēta šādi: teksta stils | B, I, U, teksta krāsa | līdzināšana | saraksti | saite, attēls, poga | nosacījums un mainīgie.

- **Teksta stils.** Izvēlnē var izvēlēties "Parasts teksts", "Virsraksts 1", "Virsraksts 2" vai "Virsraksts 3". Stils attiecas uz rindkopu, kurā ir kursors, vai uz visām atlasītajām rindkopām. Atsevišķa virsraksta lauka vairs nav. Esošo veidņu virsraksti (arī PDF dokumenta virsraksts) automātiski pārcelti teksta sākumā kā "Virsraksts 1", tāpēc saturs nezūd.
- **Līdzināšana.** Pa kreisi, centrā vai pa labi. Līdzināšana attiecas uz visu rindkopu, arī uz virsrakstiem un attēliem tajā.
- **Teksta krāsa.** Poga "A" atver paleti: CSP tirkīzzaļā `#009999`, tumši tirkīzzaļa `#006B6B`, melna `#1F2933`, tumši pelēka `#4B5563` un sarkana `#B42318`. Var ievadīt arī savu HEX kodu. "Noņemt krāsu" atgriež atlasītajam tekstam noklusēto krāsu.
- **Pogas krāsa.** Pogas logā ir lauks "Pogas krāsa" ar to pašu paleti un HEX ievadi. Noklusētā krāsa ir `#009999`. Pogas teksta krāsa (balta vai melna) tiek izvēlēta automātiski, lai teksts būtu labi salasāms.

Viss formatējums tiek saglabāts veidnē un ir redzams veidnes priekšskatījumā un sadaļā "Sagatavot komunikāciju" tieši tā, kā to redzēs saņēmējs.

PDF dokuments sastāv no divām daļām:
- **pastāvīgās daļas:** veidlapas galva, apsekojuma baneris, konfidencialitātes sadaļa, plašāka informācija, paraksts un kājene. Tās rediģē sadaļā "Pastāvīgās daļas";
- **mainīgā daļa:** pats vēstules teksts, ko raksta katrā veidnē.

Abos veidos var lietot iepriekš definētus laukus. Tos ievieto ar izvēlni "+ Ievietot lauku":

| Grupa | Lauki |
|---|---|
| Respondents | `{vārds}`, `{uzņēmums}`, `{adresāts}` |
| Apsekojums | `{apsekojums}`, `{sākums}`, `{termiņš}`, `{e-anketa}`, `{apsekojuma_epasts}`, `{apsekojuma_vietne}` |
| Dokuments | `{datums}`, `{dok_nr}`, `{tālrunis}`, `{parakstītājs}`, `{amats}` |

## Sagataves

Cilnē **Veidnes** ir divas apakšcilnes: **"Veidnes"** un **"Sagataves"**. Atsevišķas cilnes "Pielikumi" vairs nav; vecā saite `#pielikumi` atver sadaļu "Sagataves".

Sagataves ir divās grupās:
- **E-pasta satura šabloni** – teksta sagataves, no kurām var sākt jaunu e-pasta veidni (poga "Jauna veidne" kartītē vai "No sagataves" redaktorā). Sākotnēji tie ir esošo e-pasta satura veidņu teksti un trīs papildu šabloni, lai katrai adresātu grupai katrā kategorijā ir vismaz viens. Šablonus var pievienot, rediģēt un dzēst.
- **Pielikumu sagataves** – dokumenti, arī tie, kas izdalīti no PDF faila ar vēstuļu paraugiem, un citi faili.

Abās grupās sagataves ir sakārtotas pēc adresāta (fiziskās / juridiskās personas / visi) un kategorijas (Uzaicinājumi, Atgādinājumi, Informatīvie ziņojumi, Citi). Ir meklēšana, filtri un poga **"+ Pievienot sagatavi"**.

Pielikumu sagatavju funkcijas:
- **Iepriekš ielādētie paraugi.** Tie ir atzīmēti ar birku "Sagatave", un faili glabājas mapē `pielikumi/` (sīkbildes – `pielikumi/sikbildes/`). Paraugus nevar labot vai dzēst.
- **Apraksts.** Katram pielikumam ir nosaukums, īss apraksts, kategorija, adresāti un valoda, ja tā ir zināma.
- **Savi faili.** Var augšupielādēt savu PDF vai DOCX failu (ne lielāku par 1 MB). Tas tiek saglabāts pārlūkā, un to var labot vai dzēst.
- **Versijas.** Aizstājot failu, iepriekšējais tiek saglabāts kā versija (pēdējās 3 versijas). Versijas redzamas labošanas logā, un tās var atvērt.
- **Pievienošana veidnei.** Pielikumu var pievienot veidnei ar pogu "Pievienot veidnei" vai veidnes redaktorā: kā galveno vēstuli vai sadaļā "Papildu pielikumi".
- **Dzēšana.** Kartītē redzams, kurām veidnēm pielikums pievienots. Pirms dzēšanas parādās brīdinājums. Pielikumu, kas kādai veidnei ir galvenā vēstule, nevar dzēst, kamēr tas nav nomainīts veidnē.

| Fails mapē `pielikumi/` | Saturs |
|---|---|
| `uzaicinajums_darbaspeka_apsekojums_intervija_lv.pdf` | Uzaicinājums – Darbaspēka apsekojums (telefona vai klātienes intervija), 2 lapas |
| `isa_vestule_celotaju_apsekojums_e-anketa_lv.pdf` | Īsā vēstule – Ceļotāju apsekojums (e-anketa vai telefonintervija), 1 lapa |
| `isa_vestule_celotaju_apsekojums_telefonaptauja_lv.pdf` | Īsā vēstule – Ceļotāju apsekojums (telefonaptauja), 1 lapa |
| `uzaicinajums_ikt_2026_ar_pogu_lv.pdf` | Uzaicinājums – IKT lietošana 2026 (ar pogu "Dodies uz anketu"), 2 lapas |
| `uzaicinajums_celotaju_apsekojums_e-anketa_lv.pdf` | Uzaicinājums – Ceļotāju apsekojums (e-anketa), 2 lapas |
| `uzaicinajums_ikt_2026_e-anketa_lv.pdf` | Uzaicinājums – IKT lietošana 2026 (e-anketa), 2 lapas |

Sagatavēs paraksti ir noņemti, parakstītāju vārdi aizstāti ar izdomātiem ("A. Paraugs", "L. Paraudziņa"), un apsekojuma vadītāja tālrunis aizstāts ar `60000000`.

## Respondenti (dati no Respondentu pārvaldības)

Cilne **Respondenti** atspoguļo datus no Respondentu pārvaldības moduļa (prototipā – izdomāti testa dati). Respondenti ir sagrupēti pēc pārskatiem un periodiem, kas viņiem jāiesniedz.

- **Datu modelis:**
  - **respondents:** tips (juridiska / fiziska persona), nosaukums vai vārds, reģistrācijas Nr. (juridiskām personām), e-adrese, e-pasts 1, e-pasts 2;
  - **pārskats:** nosaukums, kods un periodiskums (mēneša, ceturkšņa, pusgada, gada);
  - **pienākums (matrica):** respondents, pārskats, periods (piem., "2026. gada septembris", "2026. g. 3. ceturksnis"), iesniegšanas termiņš, iesniegšanas datums un statuss. Statuss ir "Iesniegts", "Nav iesniegts" vai "Kavēts" (termiņš pagājis, bet pārskats nav iesniegts). Vienam respondentam var būt vairāki pienākumi.
  - Fiziskās personas ir piesaistītas apsekojumam (Darbaspēka apsekojums, Mājsaimniecību budžeta apsekojums) ar vienu periodu un termiņu.
- **Testa dati:**
  - 15 uzņēmumi ar 1–5 pienākumiem katram, 6 pārskati ar dažādu periodiskumu un 10 fiziskās personas divos apsekojumos;
  - periodi un termiņi tiek aprēķināti attiecībā pret šodienu, tāpēc statusi vienmēr ir jaukti.
- **Pārslēgs** "Juridiskās personas / Fiziskās personas".
- **Filtri:** pārskats (vai apsekojums), periodiskums, periods, statuss, termiņš no–līdz un meklēšana pēc nosaukuma vai reģ. Nr.
- **Juridiskās personas:** tabula ar respondentu, kontaktiem, pienākumu skaitu un neiesniegto skaitu. Uzklikšķinot uz rindas, tā izvēršas un parāda pienākumu tabulu: Pārskats | Periods | Termiņš | Statuss.
- **Fiziskās personas:** sagrupētas pa apsekojumiem sakļaujamos blokos. Katrā blokā ir saraksts ar vārdu, e-pastiem, e-adresi un statusu.
- **Respondenta forma un CSV imports** papildināti ar laukiem "Reģistrācijas Nr." un "E-pasts 2".

### Respondentu adreses un adrešu prioritāte

**Adreses.** Katram respondentam ir četras adreses:
- **eAdrese** (juridiskām personām – uzņēmuma eAdrese), **E-pasts 1** un **E-pasts 2**. Tās ir sinhronizētas no Respondentu pārvaldības.
- **E-pasts 3 (manuāli)**, ko darbinieks var ievadīt vai labot komunikācijas modulī.

**Izvērstā respondenta rinda** (gan juridiskām, gan fiziskām personām) parāda:
- sinhronizētās adreses kā tikai lasāmas, ar birku "No Respondentu pārvaldības", datumu "Sinhronizēts: …" un pogu "Sinhronizēt" (simulācija);
- lauku "E-pasts 3 (manuāli)" ar e-pasta formāta pārbaudi un pogu "Saglabāt", kā arī informāciju, kas un kad to ievadīja.

**Testa dati** satur dažādus gadījumus:
- dažiem respondentiem nav eAdreses;
- daudziem ir tikai viens e-pasts, dažiem aizpildītas visas adreses;
- vienam respondentam nav nevienas adreses.

**Prioritāte sesijā.** Sadaļas "Sagatavot komunikāciju" 5. solī "Adreses" izvēlas "1. prioritāte", "2. prioritāte" un "3. prioritāte".
- Vienu adreses veidu nevar izvēlēties divreiz. 1. prioritāte ir obligāta.
- Noklusējums: eAdrese → E-pasts 1 → E-pasts 2.
- Kopsavilkumā redzams, cik respondentiem vēstule tiks sūtīta uz katras prioritātes adresi un cik respondentiem nav nevienas atbilstošas adreses. Šos respondentus var apskatīt un tiem ievadīt manuālo e-pastu.

**Sūtīšana:**
- Katram respondentam izmanto pirmo pieejamo adresi pēc prioritātes. Ja sūtīšana neizdodas, mēģina nākamo.
- Simulācijā e-adreses `_DEFAULT@00000000112` un `_PRIVATE@00000000222` nav aktivizētas, un e-pasti uz domēnu `nepiegadajams.example` nav sasniedzami.
- Priekšskatījumā un nosūtītajā vēstulē redzama prioritāšu secība un katrs mēģinājums: adreses veids, adrese un rezultāts.
- Cilnē "Nosūtītās" ir **sūtīšanas sesiju** saraksts ar izmantoto prioritāti, piem., "eAdrese → E-pasts 1 → E-pasts 2". Uzklikšķinot uz sesijas, tabulā redzamas tikai tās vēstules.

### Pārskatu tabula vēstulē – `{pārskatu_tabula}`

- **Ievietošana.** Veidnes redaktora izvēlnē "+ Ievietot lauku" ir bloks **"Pārskatu tabula"**. To ievietojot, var izvēlēties:
  - kolonnas: Pārskats, Periods, Termiņš, Statuss;
  - rindas: "Visi atlasītie pienākumi" (uzaicinājumiem) vai "Tikai neiesniegtie" (atgādinājumiem).

  Uzklikšķinot uz bloka redaktorā, iestatījumus var mainīt vai bloku dzēst.
- **Atlase sagatavošanā.** Sadaļas "Sagatavot komunikāciju" 2. solī "Respondenti" var atlasīt pienākumus pēc pārskata vai apsekojuma, perioda un statusa. Tiek rādīti tikai respondenti ar atbilstošiem pienākumiem.
- **Ģenerēšana.** Tabula tiek izveidota katram respondentam no viņa pienākumiem, kas atbilst šai atlasei. Kavētie termiņi ir izcelti sarkanā krāsā. E-adreses ziņojumā tabula tiek pārvērsta tekstā.
- **Esošās veidnes.** Tabula pievienota uzaicinājuma ("Uzaicinājums sniegt datus apsekojumā (vēstule pielikumā)" – PDF dokumentā) un atgādinājuma ("Atgādinājums par datu iesniegšanas termiņu") veidnēm juridiskām personām.

## Sūtīšanas sesija (Sagatavot komunikāciju)

Sesijai ir seši soļi:

1. **Sesija.** Šeit norāda sesijas nosaukumu (pēc noklusējuma "Sūtījums Nr. N"), adresātu un apsekojuma un vēstules datus. Adresāts nosaka, kuras veidnes tiek piedāvātas. Mainot adresātu, tiek pielāgots arī filtrs "Respondenta veids".
2. **Respondenti.** Atlasa respondentus pēc pienākumiem un pazīmēm.
3. **Saturs.** Ir divas kartītes: "Izmantot veidni" un "Noformēt saturu".
   - **Izmantot veidni.** Atveras veidņu izvēle. Tajā redzamas tikai sesijas adresātam paredzētās veidnes, sagrupētas pēc kategorijas, ar meklēšanu un teksta priekšskatījumu. Izvēlēto veidni var izmantot uzreiz ("Izmantot veidni") vai pielāgot ("Pielāgot šai sesijai"). Pielāgojot atveras redaktors ar veidnes saturu. Izmaiņas attiecas tikai uz šo sesiju, un pati veidne netiek mainīta.
   - **Noformēt saturu.** Atveras tas pats redaktors, kas veidnes izveidei, ar visām tā iespējām. Atšķirības no veidnes izveides:
     - nav lauku "Veidnes nosaukums" un "Kategorija", adresāts tiek ņemts no sesijas;
     - virsraksts ir "Vēstules saturs: [sesijas nosaukums]";
     - priekšskatījumā redzami sesijā atzīmētie respondenti, starp kuriem var pārslēgties ar ← →;
     - apakšā ir pogas "Atcelt", "Saglabāt arī kā veidni" un "Izmantot sesijā".
   - **Saglabāt arī kā veidni.** Prasa norādīt veidnes nosaukumu un kategoriju. Saturs tiek saglabāts kā jauna veidne, un sesija to izmanto.
   - **Kopsavilkums.** Kad saturs ir apstiprināts, solī redzams satura avots ("Veidne: [nosaukums]", "Veidne, pielāgota sesijai" vai "Individuāls saturs"), temats un vēstules veids. Ir pogas "Labot saturu" un "Izvēlēties citu saturu".
4. **Paraksts.** Parakstītājs un amats tiek izmantoti laukos `{parakstītājs}` un `{amats}`, kā arī PDF vēstules parakstā. Pēc noklusējuma tie tiek ņemti no sadaļas "Pastāvīgās daļas". Šeit veiktās izmaiņas attiecas tikai uz šo sesiju.
5. **Adreses.** Šeit izvēlas adrešu prioritāti.
6. **Pārbaude un nosūtīšana.** Šeit redzams katras vēstules priekšskatījums, kopsavilkums un poga "Nosūtīt".

**Melnraksts.** Sesija, arī tās saturs, tiek automātiski saglabāta pārlūkā kā melnraksts, tāpēc pēc lapas pārlādes darbu var turpināt. Poga "Sākt no jauna" dzēš melnrakstu. Pēc nosūtīšanas sākas jauna sesija. Nosūtīto vēstuļu sadaļā sesijas tabulā redzams sesijas nosaukums un saturs.

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
