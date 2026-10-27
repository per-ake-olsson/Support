# Key2Voice Windows – användarmanual

**Eureka Consulting AB**  
**Svenskt original – första utkast, version 0.1 (27 oktober 2026)**

> **Viktigt innan du börjar:** Key2Voice använder Microsofts molntjänst **Azure Speech** för taligenkänning och översättning. Du behöver en fungerande egen Azure Speech-resurs, rätt region och en giltig nyckel samt internetanslutning för att använda dessa funktioner. Azure är en separat tjänst som kan medföra kostnader. **Köp inte Key2Voice Premium innan du har konfigurerat din egen Azure Speech-resurs och verifierat att taligenkänningen fungerar i Key2Voice Basic.**
>
> Behöver du skapa Microsoft-konto, Azure-prenumeration eller Speech-resurs? Följ den separata svenska guiden **Skapa ett Microsoft Azure-konto**. Den här manualen beskriver hur du använder ett redan skapat Azure-konto i Key2Voice.

## Syfte

Key2Voice hjälper dig att omvandla tal till läsbar text. Windows-versionen är huvudplattformen: här konfigurerar du Azure Speech, använder **Tal till text**, hanterar dina transkriptioner och gör säkerhetskopior. Med Premium kan du även skapa en krypterad synkfil för iPhone-appen. Den här manualen gäller den vanliga **Windows Production-versionen**, inte utvecklings- och testfunktioner.

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

Du behöver en Windows-dator där Key2Voice kan installeras, en fungerande internetanslutning och en egen Azure Speech-resurs. För tal från mikrofon behöver du en mikrofon som fungerar i Windows. För ljud från datorn behöver rätt ljudkälla vara tillgänglig.

**Azure och Key2Voice är två skilda tjänster.** Key2Voice Premium är en licens för programfunktioner; den omfattar **inte** Azure-prenumeration eller förbrukningskostnader. Kontrollera Microsofts aktuella villkor och priser i Azure-portalen.

### Om du inte redan har Azure Speech

Läs först **Skapa ett Microsoft Azure-konto** (svensk separat guide i `Key2Voice/Azure/Swe/`). Den visar hur du skapar Microsoft-konto vid behov, registrerar dig för Azure, ordnar en prenumeration, skapar en Speech-resurs och hittar dess nyckel och region. Återvänd sedan hit.

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

**Viktigt:** Om du förlorar passfrasen kan återställning av krypterade uppgifter vara omöjlig. Eureka Consulting AB kan inte återskapa din privata passfras. Gör regelbundna säkerhetskopior enligt avsnittet nedan.

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
3. Välj **mikrofon** som ljudkälla och välj **svenska** som inkommande talspråk (görs i Inställningar).
4. Starta transkriberingen med fönstrets startkommando.
5. Läs upp en tydlig mening, exempelvis: *”Det här är ett test av taligenkänningen i Key2Voice.”*
6. Kontrollera att text visas i transkriberingsfönstret.
7. Avsluta transkriberingen med stoppkommandot.

Om du får begriplig text från ditt tal har du verifierat den grundläggande kedjan **mikrofon → Key2Voice → Azure Speech → text**. Testa gärna flera meningar och normalt taltempo. Ett enstaka lyckat test garanterar inte att alla ljudmiljöer eller språk fungerar lika bra.

**Om testet misslyckas:** Kontrollera nyckel, region, Azure-resursens status, internetanslutning, mikrofonbehörighet och vald ljudkälla. Se [Felsökning](#felsökning). Köp inte Premium i hopp om att det ska lösa Azure- eller mikrofonproblem.

## Tal till text – daglig användning

I Windows versionen är **Tal till text** den tillgängliga talfunktionen.

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
5. Använd funktionerna för att spara, hämta, redigera och fortsätta med tidigare transkriptioner när det är lämpligt.

Taligenkänningens kvalitet påverkas av bakgrundsljud, mikrofon, taltydlighet, språkval och Azure-tjänstens tillgänglighet.

## Språk och översättning

Key2Voice har separata val för **inkommande talspråk** och **utgående textspråk**. De implementerade språkvalen omfattar **svenska, engelska, franska och tyska**.

- Vill du ha svensk text från svenskt tal, välj **svenska** för båda.
- Vill du få svensk text från exempelvis engelskt tal, välj **engelska** som inkommande språk och **svenska** som utgående textspråk.
- Kontrollera resultatet innan du använder en översättning i ett viktigt sammanhang. Automatiska översättningar kan innehålla fel.

**Automatiskt språkval** ska inte förutsättas fungera i denna version; välj ett uttryckligt språk. Översättning kan innebära ytterligare behandling i Azure och omfattas av Microsofts aktuella villkor och prissättning.

## Spara och hantera transkriptioner

Key2Voice kan hantera transkriberad text så att du kan återvända till den.

1. Kontrollera innehållet innan du sparar.
2. Använd **Spara** när du vill bevara transkriptionen.
3. Använd programmets funktion för att **hämta** en tidigare transkription när du vill läsa eller fortsätta den.
4. Du kan **redigera text manuellt** och spara dina ändringar.
5. När du fortsätter transkribera, kontrollera att nytt innehåll hamnar i rätt sammanhang innan du sparar på nytt.

Sparade transkriptioner kan innehålla personliga eller känsliga uppgifter. Var därför försiktig med vad du spelar in och delar. Säkerhetskopiera valvet om texterna är viktiga.

## Basic och Premium

Key2Voice för Windows har två licensnivåer:

| Funktion | Basic | Premium |
|---|---|---|
| Installera och prova grundläggande taligenkänning med eget Azure Speech | Ja | Ja |
| Använda Azure Speech | Ja, med egen fungerande Azure-resurs | Ja, med egen fungerande Azure-resurs |
| Portabel export/import för säkerhetskopiering och återställning | Ja | Ja |
| Skapa krypterad **Synkexport** för iPhone | Nej | Ja |
| Använda iPhone-/Watch-kompanjonen efter korrekt synkimport | Kräver synkfil skapad från Windows Premium | Ja, via synkexport |

**Premium ger inte tillgång till ett Azure-konto och betalar inte dina Azure-kostnader.**

### Innan du köper Premium

Verifiera först i **Basic** att din egen Azure Speech-resurs fungerar i praktiken, helst genom att transkribera flera meningar med den ljudkälla du tänker använda. Köp **inte** Premium förrän detta har lyckats och du har bedömt att Key2Voice motsvarar dina behov.

### Köpa och kontrollera Premium

Premium köps via Microsoft Store-funktionen i Key2Voice. Öppna programmets licens- eller **Om Key2Voice**-vy och följ anvisningarna för uppgradering. Köp och rättighet kontrolleras av Microsoft Store; ett köpkvitto eller en återställd databas är inte ensamt ett bevis på att Premium är aktivt på den aktuella installationen.

Om ett köp slutförts men Premium ännu inte kan bekräftas kan en nyare version visa **Kontrollera Premium igen**. Den funktionen kontrollerar ett redan genomfört köp utan att starta ett nytt. Om den inte visas eller problemet kvarstår, kontrollera Microsoft Store-kontot och kontakta support utan att skicka betalningshemligheter.

## Synkronisera med iPhone och Apple Watch

Key2Voice för iPhone använder en **krypterad synkfil** från Windows för att få den konfiguration som behövs, inklusive Azure Speech-uppgifter. **Synkexport från Windows kräver Premium.** iPhone- och Watch-apparna har inte ett separat Windows-Premium-köp.

### Skapa synkfil i Windows

1. Kontrollera att Azure Speech fungerar i Windows och att Premium är aktivt.
2. Öppna Key2Voices huvudfönster och välj **Synkexport**.
3. Följ dialogens instruktioner för att skapa en krypterad synkfil (`.k2s`).
4. Ange ett starkt **fillösenord** när programmet begär det. Förvara lösenordet säkert.
5. För över filen till iPhone på ett sätt du själv kontrollerar, exempelvis via en lämplig filöverföringsfunktion.

I Basic visas Synkexport som en Premiumfunktion men kan inte användas för att skapa en ny synkfil.

### Importera på iPhone

1. Installera Key2Voice för iPhone enligt aktuell distributionsanvisning.
2. Gör synkfilen tillgänglig på iPhone, exempelvis i appen **Filer**.
3. Öppna Key2Voice och välj dess funktion för **Synkimport**.
4. Välj `.k2s`-filen och ange det fillösenord du valde vid exporten.
5. Kontrollera att konfigurationen har importerats och prova appens funktioner.

I normal användning körs Azure-bearbetningen från iPhone; Windows behöver inte vara igång efter en lyckad initial synkronisering. **Apple Watch är en kompanjon till iPhone och ska inte beskrivas som en fristående Azure-klient.** Tillgängliga Watch-funktioner och iPhone-anslutning kan bero på installerad version och enheternas konfiguration.

För detaljerade skärmbilder och Watch-användning kommer en separat **Key2Voice iOS-användarmanual** att finnas under `Key2Voice/iOS/`.

## Säkerhetskopiering och återställning

Key2Voice har **portabel export och import** för säkerhetskopiering och återställning av databasen. Funktionen kan användas i både **Basic och Premium**.

### Skapa en portabel säkerhetskopia

1. Öppna Key2Voices huvudfönster.
2. Välj funktionen för **portabel export**.
3. Välj lagringsplats och filnamn enligt dialogen.
4. Ange det exportlösenord som efterfrågas och bevara det på en säker plats.
5. Kontrollera att filen skapats och förvara den skyddat, gärna skilt från datorn.

### Återställ från en portabel säkerhetskopia

1. Se till att du har den portabla exportfilen och **lösenordet som användes när filen skapades**.
2. Öppna Key2Voice på den installation där uppgifterna ska återställas.
3. Välj funktionen för **portabel import** och peka ut filen.
4. Ange exportfilens lösenord när programmet begär det.
5. Följ eventuella bekräftelser och kontrollera sedan att dina data och inställningar har återställts.

**Viktigt:** Återställning av en databas som tidigare använts med Premium innebär **inte** att en ny Windows-installation automatiskt får en giltig Premiumlicens. Microsoft Store-rättigheter och andra licensbevis verifieras separat. **En Basic-installation kan återställa en portabel databas som exporterats från en Premium-installation**, men förblir Basic om ingen giltig Premiumrättighet finns.

En portabel säkerhetskopia och en synkfil har olika syften: **portabel export** används för återställning av databasen; **Synkexport** används för konfigurationsöverföring till iPhone. Förväxla inte filerna eller deras lösenord.

## Inställningar och Om Key2Voice

I **Inställningar** hanterar du bland annat Azure Speech-uppgifter, språkval och tillgängliga säkerhets-/programinställningar. Vilka alternativ som visas kan bero på version och produktionsprofil.

I **Om Key2Voice** hittar du information om programmet och aktuell licensstatus samt vägar till support och eventuellt Premium-köp. Kontrollera alltid licensstatus i själva programmet efter köp eller återställning.

## Felsökning

| Problem | Kontrollera först |
|---|---|
| Ingen transkriberad text visas | Att transkriberingen är startad, rätt ljudkälla vald och ljud faktiskt kommer in. |
| Mikrofonen fungerar inte | Mikrofonanslutning, Windows mikrofonbehörigheter och vald inmatningsenhet. |
| Azure-anslutning misslyckas | Internet, exakt Speech-nyckel, rätt region, resursstatus och aktiv Azure-prenumeration. |
| Texten får fel språk | Inkommande talspråk och utgående textspråk i Key2Voice. |
| Systemljud ger ingen text | Att ljud spelas på datorn och att rätt systemljudkälla används. |
| WAV-filen kan inte läsas | Att filen är en riktig, kompatibel WAV-fil med stödd ljudkodning. |
| Synkexport är inaktiverad | Om Windows-licensen verkligen är Premium och valvet är i rätt tillstånd. |
| iPhone kan inte importera synkfil | Att rätt `.k2s`-fil och dess fillösenord används. |
| Premium syns inte efter köp | Kontrollera Store-konto, tillgänglig rättighetskontroll och eventuell funktion **Kontrollera Premium igen**. |
| Portabel import misslyckas | Rätt exportfil, rätt exportlösenord och programmets felmeddelande. |

Vid kvarstående problem: notera programversion, Windows-version, vad du gjorde och exakt felmeddelande. **Skicka aldrig Azure-nyckel, valvpassfras, synk-/exportlösenord eller känsliga transkriptioner till support.**

## Säkerhet och integritet

- Key2Voice använder lokalt krypterat valv för användarstyrd lagring och konfiguration.
- **Tal som behandlas med Azure Speech skickas till Microsofts molntjänst.** Detta är inte offline-transkribering. Läs Microsofts aktuella villkor och integritetsinformation.
- Skydda Azure-nycklar och lösenord; förvara säkerhetskopior på ett tryggt sätt.
- Dela inte synkfiler eller portabla exportfiler med obehöriga, även om de är krypterade.
- Använd inte automatiskt transkriberad eller översatt text som enda underlag för viktiga medicinska, juridiska eller säkerhetskritiska beslut.
- Den ordinarie Production-versionen ska inte automatiskt skapa egna diagnostikloggar; det utesluter inte Microsofts eller operativsystemets egen tjänstebehandling.

## Uppdatering och support

Microsoft Store kan erbjuda uppdateringar av Key2Voice. Gör gärna en **portabel säkerhetskopia före större uppdateringar**, särskilt om dina sparade transkriptioner är viktiga. Avinstallera eller radera inte programmets lokala data utan att först ha säkerställt att du kan återställa dem.

För frågor, felrapporter och synpunkter: **[support@eureka.nu](mailto:support@eureka.nu)**. Ange gärna programversion och en kort beskrivning av problemet, men aldrig hemliga uppgifter.

### Dokument och länkar

- **Skapa ett Microsoft Azure-konto** – separat svensk Azure-guide i `Support/Key2Voice/Azure/Swe/` (lägg in publicerad länk när dokumentets slutliga placering är fastställd).
- [Microsoft Azure-portalen](https://portal.azure.com/)
- [Microsoft Azure AI Speech – dokumentation](https://learn.microsoft.com/azure/ai-services/speech-service/)
- [Microsoft Azure – priser](https://azure.microsoft.com/pricing/)
- [Key2Voice – Support-repositoriet](https://github.com/per-ake-olsson/Support)

---

## Redaktionsanmärkning – tas bort före publicering

Detta är **första utkastet** till svensk originalmanual. Granska menytexter, knappar och navigering mot det aktuella **Windows Production-paketet** innan dokumentet publiceras som slutlig manual. Särskilt behöver steg för valvstart, filväljare, exakta start-/stoppknappar, licensdialog och iOS-import kompletteras med verifierade skärmbilder. Guiden för Azure-konto bör få en beständig relativ eller publik länk när den lagts i Support.

**Viktig teknisk iakttagelse från Support-repot:** Nuvarande `.github/workflows/md-to-pdf.yml` bevakar och konverterar endast `Key2Pass/Win/Swe/downloads/*.md` och `Key2Pass/Win/Eng/downloads/*.md`. Det genererar **inte automatiskt PDF** för Key2Voice-filer. Arbetsflödet behöver utökas separat innan automatisk PDF-generering för `Key2Voice/Win/Swe/downloads/Key2Voice_manual_Swe.md` fungerar. Detta dokument ändrar inte workflowet.

**Föreslagen filplacering:** `Key2Voice/Win/Swe/downloads/Key2Voice_manual_Swe.md`.
