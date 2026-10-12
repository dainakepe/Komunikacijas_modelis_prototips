# Komunikācijas moduļa prototips

CSP datu vākšanas sistēmas komunikācijas moduļa prototips: komunikācijas kampaņas, vēstuļu veidnes, sūtīšanas vēsture, atskaites un simulēta nosūtīšana. Respondentu dati nāk no citiem DELTA moduļiem (prototipā – izdomāti testa dati).

> **Galvenā atsauce:** komunikācijas moduļa funkcionālais apraksts – [`docs/komunikacija_specifikacija.md`](docs/komunikacija_specifikacija.md). Prototipa struktūra un funkcijas tiek veidotas atbilstoši tam.

Prototips ir vienā failā `index.html`, un serveris nav vajadzīgs. Failu var atvērt tieši pārlūkā vai publicēt ar GitHub Pages. Pielikumu bibliotēkas PDF faili atrodas mapē `pielikumi/`, attēli (piem., sākumlapas ilustrācija) – mapē `atteli/`. Tie tiek ielādēti ar relatīvu ceļu.

- Visi testa dati ir izdomāti. E-pasta adresēm ir rezervētais domēns `.example`, un e-adrešu numuri sākas ar `0000…`.
- Dati glabājas tikai pārlūka `localStorage`. Kājenē ir poga, ar kuru var atjaunot sākotnējos testa datus.
- Nosūtīšana ir simulācija. E-pasti uz domēnu `nepiegadajams.example` simulācijā "neizdodas", lai var redzēt kļūdas statusu.
- Krāsas ir definētas kā CSS mainīgie `index.html` faila sākumā (`:root`). Saskarnes pamatkrāsa ir `#297785` (`--primary`). Lielajām tumšajām joslām (galvenei) ir maiga vertikāla krāsu pāreja – mainīgais `--header-gradient`: `linear-gradient(to bottom, #3D8C99 0%, #297785 60%, #297785 100%)`; teksts uz tām ir balts. Pogas, birkas, cilnes un citi mazi elementi ir vienā krāsā `#297785` (bez pārejas).

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

## Paskaidrojošie teksti un kļūdas

Prototipā nav piezīmju par datu avotiem (piem., "Dati no Respondentu pārvaldības", "Dati no Metadatu pārvaldības", "Dati no Datu vākšanas pārraudzības") – ne pie laukiem, ne "i" padomos, tabulās vai respondenta kartītē.

Ekrāni ir tīri: pastāvīgi redzamu paskaidrojošo tekstu un informatīvo paziņojumu nav.
- **Padomi "i".** Svarīgā informācija ir mazā "i" ikonā blakus attiecīgajam virsrakstam vai laukam. Padoms parādās, uzbraucot ar peli vai fokusējot ar tastatūru (pie ekrāna malām tas tiek izlīdzināts, lai neiziet ārpus ekrāna). Tā ir arī lapu virsrakstiem (piem., "Komunikācijas kampaņas", "Sūtīšanas vēsture", "Atskaites", "Sagataves"), kampaņas soļiem, grafiku virsrakstiem atskaitēs un modālo logu virsrakstiem.
- **Redzams paliek tikai būtiskais:** lauku un pogu nosaukumi, statusi, kopsavilkuma skaitļi un īsi stāvokļa paziņojumi (piem., "Nekas netika atrasts", "Nav pārskatu ar šo termiņu").
- **Kļūdas** (obligātie lauki un pārbaudes) tiek rādītas tikai pēc mēģinājuma pāriet uz nākamo soli ("Tālāk", pāreja uz vēlāku soli progresa joslā), saglabāt melnrakstu vai nosūtīt: īss sarkans teksts pie konkrētā lauka (piem., "Norādiet periodu vai apsekojumu.", "Nosūtīšanas datums nedrīkst būt pagātnē.", "Norādiet vismaz vienu parakstītāju."). Progresa joslā "!" parādās tikai soļiem, kuros ir bijis šāds mēģinājums. Poga "Nosūtīt" vairs nav bloķēta: ja ir kļūdas, kampaņa netiek nosūtīta, un kopsavilkumā tiek parādīts kļūdu saraksts.
- Ilustrācijas rāmī sākumlapā teikums zem virsraksta paliek, jo tas ir daļa no ilustrācijas.

## Moduļa cilnes

Komunikācijas modulim ir četras cilnes (atbilstoši specifikācijai):
1. **Kampaņas** (pirmā un noklusējuma cilne). Tajā ir saraksts "Komunikācijas kampaņas" un poga "+ Jauna kampaņa". Skaidrojums "Kampaņa ir viena sūtīšana izvēlētiem respondentiem: uzaicinājums, atgādinājums vai cita informācija." ir "i" padomā blakus virsrakstam.
2. **Veidnes.** Vēstuļu veidnes un sagataves.
3. **Sūtīšanas vēsture.** Nosūtītās vēstules, sagrupētas pa kampaņām.
4. **Atskaites.** Rādītāji, grafiki un tabulas par sūtīšanas rezultātiem ar CSV eksportu un MI kopsavilkumu.

- **Noformējums.** Cilnēm nav skaita ciparu. Teksts ir lielāks (16,5 px), pustrekns, ar ikonu pirms nosaukuma. Aktīvajai cilnei ir pamatkrāsas (#297785) teksts, bieza apakšlīnija un ļoti gaišs tirkīzzaļš fons. Neaktīvās ir tumši pelēkas un, uzbraucot ar peli, kļūst tirkīzzaļas.
- **Navigācijas ceļš:** "DELTA › Respondentu pārvaldība › Komunikācija › [cilne]".
- **Apakšsadaļas** ir filtru pogas zem virsraksta (bez skaitītājiem):
  - Kampaņas: Visas · Melnraksti · Ieplānotās · Izpildē · Pabeigtās. Atverot cilni, vienmēr aktīva ir "Visas";
  - Veidnes: adresātu grupu kartītes (Fiziskām personām · Juridiskām personām · Cita komunikācija). "Sagataves" ir poga augšējā labajā stūrī pirms "Pastāvīgās daļas", un tā atver atsevišķu skatu ar pogu "← Atpakaļ uz veidnēm";
  - Sūtīšanas vēsture: Visas · Gaida parakstu · Procesā · Piegādātas · Neveiksmīgas · Manuāla pārbaude · Administratoram;
  - Atskaites: Nosūtīšanas kopsavilkums · Piegādes rezultāti · Neveiksmīgās ziņas · Atkārtotā nosūtīšana · Citi pārskati.

Atsevišķas cilnes "Respondenti" nav, jo respondentu dati nāk no citiem DELTA moduļiem. Tie ir redzami kampaņas solī "Respondenti" un respondenta kartītē. Vecās saites turpina darboties: `#sagatavot` atver kampaņas redaktoru, `#nosutitas` atver cilni "Sūtīšanas vēsture", bet `#respondenti` atver cilni "Kampaņas".

**Kampaņu saraksts** (specifikācija F1). Kompakts saraksts, kas ir viegli pārskatāms arī garam sarakstam.
- **Augšdaļa** (no augšas uz leju):
  - 1. rinda: virsraksts "Komunikācijas kampaņas" kreisajā pusē, poga **"+ Jauna kampaņa"** labajā pusē;
  - 2. rinda: statusa pogas **Visas · Melnraksti · Ieplānotās · Izpildē · Pabeigtās** ("Visas" – atverot cilni, vienmēr aktīva);
  - 3. rinda: **filtru josla** (gaišs fons, viena rinda): meklēšana pēc kampaņas nosaukuma; **"Kampaņas veids"** (Visi veidi / Uzaicinājums / Atgādinājums / Informatīvs ziņojums / Cits; atgādinājumi – gan pirms, gan pēc termiņa); **"Veidotājs"** (Visi veidotāji / darbinieku vārdi; izvēlnē ir meklēšana, var pārvietoties ar bultiņām); **"Izveidota"** – datuma diapazons no–līdz (DD.MM.GGGG, ar kalendāru) un ātrās izvēles "Šodien", "Pēdējās 7 dienas", "Šis mēnesis", "Šis gads" (nederīgam datumam – kļūdas paziņojums); labajā malā saite **"Notīrīt"** (redzama tikai, ja kāds filtrs aktīvs);
  - 4. rinda: tabula.
- **Filtri darbojas kopā ar statusa pogām.** Ja nekas neatbilst, tabulas vietā redzams "Nav kampaņu, kas atbilst filtriem" un poga **"Notīrīt filtrus"** (statusa poga paliek).
- **Izveides datums un veidotājs:** melnrakstam – kampaņas izveide (agrākiem melnrakstiem – saglabāšana) un pašreizējais lietotājs; ieplānotajai – izveide; nosūtītajai – izveide (testa datos – 1–6 dienas pirms nosūtīšanas) un kampaņas veidotājs. Testa datos ir 4 veidotāji (Testa Darbinieks, Rūta Testa, Mārtiņš Paraudziņš, Elīna Izdomāta) un dažādi izveides datumi, t. sk. pēdējo 6 mēnešu laikā.
- **Šauri ekrāni:** filtru josla pārceļas divās rindās (meklēšana, veids, veidotājs / izveides periods un "Notīrīt"); telefonā filtri paslēpti aiz pogas **"Filtri"** (ar aktīvo filtru skaitu).
- **Rindas** ~48 px augstas, viena teksta rinda; uzbraucot ar peli, rinda tiek izcelta:
  - **Kampaņa** – nosaukums pustreknā (garš – saīsināts ar "…"); uzbraucot ar peli vai fokusējot – padoms ar pilnu nosaukumu un "Saglabāta 08.10.2026., 13:50" (melnrakstiem) vai "Izveidoja: [vārds], 08.10.2026." (pārējām);
  - **Veids** – ikona un teksts (✉ Uzaicinājums, ◷ Atgādinājums, ⓘ Informatīvs ziņojums, Cits); atgādinājumam tajā pašā rindā pelēkā tekstā "pirms termiņa" / "pēc termiņa";
  - **Respondenti** – skaits;
  - **Nosūtīšana** – "Tūlīt pēc apstiprināšanas", "Plānota 10.10. 09:00" vai "Nosūtīta 06.10. 16:41"; datumi tekošajā gadā – "06.10. 16:41", citādi – "06.10.2025.";
  - **Statuss** – krāsains aplītis un teksts: Melnraksts (pelēks), Ieplānota (zils), Gaida parakstu (dzeltens), Izpildē (tirkīzzaļš), Pabeigta (zaļš), Daļēji neveiksmīga (oranžs). Filtrā "Izpildē" ir arī kampaņas, kas gaida parakstu, "Pabeigtās" – arī daļēji neveiksmīgās;
  - **Rezultāts** – nosūtītām kampaņām šaura progresa josla (zaļa – piegādātas, oranža – neveiksmīgas) un īss teksts "3/5 · 1 ✕"; pilnais teksts ("Piegādātas 3 no 5 · 1 neveiksmīga · 1 procesā") – padomā; pārējām "—".
- **Viena nepārtraukta tabula** bez grupām: visas kampaņas (melnraksti, ieplānotās, nosūtītās) sakārtotas no jaunākās uz vecāko pēc pēdējo izmaiņu laika (melnrakstam – saglabāšana, ieplānotajai – izveide, nosūtītajai – nosūtīšana vai parakstīšana).
- **Ritināšana:** tabulai ir maksimālais augstums (~60 % no ekrāna), ritināšana notiek tabulas iekšpusē ar redzamu ritjoslu, galvene ar kolonnu nosaukumiem paliek redzama. Zem tabulas – "Rādītas 20 no 54" un poga **"Rādīt vairāk"** (vēl 20).
- Uzklikšķinot uz rindas (vai nosaukuma), kampaņa atveras: melnraksts – rediģēšanai (saglabātajā solī), ieplānotā – pārskata logā (veids, nosūtīšana, respondenti, saturs, paraksts, adrešu prioritāte; pogas "Kopēt kā jaunu kampaņu" un "Izpildīt tagad"), nosūtītā – sūtīšanas vēsturē ar atlasītu kampaņu.
- **Izvēlne "⋯"** rindas labajā pusē (ar tastatūru – bultiņas, Escape): **Atvērt**, **Kopēt kā jaunu kampaņu** (jauns melnraksts ar tiem pašiem iestatījumiem un nosaukumu "… (kopija)"; pagājis nosūtīšanas datums tiek aizstāts ar šodienu), **Dzēst** (tikai melnrakstiem, ar apstiprinājumu). Ieplānotajai kampaņai izvēlnē ir arī "Izpildīt tagad" un "Atcelt kampaņu" (ar apstiprinājumu), kampaņai, kas gaida parakstu, – "Parakstīt".
- **Melnraksti – viens ieraksts katrai kampaņai.** Jauna kampaņa kļūst par melnrakstu, kad tajā kaut kas mainīts (nosaukums, joma, tvērums, saturs u. c.), pārejot uz nākamo soli vai ar "Saglabāt melnrakstu"; pēc tam tas pats ieraksts tiek atjaunināts. Saglabāts melnraksts netiek automātiski dzēsts (tikai ar "Dzēst"). Noklusējuma nosaukums "Kampaņa Nr. N" ir unikāls (ņem vērā arī citus melnrakstus un ieplānotās kampaņas). Ielādējot tiek noņemti agrāk radušies dublikāti (vienāds ieraksts vai neaizpildīts melnraksts ar tādu pašu nosaukumu kā cits).
- Var būt vairāki melnraksti vienlaikus. Katrs tiek saglabāts automātiski.
- Testa datos ir piecas agrāk nosūtītas kampaņas (pēdējo 75 dienu laikā, viena ar parakstu), lai sūtīšanas vēsturē, atskaitēs un respondenta kartītē būtu ko redzēt.
- Papildus tam ir **arhīvs**: ikmēneša kampaņas par pēdējiem ~2 gadiem (pirmstermiņa un nokavēto pārskatu atgādinājumi, ceturkšņa uzaicinājumi, informatīvi ziņojumi u. c.) un trīs kampaņas, kas nosūtītas pirms vairāk nekā 2 gadiem (25–31 mēnesi atpakaļ). Arhīva ierakstiem glabājas tikai metadati un piegādes mēģinājumi, bez vēstules satura, lai dati ietilptu pārlūka krātuvē; atverot šādu vēstuli, redzams temats un piegādes informācija ar norādi, ka saturs arhīvā nav saglabāts. Kopā ~570 vēstuļu.

## Veidņu grupēšana

Lapā "Veidnes" veidnes ir sagrupētas divos līmeņos.

**Izskats.** Augšējā labajā stūrī pogas secībā **[Pastāvīgās daļas] [Sagataves] [+ Jauna veidne]**: "Pastāvīgās daļas" – vienkārša pelēka teksta poga, "Sagataves" – izcelta otrā poga (gaiši tirkīzzaļš fons, tirkīzzaļš teksts un apmale, mapes ikona), "+ Jauna veidne" – galvenā poga pamatkrāsā (#297785). Adresātu grupu kartītes ir kompaktas un neitrālas (baltas, ar plānu pelēku apmali, tumši pelēks teksts, ikona pelēkā aplī, mazāks skaitlis); aktīvajai kartītei – tirkīzzaļš teksts un ikona, 3 px tirkīzzaļa apakšlīnija un ļoti gaišs tirkīzzaļš fons.


1. **Adresāts.** Trīs kartītes ar veidņu skaitu: "Fiziskām personām" (atvērta pēc noklusējuma), "Juridiskām personām" un "Cita komunikācija" (jaukta komunikācija, piem., viena ziņa visiem). Jauktās komunikācijas veidnēm adresāts ir "Visi (jaukta komunikācija)", un tajās lieto lauku `{adresāts}`: uzņēmumam tas ir nosaukums, fiziskai personai – vārds. Šādu veidni var sūtīt reizē gan fiziskām, gan juridiskām personām.
2. **Kategorija.** Katrā cilnē ir četri bloki: "Uzaicinājumi", "Atgādinājumi", "Informatīvie ziņojumi" un "Citi". Katram blokam ir veidņu skaits un poga "+ Pievienot veidni".

Bloku sakļaušana:
- **Pēc noklusējuma visi bloki ir sakļauti**, atverot lapu "Veidnes" vai pārslēdzot adresātu grupu. Redzams tikai virsraksts, veidņu skaits un poga "+ Pievienot veidni".
- Uzklikšķinot uz bloka virsraksta, tas izvēršas, vēlreiz uzklikšķinot – sakļaujas. Bultiņa rāda stāvokli.
- Saite **"Izvērst visus / Sakļaut visus"** blakus meklēšanas laukam izvērš vai sakļauj visus aktīvās grupas blokus.
- Meklējot automātiski izvēršas bloki ar rezultātiem. Notīrot meklēšanu, visi bloki atkal ir sakļauti.
- Pēc veidnes pievienošanas vai rediģēšanas izvēršas bloks, kurā tā atrodas.

Papildus:
- **Lauki veidnē.** Katrai veidnei ir lauki "Adresāts" (Iedzīvotāju statistika / Uzņēmumu statistika / Visi) un "Kategorija". Ja veidni pievieno no konkrēta bloka, abi lauki jau ir aizpildīti.
- **Meklēšana.** Meklēšanas lauks filtrē aktīvās cilnes veidnes pēc nosaukuma un temata.
- **Sagatavošana.** Veidņu izvēlne ir sagrupēta pēc adresāta un kategorijas. Ja atzīmētie respondenti neatbilst veidnes adresātam, sistēma par to brīdina, un ar vienu klikšķi var atlasīt tikai atbilstošos.

## Vēstuļu veidnes

Veidnes var būt divu veidu:

- **E-pasta saturs.** Vēstule ir pats ziņojuma teksts ar noformējumu: virsraksti, treknraksts, krāsas, līdzināšana, saraksti, saites, attēli un pogas.
- **Vēstule pielikumā.** Galvenā vēstule ir pielikumā, bet ziņojumā ir tikai īss pavadteksts. Pielikums var būt dokuments no pielikumu bibliotēkas (PDF vai DOCX) vai dokuments ar laukiem, kas katram adresātam tiek ģenerēts kā A4 PDF (to var izdrukāt vai saglabāt kā PDF).

### Veidnes izveide un rediģēšana

Veidne atveras centrētā modālajā logā, kura platums ir apmēram puse ekrāna (900–1100 px), bet augstums – līdz 90 % ekrāna. Logā ir iekšēja ritināšana, poga × aizvēršanai un fiksētas pogas "Atcelt" / "Saglabāt" apakšā.

- **Izkārtojums.** Divas kolonnas: forma un priekšskatījums, kas, ritinot formu, paliek redzams. Ja ekrāns ir šaurāks par 900 px, kolonnas ir viena zem otras.
- **Kompakta forma.** "Adresāts" un "Kategorija" ir vienā rindā. Paskaidrojumi ir paslēpti aiz mazas **"i"** ikonas un parādās, uzbraucot ar peli vai fokusējot to.

**Vēstules veids** ir divas kompaktas pogas ar ikonu un nosaukumu. Zem izvēlētās pogas atveras apakšizvēlne; neizvēlētās pogas apakšizvēlne ir paslēpta.

- **E-pasta saturs:**
  - **"No sagataves"** atver logu ar e-pasta satura šabloniem no sadaļas "Sagataves", sagrupētiem pēc kategorijas un atlasītiem pēc izvēlētā adresāta. Logs ir tāda paša izmēra kā veidnes redaktors. Šablonu izvēlas, uzklikšķinot uz kartītes (tā tiek izcelta), un apstiprina ar fiksēto pogu **"Izvēlēties"** apakšā (vai ar dubultklikšķi); "Atcelt" aizver logu bez izmaiņām. Izvēlētā šablona teksts un formatējums ielādējas redaktorā, un to var brīvi labot. Šabloniem nav temata, tāpēc temata lauki (e-pasta un eAdreses) netiek aizpildīti – tematu norāda veidnē vai kampaņā. Kartītēs temata nav, redzams tikai versiju stāvoklis. Ja šablonam ir eAdreses versija, tās teksts tiek ielādēts eAdreses cilnē.
  - **"Veidot jaunu"** atver redaktoru tikai ar uzrunu un parakstu.
- **Vēstule pielikumā:**
  - **"No sagatavēm"** atver logu ar pielikumu sagatavēm (meklēšana, filtri, PDF priekšskatījums). Izvēlētais dokuments kļūst par veidnes galveno vēstuli.
  - **"Augšupielādēt failu"** – PDF vai DOCX, līdz 1 MB. Fails tiek pievienots arī pielikumu sagatavēm.
  - Saite **"vai veidot dokumentu redaktorā ar laukiem"** saglabā iespēju veidot ģenerētu PDF dokumentu ar laukiem.
  - Izvēlētais dokuments redzams kartītē ar pogām "Priekšskatīt", "Nomainīt" un "Noņemt". Zem tās ir pavadteksta redaktors ar pavadteksta sagatavēm.

Ja pēc satura ievadīšanas nomaina vēstules veidu, sistēma brīdina: "Mainot vēstules veidu, ievadītais saturs var tikt zaudēts. Turpināt?".

**Atsevišķs saturs e-pastam un eAdresei.** Zem kopīgajiem laukiem (nosaukums, adresāts / statistikas joma, kategorija, vēstules veids) ir cilnes **"✉ E-pasts"** un **"🏛 eAdrese"**; pie katras – stāvokļa ikona ✓ (aizpildīts) / ⚠ (nav aizpildīts). Tas pats redaktors ir arī kampaņas solī "Saturs" ("Noformēt saturu", "Pielāgot šai kampaņai").
- **E-pasts:** e-pasta temats un pilns satura redaktors (formatēšana, attēli, pogas, lauki, pārskatu tabula).
- **eAdrese:** eAdreses ziņas temats un vienkārša teksta lauks (tikai teksts, rindkopas – atdala ar tukšu rindu, un lauki; bez krāsām, attēliem un pogām). Poga **"Pārņemt no e-pasta teksta"** nokopē e-pasta saturu bez noformējuma (saites – teksts ar adresi, pogas – "Teksts: saite", pārskatu tabula – lauks `{pārskatu_tabula}`, attēli netiek pārņemti; ja temats tukšs – arī e-pasta temats); ja eAdreses teksts jau ir, pirms pārrakstīšanas jautā apstiprinājumu.
- Vēstules veidam "Vēstule pielikumā" pielikuma dokuments ir kopīgs, katrai cilnei – savs pavadteksts.
- **Priekšskatījuma pārslēgs "E-pasts / eAdrese"** ir sinhronizēts ar aktīvo cilni (pārslēdzot vienu, mainās otrs); eAdreses priekšskatījums rāda vienkāršu tekstu, kā to redzēs saņēmējs.
- **Saglabājot** jābūt aizpildītai vismaz vienai versijai (temats un teksts); daļēji aizpildīta versija – kļūda. Ja otras versijas nav, redzams brīdinājums "Nav eAdreses versijas – eAdresē tiks nosūtīts e-pasta teksts bez noformējuma" (vai "Nav e-pasta versijas – e-pastā tiks nosūtīts eAdreses teksts"), un veidnes kartītē un veidņu izvēlē – birka **"Tikai e-pasts"** / **"Tikai eAdrese"**.
- **Testa dati:** testa veidnēm ir arī eAdreses versija (vienkāršs teksts no e-pasta satura); "Pateicība par dalību" (t4) un "Pateicība par datu iesniegšanu" (t11) – tikai e-pasta versija (brīdinājumu demonstrācijai).

**Pielikumi (neobligāti)** ir sakļaujama sadaļa zem abām cilnēm (pēc noklusējuma sakļauta) – pielikumi ir kopīgi e-pastam un eAdresei. Ar pogu "+ Pievienot pielikumu" var izvēlēties failu no sagatavēm vai no datora.

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

Rīkjosla ir sagrupēta šādi: teksta stils | B, I, U, teksta krāsa, Notīrīt | līdzināšana | saraksti | saite, attēls, poga | **+ Ievietot lauku…** (mainīgie un pārskatu tabulas bloks). Rīkjosla ir kompakta: veidnes redaktorā tā ietilpst divās rindās – otrajā rindā ir saraksti, saite, attēls, poga un "+ Ievietot lauku…"; platākā redaktorā – vienā rindā. Pogas "Nosacījums" vairs nav.

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
- **Bez temata.** E-pasta satura šablonā ir tikai nosaukums, kategorija, adresātu grupa un saturs (cilnes "E-pasts" un "eAdrese"). Lauku "E-pasta temats" un "eAdreses ziņas temats" nav ne izveides un rediģēšanas logā, ne sagatavju sarakstā; priekšskatījumā temata rindā ir pelēks vietturis **"Temats tiek norādīts veidnē"**. Meklēšana ir pēc nosaukuma vai teksta. Esošo (arī agrāk saglabāto) sagatavju un to versiju temata vērtības ir izdzēstas.
- **E-pasta satura šablonu versijas.** Saglabājot šablonu ar mainītu tekstu, iepriekšējais variants tiek saglabāts kā versija (pēdējās 5). Kartītē redzams versijas numurs un pēdējā labojuma datums; labošanas logā ir iepriekšējo versiju saraksts ar pogu "Ielādēt redaktorā".
- **E-pasta un eAdreses versijas.** Katram e-pasta satura šablonam var būt divas satura versijas: **✉ E-pasts** (formatēts teksts) un **🏛 eAdrese** (vienkāršs teksts), tāpat kā veidnēm. Pielikumu sagatavēm versiju nav.
  - Kartītē redzams stāvoklis: **"✓ E-pasts un eAdrese"**, ja ir abas versijas, vai birka **"Tikai e-pasts"** / **"Tikai eAdrese"**. Meklēšana ņem vērā arī eAdreses tekstu.
  - Labošanas logā ir cilnes "✉ E-pasts" un "🏛 eAdrese" (ar aizpildījuma statusu), eAdreses cilnē – poga **"Pārņemt no e-pasta teksta"** (ja eAdreses teksts jau ir, vispirms prasa apstiprinājumu). Labajā pusē ir priekšskatījums ar pārslēgu E-pasts / eAdrese, kas ir sinhronizēts ar aktīvo cilni (abos virzienos). Saglabājot jābūt aizpildītai vismaz vienai versijai (e-pasta saturs vai eAdreses teksts). Ja eAdreses versijas nav, pēc saglabāšanas parādās atgādinājums. Iepriekšējās versijas saglabā un ielādē abas satura versijas.
  - Veidojot jaunu veidni no šablona ("Jauna veidne") vai ielādējot saturu ar "No sagataves" (veidnes redaktorā un kampaņas solī "Noformēt saturu"), tiek pārņemtas abas versijas; temata lauks paliek tukšs, un tas jāaizpilda veidnē / kampaņā.
  - Testa datos visiem šabloniem ir eAdreses versija, izņemot "Pateicība par dalību" un "Atgādinājums par termiņu (visiem)" – tiem ir tikai e-pasta versija (demonstrācijai).
- **Izmantojums.** Šablona kartītē redzams, kurās veidnēs tas izmantots ("Izmantots veidnēs: …"). Veidne atceras, no kura šablona tā izveidota; sākotnējie šabloni ir saistīti ar e-pasta veidnēm, no kurām ņemts to teksts. Šablona labojumi esošās veidnes nemaina.

Abās grupās sagataves ir sakārtotas pēc adresāta (fiziskās / juridiskās personas / visi) un kategorijas (Uzaicinājumi, Atgādinājumi, Informatīvie ziņojumi, Citi). Ir meklēšana, filtri un poga **"+ Pievienot sagatavi"**.

Pielikumu sagatavju funkcijas:
- **Iepriekš ielādētie paraugi.** Tie ir atzīmēti ar birku "Sagatave", un faili glabājas mapē `pielikumi/` (sīkbildes – `pielikumi/sikbildes/`). Paraugus nevar labot vai dzēst.
- **Apraksts.** Katram pielikumam ir nosaukums, īss apraksts, kategorija un adresāti.
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
  - **apsekojuma dati vēstulei** (no Metadatu pārvaldības; prototipā – izdomāti testa dati): e-anketas saite, apsekojuma e-pasts un tīmekļvietne. Tie glabājas pie katra pārskata / apsekojuma un kampaņā tiek ņemti automātiski;
  - **Iesniegšanas statusi** ir tikai lasāmi; prototipā tie ir testa dati.
  - **Testa apsekojumi / pārskati (6):**

    | Kods | Nosaukums | Statistikas joma | Periodiskums | Testa respondenti |
    |---|---|---|---|---|
    | 1-DSA | Darbaspēka apsekojums | Iedzīvotāju statistika | Ceturksnis | 9 (fiziskās personas; reize 1.–4.) |
    | 1-C | Ceļotāju apsekojums | Iedzīvotāju statistika | Mēnesis | 9 (fiziskās personas; cikls 1.–2.) |
    | 1-MBA | Mājsaimniecību budžeta apsekojums | Iedzīvotāju statistika | Gads | 8 (fiziskās personas) |
    | 1-apgrozījums | Pārskats par apgrozījumu | Uzņēmumu statistika | Mēnesis | 13 (juridiskās personas) |
    | 1-Rūpniecība | Pārskats par rūpniecību | Uzņēmumu statistika | Gads | 11 (juridiskās personas) |
    | 2-darbs | Pārskats par darbu | Uzņēmumu statistika | Ceturksnis | 13 (juridiskās personas) |

    Visiem uzņēmumiem ir vismaz divi pārskati (piem., 1-apgrozījums un 2-darbs), lai var demonstrēt apkopotu vēstuli ar pārskatu tabulu. Uzņēmumu pārskatiem ir pienākumi katrā periodā no 2024. gada līdz tekošajam (1-apgrozījums – 2024M01 … tekošais mēnesis, piem., 2026M10; 2-darbs – 2024C1 … pēdējais pabeigtais ceturksnis, piem., 2026C3; 1-Rūpniecība – 2024, 2025, 2026); papildu periodos – pa diviem respondentiem, kuriem ir attiecīgais pārskats, pagājušie – iesniegti. Agrāk pārlūkā saglabātiem datiem pienākumi vienreiz tiek izveidoti no jauna (attiecībā pret šodienu). Agrākie testa apsekojumi (Laika izlietojuma, Iedzīvotāju ienākumu un dzīves apstākļu, IKT lietošanas, Uzņēmumu inovāciju apsekojums, degvielas cenu, vakanču, investīciju un gada darbības pārskati) ir dzēsti; melnrakstos, ieplānotajās kampaņās un saglabātajos filtros tie pārsaistīti uz esošajiem pārskatiem, bet pārskati, pienākumi un testa vēsture pārlūkā tiek izveidoti no jauna. Pielikumu sagataves (PDF vēstules, piem., par IKT apsekojumu) ir materiāli un netiek mainītas.
  - **Apsekojumu kodi un nosaukumi** visur rādīti vienādi – "1-DSA Darbaspēka apsekojums" (apsekojumu izvēlnēs, birkās, respondenta kartītē, pārskatu tabulā vēstulē, mainīgo vērtībās), bet birkās īsi ar perioda kodu – "1-DSA · 2026C3". Kodi redzami arī sūtīšanas vēsturē (kampaņas šūnā – vēstules apsekojumu kodi) un atskaitēs (kampaņu tabulā). Agrāk pārlūkā saglabātajiem datiem kodi tiek atjaunināti.
  - **Reize / cikls:** iedzīvotāju respondentiem katram periodam ir pazīme "reize" (Darbaspēka apsekojums, 1–4) vai "cikls" (Ceļotāju apsekojums, tikai 1. un 2. cikls); testa datos piešķirtas pēc kārtas.
  - **Periodu kodi** (vienots formāts): ceturksnis 2026C1–2026C4, mēnesis 2026M01–2026M12, gads 2026; papildus – pusgads 2026P1, nedēļa 2026N40, intervēšanas vilnis 2026V4. Birkās un tabulās kods tiek rādīts kopā ar apsekojuma kodu, piem., "1-DSA · 2026C3", "1-C · 2026M09".
  - Katram apsekojumam / pārskatam ir statistikas joma: iedzīvotāju statistika (respondenti – tikai fiziskās personas) vai uzņēmumu statistika (respondenti – tikai juridiskās personas). Kampaņas tvērumā jomai "Uzņēmumu statistika" tiek piedāvāti tikai uzņēmumu pārskati, "Iedzīvotāju statistika" – tikai iedzīvotāju apsekojumi, "Visi" – visi, sagrupēti pa jomām.
- **Testa dati:**
  - 18 uzņēmumu vienības un 3 uzņēmumu pārskati (mēnesis, gads, ceturksnis);
  - katram respondentam: NMK, NMK/PS (fiziskām personām nav), UUK, atbildīgais operators (trīs operatori – dažādiem respondentiem dažādi) un statusa šifrs;
  - vairākas vienības vienā NMK: SIA “Ziemeļblāzmas Koks” (galvenā vienība, Valmieras ražotne, Rēzeknes noliktava) un AS “Baltijas Stikls” (galvenā vienība, Liepājas rūpnīca);
  - tekošā gada gada pārskati (1-Rūpniecība dažiem uzņēmumiem, 1-MBA dažām mājsaimniecībām), lai "Gada pārskati" ir aktīva arī tekošajā gadā;
  - jau nosūtīti uzaicinājumi: "Darbaspēka apsekojums – uzaicinājums" un "Pārskats par darbu – uzaicinājums" (daļai uzņēmumu) – lai var pārbaudīt "Izslēgt jau uzaicinātos";
  - 10 fiziskās personas trīs apsekojumos: Ceturksnis (1-DSA), Mēnesis (1-C), Gads (1-MBA);
  - termiņi ir gan pagātnē, gan nākotnē, un statusi ir jaukti;
  - diviem pārskatiem termiņa noteikums ir izvēlēts tā, lai pēdējā perioda termiņš būtu tieši pēc 5 un 7 dienām no šodienas (1-Rūpniecība un 2-darbs);
  - testa dati tiek aprēķināti attiecībā pret šodienu, kad tie tiek izveidoti vai atjaunoti ("Atjaunot sākotnējos testa datus").

**Respondenta kartīte.** Uzklikšķinot uz respondenta nosaukuma kampaņā (atlases tabulā, adrešu solī) vai vēsturē, no labās puses atveras sānu panelis. Tajā ir:
- pamatdati (nosaukums, tips, reģ. Nr., kontaktpersona, pazīmes);
- adreses: eAdrese, E-pasts 1 un E-pasts 2 (sinhronizētas, tikai lasāmas, ar pogu "Sinhronizēt") un E-pasts 3 (manuāli, rediģējams, ar formāta pārbaudi);
- pārskati un periodi (tikai lasāmi): pārskats, periods, termiņš un statuss;
- komunikācijas vēsture: kampaņas, kurās respondents bijis, vēstules, datumi un piegādes statusi (ar pogu "Skatīt");
- ja kartīte atvērta no kampaņas redaktora, arī norāde, vai respondents ir iekļauts šajā kampaņā.

### Respondentu adreses un adrešu prioritāte

**Adreses.** Katram respondentam ir četras adreses:
- **eAdrese** (juridiskām personām – uzņēmuma eAdrese), **E-pasts 1** un **E-pasts 2**. Tās ir sinhronizētas no Respondentu pārvaldības.
- **E-pasts 3 (manuāli)**, ko darbinieks var ievadīt vai labot komunikācijas modulī.

**Respondenta kartītē** redzamas:
- sinhronizētās adreses kā tikai lasāmas, ar datumu "Sinhronizēts: …" (vai "Nav sinhronizēts") un pogu "Sinhronizēt" (simulācija);
- lauku "E-pasts 3 (manuāli)" ar e-pasta formāta pārbaudi un pogu "Saglabāt", kā arī informāciju, kas un kad to ievadīja.

**Testa dati** satur dažādus gadījumus:
- dažiem respondentiem nav eAdreses;
- daudziem ir tikai viens e-pasts, dažiem aizpildītas visas adreses;
- vienam respondentam nav nevienas adreses;
- adrešu pārbaudei – katrs kļūdas veids vismaz vienreiz: automātiski labojamas pārrakstīšanās (`gmial.com`, `gmail.gmeil`, `gmail.con`, `inbox.lvv`, `inboks.lv`, `outlok.com`), atstarpes un lielie burti, punkts beigās, eAdrese ar mazajiem burtiem; jālabo manuāli – nav "@", vairāki "@", atstarpe, komats, semikols, nav vārda pirms "@", nav domēna, nepilnīgs domēns, dubultpunkts, punkts pirms "@", dublikāts, eAdrese neatbilst formātam, nederīga pēc nepiegādes; vienai uzņēmuma vienībai (SIA "Ziemeļblāzmas Koks" – Valmieras ražotne) nav nevienas adreses.

**Prioritāte kampaņā.** Kampaņas solī "Pamatdati" zem kampaņas tvēruma kartītēm ir kartīte **"Adrešu prioritāte"** (virsraksts ar ikonu) ar trim izvēlnēm vienā rindā: [1. … ▾] → [2. … ▾] → [3. … ▾].
- Vērtības: eAdrese, E-pasts 1, E-pasts 2, E-pasts 3 (manuāli). 1. prioritāte ir obligāta, 2. un 3. var būt tukšas ("— nav —"); vienu adreses veidu nevar izvēlēties divreiz.
- Noklusējums: uzņēmumu statistikā (un jomai "Visi") eAdrese → E-pasts 1 → E-pasts 2; iedzīvotāju statistikā E-pasts 1 → E-pasts 2. Mainot statistikas jomu, noklusējums nomainās, ja lietotājs prioritāti nav mainījis manuāli.
- Solī "Respondenti" prioritāte redzama tikai lasāmā veidā ("Sūtīšanas secība: …" ar saiti "Mainīt"), un pēc tās tiek kārtotas tabulas adrešu kolonnas, noteikta primārā adrese un skaits pa kanāliem; kvalitātes pārbaude ņem vērā tikai prioritātē iekļautās adreses.
- Ja adrešu prioritātē ir kanāls, kuram vēstules saturam nav versijas (piem., eAdrese, bet veidnei ir tikai e-pasta versija), solī "Saturs" redzams brīdinājums ar saiti **"Labot saturu"**.
- Respondentiem bez adreses pēc prioritātes E-pastu 3 var pievienot solī "Respondenti" (izvērstā rindā – "Pievienot e-pastu").

**Sūtīšanas simulācija** (specifikācija F9, F10, F16, F17). Vēstules apstrādā pēc adrešu prioritātes un **klasifikācijas noteikumiem** (sk. sadaļu "Sūtīšanas statusi un kļūdu apstrāde"). Iznākumi tiek simulēti deterministiski (pēc adreses un sūtījuma), un statuss tiek atvasināts no mēģinājumu laikiem – procesā esošie statusi ar laiku mainās (lapā – ik pēc 30 s):
- **eAdrese:** Nosūtīta → Pieņemts DIV → (pēc 2 min) Notiek piegāde → (pēc 5 min) Saņēmēja pieņemts = Piegādāta. Ja piegāde nav apstiprināta 48 h laikā – pāreja uz e-pastu.
- **E-pasts:** Nosūtīta (nodota e-pasta serverim) nav galīgs statuss: ja 72 h laikā nav saņemts NDR, vēstule kļūst Piegādāta; ja saņemts NDR – statuss mainās atbilstoši klasifikācijai.
- **Zināmās kļūdas** (redzamas arī priekšskatījumā): e-adreses `_DEFAULT@00000000112` un `_PRIVATE@00000000222` – "Nav publiskās atslēgas šifrēšanai" (sūta uz e-pastu, respondents tiek informēts); e-pasti uz `nepiegadajams.example` – "Adrese vai domēns neeksistē" (pastāvīga kļūda); e-pasti uz `surogatfiltrs.example` – "Bloķēts kā spams" (sūtītāja puse).
- **Neveiksmīga:** ja visas adreses ir izsmeltas, vēstule ir neveiksmīga un nodota manuālai pārbaudei.
- Adreses, kas pēc pastāvīgas kļūdas atzīmētas kā **nederīgas**, nākamajās kampaņās netiek izmantotas (kamēr adrese nav mainīta).
- Testa datos ir arī nesen (pirms 1 min no pirmās ielādes) nosūtīta kampaņa "Informācija par datu iesniegšanas kalendāru" ar dažādiem iznākumiem un procesā esošiem statusiem.

Priekšskatījumā redzama prioritāšu secība un paredzamais rezultāts (zināmās kļūdas), bet nosūtītajā vēstulē – katrs faktiskais mēģinājums.

### Pārskatu tabula vēstulē – `{pārskatu_tabula}`

- **Ievietošana.** Veidnes redaktora izvēlnē "+ Ievietot lauku" ir bloks **"Pārskatu tabula"**. To ievietojot, var izvēlēties:
  - kolonnas: Pārskats, Periods, Termiņš, Statuss;
  - rindas: "Visi atlasītie pienākumi" (uzaicinājumiem) vai "Tikai neiesniegtie" (atgādinājumiem).

  Uzklikšķinot uz bloka redaktorā, iestatījumus var mainīt vai bloku dzēst.
- **Atlase kampaņā.** Kampaņas 2. solī "Respondenti" pienākumus atlasa pēc kampaņas veida, pārskata un perioda (skatīt "Komunikācijas kampaņa").
- **Ģenerēšana.** Tabula tiek izveidota katram respondentam no viņa pienākumiem, kas atbilst šai atlasei. Kavētie termiņi ir izcelti sarkanā krāsā. E-adreses ziņojumā tabula tiek pārvērsta tekstā.
- **Esošās veidnes.** Tabula pievienota uzaicinājuma ("Uzaicinājums sniegt datus apsekojumā (vēstule pielikumā)" – PDF dokumentā) un atgādinājuma ("Atgādinājums par datu iesniegšanas termiņu") veidnēm juridiskām personām.

## Komunikācijas kampaņa

Jaunu kampaņu sagatavo piecos soļos: Pamatdati, Respondenti, Saturs, Paraksts, Pārbaude (specifikācija F1–F11). Atsevišķa soļa "Adreses" vairs nav – adrešu prioritāte ir solī "Pamatdati"; agrāk saglabātajos melnrakstos solis "Adreses" atveras kā "Pamatdati", bet "Pārbaude" – kā 5. solis.
- Augšā ir **progresa josla**: pabeigtie soļi ir atzīmēti ar ķeksīti, soļi ar trūkstošu informāciju – ar "!".
- Starp soļiem var pārvietoties brīvi: ar progresa joslu vai pogām "← Atpakaļ" / "Tālāk →".
- Pogu **"Saglabāt melnrakstu"** var izmantot jebkurā solī. Kampaņa tiek saglabāta arī automātiski.

1. **Pamatdati** (F1):
   - **statistikas joma** (Iedzīvotāju statistika / Uzņēmumu statistika / Visi; agrāk – lauks "Adresāts" ar vērtībām Fiziskās personas / Juridiskās personas / Visi) un **kampaņas nosaukums** (pēc noklusējuma "Kampaņa Nr. N"). Joma nosaka kampaņas tvērumu un piedāvātās veidnes: "Iedzīvotāju statistika" – veidnes ar adresātu "Fiziskā persona" un "Visi (jaukta komunikācija)", "Uzņēmumu statistika" – "Juridiskā persona" un "Visi", "Visi" – visas veidnes (veidņu izvēlē pie katras veidnes redzams adresāts). Saglabājot kampaņas saturu kā veidni ("Saglabāt arī kā veidni"), adresāts tiek aizpildīts automātiski pēc kampaņas statistikas jomas (iedzīvotāju → Fiziskā persona, uzņēmumu → Juridiskā persona, visi → Visi). Kampaņās (pamatdati, veidņu izvēle, satura redaktors, kopsavilkums, 2. soļa tvēruma josla) joma redzama ar šiem nosaukumiem;
   - **komunikācijas veids**: četras kompaktas pogas vienā rindā (ikona un nosaukums) – Uzaicinājums / Atgādinājums / Informatīvs ziņojums / Cits. Pēc veida tiek filtrēta veidņu izvēle 3. solī;
   - **atgādinājuma iestatījumi** (tikai veidam "Atgādinājums") – kompakta rinda tieši zem veida pogām: pārslēgs "Pirms termiņa / Pēc termiņa (nokavēts)" kreisajā pusē un tajā pašā rindā pa labi lauks "Dienas līdz termiņam [N]" vai "Kavēts vismaz [N] dienas" (neobligāts). Blakus laukam mazā tekstā – aprēķinātais termiņš, piem., "Termiņš: 11.10.2026" (pirms termiņa: nosūtīšanas datums + N dienas, kur nosūtīšanas datums – šodiena vai ieplānotais datums) vai "Termiņš līdz: …" (pēc termiņa). Kampaņas tvēruma kartītes (apsekojumu saraksts) un kopsavilkums "Atlasīti X respondenti" jau 1. solī ņem vērā tikai neiesniegtos pārskatus ar atbilstošo termiņu;
   - **nosūtīšanas datums un laiks**: kompakts pārslēgs "Nosūtīt tūlīt / Ieplānot" kreisajā pusē. Izvēloties "Ieplānot", tajā pašā rindā pa labi parādās kompakti lauki bez virsrakstiem – datums (vietturis "DD.MM.GGGG", kalendāra ikona atver datuma izvēli) un laiks (vietturis "HH:MM", pulksteņa ikona, ieteikumi ik pēc 30 minūtēm). "Nosūtīt tūlīt" gadījumā lauki ir paslēpti:
     - datums tiek rādīts formātā DD.MM.GGGG, laiks – 24 stundu formātā (piem., 09:00). Rakstot punkti un kols tiek ievietoti automātiski;
     - noklusējums – rītdiena plkst. 09:00;
     - pagātnes datumu un laiku nevar izvēlēties: kalendārā tie nav pieejami, šodienai laika ieteikumos ir tikai nākotnes laiki, bet ievadītam pagātnes vai nederīgam datumam vai laikam tiek parādīta kļūda, un kampaņu nevar ieplānot;
     - uz šauriem ekrāniem datuma un laika lauki pārceļas zem pārslēga;
   - **"Kampaņas tvērums"** – skaidrojums ir "i" ikonas padomā blakus virsrakstam (saglabāto filtru – izvēlnes "Mani filtri" un pogu "Saglabāt filtru" / "Notīrīt filtrus" – vairs nav, arī agrāk pārlūkā saglabātie filtri tiek dzēsti). Kartītes atkarīgas no statistikas jomas:
     - **Uzņēmumu statistika:** trīs vienāda platuma un augstuma kartītes vienā rindā (zem 1000 px – viena zem otras) – "Pēc perioda", "Pēc apsekojuma", "Pēc respondenta" (aprakstītas zemāk). Atlase ir visu kartīšu kritēriju krustpunkts;
     - **Iedzīvotāju statistika:** tikai kartīte **"Pēc apsekojuma"** visā tvēruma bloka platumā. Lauks "Apsekojums" ir atsevišķā rindā, zem tā vienā rindā blakus, vienāda platuma – "Gads" → "Periods" → "Cikls" (zem 700 px – viens zem otra):
       1. **"Apsekojums"** (obligāts) – izkrītošā izvēlne ar iedzīvotāju apsekojumiem, piem., "1-DSA Darbaspēka apsekojums", "1-C Ceļotāju apsekojums";
       2. **"Gads"** (neobligāts) – gadi, kuros apsekojumam ir periodi, dilstošā secībā; pirmā vērtība "Visi gadi";
       3. **"Periods"** (obligāts) – pakārtots gadam: bez gada – visi apsekojuma periodi, ar gadu – tikai šī gada periodi. Periodi dilstošā secībā (augšā jaunākais, piem., 2026C3, 2026C2… vai 2026M09, 2026M08…); prototipā – testa dati no 2024. gada līdz tekošajam (pēdējam noslēgtajam) periodam. Noklusējumā izvēlēts jaunākais periods;
       4. **"Cikls"** (nosaukums vienmēr "Cikls") – izkrītošā izvēlne ar vairākizvēli: izvēles rūtiņas izvēlnes iekšpusē (izvēlne paliek atvērta, atzīmējot vairākas), izvēlētās vērtības redzamas laukā kā birkas. Vērtības atkarīgas no apsekojuma: 1-DSA – 1.–4. reize, 1-C – 1. un 2. cikls; 1-MBA (un bez apsekojuma) – izvēlne tukša un neaktīva. Noklusējumā izvēlētas visas pieejamās vērtības.
       - Kamēr apsekojums nav izvēlēts, pārējie lauki ir neaktīvi. Mainot apsekojumu, gads, periods un reize / cikls tiek aizpildīti no jauna ar noklusējumiem. Mainot gadu, ja periods tam neatbilst, tiek izvēlēts šī gada jaunākais periods.
       - Bez apsekojuma vai perioda nevar pāriet uz nākamo soli: kļūda pie lauka parādās tikai pēc mēģinājuma iet tālāk.
       - Atlase = apsekojums + periods + atzīmētās reizes / cikli. 2. solī birkās, piem., "1-DSA · 2026C3 · 1. reize", tvēruma joslā – "Cikls: 1." (ja nav atzīmētas visas).
       - Kopsavilkuma rinda "Atlasīti X respondenti, Y pārskati/periodi" šajā jomā netiek rādīta;
     - **Visi:** tikai kartīte "Pēc apsekojuma" ar visiem apsekojumiem, sagrupētiem divās grupās "Iedzīvotāju statistika" un "Uzņēmumu statistika" (bez perioda izvēles; ja apsekojums nav izvēlēts – visi);
     - **mainot statistikas jomu**, tvēruma vērtības, kas jaunajā jomā vairs neder (citas jomas apsekojumi un to periodi; pārejot uz iedzīvotāju statistiku vai "Visi" – arī perioda un respondenta filtri), tiek notīrītas, un uz brīdi parādās paziņojums "Kampaņas tvērums notīrīts, jo mainīta statistikas joma". Atlasīto respondentu kopsavilkums pārrēķinās uzreiz.
     Uzņēmumu statistikas kartītes:
     - **Pēc perioda** – divi skaidri nodalīti līmeņi:
       - **"1. Vākšanas gads"** (augšā): gaiša josla – ļoti gaišs pamatkrāsas fons (#EEF5F6) ar plānu apmali (#CFE1E4), virsraksts "1. Vākšanas gads *" tumši tirkīzā (#1F5E69) pustreknā un zem tā pelēks teksts "Visi šī gada pārskati", labajā pusē gada izvēlne parastā baltā laukā (dilstoši – nākamais gads … 2020, noklusējumā tekošais). Obligāts. Gads nosaka pamata atlasi: visi respondenti ar jebkura periodiskuma pārskatiem šajā gadā;
       - **"2. Pārskata periods (neobligāti sašaurina)"**: rindas katram periodiskumam – "Gada pārskati", "Pusgada pārskati", "Ceturkšņa pārskati", "Mēneša pārskati", "Nedēļas pārskati". Katrā rindā kreisajā pusē slēdzis (iekļaut / neiekļaut), vidū nosaukums, labajā pusē izkrītošā vairākizvēle ar šī gada periodiem dilstošā secībā: "Visi pusgadi", 2026P2, 2026P1; "Visi ceturkšņi", 2026C4 … 2026C1; "Visi mēneši", 2026M12 … 2026M01; "Visas nedēļas", 2026N53 … 2026N01. Izvēlētie periodi redzami kā birkas ar × (var izvēlēties vairākus; atzīmējot "Visi …", izvēle tiek notīrīta). Gada pārskatiem izvēlnes nav – redzams tikai gads;
       - noklusējumā (jaunā kampaņā un pēc vākšanas gada maiņas) visas rindas ar pārskatiem ir ieslēgtas un "Visi …". Ieslēgts slēdzis ir pamatkrāsā (#297785), izslēgts – pelēks. Izslēdzot rindu, tās periodiskuma pārskati netiek atlasīti; izvēloties konkrētus periodus – tikai šie periodi. Ja izslēgtas visas rindas, tiek atlasīti visi izvēlētā gada pārskati, un zem rindām redzams "Nav izvēlēts periods – atlasīti visi gada pārskati";
       - rindas, kurām izvēlētajā gadā nav pārskatu (testa datos – pusgads un nedēļa), ir pelēkas un neaktīvas, ar tekstu "nav pārskatu";
       - **zem kartīšu rindas** vienā rindā – kopsavilkums, kas tiek atlasīts, piem., "Tiek atlasīts: 1-Rūpniecība 2026 · 2-darbs 2026C1–C4 · 1-apgrozījums 2026M01–M12" (pārskati, kuriem izvēlētajos periodos ir dati; ja izvēlēti apsekojumi – tikai tie).
     - **Pēc apsekojuma:** meklējama vairākizvēle ar apsekojumiem / pārskatiem (atbilstoši statistikas jomai). Uzņēmumu statistikā saraksts ir redzams kartītē uzreiz (nav jāklikšķina meklēšanas laukā); ja izvēlētajā gadā nav neviena pārskata, kartītē redzams "Šajā gadā nav pārskatu.", ja pārskati ir, bet neatbilst izvēlētajiem periodiem – "Izvēlētajos periodos nav pārskatu." Pie katra redzams kods, periodiskums un termiņa noteikums. Izvēlētie apsekojumi redzami kā birkas ar ×. Sarakstā var pārvietoties ar bultiņām un izvēlēties ar Enter. Saraksts ir atkarīgs no perioda izvēles: tajā ir tikai pārskati, kuru periodiskuma rinda ir ieslēgta un kuriem izvēlētajos periodos ir dati (2-darbs – ceturksnis, 1-apgrozījums – mēnesis, 1-Rūpniecība – gads). Ieslēgta rinda ar "Visi …" nozīmē jebkuru izvēlētā gada periodu; konkrēti periodi sašaurina atlasi tikai tad, ja tie izvēlēti (tukša izvēle = visi periodi). Ja jau izvēlēts apsekojums vairs neatbilst (mainot gadu, izslēdzot rindu vai mainot periodus), tas tiek noņemts, un uz brīdi parādās paziņojums. Ja izvēlēts apsekojums bez pienākumiem periodā (piem., pēc atgādinājuma iestatījumu maiņas), birka atzīmēta ar ⚠, un tā augšā ir "Visi apsekojumi" (bez ierobežojuma pēc apsekojuma).
     - **Pēc respondenta** – redzami lauki "Nosaukums" (daļējs teksts), "NMK" un **"Atbildīgais operators"** (izvēlne ar testa darbiniekiem, noklusējumā "Visi"; operators ir piesaistīts respondentam); saite **"+ Vairāk filtru"** kartītes iekšpusē izvērš pārējos laukus (kartīte tad var kļūt augstāka par pārējām). Ja slēptie lauki aizpildīti, saitē redzams skaits, piem., "+ Vairāk filtru (2 aktīvi)". Virsrakstā – visu aktīvo filtru skaits:
       - identifikatori: "NMK", "NMK/PS", "UUK" (var ievadīt vairākas vērtības, atdalot ar komatu; precīza atbilstība);
       - adreses: "E-pasts", "eAdrese" (daļējs teksts);
       - "Izslēgt pēc statusa šifra": izkrītoša vairākizvēle ar šifriem un to paskaidrojumiem (1 – Aktīva vienība, 2 – Darbība uz laiku pārtraukta, 5 – Likvidācijas procesā, 8 – Atteicies sniegt datus, q – Datu kvalitātes pārbaude, a – Adrese nav aktuāla, v – Vienība apvienota ar citu) un respondentu skaitu pie katra;
       - "Ielādēt sarakstu no faila": CSV vai TXT ar NMK vai UUK sarakstu (atdalīti ar komatu, semikolu vai jaunu rindu; galvenes rinda tiek izlaista). Atlasē paliek tikai sarakstā esošie. Pēc ielādes redzams, cik atrasti un cik nav atrasti, ar pogām "Skatīt neatrastos" un "Noņemt".
     - **Atlases opcijas** (slēdži vienā rindā; redzamas un darbojas tikai jomai "Uzņēmumu statistika", jomām "Iedzīvotāju statistika" un "Visi" – nav; pārslēdzot jomu, rinda pazūd uzreiz, un opcijas tiek izslēgtas):
       - "Izslēgt jau uzaicinātos" – neiekļauj pienākumus (un līdz ar to respondentus), par kuriem jau nosūtīts uzaicinājums (pēc nosūtīto vēstuļu pienākumu sarakstiem; neveiksmīgās vēstules netiek ņemtas vērā);
       - "Apvienot vēstules pēc NMK" – vairākas vienības ar vienu NMK saņem vienu kopīgu vēstuli: adresāts ir pirmā vienība, bet `{pārskatu_tabula}` ietver visu vienību pienākumus (pie citu vienību pienākumiem – vienības nosaukums). 2. solī pie vēstules adresāta redzams "Apvienota vēstule: N vienības (NMK …)".
     - zem kartītēm ir dzīvs kopsavilkums "Atlasīti X respondenti, Y pārskati/periodi" (apvienojot – arī apvienoto vienību skaits);
   - **vēstules dati:**
     - lauka "Nosaukums vēstulē" nav: `{apsekojums}` vēstulē aizpildās automātiski no izvēlētā apsekojuma (ja apsekojumi ir vairāki – ar respondenta apsekojumu nosaukumiem; tie redzami arī blokā `{pārskatu_tabula}`), bet vēstules tekstu definē solī "Saturs";
     - "Vēstules datums `{datums}`" un "Dokumenta Nr. `{dok_nr}`";
     - laukā nav "Sākums" un "Termiņš": `{termiņš}` tiek ņemts automātiski no pārskata un perioda datiem (respondenta tuvākais termiņš, kas nosūtīšanas dienā vēl nav pagājis; ja tāda nav – agrākais), bet `{sākums}` ir nākamā diena pēc attiecīgā perioda beigām;

   Statistikas joma nosaka, kuras veidnes tiek piedāvātas (iedzīvotāju statistika – veidnes fiziskām personām, uzņēmumu statistika – juridiskām personām, Visi – jauktai komunikācijai).
   - **"Adrešu prioritāte"** (F7) – kompakta kartīte zem kampaņas tvēruma kartītēm: [1. eAdrese ▾] → [2. E-pasts 1 ▾] → [3. E-pasts 2 ▾] (sk. "Prioritāte kampaņā").
2. **Respondenti** (F2, F11; darba grupas scenārija apakšprocesi 1.1–1.3). Divu kolonnu izkārtojums (līdzīgi solim "Pārbaude"): kreisajā pusē šaura kolonna (~260 px) ar kartītēm **"Mērķa grupa"** un **"Kontaktu kvalitāte"** viena zem otras (ritinot lapu, kolonna paliek redzama), labajā pusē kartīte **"Respondenti"** ar tabulu (aizņem atlikušo platumu). Uz ekrāniem, kas šaurāki par 1000 px, kreisā kolonna ir virs tabulas. Kartīšu stils – kā kampaņas tvēruma kartītēm 1. solī (virsraksts ar ikonu). Visi atlases iestatījumi (kampaņas tvērums, atgādinājuma veids, dienas līdz termiņam / kavējums, statusu atjaunošana, adrešu prioritāte) ir 1. solī.
   - **Mērķa grupa** (ikona – cilvēku grupa; tikai lasāma): statistikas joma, apsekojums / periods (un cikls, ja ir), piem., "Iedzīvotāju statistika · 1-DSA · 2026C3 · Cikls: 1., 2., 4. reize" (uzņēmumiem – izvēlētie pārskati un periodi; atgādinājumam – "Pirms termiņa, 5 dienas (termiņš …)"; aktīvie filtri); respondentu skaits lielā skaitlī; sadalījums pa kanāliem pēc primārās adreses (pirmā pieejamā pēc prioritātes): "eAdrese 13 · E-pasts 4 · Bez adreses 1" (kampaņā iekļautie; ja eAdrese nav prioritātē – "eAdrese 0"); sūtīšanas secība tikai lasāmā veidā – "Sūtīšanas secība: eAdrese → E-pasts 1 → E-pasts 2"; saites **"Izņēmumi (N)"** un **"Mainīt tvērumu"** (atgriež uz 1. soli, kur var mainīt arī adrešu prioritāti).
     - **Izņēmumi:** logā var pievienot izņemamos respondentus pēc NMK vai nosaukuma (katru jaunā rindā vai atdalītus ar komatu) ar iemeslu (noklusējumā "Manuāli izņemts") vai ielādēt sarakstu no faila (CSV / TXT ar NMK vai nosaukumiem); redzams, cik pievienoti un kuri nav atrasti. Logā ir izņemto saraksts ar iemeslu un saiti "Atjaunot". Izņemtie tabulā redzami pelēki ar birku **"Izņēmums"** un iemeslu (atzīme "Iekļaut" nav pieejama), un viņi vēstuli nesaņem.
   - **Kontaktu kvalitāte** (ikona – vairogs ar ķeksīti):
     - statusi kā saraksts ar krāsainu punktu un skaitli labajā pusē (uzklikšķinot filtrē tabulu, atkārtots klikšķis – filtrs noņemts; ar 0 – blāvi): **Derīgas**, **Potenciāli kļūdainas**, **Nederīgas**, **Bez adreses**;
     - zem atdalītāja viena rinda: **"Koplietojamas N · Dublikāti N · MI ieteikumi N"** (klikšķināmi, filtrē tabulu; pie "Koplietojamas" – oranža ⚠ ikona, ja kāda adrese nav izvērtēta);
     - pogas viena zem otras visā kartītes platumā: **"↻ Pārbaudīt adreses"** (~1 sekundi "Pārbauda…" ar griezošos ikonu, pēc tam atjaunojas saraksts un tabula, paziņojums ar rezultātu un pelēkā tekstā "Pārbaudīts 19:06"), **"Izņemt nederīgos (N)"** (tikai, ja tādi ir; ar apstiprinājumu) un **"Eksportēt kontaktus"**.
     - **Dublikāti:** vienam respondentam vienāda adrese E-pastā 1 un E-pastā 2 (vai E-pastā 3) – otrā tiek noņemta, šūnā tā ir pārsvītrota ar birku **"Dublikāts noņemts"** un saiti **"Atsaukt"** (pēc atsaukšanas – birka "Dublikāts (= E-pasts 1)" un saite "Noņemt").
     - **Koplietojamas adreses:** viena e-pasta adrese vairākiem kampaņas tvēruma respondentiem. Tabulā pie adreses – oranža birka **"Koplietojama (N)"**; uzklikšķinot atveras logs ar respondentiem, kuri izmanto šo adresi (lauks, NMK), un izvēli katram: **"Atstāt"**, **"Izņemt no kampaņas"** (respondents kļūst par izņēmumu ar iemeslu "Koplietojama adrese …"), **"Atzīmēt izvērtēšanai"**. Pēc saglabāšanas birkā redzama izvēle, piem., "Koplietojama (3) · Atstāt".
     - **Eksportēt kontaktus** – CSV (UTF-8, atdalītājs ";"): respondents, NMK, iekļauts, primārā adrese un kanāls, eAdrese, E-pasts 1–3, kvalitāte, piezīmes (izņēmums, dublikāts, kļūdas, MI ieteikums, koplietojama adrese un izvēle).
     - Pārbaudes: sintakse un drukas kļūdas kā līdz šim (nav "@" vai vairāki "@"; atstarpes, komati, semikoli un citi neatļauti simboli; nav vārda pirms "@", nav domēna vai tas nepilnīgs; dubultpunkti vai punkts sākumā / beigās; eAdreses formāts; adrese, kas pēc sūtīšanas vēstures atzīmēta kā nederīga); **domēna eksistences pārbaude** (simulēta: neeksistējošs domēns, piem., `jurmalas-viesnica.example`, `pasts-lv.example` → nederīga, "Domēns neeksistē"); **riskantās adreses** – lomas adreses (info@, office@, noreply@, no-reply@) un vienreizējo e-pastu domēni (piem., mailinator.com) → potenciāli kļūdainas ar birku **"Riskanta adrese"** un iemeslu (tās tiek izmantotas sūtīšanā).
     - Droši labojamās kļūdas (liekas atstarpes un punkti, lielie burti) joprojām labo automātiski (birka "Labots", sākotnējā vērtība un "Atsaukt").
     - **MI ieteikumi:** zināmas pārrakstīšanās domēnā (gmail.gmeil, gmial.com, gmail.con → gmail.com; inbox.lvv, inboks.lv → inbox.lv; outlok.com → outlook.com u. c.) vairs netiek labotas automātiski – adrese ir potenciāli kļūdaina ar birku **"✨ MI ieteikums: evija.klava@gmail.com"** un pogām **"Pieņemt"** / **"Noraidīt"**. Pieņemtā adrese tiek labota, tai ir birka **"Labots (MI)"** (sākotnējā vērtība un "Atsaukt" – uzbraucot ar peli vai uzklikšķinot); noraidītā paliek kā ievadīta ("MI ieteikums noraidīts") un tiek izmantota. Kamēr ieteikums nav izvērtēts, adrese sūtīšanā netiek izmantota.
     - **Manuāli labo:** uzklikšķinot uz adreses, to var labot turpat tabulā (Enter – saglabāt, Escape – atcelt); labojums attiecas uz šo kampaņu, pēc izvēles arī respondenta datos (simulācija). Izvērstā rindā – poga **"Pievienot e-pastu"** (E-pasts 3).
   - **Uzaicinājums, informatīvs ziņojums un cits** atlasa visus respondentus, kuriem ir pienākums kampaņas tvērumā. Termiņš un statuss netiek ņemti vērā.
   - **"Atgādinājums"** atlasa tikai neiesniegtos pienākumus: "Pirms termiņa" – ar termiņu tieši nosūtīšanas datums + N dienas; "Pēc termiņa" – ar pagājušu termiņu (neobligāti – kavēts vismaz N dienas). Ieplānotai atgādinājuma kampaņai atlase izpildes brīdī tiek pārrēķināta pēc aktuālajiem statusiem (prototipā – poga "Izpildīt tagad" kampaņu sarakstā).
   - Atlase notiek **tikai pēc kampaņas tvēruma** un atgādinājumiem – pēc iesniegšanas statusa un termiņa. Respondentu pazīmes (veids, dalības veids, iepriekšējā dalība) paliek datos, jo tās izmanto adresātu grupēšanā.
   - **Kartīte "Respondenti":** virsraksts, meklēšana, izvēlne **"Apsekojums"** un saites "Iekļaut visus" / "Izņemt visus" (attiecas uz pašlaik redzamajiem respondentiem). Tabulas augstums – līdz ~65% ekrāna ar iekšēju ritināšanu, galvene paliek redzama.
     - Kolonnas: **Respondents**, adrešu kolonnas **adrešu prioritātes secībā** ar mazu numuru virsrakstā (piem., "eAdrese 1 | E-pasts 1 2 | E-pasts 2 3" vai "E-pasts 1 1 | E-pasts 2 2"), **Citas adreses** (pelēki – adrešu veidi, kas nav prioritātē; kolonna redzama, ja tādas adreses ir), **Kvalitāte**, **Apsekojumi / periodi**.
     - **Primārā adrese** – pirmā pieejamā pēc adrešu prioritātes – atzīmēta ar birku **"Primārā"**; pārējās izmantojamās adreses ir pelēkas (alternatīvās). Ja primārā ir E-pasts 3, kas nav prioritātē (izmanto, ja citu adrešu nav), birka "Primārā" un adrese redzama zem respondenta vārda.
     - Kolonnā **"Kvalitāte"** – krāsains aplītis un īss teksts: Derīga (zaļš), Pot. kļūdaina (oranžs), Nederīga (sarkans), Bez adreses (pelēks). Respondenta kvalitāte ir sliktākā no viņa adrešu prioritātē iekļautajām adresēm (noņemtie dublikāti netiek ņemti vērā).
     - Adrešu šūnās – pārbaudes rezultāts un birkas ("Labots", "Labots (MI)", "Dublikāts noņemts", "Riskanta adrese", "MI ieteikums", "Koplietojama"); kļūdainajām – sarkans teksts ar īsu iemeslu; tukšajām – pelēks "—". Rindām ar kļūdām pie vārda – oranža ikona.
     - Kolonnā "Apsekojumi / periodi" – birkas ar apsekojuma un perioda kodu un ciklu / reizi; izvēršot rindu – pilna informācija par respondentu, visas adreses un pienākumu tabula.
   - **Kartītes "Respondenti" apakšā** – kopsavilkums "**X** gatavi · **Y** jāpārskata" (jāpārskata – adrešu kvalitāte nav "Derīga" vai ir neizvērtēta koplietojama adrese) un galvenā poga **"Apstiprināt atlasi un turpināt"** (navigācijas joslā šajā solī ir tikai "← Atpakaļ" un "Saglabāt melnrakstu"); ja ir neizvērtētas koplietojamas adreses vai respondenti ar nederīgām adresēm, pirms turpināšanas atveras brīdinājums ar to sarakstu un izvēli **"Pārskatīt"** (tabula tiek filtrēta) / **"Turpināt"**.
   - Labojumi, MI izvēles, dublikātu atsaukšana, koplietojamo adrešu izvērtējums un izņēmumi tiek saglabāti kampaņas melnrakstā; nosūtīšanā tiek izmantotas labotās adreses (adreses ar kļūdām, noņemtie dublikāti un neizvērtēti MI ieteikumi – netiek).
   - **Testa dati** (gadījumi katrai situācijai): dublikāts – Sergejs Petrovs, AS "Daugavkrasta Piens"; koplietojama adrese – `majas.dators@pasts.example` (Laura Kalēja, Olga Smirnova) un `birojs@gramatvedis-serviss.example` (3 uzņēmumi); lomas adreses – info@ (SIA "Mākoņu Maiznīca"), office@ (SIA "Rīgas Ritenis"); vienreizējā e-pasta domēns – Edgars Liepa; neeksistējošs domēns – Anna Bērziņa, SIA "Jūrmalas Viesnīca"; MI ieteikumi – Elīna Zvaigzne, AS "Gaujas Enerģija", SIA "Ventspils Loģistika" u. c.
   - Zem kampaņas tvēruma 1. solī ir norāde "Statusi atjaunoti …" un poga "Atjaunot statusus" (iesniegšanas statusi no Datu vākšanas pārraudzības; simulācija: daļa neiesniegto pienākumu kļūst iesniegti).
   - Ja respondentam ir atlasīti vairāki pārskati vai periodi, viņš saņem vienu vēstuli. `{pārskatu_tabula}` ietver tikai atlasītos pienākumus, bet atgādinājumā tikai neiesniegtos.
3. **Saturs.** Ir divas kartītes: "Izmantot veidni" un "Noformēt saturu".
   - **Satura logu izmērs.** Visi soļa logi – veidņu izvēle ("Izmantot veidni"), satura redaktors ("Noformēt saturu", "Pielāgot šai kampaņai") un sagatavju izvēle ("No sagataves") – ir tādi paši kā veidnes redaktors cilnē "Veidnes" ("+ Jauna veidne"), un tiem lieto to pašu modālā loga komponentu: centrēts logs virs lapas ar daļēji caurspīdīgu tumšu fonu, platums ~puse ekrāna (900–1100 px), augstums līdz 90% ekrāna, ritināšana loga iekšpusē, virsraksts augšā, × aizvēršanai un fiksētas pogas apakšā. Neviens no tiem neatveras pa visu ekrānu (izņemot ekrānus, kas šaurāki par 900 px, kur logs aizņem visu ekrānu tāpat kā veidnes redaktors).
   - **Izmantot veidni.** Atveras veidņu izvēle. Kreisajā pusē – veidņu saraksts (tikai kampaņas statistikas jomai un veidam atbilstošās veidnes, sagrupētas pēc kategorijas, ar meklēšanu), labajā pusē – izvēlētās veidnes priekšskatījums ar pirmā kampaņas adresāta datiem un pārslēgu **E-pasts / eAdrese**. Apakšā fiksētas pogas **"Atcelt"**, **"Pielāgot šai kampaņai"** un **"Izmantot kampaņā"** (aktīvas, kad veidne izvēlēta; dubultklikšķis uz veidnes – "Izmantot kampaņā"). Aizverot logu (× , "Atcelt" vai "← Atpakaļ uz kampaņu"), atgriežas solī "Saturs", kampaņas saturs nemainās, un, atverot logu vēlreiz, iepriekš izvēlētā veidne un pārslēga stāvoklis ir saglabāti. Pielāgojot atveras redaktors ar veidnes saturu. Izmaiņas attiecas tikai uz šo kampaņu, un pati veidne netiek mainīta.
   - **Noformēt saturu.** Atveras tas pats redaktors, kas veidnes izveidei, ar visām tā iespējām. Atšķirības no veidnes izveides:
     - nav lauku "Veidnes nosaukums" un "Kategorija", statistikas joma (veidnes adresāts) tiek ņemta no kampaņas;
     - virsraksts ir "Vēstules saturs: [kampaņas nosaukums]";
     - priekšskatījumā redzami kampaņā atzīmētie respondenti, starp kuriem var pārslēgties ar ← →;
     - apakšā ir pogas "Atcelt", "Saglabāt arī kā veidni" un "Izmantot kampaņā".
   - **Saglabāt arī kā veidni.** Prasa norādīt veidnes nosaukumu un kategoriju. Saturs tiek saglabāts kā jauna veidne, un kampaņa to izmanto.
   - **Kopsavilkums.** Kad saturs ir apstiprināts, solī redzams satura avots ("Veidne: [nosaukums]", "Veidne, pielāgota kampaņai" vai "Individuāls saturs"), temats un vēstules veids. Ir pogas "Labot saturu" un "Izvēlēties citu saturu".
   - **Mainīgo vērtības** – sakļaujama sadaļa zem satura izvēles (pēc noklusējuma sakļauta):
     - ja kampaņā ir viens apsekojums – tabula: mainīgais (`{e-anketa}`, `{apsekojuma_epasts}`, `{apsekojuma_vietne}`), vērtība un avots "No apsekojuma". Poga "Mainīt šai kampaņai" ļauj vērtību mainīt (Enter – saglabāt, Escape – atcelt); mainītā vērtība ir atzīmēta ar birku "Mainīts", un to var atjaunot ("Atjaunot");
     - ja kampaņā ir vairāki apsekojumi – vērtības sagrupētas izvēršamos blokos pa apsekojumiem (blokā redzams mainīto vērtību skaits), un vēstulē katram respondentam tiek izmantotas viņa apsekojuma vērtības;
     - "Tēmturi banerī" un "Sauklis zem banera" – kampaņas līmeņa lauki (sākotnēji no apsekojuma, ja tam tādi ir);
     - priekšskatījumā un nosūtītajās vēstulēs mainīgie tiek aizpildīti ar šīm vērtībām. Izmaiņas tiek saglabātas kampaņas melnrakstā.
4. **Paraksts** (F8):
   - "Nav jāparaksta" vai "Jāparaksta" (DVS NAMEJS integrācija; prototipā – simulācija);
   - ja jāparaksta – parakstīšanas veids (Secīga / Paralēla / Paka) un parakstītāji. Secīgai parakstīšanai secība ir atzīmēšanas kārtībā;
   - "Paraksts vēstulē": lauki `{parakstītājs}` un `{amats}` (arī PDF vēstules parakstā). Pēc noklusējuma tos ņem no pirmā parakstītāja vai no "Pastāvīgajām daļām", un tos var mainīt tikai šai kampaņai.
5. **Pārbaude** (F3, F5, F6):
   - **kampaņas kopsavilkums** ar saitēm "Labot" uz attiecīgo soli;
   - **priekšskatījums:** viena vēstule katram respondentam ar `{pārskatu_tabula}` (atgādinājumā tikai neiesniegtie pienākumi), pārslēgšanās starp respondentiem un pārslēgs "E-pasts / eAdrese";
   - **"Pielāgot šo vēstuli"** (F5): konkrētā respondenta vēstulei var labot tematu un tekstu, pievienot vai noņemt papildu pielikumus. Pielāgotā vēstule ir atzīmēta ar birku "Pielāgota vēstule" (arī atlases tabulā un vēsturē), un to var atjaunot uz sākotnējo;
   - **galvenā poga** atkarībā no iestatījumiem: "Ieplānot" (ieplānota kampaņa), "Nodot parakstīšanai" (jāparaksta) vai "Nosūtīt".

**Parakstīšana (simulācija).** Pēc "Nodot parakstīšanai" kampaņa ir sadaļā "Izpildē", un tās vēstulēm ir statuss "Gaida parakstu" (redzams arī sūtīšanas vēsturē). Poga "Parakstīt" (kampaņu sarakstā vai vēstures blokā) paraksta vēstules, un tās tiek nosūtītas. Ieplānotai kampaņai ar parakstu vēstules tiek nodotas parakstīšanai izpildes brīdī.

**Melnraksts.** Kampaņa, arī tās saturs, tiek automātiski saglabāta kā melnraksts, tāpēc darbu var turpināt vēlāk, arī pēc lapas pārlādes. Melnraksti redzami kampaņu sarakstā. Poga "Dzēst melnrakstu" redaktorā to dzēš. Pēc nosūtīšanas atveras cilne "Sūtīšanas vēsture" ar šīs kampaņas bloku, bet pēc plānošanas – kampaņu saraksta sadaļa "Ieplānotās".

## Sūtīšanas vēsture

Cilnē **Sūtīšanas vēsture** (specifikācija F16, F17) ir visas nosūtītās un nosūtīšanas procesā esošās vēstules.
- **Statusu pogas:** Visas · Gaida parakstu · Procesā (Rindā, Nosūtīta, Pieņemts DIV, Notiek piegāde, Atkārtots mēģinājums) · Piegādātas · Neveiksmīgas (Neveiksmīga, Sūtītāja puses kļūda, Neatpazīts) · Manuāla pārbaude (neveiksmīgās un neatpazītās, kas vēl nav izskatītas) · Administratoram (neatrisinātas sūtītāja puses kļūdas). Pie katras pogas iekavās redzams vēstuļu skaits pēc izvēlētajiem filtriem.
- Augšā poga **"Klasifikācijas noteikumi"** atver abas specifikācijas tabulas (E-pasts un E-adrese: iemesls / pašreizējais statuss → tips → automātiskā rīcība) tikai lasīšanai.
- **Filtri** (divās rindās):
  - 1. rinda: **meklēšana** (respondents vai adrese), **NMK** (viens vai vairāki, atdalot ar komatu – atlasa vēstules respondentiem ar šiem NMK), **Nosūtīšanas periods** – datuma diapazons "no – līdz" (DD.MM.GGGG, ar kalendāra pogu) un ātrās izvēles: Šodien, Pēdējās 7 dienas, Šis mēnesis, Iepriekšējais mēnesis, Šis gads, Jebkurā laikā. Ātrā izvēle aizpilda datumus; ja datumus maina manuāli, izvēlnē redzams "Norādīts periods". Nederīgam datumam vai ja "no" ir vēlāks par "līdz", zem lauka redzama kļūda;
  - 2. rinda: **Kampaņa**, **Kampaņas veids**, **Kanāls** (eAdrese / e-pasts), **Kampaņas veidotājs** (darbinieki, kuri izveidojuši kampaņas; noklusējumā "Visi"). Labajā pusē – saite **"Notīrīt filtrus"**, kas redzama tikai tad, ja kāds filtrs ir aktīvs (statusa izvēle paliek);
  - zem filtru bloka aktīvie filtri redzami kā birkas ar × katram (noņem attiecīgo filtru).
- **Rādītāju kartītes** (kopā, procesā, piegādātas, neveiksmīgas, manuāla pārbaude) un statusa pogu skaiti tiek pārrēķināti pēc izvēlētajiem filtriem.
- **Kampaņas veidotājs** tiek saglabāts katrai nosūtītajai vēstulei (jaunām kampaņām – pašreizējais lietotājs). Testa datos kampaņām piešķirti dažādi izdomāti veidotāji: Testa Darbinieks, Rūta Testa, Mārtiņš Paraudziņš, Elīna Izdomāta.
- Tabulā sākotnēji redzami 50 jaunākie ieraksti; poga "Rādīt vēl" ielādē nākamos 50.
- **Versija.** Sūtot katram respondentam tiek izmantota tā satura versija, uz kuras kanālu vēstule faktiski tiek nosūtīta – arī pēc pārejas uz nākamo adresi (piem., eAdrese bez publiskās atslēgas → e-pasts: vēsturē redzama e-pasta versija). Tabulas kanāla šūnā ir saite "E-pasta versija" / "eAdreses versija" (ja veidnei nebija attiecīgās versijas – "E-pasta teksts (bez noformējuma)"), kas atver tieši nosūtīto versiju; arī vēstules skatā ir rinda "Versija".
- **Tabula:** katrai vēstulei redzams adresāts (uzklikšķinot atveras respondenta kartīte), kampaņa, statuss (birka ar krāsu un ikonu), kanāls, adrese un nosūtīšanas laiks. Statusa šūnā redzams arī turpmākais solis (piem., "→ Manuāla pārbaude"), birka "Prombūtne līdz DD.MM.", NDR/DIV iemesli un "Atkārtoti nosūtīta".
- **Izvērstā rinda:** laika līnija ar katru soli un mēģinājumu – laiks, kanāls, adrese, statuss, NDR/DIV teksts (ar saņemšanas laiku), klasifikācija (iemesls, tips, "MI klasificēts" ar ticamību vai "DIV statuss"), automātiskā rīcība un novirzījums (sistēma, darbinieks, abi vai administrators). Nākamais plānotais mēģinājums (piem., pēc 24 h) redzams kā "Nākamais mēģinājums plānots". Laika līnijā ir arī manuālās darbības.
- **Manuāla pārbaude / izskatīšana** (statuss "Neveiksmīga" vai "Neatpazīts"): darbības **"Ievadīt jaunu adresi un sūtīt"** (adrese tiek pārbaudīta un saglabāta kā respondenta E-pasts 3; jaunais mēģinājums tiek apstrādāts pēc tiem pašiem noteikumiem), **"Atzīmēt kā izskatītu"** un **"Nodot kontaktu aktualizēšanai"** (izveido uzdevumu "Kontaktu aktualizēšana").
- **Administratoram:** saraksts ar sūtītāja puses kļūdām (laiks, adresāts, kampaņa, kanāls un adrese, klasifikācija, paziņojuma teksts) un pogu **"Atzīmēt kā atrisinātu"**. Arī izvērstajā rindā ir šī darbība.
- Kampaņām, kas gaida parakstu, virs tabulas ir poga "Parakstīt".
- **Ierakstu dzēšana.** Vēstures ierakstus var dzēst tikai tad, ja tie nosūtīti pirms vairāk nekā 2 gadiem (pēc nosūtīšanas datuma):
  - rindas dzēšanas poga ir aktīva tikai šādiem ierakstiem; jaunākiem tā ir neaktīva ar padomu "Ierakstus var dzēst tikai pēc 2 gadiem";
  - augšā ir poga **"Dzēst ierakstus, vecākus par 2 gadiem"**. Iekavās redzams dzēšamo ierakstu skaits. Pirms dzēšanas parādās apstiprinājuma logs ar ierakstu un kampaņu skaitu un robežas datumu. Ja šādu ierakstu nav, poga ir neaktīva;
  - noteikums tiek pārbaudīts arī pašā darbībā, tāpēc jaunāku ierakstu nevar izdzēst.
- Nosūtīšana prototipā ir simulēta (vēstules reāli netiek sūtītas).

### Sūtīšanas statusi un kļūdu apstrāde

Statusi ir vienoti visā prototipā (sūtīšanas vēsture, kampaņu saraksts, atskaites, respondenta kartīte, nosūtītās vēstules skats); katram statusam ir sava krāsa un ikona:
- **pamata ceļš:** Melnraksts → Gaida parakstu → Parakstīta → Nosūtīta → Piegādāta; bez paraksta: Melnraksts → Nosūtīta → Piegādāta;
- **eAdreses starpstatusi:** Pieņemts DIV → Notiek piegāde → Saņēmēja pieņemts (= Piegādāta);
- **alternatīvie:** Pagaidu kļūda → Atkārtots mēģinājums; Pastāvīga kļūda → Nākamā adrese; Neveiksmīga → Manuāla pārbaude; Sūtītāja puses kļūda → Paziņojums administratoram; Neatpazīts → Manuāla izskatīšana. Prombūtnes atbilde statusu nemaina, bet pievieno birku "Prombūtne līdz DD.MM.".

**Klasifikācijas noteikumi** (specifikācija F17) – iemesls → tips → automātiskā rīcība, kā prototipā izpildīta:
- *E-pasts:*
  - adrese vai domēns neeksistē, konts slēgts (pastāvīgs) – adrese respondenta kartītē atzīmēta kā **"Nederīga"** (pārsvītrota, ar birku), sūtīšana uz nākamo adresi, izveidots uzdevums "Kontaktu aktualizēšana" (redzams respondenta kartītē un vēstules detaļās);
  - pastkaste pilna (īslaicīgs) – atkārtoti mēģinājumi pēc 24 h un 48 h ar laika zīmogiem, tad nākamā adrese;
  - serveris nesasniedzams, ātruma limits (īslaicīgs) – atkārtojumi pēc 1, 4 un 12 h; pēc 3 reizēm – pastāvīga kļūda (nederīga adrese, nākamā adrese);
  - ziņa par lielu (saturs) – atkārtota sūtīšana bez pielikuma, ar saiti;
  - bloķēts kā spams, autentifikācijas kļūda (sūtītāja puse) – adrese netiek mainīta, ieraksts sarakstā "Administratoram";
  - prombūtnes atbilde (nav kļūda) – statuss nemainās, birka ar atgriešanās datumu;
  - "adrese mainīta", neatpazīts teksts (manuāli) – statuss "Neatpazīts", ieraksts manuālajā rindā.
- *E-adrese:* Pieņemts DIV / Notiek piegāde (starpstatuss) – gaida, pēc 48 h sūta uz e-pastu; Saņēmēja pieņemts (gala) – piegādāta; Noraidīts DIV (sūtītāja puse) – neatkārto, "Administratoram"; Saņēmēja noraidīts (pastāvīgs) – pāreja uz e-pastu, ja atkārtojas – manuāli; Nokavēta piegāde (īslaicīgs) – atkārto pēc 6 un 12 h, tad e-pasts; Nav publiskās atslēgas šifrēšanai (saņēmēja konfigurācija) – pāreja uz e-pastu, respondents tiek informēts; Adresāta pastkastīte pilna (īslaicīgs) – ja ir e-pasts, paralēli sūta uz to, citādi atkārto pēc 24 un 48 h.
- Katram e-pasta NDR ir birka **"MI klasificēts"** ar ticamību (piem., 92%; neatpazītam tekstam – zemāka), DIV statusiem – birka "DIV statuss".
- Agrāk pārlūkā saglabātās vēstules tiek pārvērstas uz jaunajiem noteikumiem; ja vēsturē ir tikai testa ieraksti, testa vēsture tiek izveidota no jauna.

## Atskaites

Cilnē **Atskaites** (specifikācija F18) katrai apakšsadaļai ir savs skats. Visos skatos ir:
- filtri vienā rindā augšā: periods (datums no–līdz ar ātrajām izvēlēm "Šis mēnesis", "Pēdējie 3 mēneši", "Šis gads", "Pēdējie 12 mēneši"), kampaņas veids, kanāls (eAdrese / e-pasts) un kampaņa (sarakstā tikai atlasītā perioda kampaņas). Pirmajā atvēršanā atlasīti pēdējie 12 mēneši;
- poga **"Eksportēt CSV"** (atdalītājs – semikols, UTF-8 ar BOM, lai fails pareizi atveras Excel);
- bloks **"MI kopsavilkums"** ar simulētām galvenajām atziņām par atlasītajiem datiem: piegādes īpatsvars, neveiksmīgo ziņu īpatsvara izmaiņas e-pastā salīdzinājumā ar iepriekšējo tāda paša garuma periodu, biežākais NDR iemesls, atkārtotā nosūtīšana, manuāla pārbaude un paraksti.

Skati:
- **Nosūtīšanas kopsavilkums** (pilna atskaite):
  - sešas rādītāju kartītes: nosūtīts, piegādāts, neveiksmīgs, atkārtoti nosūtīts, gaida parakstu un piegādes īpatsvars (%). Katrā kartītē ir izmaiņa pret iepriekšējo tāda paša garuma periodu (ja atlasīta konkrēta kampaņa, salīdzinājums netiek rādīts). "Piegādāts" nozīmē piegādāts eAdresē vai nodots e-pasta serverim;
  - līniju grafiks "Nosūtītās un piegādātās ziņas pa mēnešiem" (divas līnijas, leģenda un vērtības pēdējā punktā, rīka padoms katram mēnesim);
  - stabiņu grafiki: ziņas pa kanāliem, ziņas pēc kampaņas veida un NDR/DIV iemeslu sadalījums (biežākie iemesli pēc klasifikācijas noteikumiem);
  - tabula "Kampaņas": nosaukums, datums, veids, nosūtīto, piegādāto un neveiksmīgo skaits un piegādes %. Tabulu var kārtot, uzklikšķinot uz kolonnas nosaukuma (atkārtots klikšķis maina virzienu);
  - "MI kopsavilkums" – 3–4 teikumi par atlasīto periodu (apjoms un piegādes īpatsvars, problemātisko ziņu īpatsvars pa kanāliem, biežākais kampaņas veids, biežākais NDR iemesls), kas mainās atkarībā no filtriem (simulācija);
  - "Eksportēt CSV" lejupielādē kampaņu tabulu ar pašreizējiem filtriem un kārtošanu;
  - grafikiem ir rīka padoms (pelei un tastatūrai) un datu tabula. Krāsas pārbaudītas krāsu redzes traucējumu gadījumam.
- **Piegādes rezultāti:** tabula pa kampaņām (vēstules, piegādātas, procesā, neveiksmīgas, gaida parakstu, piegādes %) un kopsavilkums pa kanāliem. Piegādātas – e-adresē "Saņēmēja pieņemts", e-pastā – 72 h laikā nav saņemts NDR.
- **Neveiksmīgās ziņas:** NDR/DIV paziņojumu sadalījums pa iemesliem (kategorijām no abām klasifikācijas tabulām), pa tipiem (pastāvīgs, īslaicīgs, saturs, sūtītāja puse, nav kļūda, manuāli, starpstatuss, saņēmēja konfigurācija) un pa novirzījumam, kā arī visu paziņojumu tabula (laiks, respondents, kampaņa, kanāls un adrese, iemesls, tips, klasifikācija – MI ar ticamību vai DIV statuss, automātiskā rīcība, vēstules statuss).
- **Atkārtotā nosūtīšana:** rādītāji un tabula ar mēģinājumu skaitu un iemeslu: pagaidu kļūda, pāreja uz nākamo adresi vai manuāla atkārtota nosūtīšana.
- **Citi pārskati:** parakstīšanas rezultāti pa kampaņām (veids, parakstītāji, parakstītās vēstules, gaida parakstu, laiki).

## Respondentu pazīmes

Respondentiem ir pazīmes:
- **respondenta veids:** uzņēmums vai privātpersona. Ja tas nav norādīts, to nosaka pēc e-adreses: `_DEFAULT@` nozīmē uzņēmumu, `_PRIVATE@` nozīmē privātpersonu. Ja e-adreses nav, skatās, vai norādīta kontaktpersona;
- **dalības veids:** e-anketa, tikai telefonintervija vai klātienes intervija;
- **iepriekšējā dalība:** piedalījās, nepiedalījās vai izlasē pirmo reizi.

**CSV importā** pazīmes var norādīt kolonnās `respondenta veids`, `dalības veids` un `iepriekšējā dalība`. Tās nav obligātas. Atpazīst arī saīsinājumus CAWI/CATI/CAPI un vērtības jā/nē.

**Nosacījumu (teksta daļu, kas redzamas tikai noteiktiem respondentiem) lietotāja saskarnē vairs nav:**
- redaktora rīkjoslā nav pogas "Nosacījums";
- veidņu kartītēs nav rindas "Nosacījumi: …" ar birkām;
- veidnes un kampaņas satura priekšskatījumā nav varianta izvēles, kampaņas kopsavilkumā – variantu skaita, vēstules priekšskatījumā – rindas "Variants"; izvēle "Iezīmēt laukus" iezīmē tikai laukus.

**Esošās veidnes.** Teksta daļas, kas agrāk bija nosacījumi, pārvērstas par parastu tekstu: atstāts vispārīgais (noklusējuma) variants, pārējie varianti izdzēsti. Vispārīgais variants ir:
- dalības veids – e-anketa (paliek norādes par e-anketu; teksti telefonintervijas un klātienes intervijas respondentiem izdzēsti);
- iepriekšējā dalība – izlasē pirmo reizi (pateicība par iepriekšējo dalību un aicinājums "ja iepriekš nepiedalījāties" izdzēsti);
- respondenta veids – atbilstoši veidnes adresātam: fiziskām personām – teksts privātpersonai, juridiskām personām – teksts uzņēmumam, veidnēm visiem – teksts privātpersonai.

Tas attiecas arī uz pārlūkā jau saglabātajām veidnēm, e-pasta satura šabloniem, melnrakstiem, ieplānotajām kampaņām un pastāvīgajām daļām (pārvērš, ielādējot lapu), kā arī uz ielīmētu tekstu. Nosūtīto vēstuļu vēsture netiek mainīta.

## Valodas

Vēstules tiek veidotas un sūtītas **tikai latviešu valodā**.

- Veidņu redaktorā, kampaņas satura redaktorā ("Izmantot veidni" → "Pielāgot šai kampaņai" un "Noformēt saturu"), veidņu izvēlē, sagatavēs un "Pastāvīgajās daļās" nav valodas izvēles (LV / RU / EN), valodu birku un padomu par valodām; priekšskatījumā nav rindas "Valoda".
- Datos glabājas tikai latviešu teksts: veidņu un pastāvīgo daļu krievu un angļu versijas, kā arī apsekojumu nosaukumi angliski / krieviski ir dzēsti (arī pārlūkā jau saglabātajos datos – ielādējot lapu).
- Respondentiem nav pazīmes "valoda" (tā dzēsta arī pārlūkā jau saglabātajos datos).
- Kodā ir tikai viens veidņu redaktors – modālais logs. Tas atveras no "+ Jauna veidne", "+ Pievienot veidni" kategorijā, veidnes rediģēšanas, sagatavju "+ Jauna veidne" un kampaņas soļa "Saturs" ("Noformēt saturu", "Izmantot veidni" → "Pielāgot šai kampaņai"; "Saglabāt arī kā veidni" saglabā no tā paša loga). Lauka **"Adresāts"** vērtības veidnēs un sagatavēs (veidnes izveide un rediģēšana, "+ Pievienot veidni" kategorijā, sagatavju izveide un rediģēšana, sagatavju filtri un birkas) ir "Fiziskā persona", "Juridiskā persona" un "Visi (jaukta komunikācija)"; veidņu sākuma ekrāna un sagatavju grupas – "Fiziskām personām", "Juridiskām personām", "Cita komunikācija". Kampaņās lauks "Statistikas joma" nav mainīts. Datos adresāts glabājas kā kods (fiz / jur / visi), tāpēc esošās veidnes un sagataves automātiski rāda jaunos nosaukumus.
- Kājenē redzams prototipa versijas numurs ("Versija 51"); ja pēc atjaunināšanas redzams vecāks numurs, lapa jāpārlādē (Ctrl+Shift+R).

## GitHub Pages

1. Repozitorijā atveriet **Settings → Pages**.
2. Sadaļā **Build and deployment** pie **Source** izvēlieties **Deploy from a branch**.
3. Pie **Branch** izvēlieties `main` un mapi `/ (root)`, tad spiediet **Save**.
4. Pēc 1–2 minūtēm prototips būs pieejams adresē `https://<lietotājvārds>.github.io/<repozitorija-nosaukums>/`.
