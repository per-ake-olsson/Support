# Key2Voice Windows – användarmanual

**Eureka Consulting AB**  
**Svenskt original – arbetsversion 0.9 (4 november 2026)**

> **Viktigt innan du börjar:** Key2Voice använder Microsofts molntjänst **Azure Speech** för taligenkänning och översättning. Du behöver en fungerande egen Azure Speech-resurs, rätt region och en giltig nyckel samt internetanslutning för att använda dessa funktioner. Azure är en separat tjänst som kan medföra kostnader. **Köp inte Key2Voice Premium innan du har konfigurerat din egen Azure Speech-resurs och verifierat att taligenkänningen fungerar i Key2Voice Basic.**
>
> Behöver du skapa Microsoft-konto, Azure-prenumeration eller Speech-resurs? Följ den separata svenska guiden [**Azure Speech-guiden**](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto). Den här manualen beskriver hur du använder ett redan skapat Azure-konto i Key2Voice.

## Syfte

Key2Voice hjälper dig att omvandla tal till läsbar text. Windows-versionen är huvudplattformen: här konfigurerar du Azure Speech, använder **Tal till text**, hanterar dina transkriptioner och gör säkerhetskopior. Med Premium kan du även skapa en krypterad synkfil för iPhone-appen. Den här manualen gäller **Windows-versionen**, inte iOS-versionen.

## Innehåll

1. [Innan du börjar](#innan-du-börjar)
2. [Installation](#installation)
3. [Första starten och valvet](#första-starten-och-valvet)
4. [Konfigurera befintlig Azure Speech-resurs](#konfigurera-befintlig-azure-speech-resurs)
5. [Testa taligenkänningen](#testa-taligenkänningen)
6. [Tal till text – daglig användning](#tal-till-text--daglig-användning)
7. [Språk och översättning](#språk-och-översättning)
8. [Spara och hantera transkriptioner](#spara-och-hantera-transkriptioner)
9. [Basic och Premium](#basic-och-premium)
10. [Synkronisera med iPhone och Apple Watch](#synkronisera-med-iphone-och-apple-watch)
11. [Säkerhetskopiering och återställning](#säkerhetskopiering-och-återställning)
12. [Inställningar och Om Key2Voice](#inställningar-och-om-key2voice)
13. [Felsökning](#felsökning)
14. [Säkerhet och integritet](#säkerhet-och-integritet)
15. [Uppdatering och support](#uppdatering-och-support)

## Innan du börjar

Du behöver en Windows-dator där Key2Voice kan installeras, en fungerande internetanslutning och en egen Azure Speech-resurs. För tal från mikrofon behöver du en mikrofon som fungerar i Windows. 

**Azure och Key2Voice är två skilda tjänster.** Key2Voice Premium är en licens för programfunktioner; den omfattar **inte** Azure-prenumeration eller förbrukningskostnader. Kontrollera Microsofts aktuella villkor och priser i Azure-portalen.

### Om du inte redan har Azure Speech

Läs först [**Azure Speech-guiden**](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto). Den visar hur du skapar Microsoft-konto vid behov, registrerar dig för Azure, ordnar en prenumeration, skapar en Speech-resurs och hittar dess nyckel och region. Återvänd sedan hit.

## Installation

1. Öppna **Microsoft Store** på Windows-datorn.
2. Sök efter **Key2Voice** och kontrollera att du har valt rätt app från **Eureka Consulting AB**.
3. Välj **Hämta** eller **Installera**. Grundversionen **Basic** är gratis och avsedd att kunna användas utan Premium-köp.
4. Starta Key2Voice via Windows Start-meny när installationen är klar.
5. Om Windows frågar om mikrofonbehörighet, ge åtkomst om du vill transkribera via mikrofon.

Installations- och licensdialogernas utseende kan variera med Windows- och Store-version.

## Första starten och valvet

Key2Voice använder ett lokalt **valv** för att skydda konfiguration och sparade uppgifter.

1. Följ programmets instruktioner för att skapa ett nytt valv vid första starten.
2. Välj en stark valvpassfras och förvara den på ett säkert ställe, skilt från datorn.
3. Kontrollera att valvet kan öppnas och att huvudfönstret visar valvstatus.
4. Kontrollera att licensnivån är **Basic** om du inte redan har en giltig Premium-rättighet.

### Öppna eller skapa valv och Stäng valv

- **Öppna eller skapa valv** i huvudfönstret öppnar ett befintligt valv eller skapar ett nytt om inget valv finns. Om valvet redan är öppet förblir det öppet. Beroende på dina inställningar kan du behöva ange valvets passfras. När valvet öppnats visas **Öppet** i valvstatus och du kan använda funktioner som behöver tillgång till valvet.
- **Stäng valv** stänger programmets aktiva åtkomst till det krypterade valvet och visar **Stängt** i valvstatus. Det **raderar inte** valvet eller dina sparade transkriptioner. Använd **Öppna eller skapa valv** igen när du vill fortsätta.
- Att stänga valvet innebär inte att en tidigare sparad passfras automatiskt glöms bort. Vill du behöva ange passfrasen vid varje start använder du inställningen **Kräv lösenfras vid start** under **Valvkryptering**.

### Vad betyder KDF-status?

I huvudfönstret visas **KDF** tillsammans med värden för valvets lösenordsbaserade nyckelhärledning. KDF står för *Key Derivation Function* och används när programmet omvandlar din valvpassfras till krypteringsnycklar. Informationen visas i formen **iterationer / minne i KiB / pN**, där det sista värdet anger parallellism. Detta är **tekniska skyddsparametrar**, inte en varning eller ett mått på hur stark din valvpassfras är. Värdena uppdateras när valvets KDF-inställningar förnyas. Du behöver normalt inte ändra dem själv.

**Viktigt:** Om du förlorar passfrasen kan återställning av krypterade uppgifter vara omöjlig. Eureka Consulting AB kan inte återskapa din privata passfras. Gör regelbundna säkerhetskopior enligt avsnittet nedan.

### När Key2Voice arbetar med krypterade uppgifter

Key2Voice skyddar valvet och sparade uppgifter med kraftfull kryptering. Vissa moment kan därför ta **märkbart längre tid** än vanliga knapptryckningar, beroende på datorn och mängden data. Det gäller exempelvis när programmet startar, när valvet öppnas, när sparade transkriptioner hämtas samt vid byte av valvpassfras eller uppdatering av valvets krypteringsskydd.

Under sådana moment visar Key2Voice en **aktivitetsindikator** som talar om att arbete pågår. Vänta tills operationen är klar. Undvik att stänga programmet eller avbryta datorn mitt under en säkerhetskritisk åtgärd. Om indikatorn verkar stå stilla ovanligt länge, notera vad du gjorde och kontakta support i stället för att upprepa samma åtgärd flera gånger.

## Konfigurera befintlig Azure Speech-resurs

Du ska nu använda **en Speech-resurs som redan finns i ditt eget Azure-konto**. Du behöver inte skapa ett nytt Azure-konto för varje installation av Key2Voice.

### A. Hitta uppgifterna i Azure

1. Öppna [Azure-portalen](https://portal.azure.com/) och logga in med det konto som har tillgång till din Azure-prenumeration.
2. Öppna den **Speech-resurs** du skapade enligt Azure-guiden. Om du har flera resurser, välj rätt resurs.
3. Leta upp resursens sida för **Keys and Endpoint** (benämningen kan variera i portalen).
4. Notera resursens **region** och kopiera en tillgänglig **nyckel**. Regionen är inte samma sak som ett visningsnamn eller resursgruppens namn.
5. Behandla nyckeln som ett lösenord. Skicka den inte via vanlig e-post och publicera den aldrig i skärmbilder eller supportärenden.

### B. Ange uppgifterna i Key2Voice

1. Starta Key2Voice och öppna **Inställningar**.
2. Leta upp inställningarna för **Azure Speech**.
3. Ange **prenumerationsnyckeln för Speech-resursen** och **regionen** exakt som de anges i Azure-portalen.
4. Spara inställningarna enligt programmets anvisningar.
5. Öppna **Tal till text** för att prova anslutningen praktiskt.

**Obs:** Ett lyckat sparande av nyckel och region är inte i sig bevis på att Azure Speech fungerar. Genomför alltid ett transkriberingstest.

## Testa taligenkänningen

Gör detta **innan du köper Premium**.

1. Kontrollera att datorn är ansluten till internet och att mikrofonen fungerar i Windows.
2. Öppna **Tal till text** i Key2Voice.
3. Välj **mikrofon** som ljudkälla och välj **svenska** som inkommande talspråk (språkval görs under Inställningar).
4. Starta transkriberingen med fönstrets startkommando.
5. Läs upp en tydlig mening, exempelvis: *”Det här är ett test av taligenkänningen i Key2Voice.”*
6. Kontrollera att text visas i transkriberingsfönstret.
7. Avsluta transkriberingen med stoppkommandot.

Om du får begriplig text från ditt tal har du verifierat den grundläggande kedjan **mikrofon → Key2Voice → Azure Speech → text**. Testa gärna flera meningar och normalt taltempo. Ett enstaka lyckat test garanterar inte att alla ljudmiljöer eller språk fungerar lika bra.

**Om testet misslyckas:** Kontrollera nyckel, region, Azure-resursens status, internetanslutning, mikrofonbehörighet och vald ljudkälla. Se [Felsökning](#felsökning). Köp inte Premium i hopp om att det ska lösa Azure- eller mikrofonproblem.

## Tal till text – daglig användning

I Key2Voice för Windows använder du **Tal till text** för att omvandla tal från mikrofon, systemljud eller WAV-fil till text.

### Välj ljudkälla

Key2Voice kan transkribera tal från flera källor:

- **Mikrofon:** tal som fångas av en mikrofon ansluten till datorn.
- **Systemljud:** tal som spelas upp på datorn, exempelvis i en video eller annan applikation.
- **WAV-fil:** tal som redan finns i en ljudfil i ett format som Key2Voice stöder.

Välj rätt källa i **Tal till text** innan du startar. För systemljud måste datorn spela upp ljud från rätt enhet. För WAV väljer du en kompatibel fil i den filväljare som visas. Om en fil inte kan öppnas, kontrollera filformatet; att en fil har ändelsen `.wav` garanterar inte att dess ljudkodning stöds.

### Starta, stoppa och fortsätt

1. Välj ljudkälla (språk väljs under Inställningar).
2. Starta transkriberingen.
3. Följ den text som visas medan talet behandlas.
4. Stoppa när du är klar.
5. När du har stoppat transkriberingen kan du redigera texten, spara den eller visa den i undertextfönstret. Se [Spara och hantera transkriptioner](#spara-och-hantera-transkriptioner) för hur du hämtar och fortsätter ett sparat dokument.

Taligenkänningens kvalitet påverkas av bakgrundsljud, mikrofon, taltydlighet, språkval och Azure-tjänstens tillgänglighet.

## Språk och översättning

Key2Voice har separata val för **inkommande talspråk** och **utgående textspråk**. De implementerade språkvalen omfattar **svenska, engelska, franska och tyska**.

- Vill du ha svensk text från svenskt tal, välj **svenska** för båda.
- Vill du få svensk text från exempelvis engelskt tal, välj **engelska** som inkommande språk och **svenska** som utgående textspråk.
- Kontrollera resultatet innan du använder en översättning i ett viktigt sammanhang. Automatiska översättningar kan innehålla fel.

**Automatiskt språkval** ska inte förutsättas fungera i denna version; välj ett uttryckligt språk. Översättning kan innebära ytterligare behandling i Azure och omfattas av Microsofts aktuella villkor och prissättning.

## Spara och hantera transkriptioner

I **Tal till text** kan du skapa, namnge, spara, återuppta, redigera, kopiera, radera och överföra sparade transkriptioner. De sparas i det lokala krypterade valvet, inte som fristående textfiler. Fönstret innehåller bland annat knapparna **Start**, **Stopp**, **Rensa**, **Spara**, **Spara som**, **Hämta**, **Ta bort** och **Undertexter**.

### Skapa och spara en transkription

1. Välj ljudkälla och starta transkriberingen med **Start**.
2. Följ texten medan talet känns igen. Under pågående transkribering är textfältet skrivskyddat.
3. Välj **Stopp** när du är klar. Därefter kan du korrigera texten direkt i textfältet.
4. Välj **Spara**. För en ny transkription får du ange ett namn. Dokumentet lagras då i valvet.
5. Om du vill behålla originalet och skapa en **separat kopia**, välj **Spara som**, ange ett nytt namn och spara. Den nya kopian blir det aktiva dokumentet.

**Skillnaden mellan Spara och Spara som:** När ett sparat dokument redan är aktivt uppdaterar **Spara** samma dokument, medan **Spara som** skapar ett nytt dokument med ett nytt ID. Ett dokumentnamn måste innehålla 1–120 tecken och får inte innehålla kontrolltecken.

### Hämta, redigera och fortsätta

1. Stoppa en eventuell pågående transkribering.
2. **Hämta** är tillgängligt först när textfältet är tomt. Spara därför först eventuella ändringar som du vill behålla och välj sedan **Rensa**. **Rensa tar bort texten från arbetsytan utan att radera ett redan sparat dokument ur valvet.** Osparad text kan däremot gå förlorad.
3. Välj **Hämta**. Dialogen visar sparade dokument med namn och senaste ändringstid.
4. Markera **ett** dokument och välj **Öppna**. Dokumentets text visas i arbetsytan.
5. Redigera vid behov och välj **Spara** för att uppdatera dokumentet, eller **Spara som** för att skapa en separat kopia.
6. Du kan även välja ljudkälla och trycka **Start** för att fortsätta transkribera. Ny igenkänd text läggs till i arbetsytan. Stoppa och spara när du är klar.

Om **Hämta** är inaktivt, kontrollera att ingen transkribering eller lagringsåtgärd pågår och att textfältet är tomt.

### Ta bort sparade dokument

- **Ta bort** i huvudfönstret för Tal till text gäller det **aktiva sparade dokumentet**. Programmet begär bekräftelse.
- I dialogen **Hämta** kan du markera **ett eller flera** dokument och välja **Ta bort**. En bekräftelse visas innan borttagningen.
- Borttagning ur valvet är inte samma sak som **Rensa** på arbetsytan. Kontrollera urvalet noggrant och se till att du har en aktuell säkerhetskopia om dokumenten är viktiga.

### Visa text som undertexter

Välj **Undertexter** för att öppna ett separat fönster med **stor, tydlig text som uppdateras i realtid** medan tal transkriberas. Texten **rullar automatiskt** så att den senaste texten hålls synlig. Fönstret kan användas som ett lättläst stöd vid samtal eller uppspelning av tal. Det visar texten men sparar inte dokumentet; använd **Spara** eller **Spara som** i **Tal till text** för att bevara transkriptionen.

### Exportera valda transkriptioner till en annan installation

I dialogen **Hämta** kan du markera ett eller flera sparade dokument och välja **Exportera valda**. Funktionen skapar en krypterad synkfil (**.k2s**) med **endast de valda transkriptionerna**, avsedd för import i en annan Key2Voice-installation.

1. Kontrollera att Windows-installationen har en giltig **Premium**-rättighet och att valvet är öppet.
2. Öppna **Hämta** från en tom arbetsyta och markera önskade dokument. Du behöver inte öppna ett av dem.
3. Välj **Exportera valda**, ange filplats och ett separat **fillösenord** samt bekräfta lösenordet.
4. Överför synkfilen säkert och använd mottagarens **Synkimport** för att läsa in den.

**Viktigt:** Selektiv transkriptionsexport innehåller **inte** Azure Speech-nyckeln eller andra konfigurationsuppgifter. Den är inte en fullständig säkerhetskopia. Vill du överföra Azure-konfiguration till iPhone använder du i stället den vanliga **Synkexport** i huvudfönstret och gör ett uttryckligt val att inkludera Azure-uppgifterna.

**Synkimport är inte en vanlig filöppning:** importen har säkerhetskontroller för avsändare, innehåll och tidigare importerade paket. En synkfil kan nekas om den redan importerats eller om mottagarvalvet innehåller ett objekt med samma identitet men annat innehåll. Försök inte kringgå kontrollen genom att återställa förtroende eller radera data utan att först utreda orsaken.

Sparade transkriptioner kan innehålla personliga eller känsliga uppgifter. Dela dem endast med avsedda mottagare och gör regelbundna portabla säkerhetskopior om de är viktiga.

## Basic och Premium

Key2Voice för Windows har två licensnivåer:

| Funktion | Basic | Premium |
|---|---|---|
| Installera och prova grundläggande taligenkänning med eget Azure Speech | Ja | Ja |
| Använda Azure Speech | Ja, med egen fungerande Azure-resurs | Ja, med egen fungerande Azure-resurs |
| Portabel export/import för säkerhetskopiering och återställning | Ja | Ja |
| Skapa krypterad **Synkexport** för iPhone | Nej | Ja |
| Använda iPhone-/Watch-kompanjonen efter korrekt synkimport | Kräver synkfil skapad från Windows Premium | Ja, via synkexport |

**Premium ger inte automatiskt tillgång till ett Azure-konto och betalar inte dina Azure-kostnader.**

### Innan du köper Premium

Verifiera först i **Basic** att din egen Azure Speech-resurs fungerar i praktiken, helst genom att transkribera flera meningar med den ljudkälla du tänker använda. Köp **inte** Premium förrän detta har lyckats och du har bedömt att Key2Voice motsvarar dina behov.

### Köpa och kontrollera Premium

Premium köps via Microsoft Store-funktionen i Key2Voice. Öppna programmets licens- eller **Om Key2Voice**-vy och följ anvisningarna för uppgradering. Köp och rättighet kontrolleras av Microsoft Store; ett köpkvitto eller en återställd databas är inte ensamt ett bevis på att Premium är aktivt på den aktuella installationen.

Om ett köp slutförts men Premium ännu inte kan bekräftas kan Key2Voice visa **Kontrollera Premium igen**. Den funktionen kontrollerar ett redan genomfört köp utan att starta ett nytt. Om den inte visas eller problemet kvarstår, kontrollera Microsoft Store-kontot och kontakta support utan att skicka betalningshemligheter.

## Synkronisera med iPhone och Apple Watch

Key2Voice för iPhone kan använda en **krypterad synkfil** från Windows för att få den konfiguration som behövs. **Azure Speech-uppgifter följer inte med automatiskt:** du måste uttryckligen välja att inkludera dem vid vanlig Synkexport. **Synkexport från Windows kräver Premium.** iPhone- och Watch-apparna har inte ett separat Premium-köp.

### Skapa synkfil i Windows

1. Kontrollera att Azure Speech fungerar i Windows och att Premium är aktivt.
2. Öppna Key2Voices huvudfönster och välj **Synkexport**.
3. Välj plats för den krypterade synkfilen (`.k2s`). I lösenordsdialogen anger och bekräftar du ett starkt **fillösenord** som är skilt från valvpassfrasen.
4. Markera uttryckligen **Inkludera Azure Speech-uppgifter** om du vill att iPhone ska få din Azure-konfiguration. Valet är avmarkerat från början och programmet kräver ytterligare bekräftelse för export av sådana uppgifter. Låt övriga val vara oförändrade om du inte har ett särskilt behov av dem.
5. För över filen till iPhone på ett sätt du själv kontrollerar, exempelvis via en lämplig filöverföringsfunktion. Förvara fillösenordet separat och säkert.

I Basic visas Synkexport som en "grå" Premiumfunktion men kan inte användas för att skapa en ny synkfil.

### Importera på iPhone

1. Installera Key2Voice för iPhone enligt aktuell distributionsanvisning.
2. Gör synkfilen tillgänglig på iPhone, exempelvis i appen **Filer**.
3. Öppna Key2Voice och välj dess funktion för **Synkimport**.
4. Välj `.k2s`-filen och ange det fillösenord du valde vid exporten.
5. Kontrollera att konfigurationen har importerats och prova appens funktioner.

I normal användning körs Azure-bearbetningen från iPhone; Windows behöver inte vara igång efter en lyckad initial synkronisering. **Apple Watch är en kompanjon till iPhone och ska inte beskrivas som en fristående Azure-klient.** Tillgängliga Watch-funktioner och iPhone-anslutning kan bero på installerad version och enheternas konfiguration.

För detaljerade skärmbilder och Watch-användning kommer en separat **Key2Voice iOS-användarmanual** att finnas under `Key2Voice/iOS/`.

### Synkfingeravtryck – kontrollera avsändaren

En synkfil kan innehålla viktiga inställningar och skyddad information. Key2Voice använder därför ett **synkfingeravtryck**, en identifierare som är knuten till avsändarens kryptografiska identitet. Fingeravtrycket hjälper mottagaren att kontrollera **vem synkfilen kommer från** innan importen godkänns. Det är **inte** ett fingeravtryck från ditt finger och används inte som biometrisk inloggning.

1. Öppna **Visa synkfingeravtryck** i Key2Voice på Windows-datorn som skapar synkfilen.
2. Förmedla fingeravtrycket till mottagaren genom en **separat, betrodd kanal** – exempelvis genom att jämföra det direkt med mottagaren, inte enbart genom att läsa samma uppgift ur synkfilen.
3. Vid den första synkimporten på iPhone: jämför det fingeravtryck som visas där med avsändarens fingeravtryck.
4. **Godkänn endast om de överensstämmer och du känner igen avsändaren.** Om uppgifterna skiljer sig åt eller avsändaren är okänd, avbryt importen och undersök orsaken.

Fingeravtrycket är ett stöd för att bekräfta avsändaridentiteten. Det ersätter **inte** skyddet med fillösenord eller behovet av att hantera synkfilen säkert. Vid byte av avsändaridentitet kan ett nytt fingeravtryck behöva verifieras.

## Säkerhetskopiering och återställning

Key2Voice har **portabel export och import** för säkerhetskopiering och återställning av databasen. Funktionen kan användas i både **Basic och Premium**.

### Skapa en portabel säkerhetskopia

1. Öppna Key2Voices huvudfönster.
2. Välj funktionen för **portabel export**.
3. Välj lagringsplats och filnamn enligt dialogen.
4. Ange och bekräfta ett **separat lösenord för säkerhetskopian** och bevara det på en säker plats.
5. Kontrollera att filen skapats och förvara den skyddat, gärna skilt från datorn.

### Återställ från en portabel säkerhetskopia

1. Se till att du har säkerhetskopian (`.k2b`) och **lösenordet som användes när filen skapades**. Du kan även behöva **passfrasen till valvet som säkerhetskopian innehåller**; den är inte nödvändigtvis samma som lösenordet till säkerhetskopian.
2. Öppna Key2Voice på den installation där uppgifterna ska återställas.
3. Välj funktionen för **portabel import** och peka ut filen.
4. Ange säkerhetskopians lösenord när programmet begär det. Om det återställda valvet inte kan öppnas med den nuvarande valvpassfrasen kan du behöva ange **den gamla valvpassfrasen**.
5. Läs bekräftelsen noga: återställningen **ersätter det aktuella valvet och relevanta inställningar** i stället för att slå samman innehållet. Kontrollera därefter att data och inställningar har återställts.

**Viktigt:** Återställning av en databas som tidigare använts med Premium innebär **inte** att en ny Windows-installation automatiskt får en giltig Premiumlicens. Microsoft Store-rättigheter och andra licensbevis verifieras separat. **En Basic-installation kan återställa en portabel databas som exporterats från en Premium-installation**, men förblir Basic om ingen giltig Premiumrättighet finns.

En portabel säkerhetskopia och en synkfil har olika syften: **portabel export** används för återställning av databasen; **Synkexport** används för konfigurationsöverföring till iPhone. Förväxla inte filerna eller deras lösenord.

## Inställningar och Om Key2Voice

Klicka på **Mer…** i **övre högra hörnet av huvudfönstret** och välj **Inställningar**. Där hanterar du bland annat Azure Speech-uppgifter, språkval, utseende och valvets säkerhetsinställningar.

### Valvkryptering

Under **Inställningar → Valvkryptering** finns följande funktioner:

- **Kräv lösenfras vid start:** När alternativet är aktiverat behöver du ange valvpassfrasen vid start eller när valvet ska öppnas, i stället för att använda en tidigare sparad passfras. Det ger ett extra skydd om någon annan får tillgång till datorn. **Behåll alltid en säker kopia av passfrasen.**
- **Byt lösenfras:** Byter passfrasen för det befintliga valvet. Programmet begär den nuvarande passfrasen och den nya passfrasen med bekräftelse. Valvets krypterade innehåll uppdateras så att den nya passfrasen används. Säkerställ att du har en aktuell portabel säkerhetskopia och avbryt inte åtgärden medan den pågår.
- **Förnya KDF:** Förnyar valvets parametrar för den lösenordsbaserade nyckelhärledningen utan att du behöver byta själva passfrasen. Programmet begär valvpassfrasen och arbetar därefter med valvets krypteringsskydd. Det kan ta en stund; vänta på programmets bekräftelse. **KDF-värdena i huvudfönstret** visar parametrarna efter åtgärden.
- **Visa synkfingeravtryck:** Visar en identifierare som kan användas för att kontrollera avsändaren vid synkronisering mellan installationer. Jämför fingeravtryck via en betrodd kanal innan du godkänner en ny avsändare.
- **Återställ betrodda synkavsändare:** Rensar listan över avsändare som tidigare godkänts för synkimport. Därefter behöver avsändare godkännas på nytt. Detta är en säkerhetsåtgärd, **inte** en metod för att kringgå ett importfel.

**Viktigt:** Byte av valvpassfras och förnyelse av KDF påverkar åtkomsten till krypterade uppgifter. Starta inte sådana åtgärder utan att först ha säkerställt att du kan återställa ditt valv från en aktuell portabel säkerhetskopia. Stäng inte av datorn medan åtgärden pågår.

Under **Mer… → Om Key2Voice** hittar du information om programmet och aktuell licensstatus samt vägar till support och eventuellt Premium-köp. Kontrollera alltid licensstatus i själva programmet efter köp eller återställning.

## Felsökning

| Problem | Kontrollera först |
|---|---|
| Ingen transkriberad text visas | Att transkriberingen är startad, rätt ljudkälla vald och ljud faktiskt kommer in. |
| Mikrofonen fungerar inte | Mikrofonanslutning, Windows mikrofonbehörigheter och vald inmatningsenhet. |
| Azure-anslutning misslyckas | Internet, exakt Speech-nyckel, rätt region, resursstatus och aktiv Azure-prenumeration. |
| Texten får fel språk | Inkommande talspråk och utgående textspråk i Key2Voice. |
| Systemljud ger ingen text | Kontrollera att ljud faktiskt spelas upp på datorn och att rätt ljudkälla och uppspelningsenhet är valda. |
| WAV-filen kan inte läsas | Att filen är en riktig, kompatibel WAV-fil med stödd ljudkodning. |
| Synkexport eller Exportera valda är inaktiverad | Om Windows-licensen verkligen är Premium, valvet är öppet och (för Exportera valda) minst ett dokument är markerat. |
| iPhone kan inte importera synkfil | Att rätt `.k2s`-fil och dess fillösenord används, samt att avsändarens fingeravtryck och eventuella importbekräftelser hanteras korrekt. |
| Premium syns inte efter köp | Kontrollera Store-konto, tillgänglig rättighetskontroll och eventuell funktion **Kontrollera Premium igen**. |
| Portabel import misslyckas | Rätt `.k2b`-fil, säkerhetskopians lösenord, eventuell gammal valvpassfras och programmets felmeddelande. |
| Hämta är inaktiverat | Stoppa transkriberingen, spara osparade ändringar och välj **Rensa** så att arbetsytan är tom. |
| Synkimport avvisar ett tidigare paket eller ett befintligt objekt | Kontrollera felmeddelandet. Återimport av samma paket och objektkonflikter kan blockeras av säkerhetsskäl; ändra inte förtroende eller radera valvdata som genväg. |

Vid kvarstående problem: notera programversion, Windows-version, vad du gjorde och exakt felmeddelande. **Skicka aldrig Azure-nyckel, valvpassfras, synk-/exportlösenord eller känsliga transkriptioner till support.**

## Säkerhet och integritet

- Key2Voice använder lokalt krypterat valv för användarstyrd lagring och konfiguration.
- **Tal som behandlas med Azure Speech skickas till Microsofts molntjänst.** Detta är inte offline-transkribering. Läs Microsofts aktuella villkor och integritetsinformation.
- Skydda Azure-nycklar och lösenord; förvara säkerhetskopior på ett tryggt sätt.
- Dela inte synkfiler eller portabla exportfiler med obehöriga, även om de är krypterade.
- Använd inte automatiskt transkriberad eller översatt text som enda underlag för viktiga medicinska, juridiska eller säkerhetskritiska beslut.
- Microsofts molntjänster och Windows kan behandla information enligt sina respektive villkor och integritetspolicyer.

## Uppdatering och support

Microsoft Store kan erbjuda uppdateringar av Key2Voice. Gör gärna en **portabel säkerhetskopia före större uppdateringar**, särskilt om dina sparade transkriptioner är viktiga. Avinstallera eller radera inte programmets lokala data utan att först ha säkerställt att du kan återställa dem.

För frågor, felrapporter och synpunkter: **[contact@eureka.nu](mailto:contact@eureka.nu)**. Ange gärna programversion och en kort beskrivning av problemet, men aldrig hemliga uppgifter.

### Dokument och länkar

- [Azure Speech-guide – skapa och konfigurera ett Azure-konto](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto)
- [Microsoft Azure-portalen](https://portal.azure.com/)
- [Microsoft Azure AI Speech – dokumentation](https://learn.microsoft.com/azure/ai-services/speech-service/)
- [Microsoft Azure – priser](https://azure.microsoft.com/pricing/)
