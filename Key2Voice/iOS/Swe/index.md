## **Key2Voice** – Tal till text och översättning
Copyright 2026 Eureka Consulting AB

Key2Voice för iPhone eller iPad hjälper dig att följa tal genom att visa det som läsbar text i realtid. Appen använder mikrofonen på iPhone eller iPad för taligenkänning och kan översätta mellan de språk som stöds. Du kan även spara och hantera transkriptioner. **Apple Watch kan användas tillsammans med iPhone** som ett frivilligt komplement för att läsa den aktuella texten och starta eller stoppa taligenkänningen. iPhone sköter ljudinsamling och talbehandling även när du använder Apple Watch.

**Key2Voice för iPhone och iPad är gratis** och har inget separat Premium-köp. För att använda appen behöver du först konfigurera Key2Voice för Windows och importera en krypterad synkfil med nödvändiga uppgifter till iPhone eller iPad. **Synkexport från Windows kräver Premium**. Du behöver också en egen fungerande **Microsoft Azure Speech-resurs** och internetanslutning. Azure är en separat tjänst som kan medföra kostnader; Windows Premium inkluderar inte Azure-prenumeration eller Azure-förbrukning. Azure-uppgifter följer bara med den vanliga synkexporten om du uttryckligen väljer att inkludera dem.

Denna sida innehåller användnings- och supportinformation, dokumentation, kontaktuppgifter och integritetspolicy för Key2Voice för iPhone och iPad samt Apple Watch som komplement till iPhone. Välj någon av länkarna nedan för mer information.

### Dokumentation

**Användarmanual för Key2Voice för Windows**  
Beskriver bland annat konfiguration av Azure Speech och hur du skapar en synkfil för iPhone och iPad. Manualen gäller Windows-versionen; den är inte en separat iOS-manual.  
[Läs Windows-manualen](https://per-ake-olsson.github.io/Support/Key2Voice/Win/Swe/downloads/Key2Voice_manual_Swe)

**Skapa ett Microsoft Azure-konto och en Speech-resurs**  
Separat guide för att skapa Azure-konto, prenumeration och Speech-resurs.  
[Läs Azure-guiden](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto)

**Licensavtal för slutanvändare (EULA)**  
*Länk för läsning och nedladdning läggs till när relevant avtal finns tillgängligt.*

---

#### Kontakt för support eller synpunkter

Kontakta oss via e-post:

[contact@eureka.nu](mailto:contact@eureka.nu)

Beskriv gärna problemet och vilken programversion du använder. Skicka **inte** valvpassfraser, Azure-nycklar, synkfilslösenord eller känsligt innehåll från transkriptioner.

---

#### Integritetspolicy för Key2Voice för iPhone, iPad och Apple Watch

Denna kompletterande integritetsinformation beskriver **Key2Voice-specifik hantering av ljud, text och lokalt lagrade uppgifter** på iPhone, iPad och Apple Watch. Eureka Consulting AB:s generella personuppgiftspolicy beskriver bland annat hur personuppgifter hanteras vid kontakt och support, vilka rättigheter du har och hur du kontaktar oss i integritetsfrågor.

**1. Taligenkänning och molnbehandling**  
När du startar taligenkänning eller översättning skickar Key2Voice ljud och nödvändiga uppgifter från iPhone eller iPad till **Microsoft Azure Speech**, med den Azure Speech-resurs som du har konfigurerat. Taligenkänningen sker alltså inte enbart på enheten. Microsofts villkor och integritetsinformation för Azure Speech och din prenumeration gäller för molntjänstens behandling.

**2. Ljud och transkriberad text**  
Du väljer själv när iPhone eller iPad ska börja eller sluta lyssna för taligenkänning. Den text som visas eller sparas kan innehålla personuppgifter eller känslig information beroende på vad som sägs. Använd funktionen med hänsyn till berörda personers integritet och tillämpliga regler.

**3. Lokal lagring och skydd**  
Key2Voice använder ett lokalt krypterat valv på iPhone eller iPad för konfiguration och appuppgifter, inklusive transkriptioner som sparas. Uppgifterna skyddas av appens valvhantering och iOS säkerhetsfunktioner. Förvara synkfiler och deras lösenord säkert; Eureka Consulting AB kan inte återskapa förlorade privata lösenord.

**4. Synkronisering och överföring**  
iPhone och iPad kan importera en krypterad synkfil som skapats i Key2Voice för Windows. Importen använder kontroller av filens avsändare och integritet. Synkfilen överförs av användaren; detta är inte en automatisk molnsynkronisering via Eureka Consulting AB. Azure Speech-uppgifter inkluderas i en vanlig synkexport från Windows endast efter ett uttryckligt val och ingår inte i en selektiv export av transkriptioner. Skydda synkfilen och dess lösenord.

**5. Apple Watch och andra tjänster**  
Om du använder Apple Watch tillsammans med iPhone skickar iPhone aktuell transkriberad text och sessionsstatus till klockan. Klockan kan skicka kommandon för att starta och stoppa taligenkänningen på iPhone. Apple Watch utför inte egen Azure-taligenkänning och får inte Azure-nycklar eller ett eget valv med transkriptionshistorik genom denna funktion. Apple och Microsoft kan behandla uppgifter enligt sina respektive tjänsters villkor och integritetsinformation.

**6. Generell personuppgiftspolicy**  
För behandling av personuppgifter i samband med support, kontakt med Eureka Consulting AB och dina rättigheter hänvisar vi till den generella policyn:

> [Personuppgiftspolicy för Eureka Consulting AB](https://www.eureka.nu/personuppgiftspolicy)

Mer information om molntjänsten finns i [Microsofts dokumentation för Azure AI Speech](https://learn.microsoft.com/azure/ai-services/speech-service/).
