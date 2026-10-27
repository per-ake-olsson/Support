# Kom igång med Azure Speech i Key2Voice

**Användarguide – svensk version, utkast 1.0**  
**Senast granskad:** 27 oktober 2026  
**Avsedd plats i Support-repot:** `Key2Voice/Azure/Swe/Azure-Speech-guide.md`  
**Status:** Första kompletta textutkastet. Kontrollera skärmtexter i aktuell Key2Voice-version och genomför ett praktiskt portaltest före publicering.

> **Kort sammanfattning:** Key2Voice använder Microsofts molntjänst Azure Speech för att omvandla tal till text och, när du väljer olika tal- och textspråk, översätta tal. Du behöver en egen Azure-prenumeration och en Speech-resurs. Du anger resursens **nyckel** och **region** i Key2Voice. Azure-användningen kan medföra kostnader som faktureras av Microsoft separat från en eventuell Key2Voice Premium-licens.

## Innehåll

1. [Vad är Azure Speech?](#1-vad-är-azure-speech)
2. [Innan du börjar](#2-innan-du-börjar)
3. [Skapa eller välj en Azure-prenumeration](#3-skapa-eller-välj-en-azure-prenumeration)
4. [Förstå kostnaderna](#4-förstå-kostnaderna)
5. [Skapa en Speech-resurs](#5-skapa-en-speech-resurs)
6. [Hämta nyckel och region](#6-hämta-nyckel-och-region)
7. [Konfigurera Key2Voice för Windows](#7-konfigurera-key2voice-för-windows)
8. [Testa taligenkänning och översättning](#8-testa-taligenkänning-och-översättning)
9. [Använd Key2Voice på iPhone och Apple Watch](#9-använd-key2voice-på-iphone-och-apple-watch)
10. [Skydda din Azure-resurs och dina uppgifter](#10-skydda-din-azure-resurs-och-dina-uppgifter)
11. [Felsökning](#11-felsökning)
12. [Avsluta eller ändra tjänsten](#12-avsluta-eller-ändra-tjänsten)
13. [Officiella Microsoft-källor](#13-officiella-microsoft-källor)

---

## 1. Vad är Azure Speech?

Azure Speech är en tjänst från Microsoft som kan känna igen tal och omvandla det till text. Tjänsten har även stöd för talöversättning mellan vissa språk. Key2Voice använder Azure Speech för de talfunktioner som kräver molnbaserad taligenkänning.

I Key2Voice kan du exempelvis:

- Visa tal som text i realtid från mikrofon eller, i Windows, från systemljud.
- Transkribera ljud från WAV-filer i format som Key2Voice stöder.
- Välja ett **inkommande talspråk** och ett **utgående textspråk**. När språken skiljer sig åt används Azure Speech-översättning.
- Använda iPhone som mobil följeslagare och visa text på en kompatibel Apple Watch.

Vilka funktioner som visas beror på plattform och produktions-/utvecklingsversion. Alla Azure Speech-funktioner är inte tillgängliga i varje Key2Voice-app.

**Viktigt:** Key2Voice tillhandahåller inte något gemensamt Azure-konto. Du skapar och administrerar din egen Azure-resurs. Microsofts Azure-avgifter är separata från Key2Voice Basic/Premium.

## 2. Innan du börjar

Du behöver:

- En dator med internetanslutning och en fungerande webbläsare.
- Ett Microsoft-konto eller ett arbets-/skolkonto som kan användas med Azure.
- En aktiv Azure-prenumeration som tillåter att du skapar Speech-resurser.
- Key2Voice för Windows installerat och ett öppet Key2Voice-valv för att spara konfigurationen.
- Behörighet i Azure att skapa resurser. På ett företagskonto kan en administratör behöva hjälpa dig.

Ha gärna två fönster öppna: Azure-portalen i webbläsaren och Key2Voice. **Kopiera aldrig din hemliga Speech-nyckel till e-post, chatt, skärmbilder eller supportärenden.**

> **Observera:** Microsoft ändrar ibland namn och placering för menyer i Azure-portalen. Guiden beskriver den vanliga arbetsgången. Om gränssnittet ser annorlunda ut, använd portalens sökfunktion och kontrollera Microsofts officiella instruktioner i kapitel 13.

## 3. Skapa eller välj en Azure-prenumeration

En **Azure-prenumeration** är den administrativa och ekonomiska behållare där Microsoft samlar dina molnresurser och deras förbrukning. Den är inte samma sak som Key2Voice Premium.

1. Öppna [Azure-portalen](https://portal.azure.com/) och logga in.
2. Sök efter **Prenumerationer** (*Subscriptions*).
3. Kontrollera om du redan har en aktiv prenumeration som du får använda.
4. Om du saknar prenumeration, följ Microsofts aktuella väg för att skapa en. Du kan behöva lämna betalningsuppgifter och bekräfta identitet; tillgängliga erbjudanden varierar.
5. Notera vilken prenumeration du tänker använda. Du behöver inte skriva in prenumerations-ID i Key2Voice.

**Om du använder ett arbets- eller skolkonto:** organisationens policy kan begränsa vilka resursregioner, tjänster och prisnivåer du får välja. Be administratören om hjälp om en resurs inte går att skapa.

**Om du redan har en Speech-resurs:** du behöver normalt inte skapa en till. Fortsätt till kapitel 6 och kontrollera att resursen är av rätt typ och att du har tillgång till dess nyckel och region.

## 4. Förstå kostnaderna

### 4.1 Två olika kostnader

**Key2Voice Premium** är en produktlicens för Key2Voice. **Azure Speech** är en separat Microsoft-tjänst vars användning kan faktureras via din Azure-prenumeration. Att köpa Premium innebär inte att Azure Speech ingår utan extra kostnad.

### 4.2 Prisnivåer

Microsoft beskriver bland annat prisnivåerna **Free (F0)** och **Standard (S0)** för Azure Speech. Gratisnivån har begränsningar och månadsgränser; vilka funktioner och mängder som ingår ska kontrolleras på Microsofts aktuella prissida. Alla prisnivåer eller erbjudanden är inte nödvändigtvis tillgängliga för varje konto och prenumeration.

**Välj inte Standard (S0) utan att först kontrollera vad användningen kan kosta.** Den exakta kostnaden beror på tjänst, användningsmängd, region, prisnivå och gällande Microsoftvillkor. Denna guide anger därför inga fasta priser eller löften om kostnadsfri användning.

- [Microsofts prissida för Azure Speech](https://azure.microsoft.com/pricing/details/cognitive-services/speech-services/)
- [Kvoter och begränsningar](https://learn.microsoft.com/sv-se/azure/ai-services/speech-service/speech-services-quotas-and-limits)

### 4.3 Skapa en budget och varning

Vi rekommenderar att du gör detta **innan du börjar använda Key2Voice regelbundet**:

1. Sök efter **Cost Management + Billing** eller **Kostnadshantering** i Azure-portalen.
2. Välj rätt prenumeration och öppna området för **Budgets/Budgetar**.
3. Skapa en budget med ett belopp och en period som passar dig.
4. Ange e-postadress och tröskelvärden för varningar.
5. Kontrollera senare den faktiska förbrukningen i Cost Management.

> **Mycket viktigt:** En Azure-budget och dess varningar **stoppar inte automatiskt förbrukningen** när budgeten överskrids. Om du vill förhindra fortsatt användning måste du själv hantera resursen eller införa en separat, verifierad begränsningsmekanism. Se [Microsofts budgetguide](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets).

## 5. Skapa en Speech-resurs

Du behöver en Azure-resurs som ger åtkomst till **Azure Speech**. Microsofts produktnamn och portalgränssnitt kan även använda benämningar som *Speech* eller *Foundry Tools*.

1. Logga in på [Azure-portalen](https://portal.azure.com/).
2. Använd sökfältet och sök efter **Speech**. Kontrollera att resurstypen uttryckligen stöder Azure Speech.
3. Välj att skapa en ny resurs (**Create/Skapa**).
4. Välj din **prenumeration**.
5. Välj en **resursgrupp** (*Resource group*). Du kan skapa en ny grupp, exempelvis `Key2Voice-Resources`, om din prenumeration tillåter det.
6. Välj en **region** där Azure Speech stöds. Välj med hänsyn till tillgänglighet och dina krav på databehandling; anteckna regionen.
7. Ge resursen ett unikt och beskrivande namn, exempelvis `key2voice-speech` om namnet är tillgängligt.
8. Välj önskad **prisnivå**, efter att du kontrollerat aktuella villkor och begränsningar.
9. Granska inställningarna och skapa resursen (**Review + create/Granska + skapa** eller motsvarande).
10. Vänta tills distributionen är klar och öppna resursen (**Go to resource/Gå till resurs**).

**Om du inte hittar rätt resurstyp:** avbryt hellre än att skapa en slumpmässig AI-tjänst. Kontrollera Microsofts aktuella [Speech-snabbstart](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/get-started-text-to-speech) och vilka resurstyper den stöder.

### Vilken region ska jag välja?

Regionen är inte bara ett geografiskt namn. Den har också en teknisk identifierare, exempelvis `westeurope` eller `northeurope` **om just den regionen erbjuds för din resurs**. Key2Voice behöver rätt regionidentifierare, inte ett godtyckligt svenskt visningsnamn. En nyckel som används med fel region kan ge autentiseringsfel.

Kontrollera stödda regioner i [Microsofts regionlista](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/regions).

## 6. Hämta nyckel och region

När Speech-resursen är skapad:

1. Öppna resursen i Azure-portalen.
2. Leta efter **Keys and Endpoint**, **Nycklar och slutpunkt** eller motsvarande resursinställning.
3. Identifiera **Key 1** eller **Key 2**. Det är hemliga autentiseringsnycklar.
4. Kopiera **en** nyckel till Key2Voice när du konfigurerar programmet. Spara den inte i ett öppet textdokument.
5. Kopiera eller anteckna den **regionidentifierare** som hör till samma Speech-resurs.

| Uppgift | Exempel eller förklaring | Behövs i Key2Voice? |
|---|---|---|
| Speech-nyckel | Hemlig teckensträng från Key 1 eller Key 2 | **Ja** |
| Region | Resursens regionidentifierare, t.ex. `westeurope` | **Ja** |
| Resursnamn | Namnet du gav resursen | Normalt nej |
| Prenumerations-ID | Administrativt Azure-ID | Normalt nej |
| Endpoint | Resursens tjänsteadress | Använd endast om aktuell Key2Voice-version uttryckligen efterfrågar den |

**Använd aldrig exempelvärden som riktiga inloggningsuppgifter.** Nyckel och region måste höra till samma resurs.

## 7. Konfigurera Key2Voice för Windows

> **Versionskontroll:** De exakta svenska fältnamnen och knapptexterna i detta kapitel behöver kontrolleras i den aktuella produktionsversionens inställningsfönster innan guiden publiceras. Arbetsgången nedan beskriver avsedd användning utan att påstå att varje menynamn är verifierat.

1. Starta Key2Voice för Windows.
2. Öppna ditt valv, eller skapa ett nytt om du använder Key2Voice för första gången.
3. Öppna **Inställningar** och leta upp inställningarna för **Azure Speech**.
4. Ange den **Speech-nyckel** du kopierade från Azure-portalen.
5. Ange den tillhörande **regionidentifieraren** exakt som Azure anger den.
6. Spara inställningarna enligt programmets anvisningar.
7. Återgå till **Tal till text** och gör ett kort funktionstest enligt kapitel 8.

Om Key2Voice visar ett anslutnings- eller autentiseringsfel: kontrollera först nyckeln, regionen, att resursen är aktiv och att datorn har internetanslutning. Du behöver **inte** skriva in lösenordet till ditt Microsoft-konto i Key2Voice.

### Basic och Premium

Key2Voice för Windows kan användas i **Basic** med de funktioner som är tillgängliga för den licensnivån. **Synkexport kräver Premium**. Däremot är **Synkimport** och **Portabel export/import** tillgängliga enligt befintligt licenskontrakt. Azure-kostnaderna är separata från detta.

## 8. Testa taligenkänning och översättning

### 8.1 Första testet: tal till text

1. Kontrollera att mikrofonen är ansluten och tillåten i Windows.
2. Öppna **Tal till text** i Key2Voice.
3. Välj **mikrofon** som ljudkälla om det behövs.
4. Välj **svenska** som inkommande talspråk och **svenska** som utgående textspråk.
5. Starta transkriberingen enligt programmets knappar.
6. Säg en tydlig, kort mening och kontrollera att text visas.
7. Avsluta sessionen.

Om ingen text visas: kontrollera att rätt mikrofon är vald, att den tar emot ljud och att Azure-uppgifterna är korrekta.

### 8.2 Testa översättning

1. Välj ett inkommande talspråk, exempelvis **svenska**.
2. Välj ett annat utgående textspråk som Key2Voice stöder, exempelvis **engelska**.
3. Starta en kort session och tala en enkel mening.
4. Kontrollera att text visas på det valda textspråket.

Detta verifierar den tekniska funktionen, **inte** att varje översättning är språkligt korrekt. Kontrollera viktiga uppgifter manuellt. Alternativet **Automatiskt** för talat språk ska inte betraktas som en aktiv produktionsfunktion om det inte uttryckligen är aktiverat i den version du använder.

### 8.3 Andra ljudkällor i Windows

Key2Voice stöder även **systemljud** och transkribering av **WAV-filer** i kompatibla format. Börja gärna med mikrofontestet, eftersom det ger en enklare felsökningsväg. För systemljud och WAV behöver rätt ljudkälla respektive fil väljas i Key2Voice.

## 9. Använd Key2Voice på iPhone och Apple Watch

Key2Voice för iPhone är en följeslagare till Windows-konfigurationen. Du kan överföra nödvändiga inställningar genom Key2Voices befintliga **Synkexport/Synkimport**.

1. Konfigurera och testa Azure Speech i Key2Voice för Windows.
2. Kontrollera att Windows-versionen har **Premium**, eftersom **Synkexport** kräver Premium.
3. Skapa en krypterad synkexport i Windows och välj ett starkt lösenord.
4. Överför synkfilen till din iPhone via en metod som du själv kontrollerar.
5. Importera synkfilen i Key2Voice för iPhone och ange lösenordet.
6. Kontrollera att inställningarna har importerats och testa taligenkänningen på iPhone.
7. Använd Apple Watch tillsammans med den kompatibla iPhone-appen när du vill se transkription på handleden.

**Viktigt:** Synkfilen kan innehålla känslig konfiguration, inklusive Azure-uppgifter. Behandla den som hemlig, skydda lösenordet separat och radera onödiga kopior. **Portabel backup för Windows är inte samma sak som synkfilen för iPhone och ska inte användas som iOS-import.**

Efter lyckad konfiguration behöver iPhone och Apple Watch inte någon fortlöpande kontakt med Windows för normal användning. Funktionerna är dock beroende av fungerande internet och Azure Speech där molnbehandling används. Apple Watch är en följeslagare till iPhone, inte en fristående Azure-klient.

## 10. Skydda din Azure-resurs och dina uppgifter

Din Azure Speech-nyckel ger åtkomst till din resurs och kan möjliggöra förbrukning som debiteras din prenumeration. Hantera den därför som ett lösenord:

- Dela inte nyckeln i e-post, chatt, offentliga GitHub-repositories eller supportärenden.
- Ta bort eller maskera nycklar i skärmbilder.
- Använd ett starkt lösenord för Key2Voice-valvet och för krypterade synk-/backupfiler.
- Håll operativsystem och Key2Voice uppdaterade.
- Följ upp användning och kostnader i Azure-portalen.
- Om du misstänker att en nyckel har röjts: **rotera nyckeln** i Azure-portalen och uppdatera Key2Voice på alla enheter som använder den.

Azure-resurser har normalt två nycklar så att en nyckel kan ersättas medan den andra används. **När en nyckel genereras om slutar dess tidigare värde att fungera.** Planera därför bytet så att du inte oavsiktligt bryter anslutningen för dina enheter. Se [Microsofts instruktion för nyckelrotation](https://learn.microsoft.com/en-us/azure/ai-services/rotate-keys).

### Sekretess och molnbehandling

Tal som skickas till Azure Speech behandlas av Microsofts molntjänst för att utföra den begärda funktionen. Läs Microsofts aktuella tjänstevillkor och integritetsinformation, särskilt om du tänker transkribera känsliga samtal. Undvik att använda tjänsten för information som du inte har rätt att behandla eller dela. Key2Voice ansvarar inte för din Azure-prenumeration eller Microsofts debitering.

## 11. Felsökning

| Symtom | Kontrollera först |
|---|---|
| Ingen text visas | Mikrofonval, mikrofonbehörighet, ljudnivå, internet och att transkribering faktiskt startats. |
| Autentiseringsfel | Att nyckeln är komplett och hör till rätt Speech-resurs och region. |
| Regionen accepteras inte | Använd teknisk regionidentifierare, inte översatt visningsnamn. |
| Resursen går inte att skapa | Prenumeration, behörighet, tillåten region, resurskvoter och aktuell tjänstetillgänglighet. |
| Azure rapporterar kvot-/begränsningsfel | Kontrollera prisnivå, kvoter, samtidig användning och förbrukning i Azure. |
| Taligenkänning fungerar men översättning inte | Kontrollera att in- och utgående språk är olika och stöds av vald funktion. |
| Synkexport är inaktiverad | Kontrollera Key2Voice Premium-licens i Windows. |
| iPhone fungerar inte efter import | Kontrollera att rätt synkfil importerats, att Azure-uppgifterna följt med och att internet finns. |
| Nyckeln slutade fungera efter byte | Uppdatera Key2Voice med den nya nyckeln på berörda enheter. |
| Oväntade Azure-kostnader | Kontrollera förbrukning, prisnivå och resurser i Cost Management; en budgetvarning stoppar inte tjänsten. |

**När du kontaktar support:** beskriv Key2Voice-version, plattform, vilken åtgärd som misslyckades och det synliga felmeddelandet. **Skicka aldrig Azure-nyckel, lösenord, komplett synkfil eller känsligt transkriptionsinnehåll.**

## 12. Avsluta eller ändra tjänsten

Om du inte längre vill använda Azure Speech:

1. Stoppa pågående transkribering i Key2Voice.
2. Kontrollera vilka andra appar eller enheter som använder samma Speech-resurs.
3. Granska förbrukning och fakturering i Azure-portalen.
4. Om du vill upphöra med resursen, följ Azure-portalens funktion för att ta bort **rätt Speech-resurs**. Bekräfta konsekvenserna innan du tar bort den.
5. Om du även vill avsluta hela Azure-prenumerationen, följ Microsofts särskilda instruktioner för prenumerationen. Att avinstallera Key2Voice avslutar **inte** automatiskt Azure-prenumerationen eller dess resurser.

Att ta bort en resurs kan göra att Key2Voice slutar fungera med de tidigare uppgifterna. Kontrollera också om du har kvar andra fakturerbara resurser i Azure.

## 13. Officiella Microsoft-källor

Kontrollera alltid dessa sidor för aktuell information. Microsoft kan ändra tjänstnamn, prisnivåer, gränser och portalsteg.

- [Azure-portalen](https://portal.azure.com/)
- [Azure Speech – snabbstart och resursförutsättningar](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/get-started-text-to-speech)
- [Azure Speech – regioner](https://learn.microsoft.com/en-us/azure/ai-services/speech-service/regions)
- [Azure Speech – priser](https://azure.microsoft.com/pricing/details/cognitive-services/speech-services/)
- [Azure Speech – kvoter och gränser](https://learn.microsoft.com/sv-se/azure/ai-services/speech-service/speech-services-quotas-and-limits)
- [Azure Cost Management – budgetar och varningar](https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets)
- [Azure AI-tjänster – rotera API-nycklar](https://learn.microsoft.com/en-us/azure/ai-services/rotate-keys)

---

## Publiceringskontroll – att slutföra innan guiden fastställs

Detta avsnitt är avsett för granskning och **ska tas bort eller flyttas till intern dokumentation före publik publicering**.

- [ ] Gå igenom Azure-portalen med ett konto som får skapa Speech-resurser; kontrollera faktiska svenska/engelska menybenämningar och tillgängliga resurstyper.
- [ ] Kontrollera aktuell prisinformation och om F0 erbjuds för det avsedda kontot och regionen. Undvik löften om gratis användning.
- [ ] Jämför kapitel 7 ord för ord med Key2Voice Windows Production: inställningssida, fältnamn, spara-knapp och felmeddelanden.
- [ ] Kontrollera faktiska steg för Synkexport och Synkimport mot aktuell Windows-/iOS-version.
- [ ] Kontrollera att samtliga länkar fungerar och att eventuella skärmbilder är fria från hemligheter.
- [ ] Verifiera att guidens instruktioner överensstämmer med Key2Voices aktuella säkerhets-, licens- och sekretessdokumentation.
- [ ] Genomför ett användartest med någon som inte redan är van vid Azure.
- [ ] Fastställ svensk version innan engelsk översättning påbörjas.

*Key2Voice – Eureka Consulting AB. Azure och Microsoft Store är Microsoft-tjänster. Key2Voice Premium och Azure-förbrukning är separata.*
