# Integritetspolicy för Key2Voice iOS

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
