# Key2Voice iOS – användarmanual för iPhone, iPad och Apple Watch

**Eureka Consulting AB**    
**Svenskt original – arbetsversion 0.9 (5 november 2026)**

> **Viktigt innan du börjar:** Key2Voice för iPhone och iPad är gratis, men behöver en konfiguration som överförs från Key2Voice för Windows med en krypterad synkfil. **Synkexport i Windows kräver Premium.** För taligenkänning och översättning behövs dessutom en egen fungerande **Microsoft Azure Speech-resurs** och internetanslutning. Azure är en separat tjänst som kan medföra kostnader; Premium betalar inte Azure-förbrukningen.
>
> Om du ännu inte har en Azure Speech-resurs, läs [**guiden för att skapa Microsoft Azure-konto och Speech-resurs**](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto). Konfigurera och testa först Azure Speech i **Windows Basic** innan du överväger Premium.

## Syfte

Key2Voice omvandlar tal till läsbar text på **iPhone och iPad**. Appen kan också översätta tal mellan valda språk, visa texten som lättlästa undertexter och spara transkriptioner. **Apple Watch är ett frivilligt komplement till iPhone**: klockan visar aktuell text och kan starta eller stoppa taligenkänningen på telefonen. iPhone står för mikrofon, Azure-anslutning och lagring; klockan arbetar inte fristående.

Den här manualen gäller **iOS-appen och dess Apple Watch-komplement**. För Windows-installation, Premium-köp, Azure-inställningar och skapande av den första synkfilen, se [**Windows-manualen**](https://per-ake-olsson.github.io/Support/Key2Voice/Win/Swe/downloads/Key2Voice_manual_Swe).

## Innehåll

1. [Innan du börjar](#innan-du-börjar)
2. [Installation](#installation)
3. [Första starten och synkimport](#första-starten-och-synkimport)
4. [Tal till text – daglig användning](#tal-till-text--daglig-användning)
5. [Språk och översättning](#språk-och-översättning)
6. [Undertexter](#undertexter)
7. [Spara och hantera transkriptioner](#spara-och-hantera-transkriptioner)
8. [Apple Watch](#apple-watch)
9. [Inställningar, synkexport och Om Key2Voice](#inställningar-synkexport-och-om-key2voice)
10. [Felsökning](#felsökning)
11. [Säkerhet och integritet](#säkerhet-och-integritet)
12. [Uppdatering och support](#uppdatering-och-support)

## Innan du börjar

Du behöver en kompatibel iPhone eller iPad med Key2Voice installerat, mikrofonbehörighet, internetanslutning och en fungerande Azure Speech-konfiguration. För den första konfigurationsöverföringen behöver du även Key2Voice för Windows med **Premium**, samt en krypterad synkfil (`.k2s`) som du själv överför till enheten.

**iPhone och iPad kräver inget eget Premium-köp.** Däremot är en nyinstallerad app inte färdigkonfigurerad förrän nödvändiga uppgifter importerats. Du behöver inte ha Windows-datorn igång vid normal användning efter en lyckad import.

### Förbered på Windows-datorn

1. Installera och starta Key2Voice för Windows.
2. Konfigurera din **egen** Azure Speech-nyckel och region. Testa i **Basic** att taligenkänningen fungerar.
3. När du vill överföra konfigurationen till iOS, se till att **Premium** är aktivt i Windows.
4. Välj **Synkexport** i Windows och skapa en krypterad `.k2s`-fil med ett separat, starkt **fillösenord**.
5. Du behöver överföra Azure Speech-uppgifterna, välj uttryckligen **Inkludera Azure Speech-uppgifter** och bekräfta valet. De följer inte med automatiskt.
6. Överför synkfilen till iPhone eller iPad, exempelvis till appen **Filer**. Förvara fillösenordet separat.
7. Öppna **Visa synkfingeravtryck** i Windows och notera avsändarens fingeravtryck. Jämför det med uppgiften som visas vid import på iOS, helst via en separat betrodd kanal.

**Observera:** En selektiv synkexport med enbart transkriptioner innehåller inte Azure-konfiguration och ersätter inte den vanliga synkexporten vid första installationen.

## Installation

1. Installera Key2Voice på iPhone eller iPad via den distributionskanal där appen erbjuds.
2. Öppna appen och ge **mikrofonbehörighet** när den begärs, om du vill transkribera tal.
3. Gör din krypterade synkfil tillgänglig på enheten, till exempel i **Filer**.
4. Fortsätt med **Synkimport** enligt nästa avsnitt.

Appens utseende och systemdialoger kan variera mellan iOS- och iPadOS-versioner. Apple Watch är valfri och behövs inte för att använda appen på iPhone eller iPad.

## Första starten och synkimport

Key2Voice använder ett **lokalt krypterat valv** för appens konfiguration och sparade uppgifter. iOS-appen hanterar sin lokala valvåtkomst med hjälp av enhetens skyddade lagring. **Vid första starten på en ny enhet skapar appen automatiskt ett tomt krypterat valv.** Den genererar själv en slumpmässig valvpassfras och lagrar den i iOS skyddade nyckellagring (Secure Storage). Du behöver alltså **inte ange eller välja ett eget valvlösenord** innan du gör synkimporten. Däremot måste du ange det **separata fillösenordet** för synkfilen vid import. Om ett tidigare valv finns kvar men dess skyddade valvpassfras saknas försöker appen inte skapa om valvet eller radera dess innehåll automatiskt.

1. Öppna **Inställningar** med kugghjulsikonen i Key2Voice.
2. Välj **Synkimport**.
3. Välj importkommandot och leta upp din `.k2s`-fil i filväljaren.
4. Ange **synkfilens fillösenord** från Windows-exporten. Det är inte nödvändigtvis samma lösenord som Windows-valvets passfras.
5. Om appen visar ett **synkfingeravtryck** för en ny eller ändrad avsändare, jämför det med fingeravtrycket från Windows. **Godkänn bara om de stämmer överens** och du känner igen avsändaren.
6. Om filen innehåller skyddade uppgifter kan appen be om särskilt samtycke och hur konflikter ska hanteras: **Behåll befintliga**, **Ersätt befintliga** eller **Avvisa befintliga**. Läs valet noga innan du fortsätter.
7. Vänta på bekräftelse om att importen lyckades. Gå tillbaka till **Tal till text** och prova funktionen.

### Om importen inte går igenom

Kontrollera att du valt rätt fil, rätt fillösenord och en synkfil med den konfiguration du behöver. Importen kan avvisas om paketet redan importerats, avsändaren inte godkänts eller uppgifter står i konflikt med befintligt innehåll. **Återställ inte förtroende eller radera data enbart för att kringgå ett importfel.** Kontrollera i stället felmeddelandet och avsändarens fingeravtryck.

## Tal till text – daglig användning

Huvudvyn **Läs** visar en statusrad, aktuell text och knappar för att styra transkriberingen.

1. Kontrollera att internetanslutningen fungerar och att appen har mikrofonbehörighet.
2. Välj önskat **inkommande talspråk** och **utgående textspråk** under **Inställningar**.
3. Tryck **Start** för att börja transkribera tal från enhetens mikrofon.
4. Läs texten medan den uppdateras. Appen visar status för den pågående sessionen.
5. Tryck **Stopp** när du vill avsluta.
6. Välj **Spara** om du vill behålla texten, eller **Rensa** för att tömma arbetsytan.

Knapparna **Starta**, **Stoppa**, **Rensa text**, **Spara**, **Spara som**, **Hämta**, **Radera** och **Stor text** finns i Läs-vyn. Layouten anpassas efter skärmens orientering.

**Viktigt:** Taligenkänning kräver Azure Speech och fungerar inte som en ren offlinefunktion. Resultatet påverkas av mikrofon, bakgrundsljud, taltydlighet, språkval och nätverksanslutning.

## Språk och översättning

Under **Inställningar** finns tre separata språkval:

- **Appens språk:** språk för appens menyer och texter; svenska eller engelska.
- **Språk att lyssna på:** det språk som talas i mikrofonen.
- **Språk att skriva till:** språket som den transkriberade eller översatta texten ska visas på.

De uttryckliga talspråken omfattar **svenska, engelska, franska och tyska**. Om du vill ha svensk text från svenskt tal väljer du svenska för både inkommande och utgående språk. För exempelvis engelskt tal som ska visas på svenska väljer du engelska som inkommande och svenska som utgående språk.

**Välj ett uttryckligt inkommande språk.** Förutsätt inte att automatisk språkidentifiering fungerar i den här versionen. Översättningar kan innehålla fel och bör kontrolleras innan de används i viktiga sammanhang.

## Stor text

Tryck **Stor text** i Läs-vyn för att öppna en separat vy som visar transkriberad text med större tecken. Vyn följer den aktuella transkriberingen och rullar så att ny text hålls synlig.

I vyn finns reglage för att **minska** eller **öka textstorleken** samt för att **stänga** vyn. Undertexter är en visningsfunktion; använd **Spara** i Läs-vyn om du vill behålla en transkription i valvet.

## Spara och hantera transkriptioner

Sparade transkriptioner hanteras i appens lokala krypterade valv.

### Spara och Spara som

1. Stoppa först pågående taligenkänning.
2. Välj **Spara** för att spara texten. För en ny transkription anger du ett dokumentnamn.
3. Om ett sparat dokument redan är aktivt uppdaterar **Spara** det dokumentet.
4. Välj **Spara som** om du vill skapa en separat kopia med nytt namn.

Spara-funktionerna är tillgängliga när en transkription har färdig text och ingen taligenkänning eller lagringsåtgärd pågår.

### Hämta och fortsätta

1. Stoppa taligenkänningen och spara sådant du vill behålla.
2. Välj **Rensa text** så att arbetsytan är tom. Rensa text tar bort text från arbetsytan, **inte** ett tidigare sparat dokument ur valvet. Osparad text kan gå förlorad.
3. Tryck **Hämta**. Ett **nytt fönster med en lista över sparade transkriptioner** öppnas. Där visas bland annat dokumentnamn och senaste ändringstidpunkt.
4. Tryck direkt på **ett dokument i listan** för att öppna det. Listfönstret stängs och dokumentets text visas i arbetsytan.
5. Du kan starta taligenkänningen igen för att fortsätta och sedan spara resultatet.

I listfönstrets normalläge öppnar ett tryck på ett dokument det dokumentet. För att i stället hantera flera dokument använder du **Markera**, enligt nedan.

### Markera, radera eller exportera flera transkriptioner

1. Öppna listan via **Hämta** och tryck **Markera**.
2. Välj **en eller flera transkriptioner** i listan. Du kan också välja **Markera alla** eller **Avmarkera alla**.
3. Välj **Exportera markerade** för att exportera urvalet, eller **Radera markerade** för att radera de valda dokumenten. Radering kräver bekräftelse.
4. Tryck **Avbryt** om du vill lämna markeringsläget utan att utföra någon åtgärd.

**Radera** i huvudvyn gäller i stället det **aktiva sparade dokumentet** och kräver också bekräftelse. **Rensa text** tömmer enbart arbetsytan; det raderar inte sparade dokument ur valvet.

### Exportera utvalda transkriptioner

Välj **Hämta → Markera**, markera dokumenten och tryck **Exportera markerade**. Ett exportfönster öppnas. Ange och bekräfta ett separat fillösenord och starta exporten. Den krypterade synkfilen delas därefter via enhetens delningsfunktion.

En sådan export innehåller de valda transkriptionerna, **inte** Azure Speech-nyckeln eller en fullständig säkerhetskopia av valvet.

## Apple Watch

Om du har en kompatibel Apple Watch kan du använda Key2Voice på klockan tillsammans med **iPhone**. Klockan är **inte nödvändig** för iPhone- eller iPad-användning och fungerar inte som en fristående Azure-klient.

1. Installera och öppna Key2Voice på iPhone och se till att synkimport och taligenkänning fungerar där.
2. Installera eller öppna den tillhörande Watch-appen enligt tillgänglig Apple Watch-distribution.
3. Starta **tal till text** från iPhone eller använd **Start** på klockan när anslutningen till iPhone fungerar och appen finns i förgrunden.
4. Läs den senaste transkriberade texten på klockan. Klockan visar även sessionens status.
5. Tryck **Stopp** på klockan eller iPhone för att avsluta.
6. Klockan fortsätter fungera så länge Key2Voice är igång på iPhone, även om appen kör i bakgrunden eller iPhone går in i viloläge. Du kan t ex ha iPhone i fickan och ändå läsa uppfattat tal på din Apple Watch.
7. Med Key2Voice aktiv på din Apple Watch kan du ändra texten storlek via kronhjulet.

**iPhone ansvarar för mikrofon, Azure-anslutning och lagring.** Apple Watch visar aktuell text och skickar start-/stoppkommandon; den lagrar inte en egen fullständig transkriptionshistorik och behöver ingen separat Azure-nyckel. Om klockan inte visar ny text, klicka först på skärmen för att "väcka" klockan, kontrollera därefter att iPhone-appen fungerar och att enheterna kan kommunicera.

## Inställningar, synkexport och Om Key2Voice

Öppna **Inställningar** via kugghjulet i huvudvyn. Där finns val för **appens språk**, **språk att lyssna på** och **språk att skriva till**, samt funktionerna **Importera synkdata**, **Visa synkfingeravtryck**, **Exportera synkdata** och **Om Key2Voice**.

### Visa synkfingeravtryck

**Visa synkfingeravtryck** visar **den här iPhone- eller iPad-installationens eget avsändarfingeravtryck**. Det används när **denna enhet exporterar** en synkfil som ska importeras på en annan enhet. Det är inte ett biometriskt fingeravtryck.

När du **importerar en synkfil från Windows** visas i stället **Windows-installationens avsändarfingeravtryck** i importens godkännandedialog. Jämför **det fingeravtrycket** med det som Windows visar under **Visa synkfingeravtryck**, helst via en separat betrodd kanal. **Det ska inte jämföras med iPhone-appens eget fingeravtryck; dessa två är normalt olika.** Godkänn bara en ny eller ändrad avsändare när du har verifierat rätt avsändarfingeravtryck.

### Exportera synkdata från iOS

Key2Voice för iPhone och iPad kan även skapa och dela en krypterad synkfil från den lokala installationen:

1. Öppna **Inställningar → Exportera synkdata**.
2. Ange ett starkt fillösenord och bekräfta det.
3. Om du har fått tillgång till en testlicens för Premium så kan du inkludera den i exporten genom att markera **Inkludera utvecklarlicenser** annars låter du den vara omarkerad
4. Starta exporten och välj hur filen ska delas eller sparas via iOS.
5. Förvara filen och fillösenordet säkert.

**Observera:** iOS-exporten är inte samma sak som Windows **portabla säkerhetskopia** (`.k2b`). iOS-appen erbjuder inte Windows-funktionen för fullständig portabel återställning. iOS-exportera synkdata ska inte heller användas som metod för att föra vidare Azure Speech-hemligheter; de ingår inte i den exporten.

### Om Key2Voice

Under **Inställningar → Om Key2Voice** hittar du information om appen, bland annat version och byggnummer samt länk till appens supportsidan med dokumentation och kontaktinformation.

## Felsökning

| Problem | Kontrollera först |
|---|---|
| Ingen text visas | Att **Start** har aktiverats, mikrofonbehörighet finns, internet fungerar och tal hörs av mikrofonen. |
| Taligenkänning kan inte starta | Att en giltig Azure Speech-konfiguration importerats, rätt region och nyckel används samt att Azure-resursen är aktiv. |
| Texten visas på fel språk | **Språk att lyssna på** och **språk att skriva till** under Inställningar. |
| Automatisk språkidentifiering fungerar inte | Välj ett uttryckligt inkommande talspråk. |
| Synkimport misslyckas | Rätt `.k2s`-fil och fillösenord, godkänt synkfingeravtryck samt eventuella importkonflikter. |
| Hämta är inaktivt | Stoppa sessionen och **Rensa** arbetsytan efter att ha sparat eventuell text. |
| Spara är inaktivt | Stoppa taligenkänningen och kontrollera att färdig transkriberad text finns. |
| Apple Watch visar ingen ny text | Klicka på Apple Watch skärm. Kontrollera att iPhone-appen fungerar och att Watch har kontakt med iPhone. |
| Stor text visar ingen ny text | Kontrollera att transkriberingen pågår och att ny text kommer in i Läs-vyn. |
| Synkexport misslyckas | Att fillösenorden matchar och att exporten kan slutföras via iOS delningsfunktion. |

Om problemet kvarstår: notera appversion, iOS-/iPadOS-version, vad du gjorde och vilket felmeddelande som visades. Skicka **aldrig** Azure-nycklar, valvhemligheter, synkfilslösenord eller känsliga transkriptioner till support.

## Säkerhet och integritet

- Tal som behandlas av **Azure Speech** skickas till Microsofts molntjänst. Key2Voice är inte en offlinebaserad taligenkänningstjänst.
- Konfiguration och sparade transkriptioner hanteras i ett **lokalt krypterat valv** på iPhone eller iPad.
- Synkfiler är krypterade, men ska ändå hanteras varsamt. Kontrollera avsändarens fingeravtryck vid import och skydda fillösenordet.
- Apple Watch används tillsammans med iPhone; aktuell text och sessionsstatus överförs till klockan. Watch hanterar inte egen Azure-konfiguration.
- Visa hänsyn till andra personer när du transkriberar samtal. Automatiskt igenkänd eller översatt text kan innehålla fel och bör inte vara enda underlag för medicinska, juridiska eller säkerhetskritiska beslut.
- Läs [**integritetspolicyn för Key2Voice iOS**](https://per-ake-olsson.github.io/Support/Key2Voice/iOS/Swe/downloads/Key2Voice_integritetspolicy_Swe.md) och Microsofts aktuella Azure-villkor.

## Uppdatering och support

Appuppdateringar erbjuds genom den distributionskanal där du installerat Key2Voice. Se till att du har tillgång till din Windows-konfiguration och en säkert förvarad synkfil innan du avinstallerar appen eller raderar dess data.

För frågor, felrapporter och synpunkter: **[contact@eureka.nu](mailto:contact@eureka.nu)**. Ange gärna appversion och en kort beskrivning av problemet, men aldrig hemliga uppgifter.

### Dokument och länkar

- [Key2Voice – Windows-användarmanual](https://per-ake-olsson.github.io/Support/Key2Voice/Win/Swe/downloads/Key2Voice_manual_Swe)
- [Azure Speech-guide – skapa konto och Speech-resurs](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto)
- [Microsoft Azure-portalen](https://portal.azure.com/)
- [Microsoft Azure AI Speech – dokumentation](https://learn.microsoft.com/azure/ai-services/speech-service/)
