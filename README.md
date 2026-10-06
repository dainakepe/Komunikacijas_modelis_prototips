# Komunikācijas moduļa prototips

CSP datu vākšanas sistēmas komunikācijas moduļa prototips: komunikācijas kampaņas, vēstuļu veidnes, sūtīšanas vēsture, atskaites un simulēta nosūtīšana. Respondentu dati nāk no citiem DELTA moduļiem (prototipā – izdomāti testa dati).

> **Galvenā atsauce:** komunikācijas moduļa funkcionālais apraksts – [`docs/komunikacija_specifikacija.md`](docs/komunikacija_specifikacija.md). Prototipa struktūra un funkcijas tiek veidotas atbilstoši tam.

Prototips ir vienā failā `index.html`, un serveris nav vajadzīgs. Failu var atvērt tieši pārlūkā vai publicēt ar GitHub Pages. Pielikumu bibliotēkas PDF faili atrodas mapē `pielikumi/`, attēli (piem., sākumlapas ilustrācija) – mapē `atteli/`. Tie tiek ielādēti ar relatīvu ceļu.

- Visi testa dati ir izdomāti. E-pasta adresēm ir rezervētais domēns `.example`, un e-adrešu numuri sākas ar `0000…`.
- Dati glabājas tikai pārlūka `localStorage`. Kājenē ir poga, ar kuru var atjaunot sākotnējos testa datus.
- Nosūtīšana ir simulācija. E-pasti uz domēnu `nepiegadajams.example` simulācijā "neizdodas", lai var redzēt kļūdas statusu.
- Krāsas ir definētas kā CSS mainīgie `index.html` faila sākumā (`:root`).

## Sākumlapa (DELTA)

Atverot prototipu, vispirms redzama DELTA sistēmas sākumlapa ar moduļu kartītēm.
- Sveiciena nav. Lietotāja vārds "Testa Darbinieks" redzams galvenē.
- **Rāmis "Ideja"** tieši zem galvenes, virs moduļu kartītēm, ir tikpat plats kā kartīšu režģis:
  - balts fons, plāna tirkīzzaļa (#009999) apmale, noapaļoti stūri un neliela ēna;
  - augšējā kreisajā stūrī ir birka "Ideja" ar spuldzītes ikonu, kas daļēji "sēž" uz rāmja apmales;
  - blakus birkai ir virsraksts "Komunikācija ar respondentiem" un teikums "No kampaņas sagatavošanas līdz piegādes rezultātiem vienuviet.";
  - zem teksta visā rāmja platumā ir ilustrācija ar četriem komunikācijas posmiem (`atteli/komunikacija_josla.png`);
  - rāmis ir tikai informatīvs: tas nav saite, un, uzbraucot ar peli, tas nemainās. Moduli "Komunikācija" atver tikai poga "Komunikācija" kartītē "Respondentu pārvaldība";
  - uz ekrāniem, kas šaurāki par 900 px, ilustrācija nesamazinās (lai teksts tajā paliek salasāms), bet to var ritināt horizontāli. Zem tās ir norāde "Ritiniet ilustrāciju uz sāniem →".
- Visas moduļu kartītes ir vienāda izmēra un neaktīvas (pelēkas). Tajās ir tikai ikona un nosaukums, bez paskaidrojošiem tekstiem. Pirmajā rindā ir "Metadatu pārvaldība", "Respondentu pārvaldība" un "Datu vākšana", otrajā – "Datu vākšanas pārraudzība", "Mikrodatu pārvaldība" un "Administrēšana".
- Kartītē **Respondentu pārvaldība** ir maza aktīva zaļa poga **Komunikācija** (tikai aploksnes ikona, nosaukums un bultiņa →). Tā atver komunikācijas moduli ar cilni "Kampaņas". Pārējā kartītes daļa nav klikšķināma – prototipā pieejama tikai komunikācija.
- **Navigācija.** Komunikācijas moduļa galvenē ir nosaukums "Komunikācija" ar apakšvirsrakstu "Respondentu pārvaldība" un navigācijas ceļš, piem., "DELTA › Respondentu pārvaldība › Komunikācija › Kampaņas" (kampaņas redaktorā arī kampaņas nosaukums). Sākumlapā var atgriezties ar saitēm "DELTA" vai "Respondentu pārvaldība" ceļā, ar CSP logo vai ar saiti "← DELTA sākums".

## Moduļa cilnes

Komunikācijas modulim ir četras cilnes (atbilstoši specifikācijai):
1. **Kampaņas** (pirmā un noklusējuma cilne). Tajā ir saraksts "Komunikācijas kampaņas" un poga "+ Jauna kampaņa". Zem virsraksta ir viens paskaidrojošs teikums: "Kampaņa ir viena sūtīšana izvēlētiem respondentiem: uzaicinājums, atgādinājums vai cita informācija."
2. **Veidnes.** Vēstuļu veidnes un sagataves.
3. **Sūtīšanas vēsture.** Nosūtītās vēstules, sagrupētas pa kampaņām.
4. **Atskaites.** Rādītāji, grafiki un tabulas par sūtīšanas rezultātiem ar CSV eksportu un MI kopsavilkumu.

- **Noformējums.** Cilnēm nav skaita ciparu. Teksts ir lielāks (16,5 px), pustrekns, ar ikonu pirms nosaukuma. Aktīvajai cilnei ir tirkīzzaļš (#009999) teksts, bieza apakšlīnija un ļoti gaišs tirkīzzaļš fons. Neaktīvās ir tumši pelēkas un, uzbraucot ar peli, kļūst tirkīzzaļas.
- **Navigācijas ceļš:** "DELTA › Respondentu pārvaldība › Komunikācija › [cilne]".
- **Apakšsadaļas** ir filtru pogas zem virsraksta (bez skaitītājiem):
  - Kampaņas: Melnraksti · Ieplānotās · Izpildē · Pabeigtās. Pirmajā reizē atveras pirmā sadaļa, kurā ir kampaņas;
  - Veidnes: adresātu grupu kartītes (Fiziskām personām · Juridiskām personām · Cita komunikācija). "Sagataves" ir poga augšējā labajā stūrī pirms "Pastāvīgās daļas", un tā atver atsevišķu skatu ar pogu "← Atpakaļ uz veidnēm";
  - Sūtīšanas vēsture: Visas · Gaida parakstu · Nosūtītas · Piegādātas · Neveiksmīgas;
  - Atskaites: Nosūtīšanas kopsavilkums · Piegādes rezultāti · Neveiksmīgās ziņas · Atkārtotā nosūtīšana · Citi pārskati.

Atsevišķas cilnes "Respondenti" nav, jo respondentu dati nāk no citiem DELTA moduļiem. Tie ir redzami kampaņas solī "Respondenti" un respondenta kartītē. Vecās saites turpina darboties: `#sagatavot` atver kampaņas redaktoru, `#nosutitas` atver cilni "Sūtīšanas vēsture", bet `#respondenti` atver cilni "Kampaņas".

**Kampaņu saraksts** (specifikācija F1). Kampaņas ir sadalītas sadaļās pēc statusa: Melnraksti, Ieplānotās, Izpildē (vēstules gaida parakstu vai vēl tiek sūtītas) un Pabeigtās. Statusu ceļš: Melnraksts → Ieplānota → Izpildē → Pabeigta.
- Kolonnas: nosaukums, veids, satura avots, respondentu skaits, nosūtīšanas datums, statuss un rezultātu kopsavilkums (piegādes statusi).
- Darbības:
  - melnrakstu var turpināt (atveras saglabātajā solī) vai dzēst;
  - ieplānoto kampaņu var izpildīt uzreiz ("Izpildīt tagad") vai dzēst;
  - kampaņai, kas gaida parakstu, ir poga "Parakstīt";
  - nosūtītai kampaņai ir poga "Skatīt vēsturē".
- Sarakstā var meklēt un filtrēt pēc kampaņas veida.
- Var būt vairāki melnraksti vienlaikus. Katrs tiek saglabāts automātiski.
- Testa datos ir piecas agrāk nosūtītas kampaņas (pēdējo 75 dienu laikā, viena ar parakstu), lai sūtīšanas vēsturē, atskaitēs un respondenta kartītē būtu ko redzēt.
- Papildus tam ir **arhīvs**: ikmēneša kampaņas par pēdējiem ~2 gadiem (pirmstermiņa un nokavēto pārskatu atgādinājumi, ceturkšņa uzaicinājumi, informatīvi ziņojumi u. c.) un trīs kampaņas, kas nosūtītas pirms vairāk nekā 2 gadiem (25–31 mēnesi atpakaļ). Arhīva ierakstiem glabājas tikai metadati un piegādes mēģinājumi, bez vēstules satura, lai dati ietilptu pārlūka krātuvē; atverot šādu vēstuli, redzams temats un piegādes informācija ar norādi, ka saturs arhīvā nav saglabāts. Kopā ~570 vēstuļu.

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

Veidne atveras centrētā modālajā logā, kura platums ir apmēram puse ekrāna (900–1100 px), bet augstums – līdz 90 % ekrāna. Logā ir iekšēja ritināšana, poga × aizvēršanai un fiksētas pogas "Atcelt" / "Saglabāt" apakšā.

- **Izkārtojums.** Divas kolonnas: forma un priekšskatījums, kas, ritinot formu, paliek redzams. Ja ekrāns ir šaurāks par 900 px, kolonnas ir viena zem otras.
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
- Pielikumi redzami arī kampaņas redaktorā un nosūtītajās vēstulēs.

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

Viss formatējums tiek saglabāts veidnē un ir redzams veidnes priekšskatījumā un kampaņas redaktorā tieši tā, kā to redzēs saņēmējs.

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

Sagataves atver ar pogu **"Sagataves"** cilnes "Veidnes" augšējā labajā stūrī. Tās ir atsevišķā skatā ar pogu "← Atpakaļ uz veidnēm". Vecās saites `#sagataves` un `#pielikumi` atver šo skatu.

Sagataves ir divās grupās:
- **E-pasta satura šabloni** – teksta sagataves, no kurām var sākt jaunu e-pasta veidni (poga "Jauna veidne" kartītē vai "No sagataves" redaktorā). Sākotnēji tie ir esošo e-pasta satura veidņu teksti un trīs papildu šabloni, lai katrai adresātu grupai katrā kategorijā ir vismaz viens. Šablonus var pievienot, rediģēt un dzēst.
- **Pielikumu sagataves** – dokumenti, arī tie, kas izdalīti no PDF faila ar vēstuļu paraugiem, un citi faili.

Papildinājumi atbilstoši specifikācijas 2.2. sadaļai (F13):
- **Materiāla veids.** Pielikumu sagatavēm ir veids: Vēstules variants, Instrukcija, Informatīvais materiāls vai Pielikuma sagatave. Veids redzams kartītē kā birka, to var izvēlēties pievienošanas / labošanas logā, un sarakstu var filtrēt pēc veida. Iepriekš ielādētie vēstuļu paraugi ir "Vēstules variants". Testa datos ir arī trīs izdomāti materiāli (mazi ģenerēti PDF faili): "Instrukcija – e-anketas aizpildīšana", "Informatīvais materiāls – datu konfidencialitāte" un "Pielikums – pārskatu iesniegšanas termiņi 2026".
- **E-pasta satura šablonu versijas.** Saglabājot šablonu ar mainītu tematu vai tekstu, iepriekšējais variants tiek saglabāts kā versija (pēdējās 5). Kartītē redzams versijas numurs un pēdējā labojuma datums; labošanas logā ir iepriekšējo versiju saraksts ar pogu "Ielādēt redaktorā".
- **Izmantojums.** Šablona kartītē redzams, kurās veidnēs tas izmantots ("Izmantots veidnēs: …"). Veidne atceras, no kura šablona tā izveidota; sākotnējie šabloni ir saistīti ar e-pasta veidnēm, no kurām ņemts to teksts. Šablona labojumi esošās veidnes nemaina.

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

## Respondentu dati

Respondentu dati nāk no Respondentu pārvaldības moduļa, bet iesniegšanas statusi no Datu vākšanas pārraudzības (prototipā – izdomāti testa dati). Komunikācijas modulī tie ir redzami kampaņas solī "Respondenti" un respondenta kartītē.

- **Datu modelis:**
  - **respondents:** tips (juridiska / fiziska persona), nosaukums vai vārds, reģistrācijas Nr. (juridiskām personām), e-adrese, e-pasts 1, e-pasts 2;
  - **pārskats:** nosaukums, kods, periodiskums (Gads / Pusgads / Ceturksnis / Mēnesis / Nedēļa / Intervija; intervēšanas vilnis prototipā ir 2 mēneši) un termiņa noteikums, piem., "15. datums pēc pārskata perioda beigām". Termiņš tiek aprēķināts katram periodam, un tas ir vienāds visiem šī pārskata respondentiem;
  - **pienākums:** respondents × pārskats × periods (piem., "2026. g. oktobris", "2026. g. 4. ceturksnis", "2026. g. 39. nedēļa"), termiņš, iesniegšanas statuss ("Iesniegts" / "Nav iesniegts") un iesniegšanas datums. Ja pārskats nav iesniegts un termiņš ir pagājis, tas tiek rādīts kā "Nav iesniegts (kavēts)". Vienam respondentam var būt vairāki pienākumi.
  - **Iesniegšanas statusi** ir dati no Datu vākšanas pārraudzības. Tie ir tikai lasāmi; prototipā tie ir testa dati.
  - Fiziskās personas ir piesaistītas apsekojumiem (Darbaspēka, Ceļotāju, Mājsaimniecību budžeta, Laika izlietojuma, Iedzīvotāju ienākumu un dzīves apstākļu, IKT lietošanas apsekojums).
- **Testa dati:**
  - 15 uzņēmumi un 8 pārskati ar visiem periodiskumiem (arī "Intervija" – Uzņēmumu inovāciju apsekojums);
  - 10 fiziskās personas sešos apsekojumos ar visiem periodiskumiem: Gads (Mājsaimniecību budžeta), Pusgads (Iedzīvotāju ienākumu un dzīves apstākļu), Ceturksnis (Darbaspēka), Mēnesis (Ceļotāju), Nedēļa (Laika izlietojuma), Intervija (IKT lietošana 2026. gadā);
  - termiņi ir gan pagātnē, gan nākotnē, un statusi ir jaukti;
  - trīs pārskatiem termiņa noteikums ir izvēlēts tā, lai pēdējā perioda termiņš būtu tieši pēc 3, 5 un 7 dienām no šodienas (nedēļas degvielas cenu, mēneša rūpniecības produkcijas un ceturkšņa darba samaksas pārskats);
  - testa dati tiek aprēķināti attiecībā pret šodienu, kad tie tiek izveidoti vai atjaunoti ("Atjaunot sākotnējos testa datus").

**Respondenta kartīte.** Uzklikšķinot uz respondenta nosaukuma kampaņā (atlases tabulā, adrešu solī) vai vēsturē, no labās puses atveras sānu panelis. Tajā ir:
- pamatdati (nosaukums, tips, reģ. Nr., kontaktpersona, pazīmes) ar norādi "Dati no Respondentu pārvaldības";
- adreses: eAdrese, E-pasts 1 un E-pasts 2 (sinhronizētas, tikai lasāmas, ar pogu "Sinhronizēt") un E-pasts 3 (manuāli, rediģējams, ar formāta pārbaudi);
- pārskati un periodi (tikai lasāmi): pārskats, periods, termiņš un statuss;
- komunikācijas vēsture: kampaņas, kurās respondents bijis, vēstules, datumi un piegādes statusi (ar pogu "Skatīt");
- ja kartīte atvērta no kampaņas redaktora, arī norāde, vai respondents ir iekļauts šajā kampaņā.

### Respondentu adreses un adrešu prioritāte

**Adreses.** Katram respondentam ir četras adreses:
- **eAdrese** (juridiskām personām – uzņēmuma eAdrese), **E-pasts 1** un **E-pasts 2**. Tās ir sinhronizētas no Respondentu pārvaldības.
- **E-pasts 3 (manuāli)**, ko darbinieks var ievadīt vai labot komunikācijas modulī.

**Respondenta kartītē** redzamas:
- sinhronizētās adreses kā tikai lasāmas, ar birku "No Respondentu pārvaldības", datumu "Sinhronizēts: …" un pogu "Sinhronizēt" (simulācija);
- lauku "E-pasts 3 (manuāli)" ar e-pasta formāta pārbaudi un pogu "Saglabāt", kā arī informāciju, kas un kad to ievadīja.

**Testa dati** satur dažādus gadījumus:
- dažiem respondentiem nav eAdreses;
- daudziem ir tikai viens e-pasts, dažiem aizpildītas visas adreses;
- vienam respondentam nav nevienas adreses.

**Prioritāte kampaņā.** Kampaņas 5. solī "Adreses" izvēlas "1. prioritāte", "2. prioritāte" un "3. prioritāte".
- Vienu adreses veidu nevar izvēlēties divreiz. 1. prioritāte ir obligāta.
- Noklusējums: eAdrese → E-pasts 1 → E-pasts 2.
- Kopsavilkumā redzams, cik respondentiem vēstule tiks sūtīta uz katras prioritātes adresi un cik respondentiem nav nevienas atbilstošas adreses.
- **Respondenti bez derīgas adreses.** Ja kādam respondentam nav nevienas adreses atbilstoši izvēlētajai prioritātei, solī redzams šo respondentu saraksts. Katram var turpat ievadīt E-pastu 3 vai izņemt viņu no kampaņas ("Izņemt no kampaņas").

**Sūtīšanas simulācija** (specifikācija F9, F10). Vēstules apstrādā pēc adrešu prioritātes:
- **Piegādāta uzreiz:** lielākā daļa vēstuļu.
- **Pagaidu kļūda:** piem., pārpildīta pastkaste vai īslaicīgi nepieejams eAdreses serviss. Sistēma atkārtoti mēģina sūtīt uz to pašu adresi. Pēc trim pagaidu kļūdām pēc kārtas tā pāriet uz nākamo adresi.
- **Pastāvīga kļūda:** sistēma pāriet uz nākamo adresi. Simulācijā pastāvīgas kļūdas rada:
  - e-adreses `_DEFAULT@00000000112` un `_PRIVATE@00000000222` (nav aktivizētas);
  - e-pasti uz domēnu `nepiegadajams.example` (pastkaste neeksistē);
  - e-pasti uz domēnu `surogatfiltrs.example` (noraidīti kā surogātpasts).
- **Neveiksmīga:** ja visas adreses ir izsmeltas, vēstule tiek atzīmēta kā neveiksmīga un nodota manuālai pārbaudei (testa datos, piem., Mārtiņam Kalniņam).
- **Prombūtne:** daļa e-pastu saņem automātisku atbildi par prombūtni. Šādas vēstules ir piegādātas.

Pagaidu kļūdas, surogātpasts un prombūtne tiek simulēti deterministiski, pēc adreses un sūtījuma. Priekšskatījumā redzama prioritāšu secība un paredzamais rezultāts (zināmās pastāvīgās kļūdas), bet nosūtītajā vēstulē – katrs faktiskais mēģinājums.

### Pārskatu tabula vēstulē – `{pārskatu_tabula}`

- **Ievietošana.** Veidnes redaktora izvēlnē "+ Ievietot lauku" ir bloks **"Pārskatu tabula"**. To ievietojot, var izvēlēties:
  - kolonnas: Pārskats, Periods, Termiņš, Statuss;
  - rindas: "Visi atlasītie pienākumi" (uzaicinājumiem) vai "Tikai neiesniegtie" (atgādinājumiem).

  Uzklikšķinot uz bloka redaktorā, iestatījumus var mainīt vai bloku dzēst.
- **Atlase kampaņā.** Kampaņas 2. solī "Respondenti" pienākumus atlasa pēc kampaņas veida, pārskata un perioda (skatīt "Komunikācijas kampaņa").
- **Ģenerēšana.** Tabula tiek izveidota katram respondentam no viņa pienākumiem, kas atbilst šai atlasei. Kavētie termiņi ir izcelti sarkanā krāsā. E-adreses ziņojumā tabula tiek pārvērsta tekstā.
- **Esošās veidnes.** Tabula pievienota uzaicinājuma ("Uzaicinājums sniegt datus apsekojumā (vēstule pielikumā)" – PDF dokumentā) un atgādinājuma ("Atgādinājums par datu iesniegšanas termiņu") veidnēm juridiskām personām.

## Komunikācijas kampaņa

Jaunu kampaņu sagatavo sešos soļos (specifikācija F1–F11).
- Augšā ir **progresa josla**: pabeigtie soļi ir atzīmēti ar ķeksīti, soļi ar trūkstošu informāciju – ar "!".
- Starp soļiem var pārvietoties brīvi: ar progresa joslu vai pogām "← Atpakaļ" / "Tālāk →".
- Pogu **"Saglabāt melnrakstu"** var izmantot jebkurā solī. Kampaņa tiek saglabāta arī automātiski.

1. **Pamatdati** (F1):
   - **adresāts** (Fiziskās personas / Juridiskās personas / Visi) un **kampaņas nosaukums** (pēc noklusējuma "Kampaņa Nr. N");
   - **komunikācijas veids**: četras kompaktas pogas vienā rindā (ikona un nosaukums) – Uzaicinājums / Atgādinājums / Informatīvs ziņojums / Cits. Pēc veida tiek filtrēta veidņu izvēle 3. solī;
   - **nosūtīšanas datums un laiks**: kompakts pārslēgs "Nosūtīt tūlīt / Ieplānot" kreisajā pusē. Izvēloties "Ieplānot", tajā pašā rindā pa labi parādās kompakti lauki bez virsrakstiem – datums (vietturis "DD.MM.GGGG", kalendāra ikona atver datuma izvēli) un laiks (vietturis "HH:MM", pulksteņa ikona, ieteikumi ik pēc 30 minūtēm). "Nosūtīt tūlīt" gadījumā lauki ir paslēpti:
     - datums tiek rādīts formātā DD.MM.GGGG, laiks – 24 stundu formātā (piem., 09:00). Rakstot punkti un kols tiek ievietoti automātiski;
     - noklusējums – rītdiena plkst. 09:00;
     - pagātnes datumu un laiku nevar izvēlēties: kalendārā tie nav pieejami, šodienai laika ieteikumos ir tikai nākotnes laiki, bet ievadītam pagātnes vai nederīgam datumam vai laikam tiek parādīta kļūda, un kampaņu nevar ieplānot;
     - uz šauriem ekrāniem datuma un laika lauki pārceļas zem pārslēga;
   - **"Ko attiecina kampaņa"** – divas līdzvērtīgas kartītes blakus (uz šauriem ekrāniem viena zem otras). Var izmantot vienu vai abas, bet jābūt aizpildītai vismaz vienai. Ja aizpildītas abas, atlase ir abu kritēriju krustpunkts (piem., konkrēts apsekojums konkrētā periodā):
     - **Pēc perioda:** periodiskums kā pogas-birkas (vairākizvēle): Gads, Pusgads, Ceturksnis, Mēnesis, Nedēļa, Intervija. Pēc tam neobligāti var atzīmēt konkrētus periodus (vairākizvēle), piem., "2026. gads", "2026. g. 2. pusgads", "2026. g. 3. ceturksnis", "2026. g. septembris", "2026. g. 40. nedēļa", "2026. g. 5. intervēšanas vilnis". Ja konkrēts periods nav norādīts, tiek atlasīti visi izvēlētā periodiskuma **aktīvie periodi** – tie, kuros datu vākšana nav beigusies (termiņš vēl nav pienācis vai kāds pienākums nav iesniegts). Slēgtie periodi sarakstā atzīmēti ar "(slēgts)";
     - **Pēc apsekojuma:** meklējama vairākizvēle ar apsekojumiem / pārskatiem (atbilstoši adresātam). Pie katra redzams kods, periodiskums un termiņa noteikums. Izvēlētie apsekojumi redzami kā birkas ar ×. Sarakstā var pārvietoties ar bultiņām un izvēlēties ar Enter. Ja izvēlēts apsekojums, kas neatbilst izvēlētajam periodiskumam, tiek parādīts brīdinājums;
     - zem kartītēm ir dzīvs kopsavilkums "Atlasīti X respondenti, Y pārskati/periodi";
   - **vēstules dati:**
     - "Nosaukums vēstulē `{apsekojums}`" redzams, ja atlase attiecas uz vienu apsekojumu (tas tiek aizpildīts no apsekojuma datiem, un to var labot). Ja apsekojumi ir vairāki, lauks ir paslēpts: apsekojumu nosaukumi vēstulē redzami blokā `{pārskatu_tabula}`, bet `{apsekojums}` tiek aizstāts ar respondenta apsekojumu nosaukumiem;
     - "Vēstules datums `{datums}`" un "Dokumenta Nr. `{dok_nr}`";
     - laukā nav "Sākums" un "Termiņš": `{termiņš}` tiek ņemts automātiski no pārskata un perioda datiem (respondenta tuvākais termiņš, kas nosūtīšanas dienā vēl nav pagājis; ja tāda nav – agrākais), bet `{sākums}` ir nākamā diena pēc attiecīgā perioda beigām;
     - sakļaujamā sadaļā – apsekojuma kontakti, noformējums un tulkojumi.

   Adresāts nosaka, kuras veidnes tiek piedāvātas. Mainot adresātu, tiek pielāgots arī filtrs "Respondenta veids".
2. **Respondenti** (F2, F11). Atlase ir atkarīga no komunikācijas veida.
   - **Atlases kritēriji** tiek izvēlēti 1. solī ("Ko attiecina kampaņa"). 2. solī redzams to kopsavilkums (periodiskums, periodi, apsekojumi) ar pogu "Mainīt 1. solī".
   - **Uzaicinājums, informatīvs ziņojums un cits** atlasa visus respondentus, kuriem ir pienākums atlasītajos pārskatos un periodos. Termiņš un statuss netiek ņemti vērā.
   - **"Atgādinājums"** atlasa tikai neiesniegtos pienākumus. Papildus jāizvēlas viens no veidiem:
     - **Pirms termiņa.** Jānorāda "Dienas līdz termiņam" N. Nosūtīšanas datums ir šodiena vai 1. solī ieplānotais datums. Termiņa datums tiek aprēķināts kā nosūtīšanas datums + N dienas, un tiek atlasīti tikai tie neiesniegtie pienākumi, kuru termiņš ir tieši šajā datumā. Tiek parādīts aprēķinātais termiņš un pārskati un periodi, kas tam atbilst (piem., "Termiņš 07.10.2026.: Mēneša rūpniecības produkcijas pārskats, 2026. g. septembris"). Ja tādu nav, tiek parādīts paziņojums "Šajā datumā nav pārskatu ar termiņu pēc N dienām".
     - **Ieplānota atgādinājuma kampaņa.** Izpildes brīdī atlase tiek pārrēķināta pēc aktuālajiem statusiem. Prototipā to simulē poga "Izpildīt tagad" kampaņu sarakstā.
     - **Pēc termiņa (nokavēts).** Tiek atlasīti neiesniegtie pienākumi, kuru termiņš ir pagājis. Var norādīt neobligātu lauku "Kavēts vismaz N dienas".
   - **Papildu atlase pēc pazīmēm** (respondenta veids, dalības veids, iepriekšējā dalība, valoda) ir sakļaujamā sadaļā.
   - **Atlases rezultāts:**
     - kopsavilkums: respondentu skaits, pienākumu skaits un sadalījums pa pārskatiem;
     - tabula ar respondentiem: izvēršot rindu, redzami respondenta atlasītie pienākumi (pārskats, periods, termiņš, statuss), un atsevišķus respondentus var izņemt;
     - norāde "Dati no Datu vākšanas pārraudzības" un poga "Atjaunot statusus" (simulācija: daļa neiesniegto pienākumu kļūst iesniegti).
   - Ja respondentam ir atlasīti vairāki pārskati vai periodi, viņš saņem vienu vēstuli. `{pārskatu_tabula}` ietver tikai atlasītos pienākumus, bet atgādinājumā tikai neiesniegtos.
3. **Saturs.** Ir divas kartītes: "Izmantot veidni" un "Noformēt saturu".
   - **Izmantot veidni.** Atveras veidņu izvēle. Tajā redzamas tikai kampaņas adresātam paredzētās veidnes, sagrupētas pēc kategorijas, ar meklēšanu un teksta priekšskatījumu. Izvēlēto veidni var izmantot uzreiz ("Izmantot veidni") vai pielāgot ("Pielāgot šai kampaņai"). Pielāgojot atveras redaktors ar veidnes saturu. Izmaiņas attiecas tikai uz šo kampaņu, un pati veidne netiek mainīta.
   - **Noformēt saturu.** Atveras tas pats redaktors, kas veidnes izveidei, ar visām tā iespējām. Atšķirības no veidnes izveides:
     - nav lauku "Veidnes nosaukums" un "Kategorija", adresāts tiek ņemts no kampaņas;
     - virsraksts ir "Vēstules saturs: [kampaņas nosaukums]";
     - priekšskatījumā redzami kampaņā atzīmētie respondenti, starp kuriem var pārslēgties ar ← →;
     - apakšā ir pogas "Atcelt", "Saglabāt arī kā veidni" un "Izmantot kampaņā".
   - **Saglabāt arī kā veidni.** Prasa norādīt veidnes nosaukumu un kategoriju. Saturs tiek saglabāts kā jauna veidne, un kampaņa to izmanto.
   - **Kopsavilkums.** Kad saturs ir apstiprināts, solī redzams satura avots ("Veidne: [nosaukums]", "Veidne, pielāgota kampaņai" vai "Individuāls saturs"), temats un vēstules veids. Ir pogas "Labot saturu" un "Izvēlēties citu saturu".
4. **Paraksts** (F8):
   - "Nav jāparaksta" vai "Jāparaksta" (DVS NAMEJS integrācija; prototipā – simulācija);
   - ja jāparaksta – parakstīšanas veids (Secīga / Paralēla / Paka) un parakstītāji. Secīgai parakstīšanai secība ir atzīmēšanas kārtībā;
   - "Paraksts vēstulē": lauki `{parakstītājs}` un `{amats}` (arī PDF vēstules parakstā). Pēc noklusējuma tos ņem no pirmā parakstītāja vai no "Pastāvīgajām daļām", un tos var mainīt tikai šai kampaņai.
5. **Adreses** (F7). Trīs izvēlnes "1./2./3. prioritāte", kopsavilkums, cik respondentiem kura adrese tiks izmantota, un saraksts "Respondenti bez derīgas adreses" (var ievadīt E-pastu 3 vai izņemt respondentu).
6. **Pārbaude** (F3, F5, F6):
   - **kampaņas kopsavilkums** ar saitēm "Labot" uz attiecīgo soli;
   - **priekšskatījums:** viena vēstule katram respondentam ar `{pārskatu_tabula}` (atgādinājumā tikai neiesniegtie pienākumi), pārslēgšanās starp respondentiem un pārslēgs "E-pasts / eAdrese";
   - **"Pielāgot šo vēstuli"** (F5): konkrētā respondenta vēstulei var labot tematu un tekstu, pievienot vai noņemt papildu pielikumus. Pielāgotā vēstule ir atzīmēta ar birku "Pielāgota vēstule" (arī atlases tabulā un vēsturē), un to var atjaunot uz sākotnējo;
   - **galvenā poga** atkarībā no iestatījumiem: "Ieplānot" (ieplānota kampaņa), "Nodot parakstīšanai" (jāparaksta) vai "Nosūtīt".

**Parakstīšana (simulācija).** Pēc "Nodot parakstīšanai" kampaņa ir sadaļā "Izpildē", un tās vēstulēm ir statuss "Gaida parakstu" (redzams arī sūtīšanas vēsturē). Poga "Parakstīt" (kampaņu sarakstā vai vēstures blokā) paraksta vēstules, un tās tiek nosūtītas. Ieplānotai kampaņai ar parakstu vēstules tiek nodotas parakstīšanai izpildes brīdī.

**Melnraksts.** Kampaņa, arī tās saturs, tiek automātiski saglabāta kā melnraksts, tāpēc darbu var turpināt vēlāk, arī pēc lapas pārlādes. Melnraksti redzami kampaņu sarakstā. Poga "Dzēst melnrakstu" redaktorā to dzēš. Pēc nosūtīšanas atveras cilne "Sūtīšanas vēsture" ar šīs kampaņas bloku, bet pēc plānošanas – kampaņu saraksta sadaļa "Ieplānotās".

## Sūtīšanas vēsture

Cilnē **Sūtīšanas vēsture** (specifikācija F16, F17) ir visas nosūtītās un nosūtīšanas procesā esošās vēstules.
- **Apakšsadaļas** pēc statusa: Visas · Gaida parakstu · Nosūtītas · Piegādātas · Neveiksmīgas.
- **Filtri:** kampaņa, kampaņas veids, kanāls (eAdrese / e-pasts), periods (šodien, pēdējās 7, 30 vai 90 dienas) un meklēšana pēc respondenta vai adreses.
- Tabulā sākotnēji redzami 50 jaunākie ieraksti; poga "Rādīt vēl" ielādē nākamos 50.
- **Tabula:** katrai vēstulei redzams adresāts (uzklikšķinot atveras respondenta kartīte), kampaņa, statuss, kanāls, adrese un nosūtīšanas laiks. Statusa šūnā redzamas arī NDR klases, "Atkārtoti nosūtīta" un "Manuāla pārbaude" / "Izskatīta".
- **Izvērstā rinda:**
  - **statusu ceļš (laika līnija):** Melnraksts → (Gaida parakstu → Parakstīta) → Nosūtīta → Piegādāta, kā arī "Pagaidu kļūda → Atkārtots mēģinājums", "Pastāvīga kļūda → Nākamā adrese" un "Visas adreses izsmeltas → Neveiksmīga → Manuāla pārbaude";
  - **visi mēģinājumi:** laiks, adrese, rezultāts un NDR.
- **NDR (atgriezeniskie paziņojumi):** katram paziņojumam ir:
  - klasifikācija: pagaidu kļūda, pastāvīga kļūda, surogātpasts vai prombūtne;
  - birka "MI klasificēts" ar ticamību;
  - novirzījums: pagaidu kļūda → sistēma, pastāvīga kļūda → sistēma un darbinieks, surogātpasts un prombūtne → darbinieks;
  - sākotnējais paziņojuma teksts.
- **Manuāla pārbaude** (neveiksmīgajām vēstulēm): var ievadīt jaunu e-pastu un nospiest "Sūtīt atkārtoti". Adrese tiek pārbaudīta un saglabāta kā respondenta E-pasts 3, bet mēģinājums tiek pievienots vēsturei. Var arī nospiest "Atzīmēt kā izskatītu".
- Kampaņām, kas gaida parakstu, virs tabulas ir poga "Parakstīt".
- Augšā ir kopējā statistika.
- **Ierakstu dzēšana.** Vēstures ierakstus var dzēst tikai tad, ja tie nosūtīti pirms vairāk nekā 2 gadiem (pēc nosūtīšanas datuma):
  - rindas dzēšanas poga ir aktīva tikai šādiem ierakstiem; jaunākiem tā ir neaktīva ar padomu "Ierakstus var dzēst tikai pēc 2 gadiem";
  - augšā ir poga **"Dzēst ierakstus, vecākus par 2 gadiem"**. Iekavās redzams dzēšamo ierakstu skaits. Pirms dzēšanas parādās apstiprinājuma logs ar ierakstu un kampaņu skaitu un robežas datumu. Ja šādu ierakstu nav, poga ir neaktīva;
  - noteikums tiek pārbaudīts arī pašā darbībā, tāpēc jaunāku ierakstu nevar izdzēst.
- Nosūtīšana prototipā ir simulēta (vēstules reāli netiek sūtītas), bet paskaidrojošais teksts par to no cilnes noņemts.

## Atskaites

Cilnē **Atskaites** (specifikācija F18) katrai apakšsadaļai ir savs skats. Visos skatos ir:
- filtri vienā rindā augšā: periods (datums no–līdz ar ātrajām izvēlēm "Šis mēnesis", "Pēdējie 3 mēneši", "Šis gads", "Pēdējie 12 mēneši"), kampaņas veids, kanāls (eAdrese / e-pasts) un kampaņa (sarakstā tikai atlasītā perioda kampaņas). Pirmajā atvēršanā atlasīti pēdējie 12 mēneši;
- poga **"Eksportēt CSV"** (atdalītājs – semikols, UTF-8 ar BOM, lai fails pareizi atveras Excel);
- bloks **"MI kopsavilkums"** ar simulētām galvenajām atziņām par atlasītajiem datiem: piegādes īpatsvars, neveiksmīgo ziņu īpatsvara izmaiņas e-pastā salīdzinājumā ar iepriekšējo tāda paša garuma periodu, biežākais NDR iemesls, atkārtotā nosūtīšana, manuāla pārbaude un paraksti.

Skati:
- **Nosūtīšanas kopsavilkums** (pilna atskaite):
  - sešas rādītāju kartītes: nosūtīts, piegādāts, neveiksmīgs, atkārtoti nosūtīts, gaida parakstu un piegādes īpatsvars (%). Katrā kartītē ir izmaiņa pret iepriekšējo tāda paša garuma periodu (ja atlasīta konkrēta kampaņa, salīdzinājums netiek rādīts). "Piegādāts" nozīmē piegādāts eAdresē vai nodots e-pasta serverim;
  - līniju grafiks "Nosūtītās un piegādātās ziņas pa mēnešiem" (divas līnijas, leģenda un vērtības pēdējā punktā, rīka padoms katram mēnesim);
  - stabiņu grafiki: ziņas pa kanāliem, ziņas pēc kampaņas veida un NDR iemeslu sadalījums;
  - tabula "Kampaņas": nosaukums, datums, veids, nosūtīto, piegādāto un neveiksmīgo skaits un piegādes %. Tabulu var kārtot, uzklikšķinot uz kolonnas nosaukuma (atkārtots klikšķis maina virzienu);
  - "MI kopsavilkums" – 3–4 teikumi par atlasīto periodu (apjoms un piegādes īpatsvars, problemātisko ziņu īpatsvars pa kanāliem, biežākais kampaņas veids, biežākais NDR iemesls), kas mainās atkarībā no filtriem (simulācija);
  - "Eksportēt CSV" lejupielādē kampaņu tabulu ar pašreizējiem filtriem un kārtošanu;
  - grafikiem ir rīka padoms (pelei un tastatūrai) un datu tabula. Krāsas pārbaudītas krāsu redzes traucējumu gadījumam.
- **Piegādes rezultāti:** tabula pa kampaņām (vēstules, piegādātas, nosūtītas, neveiksmīgas, gaida parakstu, piegādes %) un kopsavilkums pa kanāliem.
- **Neveiksmīgās ziņas:** NDR sadalījums pa klasifikācijai un novirzījumam, kā arī visu NDR tabula (respondents, kampaņa, adrese, klasifikācija, ticamība, novirzījums, statuss).
- **Atkārtotā nosūtīšana:** rādītāji un tabula ar mēģinājumu skaitu un iemeslu: pagaidu kļūda, pāreja uz nākamo adresi vai manuāla atkārtota nosūtīšana.
- **Citi pārskati:** parakstīšanas rezultāti pa kampaņām (veids, parakstītāji, parakstītās vēstules, gaida parakstu, laiki).

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
