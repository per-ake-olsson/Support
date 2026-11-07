# Key2Voice iOS – User Manual for iPhone, iPad, and Apple Watch

**Eureka Consulting AB**  
**English translation – version 1.0 (5 November 2026)**

> **Important before you begin:** Key2Voice for iPhone and iPad is free, but requires configuration transferred from Key2Voice for Windows in an encrypted sync file. **Sync Export in Windows requires Premium.** Speech recognition and translation also require your own working **Microsoft Azure Speech resource** and an internet connection. Azure is a separate service that may incur charges; Premium does not pay for Azure usage.
>
> If you do not yet have an Azure Speech resource, read the [**guide to creating a Microsoft Azure account and Speech resource**](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Eng/Skapa-Microsoft-Azure-konto). Configure and test Azure Speech in **Windows Basic** before considering Premium.

## Purpose

Key2Voice converts speech into readable text on **iPhone and iPad**. The app can also translate speech between selected languages, display text as easy-to-read subtitles, and save transcripts. **Apple Watch is an optional companion to iPhone**: the watch displays current text and can start or stop speech recognition on the phone. The iPhone handles the microphone, Azure connection, and storage; the watch does not operate independently.

This manual covers **the iOS app and its Apple Watch companion**. For Windows installation, purchasing Premium, Azure settings, and creating the initial sync file, see the [**Windows manual**](https://per-ake-olsson.github.io/Support/Key2Voice/Win/Eng/downloads/Key2Voice_manual_Eng).

## Contents

1. [Before You Begin](#before-you-begin)
2. [Installation](#installation)
3. [First Launch and Sync Import](#first-launch-and-sync-import)
4. [Speech to Text – Daily Use](#speech-to-text--daily-use)
5. [Languages and Translation](#languages-and-translation)
6. [Large Text](#large-text)
7. [Save and Manage Transcripts](#save-and-manage-transcripts)
8. [Apple Watch](#apple-watch)
9. [Settings, Sync Export, and About Key2Voice](#settings-sync-export-and-about-key2voice)
10. [Troubleshooting](#troubleshooting)
11. [Security and Privacy](#security-and-privacy)
12. [Updates and Support](#updates-and-support)

## Before You Begin

You need a compatible iPhone or iPad with Key2Voice installed, microphone permission, an internet connection, and a working Azure Speech configuration. For the initial configuration transfer, you also need Key2Voice for Windows with **Premium** and an encrypted sync file (`.k2s`) that you transfer to the device yourself.

**iPhone and iPad do not require a separate Premium purchase.** However, a newly installed app is not fully configured until the necessary information has been imported. You do not need to keep your Windows computer running during normal use after a successful import.

### Prepare on the Windows Computer

1. Install and launch Key2Voice for Windows.
2. Configure your **own** Azure Speech key and region. Test in **Basic** that speech recognition works.
3. When you want to transfer the configuration to iOS, make sure **Premium** is active in Windows.
4. Select **Sync Export** in Windows and create an encrypted `.k2s` file with a separate, strong **file password**.
5. You need to transfer the Azure Speech credentials: explicitly select **Include Azure Speech Credentials** and confirm your choice. They are not included automatically.
6. Transfer the sync file to iPhone or iPad, for example to the **Files** app. Keep the file password separately.
7. Open **Show Sync Fingerprint** in Windows and note the sender's fingerprint. Compare it with the value shown during import on iOS, preferably through a separate trusted channel.

**Note:** A selective sync export containing only transcripts does not contain Azure configuration and cannot replace a normal sync export for the initial setup.

## Installation

1. Install Key2Voice on iPhone or iPad through the distribution channel where the app is offered.
2. Open the app and grant **microphone permission** when requested if you want to transcribe speech.
3. Make your encrypted sync file available on the device, for example in **Files**.
4. Continue with **Sync Import** as described in the next section.

The app's appearance and system dialogs may vary between iOS and iPadOS versions. Apple Watch is optional and is not needed to use the app on iPhone or iPad.

## First Launch and Sync Import

Key2Voice uses a **locally encrypted vault** for the app's configuration and saved information. The iOS app manages access to its local vault using the device's protected storage. **On first launch on a new device, the app automatically creates an empty encrypted vault.** It generates a random vault passphrase and stores it in iOS protected key storage (Secure Storage). You therefore **do not need to enter or choose your own vault password** before importing sync data. However, you must enter the **separate file password** for the sync file during import. If an existing vault remains but its protected vault passphrase is missing, the app does not attempt to recreate the vault or automatically delete its contents.

1. Open **Settings** using the gear icon in Key2Voice.
2. Select **Sync Import**.
3. Choose the import command and locate your `.k2s` file in the file picker.
4. Enter **the sync file password** from the Windows export. It is not necessarily the same as the Windows vault passphrase.
5. If the app displays a **sync fingerprint** for a new or changed sender, compare it with the fingerprint from Windows. **Approve only if they match** and you recognize the sender.
6. If the file contains protected information, the app may request specific consent and ask how to handle conflicts: **Keep Existing**, **Replace Existing**, or **Reject Existing**. Read the options carefully before proceeding.
7. Wait for confirmation that the import succeeded. Return to **Speech to Text** and test the feature.

### If Import Does Not Succeed

Check that you selected the correct file, entered the correct file password, and used a sync file containing the configuration you need. Import may be rejected if the package has already been imported, the sender has not been approved, or the information conflicts with existing contents. **Do not reset trust or delete data merely to bypass an import error.** Instead, review the error message and the sender's fingerprint.

## Speech to Text – Daily Use

The main **Read** view displays a status line, current text, and buttons to control transcription.

1. Check that the internet connection works and the app has microphone permission.
2. Select the desired **incoming spoken language** and **outgoing text language** under **Settings**.
3. Tap **Start** to begin transcribing speech from the device's microphone.
4. Read the text as it updates. The app displays the status of the current session.
5. Tap **Stop** when you want to finish.
6. Select **Save** if you want to keep the text, or **Clear** to empty the workspace.

The **Start**, **Stop**, **Clear Text**, **Save**, **Save As**, **Retrieve**, **Delete**, and **Large Text** buttons are available in the Read view. The layout adapts to the screen orientation.

**Important:** Speech recognition requires Azure Speech and is not a purely offline feature. Results depend on the microphone, background noise, clarity of speech, language selection, and network connection.

## Languages and Translation

Under **Settings**, there are three separate language selections:

- **App Language:** Language used for the app's menus and text; Swedish or English.
- **Language to Listen To:** The language spoken into the microphone.
- **Language to Write In:** The language in which transcribed or translated text is displayed.

The explicitly supported spoken languages include **Swedish, English, French, and German**. To obtain Swedish text from Swedish speech, select Swedish for both incoming and outgoing languages. For example, to display English speech as Swedish text, select English as the incoming language and Swedish as the outgoing language.

**Choose an explicit incoming language.** Do not assume automatic language identification works in this version. Translations may contain errors and should be checked before use in important situations.

## Large Text

Tap **Large Text** in the Read view to open a separate view that displays transcribed text in a larger font. The view follows the current transcription and scrolls to keep new text visible.

The view has controls to **decrease** or **increase the text size** and to **close** the view. Subtitles are a display feature; use **Save** in the Read view if you want to keep a transcript in the vault.

## Save and Manage Transcripts

Saved transcripts are managed in the app's local encrypted vault.

### Save and Save As

1. First stop any ongoing speech recognition.
2. Select **Save** to save the text. For a new transcript, enter a document name.
3. If a saved document is already active, **Save** updates that document.
4. Select **Save As** to create a separate copy with a new name.

The save functions are available when a transcript contains completed text and no speech recognition or storage operation is in progress.

### Retrieve and Continue

1. Stop speech recognition and save anything you want to keep.
2. Select **Clear Text** so the workspace is empty. Clear Text removes text from the workspace, **not** a previously saved document from the vault. Unsaved text may be lost.
3. Tap **Retrieve**. A **new window with a list of saved transcripts** opens. It shows document names and the most recent modification times, among other details.
4. Tap **a document directly in the list** to open it. The list window closes and the document's text appears in the workspace.
5. You can restart speech recognition to continue, then save the result.

In the list window's normal mode, tapping a document opens it. To manage multiple documents instead, use **Select**, as described below.

### Select, Delete, or Export Multiple Transcripts

1. Open the list using **Retrieve** and tap **Select**.
2. Choose **one or more transcripts** from the list. You can also select **Select All** or **Deselect All**.
3. Choose **Export Selected** to export the selection, or **Delete Selected** to delete the selected documents. Deletion requires confirmation.
4. Tap **Cancel** to leave selection mode without performing an action.

**Delete** in the main view instead applies to the **active saved document** and also requires confirmation. **Clear Text** only empties the workspace; it does not delete saved documents from the vault.

### Export Selected Transcripts

Select **Retrieve → Select**, select the documents, and tap **Export Selected**. An export window opens. Enter and confirm a separate file password and start the export. The encrypted sync file is then shared using the device's sharing feature.

This type of export contains the selected transcripts, **not** the Azure Speech key or a complete backup of the vault.

## Apple Watch

If you have a compatible Apple Watch, you can use Key2Voice on the watch together with **iPhone**. The watch is **not required** for iPhone or iPad use and does not function as a standalone Azure client.

1. Install and open Key2Voice on iPhone, and make sure sync import and speech recognition work there.
2. Install or open the companion Watch app according to the available Apple Watch distribution method.
3. Start **speech to text** from iPhone, or use **Start** on the watch when its connection to iPhone works and the app is in the foreground.
4. Read the latest transcribed text on the watch. The watch also displays the session status.
5. Tap **Stop** on the watch or iPhone to finish.
6. The watch continues to work as long as Key2Voice is running on iPhone, even if the app is running in the background or iPhone goes to sleep. For example, you can keep iPhone in your pocket while reading recognized speech on Apple Watch.
7. With Key2Voice active on your Apple Watch, you can adjust the text size using the Digital Crown.

**iPhone handles the microphone, Azure connection, and storage.** Apple Watch displays current text and sends start/stop commands; it does not store its own complete transcript history and does not need a separate Azure key. If the watch stops displaying new text, first tap the screen to “wake” the watch, then check that the iPhone app is working and the devices can communicate.

## Settings, Sync Export, and About Key2Voice

Open **Settings** using the gear icon in the main view. Here you can select **App Language**, **Language to Listen To**, and **Language to Write In**, and use **Import Sync Data**, **Show Sync Fingerprint**, **Export Sync Data**, and **About Key2Voice**.

### Show Sync Fingerprint

**Show Sync Fingerprint** displays **this iPhone or iPad installation's own sender fingerprint**. It is used when **this device exports** a sync file for import on another device. It is not a biometric fingerprint.

When you **import a sync file from Windows**, the **Windows installation's sender fingerprint** is displayed instead in the import approval dialog. Compare **that fingerprint** with the one shown under **Show Sync Fingerprint** in Windows, preferably through a separate trusted channel. **Do not compare it with the iPhone app's own fingerprint; these two are normally different.** Approve a new or changed sender only after verifying the correct sender fingerprint.

### Export Sync Data from iOS

Key2Voice for iPhone and iPad can also create and share an encrypted sync file from the local installation:

1. Open **Settings → Export Sync Data**.
2. Enter a strong file password and confirm it.
3. If you have been granted access to a Premium test license, you can include it in the export by selecting **Include Developer Licenses**; otherwise, leave the option unchecked.
4. Start the export and choose how to share or save the file through iOS.
5. Keep the file and its password secure.

**Note:** iOS export is not the same as the Windows **portable backup** (`.k2b`). The iOS app does not offer the Windows feature for complete portable restoration. Export Sync Data on iOS must not be used to pass on Azure Speech secrets either; they are not included in this export.

### About Key2Voice

Under **Settings → About Key2Voice**, you can find information about the app, including its version and build number, as well as a link to the app's support page with documentation and contact details.

## Troubleshooting

| Problem | Check First |
|---|---|
| No text is displayed | That **Start** has been activated, microphone permission is granted, the internet connection works, and the microphone can hear speech. |
| Speech recognition cannot start | That a valid Azure Speech configuration has been imported, the correct region and key are used, and the Azure resource is active. |
| Text appears in the wrong language | **Language to Listen To** and **Language to Write In** under Settings. |
| Automatic language identification does not work | Select an explicit incoming spoken language. |
| Sync Import fails | The correct `.k2s` file and file password, an approved sync fingerprint, and any import conflicts. |
| Retrieve is disabled | Stop the session and **Clear** the workspace after saving any text. |
| Save is disabled | Stop speech recognition and verify that completed transcribed text is present. |
| Apple Watch shows no new text | Tap the Apple Watch screen. Check that the iPhone app works and the watch is connected to iPhone. |
| Large Text shows no new text | Check that transcription is running and new text is arriving in the Read view. |
| Sync Export fails | That the file passwords match and the export can be completed through the iOS sharing feature. |

If the problem persists, note the app version, iOS/iPadOS version, what you did, and the error message displayed. **Never** send Azure keys, vault secrets, sync file passwords, or sensitive transcripts to support.

## Security and Privacy

- Speech processed by **Azure Speech** is sent to Microsoft's cloud service. Key2Voice is not an offline speech recognition service.
- Configuration and saved transcripts are managed in a **locally encrypted vault** on iPhone or iPad.
- Sync files are encrypted but must still be handled carefully. Verify the sender's fingerprint during import and protect the file password.
- Apple Watch is used together with iPhone; current text and session status are transferred to the watch. The watch does not manage its own Azure configuration.
- Respect other people's privacy when transcribing conversations. Automatically recognized or translated text may contain errors and should not be the sole basis for medical, legal, or safety-critical decisions.
- Read the [**Key2Voice iOS privacy policy**](https://per-ake-olsson.github.io/Support/Key2Voice/iOS/Eng/downloads/Key2Voice_integritetspolicy_Eng) and Microsoft's current Azure terms.

## Updates and Support

App updates are offered through the distribution channel where you installed Key2Voice. Make sure you have access to your Windows configuration and a securely stored sync file before uninstalling the app or deleting its data.

For questions, bug reports, and feedback: **[contact@eureka.nu](mailto:contact@eureka.nu)**. Please include the app version and a brief description of the problem, but never any secret information.

### Documents and Links

- [Key2Voice – Windows user manual](https://per-ake-olsson.github.io/Support/Key2Voice/Win/Eng/downloads/Key2Voice_manual_Eng)
- [Azure Speech guide – create an account and Speech resource](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Eng/Skapa-Microsoft-Azure-konto)
- [Microsoft Azure portal](https://portal.azure.com/)
- [Microsoft Azure AI Speech – documentation](https://learn.microsoft.com/azure/ai-services/speech-service/)
