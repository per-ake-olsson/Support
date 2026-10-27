# Guide: Skapa ett Microsoft Azure-konto och en Azure Speech-resurs

**För Key2Voice – svensk användarguide, utkast 1.1**  
**Senast faktagranskad:** 27 oktober 2026  
**Målgrupp:** Privatpersoner som inte tidigare har använt Microsoft Azure.  
**Syfte:** Hjälpa dig att skaffa tillgång till Azure och skapa en Speech-resurs. **Detta är inte en användarmanual för Key2Voice.**

## Viktig information – läs detta innan du börjar

**Den här guiden är endast ett frivilligt stöd** för dig som vill skapa ett Microsoft Azure-konto och en Azure Speech-resurs för användning med Key2Voice. Guiden är inte en del av Microsofts tjänst och utgör ingen garanti för att registreringen lyckas eller att tjänsten fungerar.

**Eureka Consulting AB ansvarar inte för att du lyckas skapa eller aktivera ett Microsoft-konto, en Azure-prenumeration eller en Azure Speech-resurs.** Eureka Consulting AB lämnar inte heller någon garanti för att Microsoft Azure Speech är tillgängligt, fungerar utan avbrott eller fungerar tillsammans med Key2Voice i din miljö. Registrering, tillgång, villkor, prissättning, drift och support för Azure-tjänsterna hanteras av Microsoft. Du ansvarar själv för ditt Azure-konto, dina inloggningsuppgifter, dina val av prenumeration och eventuella avgifter. Vid problem med registrering eller Azure-tjänsten behöver du i första hand kontakta Microsofts support.

**Ett fungerande eget Azure Speech-konto med en korrekt konfigurerad Speech-resurs krävs för att Key2Voices Azure-baserade talfunktioner ska fungera.** Utan fungerande åtkomst till Azure Speech kan Key2Voice inte användas för sitt avsedda ändamål med molnbaserad taligenkänning och översättning.

**Köp inte Key2Voice Premium innan du själv har verifierat att Key2Voice fungerar med ditt eget Azure Speech-konto.** Skapa och konfigurera först din Azure Speech-resurs, ange uppgifterna i Key2Voice och genomför ett lyckat praktiskt test av den funktion du behöver. Ett Premium-köp ger inte tillgång till ett Azure-konto och garanterar inte att Microsofts tjänst fungerar.

Denna information beskriver tjänsternas ansvarsfördelning och begränsningar. Den inskränker inte rättigheter som du kan ha enligt tvingande konsumentlagstiftning.

> **Viktigt om kostnader:** Azure är en tjänst från Microsoft. En del erbjudanden och förbrukningsnivåer kan vara kostnadsfria, men tjänster kan också medföra avgifter. Läs pris- och betalningsvillkoren som visas för just ditt konto innan du godkänner något. En budgetvarning stoppar **inte** automatiskt användningen eller debiteringen.

## 1. Vad ska vi göra?

Du behöver inte kunna programmera. Du ska i tur och ordning:

1. Kontrollera om du redan har ett **Microsoft-konto**, eller skapa ett.
2. Logga in på **Microsoft Azure** och registrera dig om du inte har tillgång sedan tidigare.
3. Kontrollera att du har en **Azure-prenumeration** som får användas för att skapa resurser.
4. Skapa en **Speech-resurs** – den del av Azure som erbjuder taligenkänning och översättning.
5. Hitta resursens **nyckel** och **region**. Dessa behövs senare när du konfigurerar Key2Voice.

### Fyra begrepp som är lätta att blanda ihop

| Begrepp | Enkel förklaring |
|---|---|
| Microsoft-konto | Din inloggning hos Microsoft, exempelvis en Outlook-adress eller en annan e-postadress som registrerats hos Microsoft. |
| Azure-konto/åtkomst | Möjligheten att logga in och använda Azure-portalen. Inloggning i sig ger inte alltid en aktiv prenumeration. |
| Azure-prenumeration | Den administrativa och ekonomiska ramen där Azure-tjänster används och faktureras. |
| Speech-resurs | Den specifika Azure-tjänst som du skapar för talfunktioner. Den har en region och autentiseringsuppgifter. |

**Har du redan en Azure-prenumeration?** Hoppa till kapitel 5. **Har du ett Microsoft-konto men aldrig använt Azure?** Börja i kapitel 3.

## 2. Kontrollera eller skapa ett Microsoft-konto

### 2.1 Kontrollera om du redan har ett

1. Öppna en webbläsare, exempelvis Microsoft Edge.
2. Skriv `https://account.microsoft.com/` i adressfältet och tryck **Enter**.
3. Välj **Logga in** (*Sign in*) om knappen visas.
4. Prova den e-postadress som du brukar använda för Microsofts tjänster. Följ anvisningarna på skärmen.
5. Om du kommer in på din kontosida har du redan ett fungerande Microsoft-konto. Fortsätt till kapitel 3.

> Ett Outlook.com-, Hotmail- eller Live-konto är normalt ett Microsoft-konto. Även andra e-postadresser kan vara registrerade som Microsoft-konton. Att du använder Windows betyder däremot inte säkert att du loggar in med ett Microsoft-konto; Windows kan använda ett lokalt konto.

Om du inte vet vilket konto du har, kontrollera först dina befintliga Microsoft-inloggningar. Skapa inte ett extra konto i onödan: det kan göra det svårare att hitta rätt Azure-prenumeration senare.

### 2.2 Skapa ett nytt Microsoft-konto

1. Öppna `https://account.microsoft.com/`.
2. Välj **Logga in** och därefter alternativet **Skapa ett konto** (*Create account*) om du inte redan har ett. Du kan också börja via `https://signup.live.com/`.
3. Följ Microsofts instruktioner. Du kan få möjlighet att använda en befintlig e-postadress eller skapa en ny Outlook-adress.
4. Välj ett starkt, unikt lösenord. Spara det i en betrodd lösenordshanterare.
5. Slutför eventuell kontroll av e-postadress, telefonnummer eller annan identitet enligt vad Microsoft visar.
6. Logga in på `https://account.microsoft.com/` och kontrollera att kontot fungerar.

**Rekommenderas:** Lägg till en säker metod för kontoåterställning och aktivera tvåstegsverifiering där det erbjuds. Dela aldrig engångskoder eller lösenord med andra.

**Kontrollpunkt:** Du kan logga in på Microsofts kontosida utan hjälp. Nu kan du fortsätta.

## 3. Registrera dig för Microsoft Azure

### 3.1 Börja på rätt webbplats

1. Öppna `https://azure.microsoft.com/free/`.
2. Läs erbjudandet som visas för ditt land och konto. Välj knappen för att komma igång med ett kostnadsfritt Azure-konto om du är berättigad, eller följ länken till ett annat lämpligt prenumerationsalternativ.
3. Logga in med ditt Microsoft-konto. Microsoft kan också erbjuda andra identitetsalternativ, men denna guide använder Microsoft-konto.

**Obs:** En ny användare kan vara berättigad till ett introduktionserbjudande. Belopp, giltighetstid och vilka tjänster som ingår bestäms av Microsoft och ska kontrolleras på registreringssidan. Om du tidigare haft Azure kan erbjudandet vara otillgängligt. Försök inte skapa flera konton för att kringgå villkor.

### 3.2 Fyll i dina uppgifter

Under registreringen kan Microsoft be om:

- Land/region och kontaktuppgifter.
- Namn och adress.
- Telefonnummer för identitetskontroll.
- Betalkort för identitets- eller betalningsverifiering.
- Godkännande av Microsofts avtal och villkor.

Fyll i **dina verkliga uppgifter**. Land/region och faktureringsadress ska överensstämma med dina faktiska förhållanden. Följ varje sida i den ordning den visas.

**Telefonkontroll:** Microsoft kan skicka en kod via SMS eller erbjuda samtalsverifiering. Tillgängliga alternativ kan variera. Om en metod inte fungerar, följ portalens anvisningar eller Microsofts felsökningsdokumentation.

**Kortkontroll:** Microsoft kan begära ett giltigt betal- eller kreditkort och göra en tillfällig kontrollreservation. Vilka kort som accepteras varierar. En kortkontroll är inte samma sak som ett löfte om att all framtida Azure-användning är gratis.

### 3.3 Läs villkoren innan du godkänner

Kontrollera särskilt:

1. Om du registrerar dig för ett kostnadsfritt introduktionserbjudande eller en betalprenumeration.
2. Om och när betalning för förbrukning kan börja.
3. Vilka villkor som gäller när ett eventuellt introduktionserbjudande löper ut.
4. Vilken betalningsmetod som är kopplad till kontot.

Godkänn endast om du förstår och accepterar villkoren. Om du är osäker, avbryt och läs Microsofts information innan du fortsätter.

### 3.4 Öppna Azure-portalen

1. Gå till `https://portal.azure.com/`.
2. Logga in med samma konto som vid registreringen.
3. Vänta tills Azure-portalen visas.

**Kontrollpunkt:** Du kan öppna Azure-portalen. Nästa steg är att kontrollera att en prenumeration finns och är användbar.

## 4. Kontrollera din Azure-prenumeration

### 4.1 Hitta prenumerationerna

1. Öppna `https://portal.azure.com/`.
2. Använd sökfältet högst upp i portalen och sök efter **Prenumerationer** (*Subscriptions*).
3. Öppna träffen som gäller Azure-prenumerationer.
4. Se om en prenumeration visas och kontrollera dess status.

Om du ser en **aktiv** prenumeration som du har behörighet att använda för att skapa resurser kan du fortsätta till kapitel 5.

### 4.2 Om ingen prenumeration visas

En inloggning till Azure är inte samma sak som en aktiv prenumeration. Kontrollera därför:

- Att du är inloggad med **samma konto** som användes vid registreringen.
- Om portalen visar flera kataloger (*directories/tenants*), att du tittar i rätt katalog och prenumerationsfilter.
- Om registreringen är helt slutförd eller fortfarande väntar på verifiering.

Om du fortfarande saknar prenumeration: gå tillbaka till `https://azure.microsoft.com/free/` och följ Microsofts vägledning för att skaffa en prenumeration. Välj bara ett erbjudande vars villkor du förstår. I vissa organisationer behöver en administratör ge dig tillgång; skapa då inte en privat betalprenumeration utan att först kontrollera med organisationen.

**Kontrollpunkt:** Du har identifierat den prenumeration som ska användas. Notera gärna dess **visningsnamn**, men skriv inte ned eller dela hemliga autentiseringsuppgifter.

## 5. Skapa en Speech-resurs

Det här steget skapar själva tjänsten för taligenkänning. Microsoft kan visa tjänsten under namn som **Speech**, **Azure AI Speech** eller **Speech i Foundry Tools**. Benämningar och formulär kan förändras. Följ i första hand Microsofts aktuella dokumentation om Speech-resurser.

### 5.1 Hitta tjänsten

1. Öppna Azure-portalen: `https://portal.azure.com/`.
2. Skriv **Speech** i portalens sökfält.
3. Välj en träff för att skapa en **Speech-resurs**. Om du hamnar i en produktöversikt, leta efter **Skapa** (*Create*).
4. Kontrollera att du skapar en resurs som stöder **Speech**, inte en orelaterad AI-tjänst eller ett annat abonnemang.

Om det är oklart vilken resurstyp du ser: använd Microsofts officiella snabbstart för Speech innan du går vidare (länk i kapitel 11).

### 5.2 Fyll i formuläret

Fältens namn kan variera. Vanliga val är:

| Fält | Vad du ska göra |
|---|---|
| Prenumeration (*Subscription*) | Välj den aktiva prenumerationen från kapitel 4. |
| Resursgrupp (*Resource group*) | Välj en befintlig resursgrupp som du äger, eller skapa en ny med ett begripligt namn, exempelvis `rg-key2voice`. |
| Region (*Region*) | Välj en region där Speech-funktionerna du behöver stöds. **Kom ihåg exakt region.** |
| Namn (*Name*) | Ange ett resursnamn enligt portalens regler, exempelvis `key2voice-speech`. Namnet kan behöva vara unikt. |
| Prisnivå (*Pricing tier*) | Kontrollera vilka nivåer som erbjuds, exempelvis **Free F0** eller **Standard S0**, och välj utifrån faktiska villkor och förväntad användning. |

**Viktigt om prisnivå:** F0 kan ha begränsningar och kanske inte är tillgänglig för just din prenumeration, region eller resurskombination. S0 kan innebära kostnader enligt faktisk användning. Välj inte S0 utan att först ha granskat priserna.

**Viktigt om region:** Nyckel och region hör ihop. Om de inte matchar kan autentisering misslyckas. Microsoft anger också att taldata normalt behandlas i den region där Speech-resursen skapats, med undantag för vissa särskilda funktioner.

### 5.3 Granska och skapa

1. Välj **Granska + skapa** (*Review + create*) om alternativet visas.
2. Läs sammanfattningen, särskilt **prenumeration, region och prisnivå**.
3. Korrigera eventuella fel.
4. Välj **Skapa** (*Create*).
5. Vänta tills portalen meddelar att distributionen har slutförts.
6. Välj **Gå till resurs** (*Go to resource*).

**Kontrollpunkt:** Du ser översiktssidan för din nya Speech-resurs.

## 6. Hitta nyckel och region

1. Öppna den Speech-resurs du just skapade.
2. Leta efter **Nycklar och slutpunkt** (*Keys and Endpoint*). Den kan finnas i resursens vänstermeny eller under resursinställningar.
3. Kontrollera att du ser en autentiseringsnyckel, ofta kallad **KEY 1** eller **KEY 2**, samt uppgift om region eller regionidentifierare.
4. Använd portalens kopieringsfunktion när du senare behöver nyckeln. **Klistra inte in nyckeln i e-post, chattar, supportärenden eller publika dokument.**
5. Notera regionens **tekniska identifierare** om den visas, exempelvis `swedencentral` – inte bara ett översatt geografiskt visningsnamn. Detta är ett *exempel*, inte ett påstående om vilken region du ska välja.

> **Skillnaden:** Resursnamn, resursgrupp, prenumerations-ID och Azure-kontots lösenord är **inte** samma sak som Speech-nyckeln. Du behöver rätt **Speech-nyckel** och **Speech-region** för senare konfigurering.

Förvara nyckeln säkert och begränsa vem som har tillgång till den. Om den exponeras bör du byta/återskapa den enligt Microsofts instruktioner och uppdatera de program som använder den.

## 7. Förstå och bevaka kostnader

Azure-prenumerationen och Speech-resursens prisnivå är två olika saker. En prenumeration kan vara aktiv samtidigt som vissa resurser medför kostnader.

### 7.1 Kontrollera aktuella priser

Öppna Microsofts officiella prissida för Speech: `https://azure.microsoft.com/pricing/details/ai-speech/`.

Kontrollera vilken prisnivå och vilka talfunktioner du använder. **Den här guiden anger inga fasta timpriser eller fria månadsvolymer**, eftersom Microsoft kan ändra priser och villkor.

### 7.2 Skapa en budgetvarning

1. Öppna Azure-portalen.
2. Sök efter **Cost Management + Billing** eller **Cost Management**.
3. Välj den prenumeration som används för Speech.
4. Öppna **Budgets** (*Budgetar*) där du har behörighet.
5. Välj **Add/Create** för att skapa en budget.
6. Ange ett belopp och en tidsperiod som passar dig.
7. Ange en e-postadress och minst en varningsnivå enligt formulärets anvisningar.
8. Spara och kontrollera att budgeten visas.

**Mycket viktigt:** En Azure-budget är i första hand en **varning**, inte ett automatiskt kostnadstak. När en varning skickas fortsätter resurser normalt att köras och kan fortsätta generera kostnader. Kontrollera regelbundet kostnadsöversikten och Microsofts villkor för eventuell utgiftsgräns i just din prenumeration.

## 8. Skydda kontot och Speech-resursen

- Använd ett starkt, unikt lösenord för Microsoft-kontot och aktivera tvåstegsverifiering när möjligt.
- Lämna aldrig ut Speech-nyckeln, Microsoft-lösenordet eller engångskoder till obehöriga.
- Förvara inte nyckeln i öppna textfiler eller skärmbilder som kan spridas.
- Granska Azure-prenumerationens användare och behörigheter om kontot delas inom en organisation.
- Kontrollera regelbundet förbrukning och fakturering.
- Om du inte längre behöver resursen, granska Microsofts anvisningar för att ta bort den och undvika fortsatt kostnad. Att bara avinstallera ett program tar **inte** bort Azure-resursen.

## 9. Kontrollera att allt är klart

Markera varje punkt när du har verifierat den:

- [ ] Jag kan logga in på mitt Microsoft-konto.
- [ ] Jag kan öppna Azure-portalen.
- [ ] Jag har hittat en aktiv Azure-prenumeration som jag får använda.
- [ ] Jag har skapat en Speech-resurs och ser dess översikt.
- [ ] Jag vet vilken prisnivå som gäller för resursen.
- [ ] Jag vet var jag hittar Speech-nyckeln och regionen.
- [ ] Jag har förstått att Azure-användning kan medföra kostnader.
- [ ] Jag har kontrollerat kostnadsövervakning och eventuella budgetvarningar.

**Klart!** Du har nu de förutsättningar som behövs för att konfigurera ett program som använder Azure Speech. Hur du lägger in nyckeln och testar taligenkänning i **Key2Voice** beskrivs i en **separat användarmanual för Key2Voice**.

## 10. Vanliga problem

### Jag kan logga in hos Microsoft men hittar ingen Azure-prenumeration

Kontrollera att Azure-registreringen är slutförd, att du använder rätt konto och att portalens katalog/prenumerationsfilter visar rätt innehåll. Se kapitel 4.

### Microsoft vill ha ett betalkort – är Azure då gratis?

Microsoft kan kräva ett kort för identitetskontroll. Ett introduktionserbjudande kan ha särskilda gratisvillkor, men det betyder inte att alla tjänster och all framtida förbrukning är kostnadsfri. Läs villkoren på registreringssidan.

### Jag kan inte verifiera mitt telefonnummer eller betalkort

Kontrollera landskod, telefonnummer, kortuppgifter och faktureringsadress. Använd de verifieringsalternativ som Microsoft erbjuder. Om problemet kvarstår, använd Microsofts officiella registreringsfelsökning i kapitel 11.

### Jag hittar inte Speech i portalen

Sök efter `Speech` och kontrollera att du befinner dig i Azure-portalen och har en aktiv prenumeration. Microsoft kan ändra produktnamn och navigering. Följ den aktuella Speech-snabbstarten i kapitel 11.

### Jag kan inte välja kostnadsfri prisnivå

F0 kan vara begränsad av tillgänglighet, prenumeration eller befintliga resurser. Välj inte en betalnivå automatiskt; kontrollera aktuella villkor och alternativ först.

### Jag hittar bara en slutpunktsadress, inte regionen

Öppna resursens **Keys and Endpoint** och kontrollera resursens översikt. Regionens tekniska identifierare ska motsvara resursens faktiska Azure-region. Gissa inte från resursnamnet.

### Jag ser en budgetvarning – stoppar den faktureringen?

Nej, en vanlig budgetvarning stoppar inte automatiskt tjänsten eller debiteringen. Granska förbrukningen och vidta åtgärder själv.

## 11. Officiella Microsoft-källor och fortsatt hjälp

Följande länkar användes vid faktagranskningen den **27 oktober 2026**. Microsofts gränssnitt och erbjudanden kan ändras efter detta datum.

- Microsoft-konto: https://account.microsoft.com/
- Registrera Microsoft-konto: https://signup.live.com/
- Azure – kom igång/kostnadsfritt erbjudande: https://azure.microsoft.com/free/
- Azure-portalen: https://portal.azure.com/
- Microsoft: skapa Azure-konto: https://learn.microsoft.com/en-us/dotnet/azure/create-azure-account
- Microsoft: felsök registrering för Azure: https://learn.microsoft.com/en-us/azure/cost-management-billing/troubleshoot-subscription/troubleshoot-azure-sign-up
- Microsoft: snabbstart Speech till text: https://learn.microsoft.com/en-us/azure/ai-services/speech-service/get-started-speech-to-text
- Microsoft: Speech-regioner: https://learn.microsoft.com/en-us/azure/ai-services/speech-service/regions
- Microsoft: Speech-priser: https://azure.microsoft.com/pricing/details/ai-speech/
- Microsoft: skapa budgetar: https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets
- Microsoft: budget- och kostnadsvarningar: https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/cost-mgt-alerts-monitor-usage-spending

---

## Dokumentstatus och kvalitetssäkring

**Status: Första kompletta utkastet för granskning – inte slutligt praktiskt verifierad manual.** Stegen bygger på Microsofts dokumenterade registrerings-, prenumerations-, Speech- och kostnadshantering. De exakta svenska knapptexterna och navigeringsvägarna kan skilja sig beroende på portalens språk, kontotyp och aktuellt gränssnitt. Före publicering bör en testperson utan tidigare Azure-konto gå igenom registrering och skapande av Speech-resurs, dokumentera faktiska skärmtexter och säkerställa att samtliga steg går att följa. Dokumentet innehåller inga riktiga nycklar, personuppgifter eller skärmbilder.
