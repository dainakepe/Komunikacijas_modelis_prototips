# Komunikācija – prototipa struktūra un funkcionālo bloku apraksts

*Darbnīcas projekts*

> Šis dokuments ir galvenā atsauce komunikācijas moduļa prototipam (`index.html`).

## 1. Prototipa struktūra

Komunikācijas funkcionalitāte tiek organizēta trīs savstarpēji saistītās pamatdaļās:

- **Kampaņas** – konkrētas komunikācijas sagatavošana, adresātu atlase, satura izvēle vai izveide, nosūtīšanas iestatījumu noteikšana un komunikācijas izpilde;
- **Veidnes** – atkārtoti izmantojama komunikācijas satura sagatavošana un pārvaldība;
- **Sūtīšanas vēsture** – nosūtīto komunikāciju, to statusu, kļūdu un izpildes rezultātu pārraudzība.

Šāda struktūra nošķir trīs galvenos lietotāja darba aspektus: ko nosūtīt, kam un kā nosūtīt, kā arī kas ar nosūtīto komunikāciju ir noticis.

```
KOMUNIKĀCIJA
│
├── KAMPAŅAS
│   ├── MELNRAKSTI
│   ├── IEPLĀNOTĀS
│   ├── IZPILDĒ
│   └── PABEIGTĀS
│
├── VEIDNES
│   ├── VEIDNES
│   │   ├── FIZISKĀM PERSONĀM
│   │   ├── JURIDISKĀM PERSONĀM
│   │   └── CITA KOMUNIKĀCIJA
│   │
│   └── SAGATAVES
│
├── SŪTĪŠANAS VĒSTURE
│   ├── VISAS
│   ├── GAIDA PARAKSTU
│   ├── NOSŪTĪTAS
│   ├── PIEGĀDĀTAS
│   └── NEVEIKSMĪGAS
│
└── ATSKAITES
    ├── NOSŪTĪŠANAS KOPSAVILKUMS
    ├── PIEGĀDES REZULTĀTI
    ├── NEVEIKSMĪGĀS ZIŅAS
    ├── ATKĀRTOTĀ NOSŪTĪŠANA
    └── CITI PĀRSKATI
```

## 2. Detalizēts funkcionālo bloku apraksts

### 2.1. Kampaņas

Kampaņa ir konkrētas komunikācijas sagatavošanas un izpildes vienība. Kampaņas ietvaros tiek noteikts komunikācijas mērķis, atlasīti adresāti, izvēlēts vai sagatavots komunikācijas saturs, noteikti nosūtīšanas nosacījumi un veikta vēstuļu nosūtīšana.

Kampaņas nodrošina iespēju pārvaldīt komunikācijas procesu no sagatavošanas līdz izpildei un rezultātu pārraudzībai.

| Nr. | Funkcija | Apraksts |
|---|---|---|
| F1 | Kampaņas izveide un pārvaldība | Lietotājs var izveidot jaunu kampaņu, saglabāt to kā melnrakstu, turpināt tās sagatavošanu, ieplānot nosūtīšanu vai uzsākt nosūtīšanu. Kampaņai tiek norādīts:<br>• kampaņas nosaukums;<br>• komunikācijas veids – uzaicinājums, atgādinājums, informatīvs ziņojums vai cits;<br>• nosūtīšanas datums un laiks;<br>• citi komunikācijas procesa parametri.<br>Kampaņai tiek piešķirts statuss, kas atspoguļo tās izpildes posmu: melnraksts, ieplānota, izpildē, pabeigta. |
| F2 | Respondentu atlase | Kampaņas ietvaros tiek veikta respondentu atlase, izmantojot Respondentu pārvaldības modulī pieejamos datus.<br>Uzaicinājumiem un citiem informatīviem ziņojumiem respondentus var atlasīt pēc:<br>• pārskata (apsekojuma);<br>• periodiskuma;<br>• konkrēta perioda;<br>• citiem noteiktajiem atlases kritērijiem.<br>Atgādinājumiem tiek ņemts vērā pārskata iesniegšanas statuss un termiņš. Atgādinājuma saņēmēji ir respondenti, kuri attiecīgo pārskatu nav iesnieguši.<br>Komunikācijas modulis izmanto Respondentu pārvaldības moduļa datus, kā arī iesniegšanas statusus no Datu vākšanas pārraudzības moduļa. |
| F3 | Apkopotas vēstules ģenerēšana | Katram respondentam tiek ģenerēta viena vēstule, kas aptver visus uz konkrēto respondentu attiecināmos atlasītos pārskatus un periodus. Vēstulē pārskati tiek attēloti apkopojošā tabulā, norādot, piemēram:<br>• pārskatu;<br>• periodu;<br>• iesniegšanas termiņu.<br>Atgādinājuma gadījumā tabulā iekļauj tikai tos pārskatus, kuri nav iesniegti. Šāda pieeja samazina nosūtāmo vēstuļu skaitu un nodrošina respondentam pārskatāmu informāciju. |
| F4 | Kampaņas satura izvēle un izveide | Kampaņas sagatavošanas laikā lietotājs izvēlas komunikācijas saturu. Saturu iespējams:<br>• izvēlēties no esošas veidnes;<br>• izveidot no sagataves;<br>• izveidot no jauna.<br>Ja saturs tiek izveidots kampaņas ietvaros bez iepriekš sagatavotas veidnes, to var saglabāt kā jaunu veidni atkārtotai izmantošanai. |
| F5 | Vēstules individuāla pielāgošana | Pirms nosūtīšanas lietotājam ir iespēja atsevišķu ģenerēto vēstuli pielāgot konkrētam adresātam, piemēram:<br>• labot tekstu;<br>• pievienot pielikumu;<br>• noņemt pielikumu.<br>Šī funkcija nodrošina iespēju kombinēt automatizētu masveida komunikāciju ar nepieciešamo individuālo pieeju. |
| F6 | Vēstuļu priekšskatījums un pārbaude | Pirms nosūtīšanas lietotājs var pārbaudīt kampaņas rezultātu un apskatīt ģenerētās vēstules.<br>Priekšskatījumā tiek attēlota konkrētā respondenta vēstule ar aizpildītiem mainīgajiem un ģenerēto pārskatu tabulu.<br>Nepieciešams nodrošināt iespēju pārbaudīt gan e-pasta, gan e-adreses ziņas variantu. |
| F7 | Adrešu prioritāte | Kampaņai tiek noteikta adresātu sasniedzamības secība, piemēram:<br>• eAdrese;<br>• e-pasts;<br>• alternatīva e-pasta adrese.<br>Ja konkrētā adrese nav pieejama vai ziņas nosūtīšana uz to nav veiksmīga, sistēma izmanto nākamo adresi atbilstoši noteiktajai prioritātei. |
| F8 | Parakstīšana | Kampaņas sagatavošanas laikā lietotājs norāda, vai vēstulei nepieciešams elektroniskais paraksts.<br>Ja parakstīšana ir nepieciešama, vēstule tiek nodota parakstīšanai, izmantojot DVS NAMEJS integrāciju.<br>Tiek nodrošināta:<br>• secīga parakstīšana;<br>• paralēla parakstīšana;<br>• parakstīšanas pakas.<br>Ja parakstīšana nav nepieciešama, vēstule tiek nosūtīta bez šī posma. |
| F9 | Masveida sūtīšana | Sistēma nodrošina vienlaicīgu liela vēstuļu apjoma nosūtīšanu uz eAdresēm un e-pastiem.<br>Nosūtīšana notiek automātiski atbilstoši kampaņā noteiktajiem parametriem un adrešu prioritātei. |
| F10 | Atkārtota nosūtīšana un neveiksmīgo vēstuļu apstrāde | Pagaidu kļūmes gadījumā sistēma atkārtoti mēģina nosūtīt vēstuli uz to pašu adresi.<br>Pastāvīgas kļūmes gadījumā sistēma pāriet uz nākamo adresi atbilstoši noteiktajai prioritātei.<br>Ja visas pieejamās adreses ir izsmeltas, vēstule tiek atzīmēta kā neveiksmīga un nodota manuālai pārbaudei. |
| F11 | Automātiskie atgādinājumi | Sistēma nodrošina automātisku atgādinājumu sagatavošanu un nosūtīšanu, balstoties uz pārskatu iesniegšanas statusiem un termiņiem.<br>Pirmstermiņa atgādinājumam iespējams noteikt dienu skaitu līdz iesniegšanas termiņam, savukārt nokavētam atgādinājumam – minimālo kavējuma dienu skaitu.<br>Ieplānotas atgādinājuma kampaņas gadījumā respondentu atlase tiek atkārtoti veikta faktiskajā nosūtīšanas laikā, lai ziņa netiktu nosūtīta respondentiem, kuri pa šo laiku jau ir iesnieguši pārskatu. |

### 2.2. Veidnes

Veidnes ir centralizēta atkārtoti izmantojamā komunikācijas satura pārvaldības sadaļa.

Tās mērķis ir nodrošināt principu: “Saturs tiek sagatavots vienreiz un atkārtoti izmantots, savukārt konkrētā respondenta dati tiek pievienoti sūtīšanas brīdī.”

Tas samazina manuālo darbu, nodrošina vienotu CSP komunikācijas stilu un samazina kļūdu risku.

| Nr. | Funkcija | Apraksts |
|---|---|---|
| F12 | Veidņu pārvaldība | Lietotājs var izveidot jaunu veidni, izveidot veidni no sagataves, labot veidni, dzēst veidni, atkārtoti izmantot veidni kampaņās.<br>Veidnes tiek organizētas pēc diviem principiem:<br>• Adresātu grupa: fiziskas personas, juridiskas personas, cita komunikācija.<br>• Komunikācijas mērķis: uzaicinājumi, atgādinājumi, informatīvie ziņojumi, citi. |
| F13 | Sagataves | Sagataves ir atkārtoti izmantojami komunikācijas materiāli, no kuriem iespējams veidot vai papildināt veidnes. Tajās var tikt glabāti:<br>• e-pasta satura šabloni;<br>• vēstuļu varianti;<br>• instrukcijas;<br>• informatīvie materiāli;<br>• pielikumu sagataves.<br>Sagatavēm tiek nodrošināta versiju pārvaldība un informācija par to izmantošanu veidnēs. |
| F14 | Satura personalizācija | Veidnēs iespējams izmantot mainīgos laukus, piemēram, vārds, uzņēmums, apsekojums, termiņš.<br>Mainīgie sūtīšanas laikā tiek automātiski aizpildīti atbilstoši konkrētā respondenta datiem.<br>Iespējams definēt arī nosacījumus noteiktu teksta daļu attēlošanai, kā arī nodrošināt vairākas valodu versijas.<br>Juridiskām personām iespējams ģenerēt apkopojošu pārskatu tabulu, lai viena vēstule aptvertu visus respondentam iesniedzamos pārskatus un periodus. |
| F15 | Vēstules satura veidošana | Veidnes redaktorā iespējams veidot un formatēt tekstu, pievienot attēlus, pievienot saites un pogas, izmantot pastāvīgās vēstules daļas, pievienot pielikumus.<br>Pastāvīgās daļas, piemēram, galvene, paraksts un kājene, tiek uzturētas centralizēti un automātiski pievienotas vēstulēm.<br>Veidne var būt e-pasta saturs vai oficiāla vēstule pielikumā ar īsu pavadtekstu e-pastā. |

### 2.3. Sūtīšanas vēsture

Sūtīšanas vēsture nodrošina visu nosūtīto un nosūtīšanas procesā esošo komunikāciju pārraudzību.

Tajā iespējams apskatīt komunikācijas:

- statusu;
- nosūtīšanas laiku;
- izmantoto kanālu;
- adresi;
- nosūtīšanas mēģinājumus;
- piegādes rezultātu u.c. parametrus.

| Nr. | Funkcija | Apraksts |
|---|---|---|
| F16 | Komunikācijas vēsture un statusi | Katrai nosūtītajai vēstulei tiek saglabāta tās nosūtīšanas vēsture.<br>Pamata statusa ceļš:<br>Melnraksts → Gaida parakstu → Parakstīta → Nosūtīta → Piegādāta<br>Ja parakstīšana nav nepieciešama:<br>Melnraksts → Nosūtīta → Piegādāta<br>Iespējamie alternatīvie statusa ceļi:<br>Pagaidu kļūda → Atkārtots mēģinājums<br>Pastāvīga kļūda → Nākamā adrese<br>Visas adreses izsmeltas → Neveiksmīga → Manuāla pārbaude |
| F17 | NDR un DIV kļūdu apstrāde | Sistēma centralizēti saņem un apstrādā paziņojumus par neveiksmīgu piegādi: e-pasta atgriezeniskos paziņojumus (NDR) un e-adreses (DIV) kļūdu statusus. Katrs paziņojums tiek automātiski piesaistīts sākotnējai ziņai un klasificēts pēc tipa:<br>• pagaidu kļūda – atkārtots mēģinājums;<br>• pastāvīga kļūda – adrese atzīmēta kā nederīga, sūtīšana uz nākamo adresi;<br>• sūtītāja puses kļūda (bloķēšana, noraidījums) – paziņojums administratoram;<br>• automātiska atbilde (prombūtne) – statuss netiek mainīts;<br>• neatpazīts – nodots darbiniekam manuālai izskatīšanai.<br>Atbilstoši klasifikācijai paziņojums tiek novirzīts sistēmai, darbiniekam vai abiem. Klasifikācijā paredzama arī MI izmantošanas iespēja. |

**E-pasts**

| Iemesls | Tips | Automātiskā rīcība |
|---|---|---|
| Adrese vai domēns neeksistē, konts slēgts | Pastāvīgs | Adresi atzīmēt kā nederīgu, sūtīt uz nākamo adresi, uzdevums kontaktu aktualizēšanai |
| Pastkaste pilna | Īslaicīgs | Atkārtot 2–3 reizes 24–72 h laikā, tad nākamā adrese |
| Serveris nesasniedzams, ātruma limits | Īslaicīgs | Atkārtot ar pieaugošu intervālu; pēc N reizēm – pastāvīgs |
| Ziņa par lielu | Saturs | Sūtīt bez pielikuma, ar saiti |
| Bloķēts kā spams, autentifikācijas kļūda | Sūtītāja puse | Adresi neaiztikt; brīdinājums administratoram |
| Prombūtnes atbilde | Nav kļūda | Nekas; var izmantot atgriešanās datumu atgādinājumam |
| "Adrese mainīta", neatpazīts teksts | Manuāli | Manuālā rinda |

**E-adrese**

| Pašreizējais statuss | Tips | Automātiskā rīcība |
|---|---|---|
| Pieņemts DIV / Notiek piegāde | Starpstatuss | Gaidīt; pēc noteikta laika tiek sūtīts uz e-pastu |
| Saņēmēja pieņemts | Gala | Piegādāts |
| Noraidīts DIV | Sūtītāja puse | Neatkārtot; brīdinājums administratoram |
| Saņēmēja noraidīts | Pastāvīgs | Sūtīt uz e-pastu; ja atkārtojas – manuāli |
| Nokavēta piegāde | Īslaicīgs | Atkārtot 1–2 reizes, tad e-pasts |
| Nav publiskās atslēgas šifrēšanai | Saņēmēja konfigurācija | Sūtīt uz e-pastu; informēt respondentu |
| Adresāta pastkastīte pilna | Īslaicīgs | Atkārtot pēc 24–72 h, paralēli e-pasts |

### 2.4. Atskaites

Apkopota informācija par komunikācijas procesu un tā rezultātiem. Vizualizācijai pieslēgt MI.

| Nr. | Funkcija | Apraksts |
|---|---|---|
| F18 | Atskaites | Atskaites par izsūtīšanu (nosūtīts, piegādāts, neveiksmīgs, gaida parakstu) ar eksportu, piemēram, CSV formātā:<br>• nosūtīto ziņu skaits;<br>• nosūtīšanas laiks;<br>• piegādāto ziņu skaits;<br>• neveiksmīgo ziņu skaits;<br>• atkārtoti nosūtīto ziņu skaits;<br>• ziņas pa kanāliem – eAdrese/e-pasts;<br>• ziņas pēc kampaņas veida;<br>• ziņas pēc perioda;<br>• parakstīšanas rezultāti;<br>• kļūdas/NDR;<br>• citi komunikācijas procesa rādītāji;<br>• eksports. |
