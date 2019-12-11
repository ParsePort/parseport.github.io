---
title: Security policies
permalink: /security/policies/
parent: Security
nav_order: 1
has_toc: false
---
**TODO** Translate
# Security policies

## Indledning
Dette dokument er en erklæring, henvendt til ParsePorts IT-afdeling, leverandører og partnere, om de forpligtelser de påtager sig ved omgangen med ParsePorts data og IT-systemer. Dokumentet er ligeledes en information overfor personer med tilknytning til ParsePort, om de tiltag der gøres for at sikre IT-systemerne

### Målgruppe
Denne politik er er gældende for enhver person der ved ansættelse i ParsePort, eller som ekstern samarbejdspartner har fået tildelt adgang til systemerne i ParsePort. Disse personer er samtidig ansvarlige for at eventuelle tredjeparter der tillades adgang til udstyret, overholder denne politik i forbindelse med brug af udstyret.

### Almindelige tekniske sikkerhedsforskrifter
ParsePorts netværk skal til enhver tid være baseret på standardprotokoller. Valg af protokol foretages af den IT-ansvarlige. Ved skift af protokol skal ekstern rådgiver give deres anbefaling samt hjælpe med at belyse faldgrupper, fejlkilder, mv.

Infrastrukturen skal til enhver tid være tidssvarende, og sikres af den IT-ansvarlige. Arbejdet sker under ledelse af direktionen, og eventuelt via medvirken fra en ekstern kompetencerådgiver.

Infrastrukturen skal gennemgås 1 gang årligt, i sammenhæng med planlægning af den årlige IT-strategiplan.

### Leverandører, service og reparation
Servere samt PC’ere skal såfremt der ikke er væsentlige grunde for andet, installeres med standard basissoftware, der kan serviceres af generelle IT-leverandører.

For at sikre lettest mulig tilgang til reklamationssager og afhjælpning af fejl, bør antallet af leverandører begrænses i det omfang det er muligt.

Når udstyr med indbygget lagringsmedier såsom PC’ere, servere og mobile enheder overleveres til tredjepart, skal denne overholde ParsePorts IT-sikkerhedsregler. Såfremt enheden indeholder virksomhedsdata og lagringsmediet ikke er krypteret, skal dette foretages, eller lagringsmediet skal fjernes.

#### Sikkerhedskrav til leverandrer
ParsePort stiller vise sikkerhedsmæssige krav til IT-leverandører der skal være opfyldt.

Det er nødvendigt at eventuelle IT-leverandører efterlever denne IT-sikkerhedspolitik. Samtidig forventes det at der er etableret brugerrettighedsstyring og kontrol, fysisk sikkerhed samt regelmæssige backup-rutiner af henholdsvis hardware og software. Desuden skal systemerne være beskyttet af teknologier og foranstaltninger, der begrænser risiko for angreb mod systemer, der driftes på vegne af ParsePort. Under teknologier tænkes specielt på eksempelvis firewall og antivirus, mens foranstaltninger kan være aktiv logning og politikker håndhævet på systemerne.

ParsePort forudsætter desuden, at leverandøren foretager proaktiv overvågning af det udstyr, der er outsourcet, og øvrige systemer der kan have indvirkning på drift og stabilitet af løsninger, der varetages af leverandøren på vegne af ParsePort. Omfanget af krav til leverandøren kan variere afhængig af hvilken form for service, der outsources. Da der kan være tale om forskelligartede SLA og vilkår, henvises til de individuelle kontrakter, der er indgået med leverandøren.

### IT-Udstyr
Alt IT-udstyr skal være godkendt af den IT-ansvarlige, og må kun benyttes så længe produktet fortsat har aktiv livscyklus i form af software og hardware opdateringer.

### Backup
Der skal tages backup løbende af alle interne infrastrukturkomponenter, samt for de kundevendte systemer.
Backuppen skal minimum årligt testes for mulig restore af enkeltfiler, samt af individuelle servere.

### Virus og hacking
Alle ParsePorts servere er sikret med antivirus software, der automatisk henter nye virusdefinitioner løbende. Der scannes for alle de vira, som er kendt af programmet på alle relevante filer.

Antivirusprogrammets log overvåges løbende af den IT-ansvarlige. Som udgangspunkt er det umuligt at komme med fyldestgørende retningslinjer for virus og virusangreb, men ParsePort gør løbende brug af eksternt IT-sikkerhedsfirma med teknisk erfaring i incident og forensic håndtering, så skade og nedetid minimeres, og hændelsen isoleres så hurtigt som overhovedet muligt. Har man som slutbruger mistanke om, at PC’en har fået virus, skal alle opgaver på systemet indstilles. PC’en isoleres fra netværket, og den IT-ansvarlige kontaktes.

Samtlige PC'er samt servere skal have gyldigt antivirusprogram installeret. ParsePorts interne net er beskyttet af firewall, og er isoleret fra andre netværk, kun med adgang fra den interne zone hos Global Connect, hvor basis insfrastrukturen drives fra. Alle zoner hos Global Connect er beskyttet af både firewall samt intrusion prevention system.

Alt infrastruktur der er placeret hos Global Connect er udover beskyttelse med firewall, også beskyttet med Intrusion Prevention System for yderligere beskyttelse.

For at sikre uvildig test af systemerne, foretages der mindst én gang om året ekstern penetrationstest af alle zoner hvor ParsePort har udstyr hos Global Connect.

Software til at søge at omgå system og applikationskontroller må udelukkende benyttes af professionelle sikkerhedskonsulenter, og udelukkende med henblik på sikring af systemerne. Disse må endvidere ikke benyttes uden skriftlig accept fra direktionen samt den IT-ansvarlige.

### Datalagring
Der er to lokationer for data lagring, alt efter hvorvidt data lagringen er for ParsePorts interne infrastruktur eller for ParsePorts kundevendte programmel (produkt).

Både ParsePorts interne og kundevendte IT-systemer er placeret hos Global Connect i professionelt ISAE 3402 godkendt samt ISO 27001 og ISO 9001 certificeret datacenter på en IaaS platform. Hvorfor data både er fysisk og virtuelt sikret mod uautoriseret adgang.

#### Intern infrastruktur
For at sikre en centralisering af data, samt have en mindre angrebsoverflade arbejder alle medarbejdere på en Microsoft Remote Desktop løsning som udover mail platformen er det eneste sted der lagres interne data.

#### Kundevendt infrastruktur
Den kundevendte infrastruktur benyttes udelukkende til bearbejdning og konvertering af data. En bruger får adgang med brugernavn og kodeord, og uploader en fil, der bliver bearbejdet af systemet. Når bearbejdningen er færdig kan brugeren hente de bearbejdede data. Derefter slettes både de uploadede og bearbejdede data.

### Opdatering af systemer
Alle IT-systemer skal holdes jævnligt opdaterede.

  *	Der skal som minimum én gang månedligt foretages kritiske software opdatering (Operativ system, mv)
  *	Der skal som minimum halvårligt foretages kritiske opdateringer af hardware komponenter (firmware, mv)
  *	Der skal som minimum årligt foretages en intern sårbarhedsskanning for afklaring af interne risici.

Den IT-ansvarlige er ansvarlig for at holde sig opdateret på sårbarheder, og deres potentielle risiko, såfremt de er relevante for ParsePorts infrastruktur.

### Licensering
Alt software benyttet i ParsePort skal have gyldig licens tilknyttet.

Alle software køb/registreringer skal enten foretages af, eller registreres hos en IT-ansvarlige som så står for dokumentation og asset management.

## Fysisk sikkerhed
Fundamentet for sikring af IT-udstyr er en god fysisk IT-sikkerhed.

### Fysisk sikkerhed omkring servere
Hos ParsePort er alle servere outsourcet til Global Connect.

For at opnå forsvarlig fysisk sikkerhed er der hos Global Connect følgende fysiske foranstaltninger:

*	Aircondition for at sikre mod overophedning og uhensigtsmæssig luftfugtighed
*	Døgnbemandet adgangskontrol med flere låsetyper
*	Alarm
*	Brandsikrede materialer
*	Automatisk brand bekæmpelses anlæg
*	Servere der er løftet fra gulv for sikring mod flydende væsker
*	Strømredundans i form af UPS anlæg og dieselgenerator
*	Videoovervågning
*	Perimetersikring i form af afspærrede områder

### Fysisk sikkerhed på hovedkontoret
På ParsePorts hovedkontor, placeret på Roholmsvej 12 A, 2, 2620 Albertslund har følgende fysiske foranstaltninger:

*	Nøglelås til opgang. (deles med andre lejere)
*	Nøglelås til dør, beskyttet med nøgle
*	Alarm koblet til alarmcentral med personlig kode til hver medarbejder
*	Videoovervågning tilkoblet til alarmcentral
*	Røgkanon

### Kabling
Kabler der benyttes på ParsePorts adresse til IT-udstyr i form af eksempelvis netledning, netværkskabel, HDMI kabler mv. skal være mærket så de kan identificeres. Ligeledes skal der ved brug af krydsfelter på adressen være mulighed for ved opmærkning at identificere endepunkterne.

### Trådløse netværk
Trådløse netværk omhandler WiFi kommunikation som sker med henblik på at opnå adgang til et netværk af ressourcer fra en eller flere enheder.

Alt opsætning/modifikation/nedtagning af trådløse netværk skal ske således, at de er sikret mod indtrængen for uvedkommende.

Trådløse netværk skal som minimum overholde følgende krav:

* Kryptering minimum jævnfør WPA2 standarden
* Kodeord skal benyttes til opsætningen, og omgående ændres fra det oprindelige
* SSID skal ændres fra fabriksindstilling

### Backup data
Backuppen tages af GlobalConnect, og skal overholde følgende krav:
* Der skal tages backup dagligt
* Backuppen skal være “application aware” – kunne tage backup af data lagret i applikationer, hvor fuld disk backup ikke kan generere gyldig backup. Såfremt dette ikke er muligt skal applikationen lave et data dump lokalt dagligt, således at den normale fil backup tager af denne.
* Backup data skal til hver en tid være fysisk sikret på samme måde som de data der er taget backup af
* Backup data skal fysisk placeres i andet datacenter end backup kilden og minimum 1 kilometer fra hinanden

### Bortskaffelse af data/medier
Den IT-ansvarlige står for bortskaffelse af alt internt IT-udstyr, og herunder sikringen mod datatab.

Alle lagringsmedier skal tages ud af IT-udstyr og sendes til professionel destruktion hos en udbyder der tilbyder professionel datadestruktion.

I tilfælde af at lagringsmediet ikke kan udtages fra IT-udstyret skal hele IT-udstyret indsendes til destruktion.

Såfremt IT-udstyr skal genbruges uden for ParsePort skal dette saniteres for data på en metode der som minimum overholder NIST Special Publication 800-88 Revision 1 – Purge.

### Mærkning og udlevering af udstyr
IT-ansvarlig står for registrering, mærkning og udlevering af IT-udstyr. Samt for registrering i ParsePorts IT asset management dokumentation.

### Øvrige forhold
Alle medarbejdere skal altid være opmærksomme på IT-sikkerheden på en sådan måde at data beskyttes og håndteres bedst muligt.

Medarbejdere i ParsePort skal endvidere være opmærksomme på uhensigtsmæssigheder eller deciderede overtrædelser af IT-sikkerhedspolitikken. Bliver man opmærksom på sådant, skal dette enten påtales direkte til den enkelte kollega, meddeles til nærmeste foresatte eller til IT-ansvarlig, alt efter sagens karakter.

## E-mail og dokumenthåndtering
E-mail er i dag et af de mest benyttede kommunkationsværktøjer både internt og eksternt. Håndteringen af elektronisk post og dokumenter, fremover benævnt e-mail, er derfor et centralt element i det daglige arbejde i ParsePort.

Alle medarbejdere, vil tillige skulle håndtere e-mail, og skal dermed også være i stand til at iagttage og efterleve de sikkerhedsmæssige krav i tilknytning hertil.

Med indførelsen af elektronisk dokumenthåndtering og digital signatur er retsvirkningerne af elektroniske dokumenter i mange tilfælde efterhånden bevet sidestillet med almindelige håndunderskrevne papirdokumenter. Det er derfor nødvendigt med et sæt fælles retningslinjer for, hvorledes e-mail skal modtages og besvares.

### Definition af e-mail
Med e-mails menes i denne sammenhæng: Ethvert fremsendt/afsendt dokument eller besked i elektronisk form fra eller til et et af ParsePorts domæner.

Der skelnes dog mellem interne og eksterne e-mails, hvor interne e-mails kun sendes over lukkede kredsløb, hvor alt kommunikation med mailserveren er krypteret, men eksterne e-mails kan transporteres uden kryptering.

Det følger i sagens natur, at sikkerhedsniveauerne i håndteringen heraf vil variere afhængig af dokumentets karakter og følsomhed. Der er eksempelvis forskel på en almindelig mødeindkaldelse og overførsel af kundeoplysninger.

### Juridisk gyldighed af e-mails
I Danmark er der verserende sager for at afgøre hvorvidt e-mails er juridisk bindende på samme måde som almindelig brevudveksling, da der indtil nu har været domme der er faldet ud til begge sider.

Digitalt signerede e-mails forventes at være gyldige på minimum samme niveau som fysiske breve/kontrakter, da man kan dokumentere afsender/underskriver.

Når der ikke benyttes digital signatur, samt i ethvert tvivlstilfælde om gyldigheden, retsvirkningerne eller øvrige lovgivningsmæssige rammer skal e-mail ikke benyttes.

Til uformel kommunikation og almindelig korrespondance forbliver e-mail dog et af de foretrukne værktøjer.

### Håndtering af indgående e-mails
Enhver virksomhed eller privatperson skal kunne rette elektronisk henvendelse til ParsePort i form af e-mail, samt modtage et elektronisk svar.

Behandlingen af e-mail adskiller sig ikke fra modtagelsen af almindelig post, og enhver gyldig henvendelse bør søgt besvaret hurtigst muligt.

Såfremt der vil være behandlingstid eller ventetid på henvendelsen, bør afsender modtage en kvittering for modtagelse af henvendelsen.

Som udgangspunkt vil ParsePort ikke modtage dokumenter via e-mail. Ønsker en kunde at sende deres regnskabsdata, henvises til at de anvender parseport.com til at uploade deres regnskabsdata.

### Håndtering af udgående e-mails
Enhver besvarelse af elektronisk post skal indeholde signatur der tilkendegiver ParsePort som afsender af meddelelsen.

E-mail bør indeholde information omkring forventning til modtager i tilfælde af at meddelelsen er sendt til den forkerte.

### Mailbokse
Alt officiel elektronisk korrespondance til ParsePort stiles som udgangspunkt til hovedadressen [info@parseport.com](info@parseport.com).

I forbindelse med planlagt fravær (ferie, fridage, eller lignende) på mere end én arbejdsdag, skal den enkelte medarbejder sikre, at afsendere af e-mail, som sender til en personlige postkasse, enten får besked via ”ikke tilstede”-funktionen i Outlook, eller at e-mailen omadresseres til en kollega(er) eller en fællespostkasse.

### SPAM og Mail-antivirus
Alle e-mails til og fra ParsePort bliver scannet af Fusemail for både spam og virus. Såfremt meddelelser indeholder en af disse bliver de sat i karantæne hos Fusemail i 90 dage, hvorefter de bliver slettet.

Såfrem Fusemail identificerer en virus i en mail som kan fjernes sikkert, vil den sikre del af e-mailen (meddelelsen) blive leveret.

Løsningen fra Fusemail agerer samtidig ”backup” hold for ParsePorts mailsystemer i det at Fusemail holder mail i op til 14 dage, såfremt der er problemer med at levere meddelelsen til ParsePort’s Exchange server.

## Produktionssystem (kundevendt system)
ParsePorts primære forretning er oprettelse/generering af XBRL data.

### Systemet
ParsePort giver kunder mulighed for at lave XBRL filer ud fra brug af tre forskellige interfaces.

1.	Hjemmeside med grafisk interface der præsenterer et login interface, hvor kunden ved hjælp af brugernavn og kodeord logger ind på en TLS 1.2 sikret side. Kunden kan derefter uploade en fil med data, hvorefter ParsePorts system konverterer/bearbejder den, og kunden kan derefter downloade XBRL-fil med data.
2.	Excel Add-in der sættes op med kundens brugernavn/kodeord. Ved brug af Add-in overføres data-fil via TLS 1.2 til ParsePorts systemer, hvorefter systemet konverterer/bearbejder den, og returnerer en XBRL-fil med data.
3.	API interface, til brug for kunders egne programmer/programmel. Således at kunden kan indbygge logikken fra ParsePort ind i egne programmer eller API understøttende programmel. API interfacet benyttes ved at kundens løsning kalder ParsePorts API via TLS 1.2 med en nøgle, samt data til konvertering/bearbejdning. ParsePorts system returnerer derefter XBRL-fil med data.

### Systemets tilgængelighed
Systemet er tilgængeligt fra hele internettet, og er beskyttet i henhold til de to afsnit ”Teknisk sikkerhed” og ”Fysisk sikkerhed”.

### Datasikkerhed
Alt kommunikation med produktionsssystemet, skal være krypteret under transport over internettet minimum i henhold til TLS 1.2 standarden (RFC 5246).

Alle data der er lagret i produktionssystemet, skal være segmenteret på en måde så det ikke er muligt for kunder på platformen at få adgang til hinandens data.
