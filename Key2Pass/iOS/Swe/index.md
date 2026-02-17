## **Key2Pass** - Password Generator
Copyright 2026 Eureka Consulting AB

Key2Pass är ett offlineverktyg för deterministisk lösenordsgenerering. Windows‑versionen skapar en krypterad aliasdatabas som iOS‑appen kan importera för att återgenerera identiska lösenord lokalt på enheten.

Denna sida innehåller supportinformation med kontaktuppgifter, testdata och integritetspolicy för Key2Pass iOS

---

#### Kontakt för support eller synpunkter
Kontakta oss via epost:

[support@eureka.nu](mailto:support@eureka.nu)

---

#### Testdata och instruktioner för TestFlight testare
Ladda ner testdatabas och testunderlag via zip:en som du når via länken nedan. Öppna zip:en och spara båda filerna i Filer. Därifrån kan du importera databasen till Key2Pass appen, via knappen "Importera databas" på inställningssidan. Testdata är endast avsedda för testning och ska inte användas i produktionsmiljö. Observera att denna testversion av Key2Pass bör användas i ljust skärmläge, mörkt läge fungerar ännu bristfälligt. Test och återkoppling önskas avseende funktionalitet och användbarhet.

[Ladda ner testdatabas och testunderlag](https://per-ake-olsson.github.io/Support/Key2Pass/Win/Swe//downloads/key2pass-portable_testflight.zip)

---

#### Integritetspolicy gällande Key2Pass för iOS

**1. Övergripande systembeskrivning**  
Key2Pass består av en Windows‑applikation där du skapar alias och genererar en krypterad databas, samt en iOS‑app som kan importera denna databas för att generera identiska lösenord, associerat till ett alias. Du exporterar databasen från Windows‑versionen till en fil som du själv överför till din iOS‑enhet och importerar i appen. Överföringen sker manuellt – Key2Pass samlar inte in några personuppgifter, skickar ingen information till externa servrar och erbjuder inga köp eller upplåsningar via App Store.

**2. Vilka uppgifter lagras i appen**  
Appen lagrar endast de alias du skapar samt den krypterade databasen med dessa alias och en intern master‑nyckel. Uppgifterna behandlas lokalt på respektive enhet och används enbart för lösenordsgenerering. Key2Pass samlar inte in personuppgifter, platsdata eller användningsstatistik. Key2Pass använder inga tredjeparts‑SDK:er, analysverktyg eller spårningstjänster.

**3. Kryptering och säkerhet**  
Den exporterade databasen är krypterad (AES‑CBC/GCM med stark nyckelderivering) och kan endast öppnas med det lösenord du sätter. Vi har ingen åtkomst till innehållet. Data lagras lokalt på dina enheter tills du själv raderar databasen och avinstallerar appen.

**4. Kontakt och support**  
När du kontaktar oss via supportsidan för att rapportera fel eller ge feedback behandlar vi de personuppgifter du lämnar (t.ex. namn, e‑postadress och meddelandetext) för att kunna hantera ditt ärende. Denna behandling följer vår generella personuppgiftspolicy.

**5. Lagring och radering**  
Vi sparar inga kopior av dina alias eller lösenord. Uppgifter som du skickar via supportkanalen sparas endast så länge det behövs för att hantera ditt ärende och enligt vad som anges i den generella policyn.

**6. Länk till generell policy**  
Mer information om hur Eureka Consulting AB behandlar personuppgifter, dina rättigheter och kontaktuppgifter till dataskyddsansvarig finns i vår fullständiga personuppgiftspolicy.

> **Generell policy:** [Personuppgiftspolicy för Eureka Consulting AB](https://www.eureka.nu/personuppgiftspolicy)
