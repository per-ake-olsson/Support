#### Integritetspolicy för Key2Voice för Windows

Denna kompletterande integritetsinformation beskriver **Key2Voice-specifik hantering av ljud, text och lokalt lagrade uppgifter**. Eureka Consulting AB:s generella personuppgiftspolicy beskriver bland annat hur personuppgifter hanteras vid kontakt och support, vilka rättigheter du har och hur du kontaktar oss i integritetsfrågor.

**1. Taligenkänning och molnbehandling**  
När du använder taligenkänning eller översättning överför Key2Voice ljud och nödvändiga uppgifter för behandlingen till **Microsoft Azure Speech**, med den Azure Speech-resurs som du själv har konfigurerat. Taligenkänningen är därför inte en renodlat lokal funktion. Information om Microsofts behandling, lagring och villkor finns i Microsofts dokumentation för Azure Speech och i villkoren för din Azure-prenumeration.

**2. Ljudkällor och transkriptioner**  
Du väljer själv när Key2Voice ska behandla tal från mikrofon, systemljud eller WAV-fil. Den transkriberade texten kan innehålla personuppgifter eller andra känsliga uppgifter, beroende på vad som sägs eller spelas upp. Du ansvarar för att använda funktionen med hänsyn till berörda personers integritet och tillämpliga regler.

**3. Lokal lagring och skydd**  
Key2Voice använder ett lokalt krypterat valv för konfiguration och sparade uppgifter, bland annat transkriptioner som du väljer att spara. Skydda valvets lösenord och gör säkerhetskopior om uppgifterna är viktiga. Eureka Consulting AB kan inte återskapa en förlorad privat valvpassfras.

**4. Synkronisering och säkerhetskopiering**  
Med Premium kan du skapa en krypterad synkfil för överföring av inställningar till iPhone eller för export av utvalda transkriptioner. Azure Speech-uppgifter inkluderas i den vanliga synkexporten endast om du uttryckligen väljer detta; de ingår inte i selektiv transkriptionsexport. Portabel export och import kan användas för säkerhetskopiering och återställning även i Basic. Du hanterar själv filerna, deras lösenord och hur de överförs eller förvaras. Synkfingeravtrycket används för att kontrollera avsändaridentiteten vid synkimport.

**5. Andra tjänsters behandling av uppgifter**  
Windows, Microsoft Store och Microsoft Azure kan behandla uppgifter enligt respektive tjänsts villkor och integritetsinformation. För information om Microsofts hantering av ljud och annan data vid användning av Azure Speech, se dokumentationen och villkoren för din egen Azure-prenumeration.

**6. Generell personuppgiftspolicy**  
För behandling av personuppgifter i samband med support, kontakt med Eureka Consulting AB och dina rättigheter hänvisar vi till den generella policyn:

> [Personuppgiftspolicy för Eureka Consulting AB](https://www.eureka.nu/personuppgiftspolicy)

Mer information om molntjänsten finns i [Microsofts dokumentation för Azure AI Speech](https://learn.microsoft.com/azure/ai-services/speech-service/).
