# Guide: Create a Microsoft Azure Account and an Azure Speech Resource

**For Key2Voice – English user guide, version 1.0**  
**Last fact-checked:** 27 October 2026  
**Intended audience:** Individuals who have not used Microsoft Azure before.  
**Purpose:** Help you gain access to Azure and create a Speech resource. **This is not a Key2Voice user manual.**

## Important Information – Read This Before You Begin

**This guide is provided solely as optional assistance** for anyone who wants to create a Microsoft Azure account and an Azure Speech resource for use with Key2Voice. The guide is not part of Microsoft's service and does not guarantee that registration will succeed or that the service will work.

**Eureka Consulting AB is not responsible for your ability to create or activate a Microsoft account, an Azure subscription, or an Azure Speech resource.** Nor does Eureka Consulting AB guarantee that Microsoft Azure Speech will be available, operate without interruption, or work with Key2Voice in your environment. Registration, access, terms, pricing, operation, and support for Azure services are handled by Microsoft. You are responsible for your Azure account, sign-in credentials, subscription choices, and any charges. If you encounter problems with registration or the Azure service, you should contact Microsoft support in the first instance.

**Your own working Azure Speech account, with a correctly configured Speech resource, is required for Key2Voice's Azure-based speech features to work.** Without working access to Azure Speech, Key2Voice cannot be used for its intended purpose of cloud-based speech recognition and translation.

**Do not purchase Key2Voice Premium until you have personally verified that Key2Voice works with your own Azure Speech account.** First create and configure your Azure Speech resource, enter its details in Key2Voice, and successfully perform a practical test of the feature you need. Purchasing Premium does not provide access to an Azure account or guarantee that Microsoft's service will work.

This information explains the division of responsibilities and limitations of the services. It does not restrict any rights you may have under mandatory consumer protection law.

> **Important information about costs:** Azure is a Microsoft service. Some offers and usage tiers may be free, but services may also incur charges. Read the pricing and payment terms displayed for your particular account before accepting anything. A budget alert does **not** automatically stop usage or billing.

## 1. What Are We Going to Do?

You do not need programming skills. Follow these steps in order:

1. Check whether you already have a **Microsoft account**, or create one.
2. Sign in to **Microsoft Azure** and register if you do not already have access.
3. Verify that you have an **Azure subscription** that permits you to create resources.
4. Create a **Speech resource** – the part of Azure that provides speech recognition and translation.
5. Find the resource's **key** and **region**. You will need these later when configuring Key2Voice.

### Four Terms That Are Easy to Confuse

| Term | Simple Explanation |
|---|---|
| Microsoft account | Your Microsoft sign-in, such as an Outlook address or another email address registered with Microsoft. |
| Azure account/access | The ability to sign in to and use the Azure portal. Signing in does not always mean that you have an active subscription. |
| Azure subscription | The administrative and financial framework within which Azure services are used and billed. |
| Speech resource | The specific Azure service you create for speech features. It has a region and authentication credentials. |

**Already have an Azure subscription?** Skip to section 5. **Have a Microsoft account but have never used Azure?** Start at section 3.

## 2. Check or Create a Microsoft Account

### 2.1 Check Whether You Already Have One

1. Open a web browser, such as Microsoft Edge.
2. Enter `https://account.microsoft.com/` in the address bar and press **Enter**.
3. Select **Sign in** if the button is displayed.
4. Try the email address you normally use for Microsoft services. Follow the on-screen instructions.
5. If you can access your account page, you already have a working Microsoft account. Continue to section 3.

> An Outlook.com, Hotmail, or Live account is normally a Microsoft account. Other email addresses can also be registered as Microsoft accounts. However, using Windows does not necessarily mean that you sign in with a Microsoft account; Windows can use a local account.

If you are unsure which account you have, first check your existing Microsoft sign-ins. Avoid creating an additional account unnecessarily: doing so may make it harder to find the correct Azure subscription later.

### 2.2 Create a New Microsoft Account

1. Open `https://account.microsoft.com/`.
2. Select **Sign in**, then **Create account** if you do not already have one. You can also start at `https://signup.live.com/`.
3. Follow Microsoft's instructions. You may be offered the option of using an existing email address or creating a new Outlook address.
4. Choose a strong, unique password. Save it in a trusted password manager.
5. Complete any email address, phone number, or other identity verification required by Microsoft.
6. Sign in at `https://account.microsoft.com/` and confirm that the account works.

**Recommended:** Add a secure account recovery method and enable two-step verification wherever offered. Never share one-time codes or passwords with anyone.

**Checkpoint:** You can sign in to your Microsoft account page without assistance. You can now continue.

## 3. Sign Up for Microsoft Azure

### 3.1 Start at the Right Website

1. Open `https://azure.microsoft.com/free/`.
2. Read the offer displayed for your country and account. Select the button to get started with a free Azure account if you are eligible, or follow the link to another suitable subscription option.
3. Sign in with your Microsoft account. Microsoft may also offer other identity options, but this guide uses a Microsoft account.

**Note:** A new user may be eligible for an introductory offer. The amount, validity period, and included services are determined by Microsoft and must be checked on the registration page. If you have used Azure before, the offer may not be available. Do not attempt to create multiple accounts to circumvent the terms.

### 3.2 Enter Your Details

During registration, Microsoft may request:

- Country/region and contact details.
- Name and address.
- Phone number for identity verification.
- Payment card for identity or payment verification.
- Acceptance of Microsoft's agreements and terms.

Enter **your actual details**. Country/region and billing address must reflect your real circumstances. Follow each page in the order presented.

**Phone verification:** Microsoft may send a code by SMS or offer verification by phone call. Available options may vary. If a method does not work, follow the portal's instructions or Microsoft's troubleshooting documentation.

**Card verification:** Microsoft may require a valid debit or credit card and place a temporary authorization hold. Accepted cards vary. Card verification is not a promise that all future Azure usage will be free.

### 3.3 Read the Terms Before Accepting

Pay particular attention to:

1. Whether you are signing up for a free introductory offer or a paid subscription.
2. Whether and when usage charges may begin.
3. The terms that apply when any introductory offer expires.
4. The payment method associated with the account.

Accept only if you understand and agree to the terms. If you are unsure, stop and read Microsoft's information before continuing.

### 3.4 Open the Azure Portal

1. Go to `https://portal.azure.com/`.
2. Sign in with the same account you used during registration.
3. Wait for the Azure portal to appear.

**Checkpoint:** You can open the Azure portal. The next step is to check that a subscription exists and can be used.

## 4. Check Your Azure Subscription

### 4.1 Find Your Subscriptions

1. Open `https://portal.azure.com/`.
2. Use the search field at the top of the portal to search for **Subscriptions**.
3. Open the result for Azure subscriptions.
4. Check whether a subscription is listed and review its status.

If you see an **active** subscription that you are authorized to use to create resources, you can continue to section 5.

### 4.2 If No Subscription Is Displayed

Being able to sign in to Azure is not the same as having an active subscription. Check:

- That you are signed in with **the same account** used during registration.
- If the portal shows multiple directories (*directories/tenants*), that you are viewing the correct directory and subscription filter.
- Whether registration has been fully completed or is still awaiting verification.

If you still have no subscription, return to `https://azure.microsoft.com/free/` and follow Microsoft's guidance to obtain one. Choose only an offer whose terms you understand. In some organizations, an administrator must grant you access; do not create a personal paid subscription without first checking with your organization.

**Checkpoint:** You have identified the subscription you will use. You may want to note its **display name**, but do not write down or share secret authentication credentials.

## 5. Create a Speech Resource

This step creates the actual speech recognition service. Microsoft may display the service under names such as **Speech**, **Azure AI Speech**, or **Speech in Foundry Tools**. Names and forms may change. Prefer Microsoft's current Speech resource documentation.

### 5.1 Find the Service

1. Open the Azure portal: `https://portal.azure.com/`.
2. Type **Speech** in the portal's search field.
3. Select a result for creating a **Speech resource**. If you arrive at a product overview, look for **Create**.
4. Verify that you are creating a resource that supports **Speech**, not an unrelated AI service or another subscription.

If you are unsure which resource type is displayed, consult Microsoft's official Speech quickstart before continuing (link in section 11).

### 5.2 Complete the Form

Field names may vary. Common options include:

| Field | What to Do |
|---|---|
| Subscription | Select the active subscription from section 4. |
| Resource group | Select an existing resource group that you own, or create a new one with a descriptive name, such as `rg-key2voice`. |
| Region | Choose a region where the Speech features you need are supported. **Remember the exact region.** |
| Name | Enter a resource name according to the portal's rules, such as `key2voice-speech`. The name may need to be unique. |
| Pricing tier | Check which tiers are offered, such as **Free F0** or **Standard S0**, and choose based on the actual terms and expected usage. |

**Important information about pricing tiers:** F0 may have limitations and may not be available for your subscription, region, or combination of resources. S0 may incur charges based on actual usage. Do not select S0 without first reviewing the prices.

**Important information about regions:** The key and region belong together. If they do not match, authentication may fail. Microsoft also states that speech data is normally processed in the region where the Speech resource was created, with exceptions for certain special features.

### 5.3 Review and Create

1. Select **Review + create** if that option is available.
2. Read the summary, especially the **subscription, region, and pricing tier**.
3. Correct any errors.
4. Select **Create**.
5. Wait until the portal reports that deployment is complete.
6. Select **Go to resource**.

**Checkpoint:** You can see the overview page for your new Speech resource.

## 6. Find the Key and Region

1. Open the Speech resource you just created.
2. Look for **Keys and Endpoint**. It may be in the resource's left-hand menu or under resource settings.
3. Check that you can see an authentication key, often called **KEY 1** or **KEY 2**, and information about the region or region identifier.
4. Use the portal's copy function when you need the key later. **Do not paste the key into emails, chats, support requests, or public documents.**
5. Note the region's **technical identifier** if shown, for example `swedencentral` – not just a translated geographic display name. This is an *example*, not a recommendation of which region to choose.

> **The difference:** Resource name, resource group, subscription ID, and Azure account password are **not** the same as the Speech key. You need the correct **Speech key** and **Speech region** for configuration later.

Store the key securely and restrict who has access to it. If it is exposed, rotate/regenerate it according to Microsoft's instructions and update the applications that use it.

## 7. Understand and Monitor Costs

Your Azure subscription and the Speech resource's pricing tier are two different things. A subscription can be active while some resources incur charges.

### 7.1 Check Current Prices

Open Microsoft's official Speech pricing page: `https://azure.microsoft.com/pricing/details/ai-speech/`.

Check which pricing tier and speech features you use. **This guide does not provide fixed hourly rates or free monthly allowances**, because Microsoft may change prices and terms.

### 7.2 Create a Budget Alert

1. Open the Azure portal.
2. Search for **Cost Management + Billing** or **Cost Management**.
3. Select the subscription used for Speech.
4. Open **Budgets** where you have permission.
5. Select **Add/Create** to create a budget.
6. Enter an amount and time period suitable for you.
7. Enter an email address and at least one alert threshold as instructed by the form.
8. Save and check that the budget appears.

**Very important:** An Azure budget is primarily an **alert**, not an automatic spending cap. When an alert is sent, resources normally continue running and may continue to incur charges. Review the cost overview regularly and check Microsoft's terms for any spending limit that applies to your particular subscription.

## 8. Protect Your Account and Speech Resource

- Use a strong, unique password for your Microsoft account and enable two-step verification where possible.
- Never disclose your Speech key, Microsoft password, or one-time codes to unauthorized people.
- Do not store the key in unprotected text files or screenshots that could be shared.
- Review Azure subscription users and permissions if the account is shared within an organization.
- Check usage and billing regularly.
- If you no longer need the resource, review Microsoft's instructions for deleting it to avoid ongoing charges. Merely uninstalling an application does **not** delete the Azure resource.

## 9. Check That Everything Is Ready

Check each item after you have verified it:

- [ ] I can sign in to my Microsoft account.
- [ ] I can open the Azure portal.
- [ ] I have found an active Azure subscription that I am authorized to use.
- [ ] I have created a Speech resource and can see its overview.
- [ ] I know which pricing tier applies to the resource.
- [ ] I know where to find the Speech key and region.
- [ ] I understand that using Azure may incur charges.
- [ ] I have checked cost monitoring and any budget alerts.

**All set!** You now have the prerequisites to configure an application that uses Azure Speech. How to enter the key and test speech recognition in **Key2Voice** is described in a **separate Key2Voice user manual**.

## 10. Common Problems

### I Can Sign In to Microsoft but Cannot Find an Azure Subscription

Check that Azure registration is complete, that you are using the correct account, and that the portal's directory/subscription filters show the correct information. See section 4.

### Microsoft Requires a Payment Card – Does That Mean Azure Is Free?

Microsoft may require a card for identity verification. An introductory offer may have specific free-use terms, but that does not mean all services and future usage are free. Read the terms on the registration page.

### I Cannot Verify My Phone Number or Payment Card

Check the country code, phone number, card details, and billing address. Use the verification methods offered by Microsoft. If the problem persists, use Microsoft's official registration troubleshooting resource in section 11.

### I Cannot Find Speech in the Portal

Search for `Speech` and verify that you are in the Azure portal and have an active subscription. Microsoft may change product names and navigation. Follow the current Speech quickstart in section 11.

### I Cannot Select the Free Pricing Tier

F0 may be restricted by availability, subscription, or existing resources. Do not automatically choose a paid tier; check the current terms and alternatives first.

### I Can Only Find an Endpoint Address, Not the Region

Open the resource's **Keys and Endpoint** page and check the resource overview. The region's technical identifier must correspond to the resource's actual Azure region. Do not guess from the resource name.

### I See a Budget Alert – Does It Stop Billing?

No. An ordinary budget alert does not automatically stop the service or billing. Review usage and take action yourself.

## 11. Official Microsoft Sources and Further Help

The following links were used during the fact-check on **27 October 2026**. Microsoft's interfaces and offers may change after this date.

- Microsoft account: https://account.microsoft.com/
- Register a Microsoft account: https://signup.live.com/
- Azure – get started/free offer: https://azure.microsoft.com/free/
- Azure portal: https://portal.azure.com/
- Microsoft: create an Azure account: https://learn.microsoft.com/en-us/dotnet/azure/create-azure-account
- Microsoft: troubleshoot Azure sign-up: https://learn.microsoft.com/en-us/azure/cost-management-billing/troubleshoot-subscription/troubleshoot-azure-sign-up
- Microsoft: speech-to-text quickstart: https://learn.microsoft.com/en-us/azure/ai-services/speech-service/get-started-speech-to-text
- Microsoft: Speech regions: https://learn.microsoft.com/en-us/azure/ai-services/speech-service/regions
- Microsoft: Speech pricing: https://azure.microsoft.com/pricing/details/ai-speech/
- Microsoft: create budgets: https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/tutorial-acm-create-budgets
- Microsoft: budget and cost alerts: https://learn.microsoft.com/en-us/azure/cost-management-billing/costs/cost-mgt-alerts-monitor-usage-spending
