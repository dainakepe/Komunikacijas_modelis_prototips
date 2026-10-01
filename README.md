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

### Jaunas veidnes izveide

Pēc "+ Jauna veidne" vispirms izvēlas **vēstules veidu**. Zem tā parādās izvēle, kā sākt:

- **E-pasta saturs:**
  - **"Sākt no sagataves"** atver logu ar e-pasta satura sagatavēm, sagrupētām pēc kategorijas un atlasītām pēc izvēlētā adresāta. Katrai sagatavei redzams nosaukums, temats un īss teksta priekšskatījums. Sagataves ir esošās e-pasta satura veidnes un trīs papildu sagataves, lai katrai adresātu grupai katrā kategorijā ir vismaz viena. Izvēlētās sagataves teksts un formatējums ielādējas redaktorā, un to var brīvi labot. Ja temats vēl nav aizpildīts, tiek ielādēts arī temats.
  - **"Veidot jaunu (tukšs)"** atver redaktoru tikai ar uzrunu un parakstu.
- **Vēstule pielikumā:**
  - **"Izvēlēties no sagatavēm"** atver logu ar bibliotēkas dokumentiem, kas atzīmēti kā "Sagatave". Logā ir meklēšana, filtri un PDF priekšskatījums. Izvēlētais dokuments kļūst par veidnes galveno vēstuli.
  - **"Augšupielādēt savu failu"** – PDF vai DOCX, līdz 1 MB. Fails tiek pievienots arī pielikumu bibliotēkai.
  - Saite **"Vai veidot dokumentu redaktorā ar laukiem"** saglabā iespēju veidot ģenerētu PDF dokumentu ar laukiem un nosacījumiem.
  - Izvēlētais dokuments redzams kartītē ar nosaukumu, izmēru un pogām "Priekšskatīt", "Nomainīt" un "Noņemt". Zem tās ir pavadteksta redaktors ar pavadteksta sagatavēm (uzaicinājums, atgādinājums, informācija).

Ja pēc satura ievadīšanas nomaina vēstules veidu, sistēma brīdina: "Mainot vēstules veidu, ievadītais saturs var tikt zaudēts. Turpināt?".

**Papildu pielikumi (neobligāti)** ir sakļaujama sadaļa formas apakšā (pēc noklusējuma sakļauta). Ar pogu "+ Pievienot pielikumu" var izvēlēties failu no bibliotēkas vai no datora. Faili no datora arī tiek pievienoti bibliotēkai.

**Priekšskatījumā** zem ziņojuma teksta ar saspraudes ikonu redzami pielikumi: galvenās vēstules kartīte, ko var atvērt, un papildu pielikumi. Tāpat pielikumi redzami sadaļā "Sagatavot komunikāciju" un nosūtītajās vēstulēs.

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

## Pielikumu bibliotēka

Cilnē **Pielikumi** ir gatavi PDF pielikumi, ko var pievienot veidnēm kā papildu pielikumus.

- **Sagataves.** Iepriekš ielādētie paraugi ir atzīmēti ar birku "Sagatave". Tie ir izdalīti no PDF faila ar vēstuļu paraugiem, un faili glabājas mapē `pielikumi/` (sīkbildes – `pielikumi/sikbildes/`). Sagataves nevar labot vai dzēst.
- **Katram pielikumam** ir nosaukums, īss apraksts, kategorija (uzaicinājuma vēstule, instrukcija, informatīvs materiāls vai cits), adresāti (fiziskās personas, juridiskās personas vai visi) un valoda, ja tā ir zināma.
- **Meklēšana un filtri.** Pielikumus var meklēt pēc nosaukuma, apraksta vai faila nosaukuma un atlasīt pēc adresātiem, kategorijas un valodas.
- **Savi pielikumi.** Ar pogu "Pievienot pielikumu" var augšupielādēt savu PDF vai DOCX failu (ne lielāku par 1 MB). Tas tiek saglabāts pārlūkā, un to var labot vai dzēst.
- **Pievienošana veidnei.** Pielikumu var pievienot veidnei ar pogu "Pievienot veidnei" vai veidnes redaktorā: kā galveno vēstuli vai sadaļā "Papildu pielikumi". Pielikumu, kas kādai veidnei ir galvenā vēstule, nevar dzēst, kamēr tas nav nomainīts veidnē. Vēstules priekšskatījumā un nosūtītajās vēstulēs bibliotēkas pielikumu var atvērt.

| Fails mapē `pielikumi/` | Saturs |
|---|---|
| `uzaicinajums_darbaspeka_apsekojums_intervija_lv.pdf` | Uzaicinājums – Darbaspēka apsekojums (telefona vai klātienes intervija), 2 lapas |
| `isa_vestule_celotaju_apsekojums_e-anketa_lv.pdf` | Īsā vēstule – Ceļotāju apsekojums (e-anketa vai telefonintervija), 1 lapa |
| `isa_vestule_celotaju_apsekojums_telefonaptauja_lv.pdf` | Īsā vēstule – Ceļotāju apsekojums (telefonaptauja), 1 lapa |
| `uzaicinajums_ikt_2026_ar_pogu_lv.pdf` | Uzaicinājums – IKT lietošana 2026 (ar pogu "Dodies uz anketu"), 2 lapas |
| `uzaicinajums_celotaju_apsekojums_e-anketa_lv.pdf` | Uzaicinājums – Ceļotāju apsekojums (e-anketa), 2 lapas |
| `uzaicinajums_ikt_2026_e-anketa_lv.pdf` | Uzaicinājums – IKT lietošana 2026 (e-anketa), 2 lapas |

Sagatavēs paraksti ir noņemti, parakstītāju vārdi aizstāti ar izdomātiem ("A. Paraugs", "L. Paraudziņa"), un apsekojuma vadītāja tālrunis aizstāts ar `60000000`.

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
