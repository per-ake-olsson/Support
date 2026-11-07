# Key2Voice Windows – User Manual

**Eureka Consulting AB**  
**English translation – version 1.0 (4 November 2026)**

> **Important before you begin:** Key2Voice uses Microsoft's **Azure Speech** cloud service for speech recognition and translation. To use these features, you need your own working Azure Speech resource, the correct region, a valid key, and an internet connection. Azure is a separate service that may incur charges. **Do not purchase Key2Voice Premium until you have configured your own Azure Speech resource and verified that speech recognition works in Key2Voice Basic.**
>
> Need to create a Microsoft account, Azure subscription, or Speech resource? Follow the separate Swedish-language [**Azure Speech guide**](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto). This manual explains how to use an existing Azure account in Key2Voice.

## Purpose

Key2Voice helps you convert speech into readable text. The Windows version is the main platform: here you configure Azure Speech, use **Speech to Text**, manage transcripts, and make backups. With **Premium**, you can also create an encrypted sync file for the **iPhone app**. This manual covers the **Windows version**, not the iOS version.

## Contents

1. [Before You Begin](#before-you-begin)
2. [Installation](#installation)
3. [First Launch and the Vault](#first-launch-and-the-vault)
4. [Configure an Existing Azure Speech Resource](#configure-an-existing-azure-speech-resource)
5. [Test Speech Recognition](#test-speech-recognition)
6. [Speech to Text – Daily Use](#speech-to-text--daily-use)
7. [Languages and Translation](#languages-and-translation)
8. [Save and Manage Transcripts](#save-and-manage-transcripts)
9. [Basic and Premium](#basic-and-premium)
10. [Synchronize with iPhone and Apple Watch](#synchronize-with-iphone-and-apple-watch)
11. [Backup and Restore](#backup-and-restore)
12. [Settings and About Key2Voice](#settings-and-about-key2voice)
13. [Troubleshooting](#troubleshooting)
14. [Security and Privacy](#security-and-privacy)
15. [Updates and Support](#updates-and-support)

## Before You Begin

You need a Windows computer on which Key2Voice can be installed, a working internet connection, and your own Azure Speech resource. To transcribe speech from a microphone, you need a microphone that works in Windows.

**Azure and Key2Voice are separate services.** Key2Voice Premium is a license for application features; it does **not** include an Azure subscription or usage charges. Check Microsoft's current terms and prices in the Azure portal.

### If You Do Not Already Have Azure Speech

First read the [**Azure Speech guide**](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto). It explains how to create a Microsoft account if needed, sign up for Azure, arrange a subscription, create a Speech resource, and find its key and region. Then return here.

## Installation

1. Open **Microsoft Store** on your Windows computer.
2. Search for **Key2Voice** and check that you have selected the correct app from **Eureka Consulting AB**.
3. Select **Get** or **Install**. The **Basic** edition is free and intended to be usable without purchasing Premium.
4. Launch Key2Voice from the Windows Start menu after installation.
5. If Windows requests microphone permission, grant access if you want to transcribe using a microphone.

The appearance of installation and licensing dialogs may vary depending on your Windows and Store versions.

## First Launch and the Vault

Key2Voice uses a local **vault** to protect configuration and saved information.

1. Follow the application's instructions to create a new vault on first launch.
2. Choose a strong vault passphrase and keep it somewhere safe, separate from your computer.
3. Verify that the vault can be opened and that the main window displays the vault status.
4. Verify that the license tier is **Basic** unless you already have a valid Premium entitlement.

### Open or Create Vault and Close Vault

- **Open or Create Vault** in the main window opens an existing vault or creates a new one if none exists. If the vault is already open, it remains open. Depending on your settings, you may need to enter the vault passphrase. Once opened, the vault status shows **Open**, and you can use features that require vault access.
- **Close Vault** closes the application's active access to the encrypted vault and displays **Closed** in the vault status. It does **not delete** the vault or your saved transcripts. Use **Open or Create Vault** again when you want to continue.
- Closing the vault does not automatically cause a previously saved passphrase to be forgotten. If you want to enter the passphrase every time you start the app, enable **Require Passphrase at Startup** under **Vault Encryption**.

### What Does KDF Status Mean?

The main window displays **KDF** along with values for the vault's password-based key derivation. KDF stands for *Key Derivation Function* and is used when the application converts your vault passphrase into encryption keys. The information appears in the form **iterations / memory in KiB / pN**, where the final value indicates parallelism. These are **technical protection parameters**, not a warning or a measure of how strong your vault passphrase is. The values are updated when the vault's KDF settings are renewed. Normally, you do not need to change them yourself.

**Important:** If you lose the passphrase, recovering encrypted information may be impossible. Eureka Consulting AB cannot recover your private passphrase. Make regular backups as described below.

### When Key2Voice Processes Encrypted Information

Key2Voice protects the vault and saved information with strong encryption. Some operations can therefore take **noticeably longer** than ordinary button clicks, depending on your computer and the amount of data. Examples include application startup, opening the vault, retrieving saved transcripts, changing the vault passphrase, and updating the vault's encryption protection.

During these operations, Key2Voice displays an **activity indicator** showing that work is in progress. Wait for the operation to finish. Avoid closing the application or interrupting the computer during a security-critical operation. If the indicator appears to be stuck for an unusually long time, note what you were doing and contact support instead of repeatedly attempting the same operation.

## Configure an Existing Azure Speech Resource

You will now use **a Speech resource that already exists in your own Azure account**. You do not need to create a new Azure account for every Key2Voice installation.

### A. Find the Information in Azure

1. Open the [Azure portal](https://portal.azure.com/) and sign in with the account that has access to your Azure subscription.
2. Open the **Speech resource** you created according to the Azure guide. If you have several resources, select the correct one.
3. Find the resource's **Keys and Endpoint** page (the label may vary in the portal).
4. Note the resource's **region** and copy an available **key**. The region is not the same as a display name or the name of the resource group.
5. Treat the key like a password. Do not send it by ordinary email or publish it in screenshots or support requests.

### B. Enter the Information in Key2Voice

1. Launch Key2Voice and open **Settings**.
2. Find the **Azure Speech** settings.
3. Enter the **Speech resource subscription key** and **region** exactly as shown in the Azure portal.
4. Save the settings as instructed by the application.
5. Open **Speech to Text** to test the connection in practice.

**Note:** Successfully saving the key and region does not by itself prove that Azure Speech works. Always perform a transcription test.

## Test Speech Recognition

Do this **before purchasing Premium**.

1. Make sure your computer is connected to the internet and the microphone works in Windows.
2. Open **Speech to Text** in Key2Voice.
3. Select **microphone** as the audio source and **Swedish** as the incoming spoken language (language selection is under Settings).
4. Start transcription using the window's start command.
5. Read a clear sentence aloud, for example: *“Det här är ett test av taligenkänningen i Key2Voice.”* (Swedish: “This is a test of speech recognition in Key2Voice.”)
6. Check that text appears in the transcription window.
7. End transcription using the stop command.

If understandable text appears from your speech, you have verified the basic chain **microphone → Key2Voice → Azure Speech → text**. Try several sentences and a normal speaking pace. A single successful test does not guarantee that all audio environments or languages will work equally well.

**If the test fails:** Check the key, region, Azure resource status, internet connection, microphone permissions, and selected audio source. See [Troubleshooting](#troubleshooting). Do not purchase Premium in the hope that it will resolve Azure or microphone problems.

## Speech to Text – Daily Use

In Key2Voice for Windows, use **Speech to Text** to convert speech from a microphone, system audio, or a WAV file into text.

### Select an Audio Source

Key2Voice can transcribe speech from several sources:

- **Microphone:** Speech captured by a microphone connected to the computer.
- **System audio:** Speech played on the computer, for example in a video or another application.
- **WAV file:** Speech already stored in an audio file in a format supported by Key2Voice.

Select the correct source in **Speech to Text** before starting. For system audio, the computer must play sound through the correct device. For WAV, select a compatible file using the file picker. If a file cannot be opened, check its format; a `.wav` extension alone does not guarantee that its audio encoding is supported.

### Start, Stop, and Continue

1. Select the audio source (languages are selected under Settings).
2. Start transcription.
3. Follow the text displayed while speech is being processed.
4. Stop when you are finished.
5. Once transcription has stopped, you can edit the text, save it, or display it in the subtitle window. See [Save and Manage Transcripts](#save-and-manage-transcripts) for how to retrieve and continue a saved document.

Speech recognition quality depends on background noise, the microphone, clarity of speech, language selection, and Azure service availability.

## Languages and Translation

Key2Voice has separate selections for the **language to listen to** and the **language to write in**. Implemented language options include **Swedish, English, French, and German**.

- To obtain Swedish text from Swedish speech, select **Swedish** for both.
- To obtain Swedish text from, for example, English speech, select **English** as the incoming language and **Swedish** as the outgoing text language.
- Check the result before using a translation in an important context. Automatic translations may contain errors.

**Automatic language selection** should not be assumed to work in this version; choose an explicit language. Translation may involve additional processing in Azure and is subject to Microsoft's current terms and pricing.

## Save and Manage Transcripts

In **Speech to Text**, you can create, name, save, resume, edit, copy, delete, and transfer saved transcripts. They are stored in the local encrypted vault, not as standalone text files. The window includes buttons such as **Start**, **Stop**, **Clear Text**, **Save**, **Save As**, **Retrieve**, **Delete**, and **Show Subtitles**.

### Create and Save a Transcript

1. Select an audio source and start transcription with **Start**.
2. Follow the text as speech is recognized. The text field is read-only while transcription is in progress.
3. Select **Stop** when finished. You can then correct the text directly in the text field.
4. Select **Save**. For a new transcript, you are prompted to enter a name. The document is then stored in the vault.
5. If you want to preserve the original and create a **separate copy**, select **Save As**, enter a new name, and save. The new copy becomes the active document.

**Difference between Save and Save As:** When a saved document is already active, **Save** updates that document, while **Save As** creates a new document with a new ID. A document name must contain 1–120 characters and must not contain control characters.

### Retrieve, Edit, and Continue

1. Stop any transcription currently in progress.
2. **Retrieve** is available only when the text field is empty. First save any changes you want to keep, then select **Clear Text**. **Clearing removes text from the workspace without deleting an already saved document from the vault.** Unsaved text, however, may be lost.
3. Select **Retrieve**. The dialog shows saved documents with their names and last modification times.
4. Select **one** document and choose **Open**. Its text appears in the workspace.
5. Edit if necessary and select **Save** to update the document, or **Save As** to create a separate copy.
6. You can also select an audio source and press **Start** to continue transcribing. Newly recognized text is appended to the workspace. Stop and save when finished.

If **Retrieve** is disabled, make sure no transcription or storage operation is in progress and the text field is empty.

### Delete Saved Documents

- **Delete** in the main Speech to Text window applies to the **active saved document**. The application asks for confirmation.
- In the **Retrieve** dialog, you can select **one or more** documents and choose **Delete**. A confirmation appears before deletion.
- Deleting from the vault is not the same as **Clear Text** in the workspace. Check the selection carefully and make sure you have a current backup if the documents are important.

### Display Text as Subtitles

Select **Show Subtitles** to open a separate window with **large, clear text that updates in real time** while speech is transcribed. The text **scrolls automatically** so the latest text remains visible. The window can serve as an easy-to-read aid during conversations or speech playback. It displays the text but does not save the document; use **Save** or **Save As** in **Speech to Text** to preserve the transcript.

### Export Selected Transcripts to Another Installation

In the **Retrieve** dialog, you can select one or more saved documents and choose **Export Selected**. This creates an encrypted sync file (**.k2s**) containing **only the selected transcripts**, intended for import into another Key2Voice installation.

1. Check that the Windows installation has a valid **Premium** entitlement and the vault is open.
2. Open **Retrieve** from an empty workspace and select the desired documents. You do not need to open one of them.
3. Select **Export Selected**, specify the file location and a separate **file password**, and confirm the password.
4. Transfer the sync file securely and use the recipient's **Sync Import** to load it.

**Important:** Selective transcript export does **not** include the Azure Speech key or other configuration information. It is not a complete backup. To transfer Azure configuration to iPhone, use the normal **Sync Export** in the main window instead and explicitly choose to include the Azure information.

**Sync Import is not an ordinary file-open operation:** Import includes security checks for the sender, contents, and previously imported packages. A sync file may be rejected if it has already been imported or if the receiving vault contains an object with the same identity but different contents. Do not attempt to bypass these checks by resetting trust or deleting data without first investigating the cause.

Saved transcripts may contain personal or sensitive information. Share them only with intended recipients and make regular portable backups if they are important.

## Basic and Premium

Key2Voice for Windows has two license tiers:

| Feature | Basic | Premium |
|---|---|---|
| Install and try basic speech recognition with your own Azure Speech | Yes | Yes |
| Use Azure Speech | Yes, with your own working Azure resource | Yes, with your own working Azure resource |
| Portable export/import for backup and restore | Yes | Yes |
| Create encrypted **Sync Export** for iPhone | No | Yes |
| Use the iPhone/Watch companion after correct sync import | Requires a sync file created from Windows Premium | Yes, via Sync Export |

**Premium does not automatically provide an Azure account or pay your Azure charges.**

### Before Purchasing Premium

First verify in **Basic** that your own Azure Speech resource works in practice, preferably by transcribing several sentences using the audio source you intend to use. Do **not** purchase Premium until this has succeeded and you have decided that Key2Voice meets your needs.

### Purchase and Verify Premium

Premium is purchased through the Microsoft Store feature in Key2Voice. Open the application's license or **About Key2Voice** view and follow the upgrade instructions. Purchases and entitlements are checked by Microsoft Store; a purchase receipt or restored database alone does not prove that Premium is active on the current installation.

If a purchase is complete but Premium cannot yet be confirmed, Key2Voice may display **Check Premium Again**. This checks an existing purchase without starting a new one. If the option is not displayed or the problem persists, check your Microsoft Store account and contact support without sending payment secrets.

## Synchronize with iPhone and Apple Watch

Key2Voice for iPhone can use an **encrypted sync file** from Windows to obtain the required configuration. **Azure Speech information is not included automatically:** You must explicitly choose to include it during normal Sync Export. **Sync Export from Windows requires Premium.** The iPhone and Watch apps do not have a separate Premium purchase.

### Create a Sync File in Windows

1. Verify that Azure Speech works in Windows and Premium is active.
2. Open the Key2Voice main window and select **Sync Export**.
3. Choose a location for the encrypted sync file (`.k2s`). In the password dialog, enter and confirm a strong **file password** that is different from the vault passphrase.
4. Explicitly select **Include Azure Speech Credentials** if you want iPhone to receive your Azure configuration. The option is unchecked by default, and the application requires additional confirmation before exporting such information. Leave the other options unchanged unless you have a particular reason to change them.
5. Transfer the file to iPhone using a method you control, such as a suitable file-transfer feature. Keep the file password separate and secure.

In Basic, Sync Export is shown as a “greyed-out” Premium feature but cannot be used to create a new sync file.

### Import on iPhone

1. Install Key2Voice for iPhone according to the current distribution instructions.
2. Make the sync file available on iPhone, for example in the **Files** app.
3. Open Key2Voice and select its **Import Sync Data** feature.
4. Select the `.k2s` file and enter the file password you chose during export.
5. Verify that the configuration has been imported and try the app's features.

During normal use, Azure processing runs from iPhone; Windows does not need to remain running after successful initial synchronization. **Apple Watch is a companion to iPhone and must not be described as a standalone Azure client.** Available Watch features and the iPhone connection may depend on the installed version and device configuration.

Read the separate [**Key2Voice iOS user manual**](https://per-ake-olsson.github.io/Support/Key2Voice/iOS/Swe/downloads/Key2Voice_manual_Swe) for more information.

### Sync Fingerprint – Verify the Sender

A sync file may contain important settings and protected information. Key2Voice therefore uses a **sync fingerprint**, an identifier linked to the sender's cryptographic identity. The fingerprint helps the recipient verify **who sent the sync file** before approving import. It is **not** a fingerprint from your finger and is not used for biometric sign-in.

1. Open **Show Sync Fingerprint** under **Settings** in Key2Voice on the Windows computer that creates the sync file.
2. Communicate the fingerprint to the recipient through a **separate, trusted channel** – for example by comparing it directly with the recipient, rather than relying solely on information read from the sync file itself.
3. On the first sync import on iPhone, compare the fingerprint displayed there with the sender's fingerprint.
4. **Approve only if they match and you recognize the sender.** If the values differ or the sender is unknown, cancel the import and investigate why.

The fingerprint helps confirm sender identity. It does **not** replace file-password protection or the need to handle the sync file securely. If the sender identity changes, a new fingerprint may need to be verified.

## Backup and Restore

Key2Voice provides **portable export and import** for database backup and restore. The feature can be used in both **Basic and Premium**.

### Create a Portable Backup

1. Open the Key2Voice main window.
2. Select the **portable export** feature.
3. Choose the storage location and file name as instructed by the dialog.
4. Enter and confirm a **separate backup password** and keep it somewhere safe.
5. Check that the file was created and store it securely, preferably separately from your computer.

### Restore from a Portable Backup

1. Make sure you have the backup (`.k2b`) and **the password used when the file was created**. You may also need **the passphrase for the vault contained in the backup**; it is not necessarily the same as the backup password.
2. Open Key2Voice on the installation where you want to restore the information.
3. Select **portable import** and point to the file.
4. Enter the backup password when prompted. If the restored vault cannot be opened with the current vault passphrase, you may need to enter **the old vault passphrase**.
5. Read the confirmation carefully: the restore operation **replaces the current vault and relevant settings** rather than merging their contents. Then verify that the data and settings have been restored.

**Important:** Restoring a database previously used with Premium does **not** automatically give a new Windows installation a valid Premium license. Microsoft Store entitlements and other licensing evidence are verified separately. **A Basic installation can restore a portable database exported from a Premium installation**, but remains Basic if no valid Premium entitlement exists.

Portable backups and sync files serve different purposes: **portable export** is used for database restore; **Sync Export** is used to transfer configuration to iPhone. Do not confuse the files or their passwords.

## Settings and About Key2Voice

Click **More…** in the **upper-right corner of the main window** and select **Settings**. There you can manage Azure Speech information, language selection, appearance, and vault security settings, among other things.

### Vault Encryption

Under **Settings → Vault Encryption**, the following features are available:

- **Require Passphrase at Startup:** When enabled, you must enter the vault passphrase at startup or when opening the vault, instead of using a previously saved passphrase. This provides extra protection if someone else gains access to the computer. **Always keep a secure copy of the passphrase.**
- **Change Passphrase:** Changes the passphrase for the existing vault. The application requests the current passphrase and the new passphrase with confirmation. The encrypted vault contents are updated to use the new passphrase. Make sure you have a current portable backup and do not interrupt the operation while it is running.
- **Renew KDF:** Renews the vault's password-based key-derivation parameters without requiring you to change the passphrase itself. The application requests the vault passphrase and then updates the vault's encryption protection. This may take a while; wait for the application's confirmation. **The KDF values in the main window** show the parameters after the operation. Higher values provide stronger encryption but also make the application slower. There is currently no feature to “roll back” the KDF.
- **Show Sync Fingerprint:** Displays an identifier that can be used to verify the sender when synchronizing between installations. Compare fingerprints through a trusted channel before approving a new sender.
- **Reset Trusted Sync Senders:** Clears the list of senders previously approved for sync import. Senders must then be approved again. This is a security feature, **not** a way to bypass an import error.

**Important:** Changing the vault passphrase and renewing the KDF affect access to encrypted information. Do not begin these operations without first ensuring that you can restore the vault from a current portable backup. Do not turn off the computer while an operation is in progress.

Under **More… → About Key2Voice**, you can find information about the application, current license status, support options, and any Premium purchase option. Always verify the license status in the application itself after a purchase or restore.

## Troubleshooting

| Problem | Check First |
|---|---|
| No transcribed text appears | That transcription is started, the correct audio source is selected, and audio is actually coming in. |
| The microphone does not work | Microphone connection, Windows microphone permissions, and selected input device. |
| Azure connection fails | Internet connection, exact Speech key, correct region, resource status, and active Azure subscription. |
| Text appears in the wrong language | Incoming spoken language and outgoing text language in Key2Voice. |
| System audio produces no text | Verify that audio is actually playing on the computer and that the correct audio source and playback device are selected. |
| The WAV file cannot be read | That the file is a genuine, compatible WAV file with supported audio encoding. |
| Sync Export or Export Selected is disabled | Whether the Windows license is actually Premium, the vault is open, and (for Export Selected) at least one document is selected. |
| iPhone cannot import the sync file | That the correct `.k2s` file and its file password are used, and that the sender's fingerprint and any import confirmations are handled correctly. |
| Premium does not appear after purchase | Check the Store account, available entitlement checks, and any **Check Premium Again** feature. |
| Portable import fails | Correct `.k2b` file, backup password, any old vault passphrase, and the application's error message. |
| Retrieve is disabled | Stop transcription, save unsaved changes, and select **Clear Text** so the workspace is empty. |
| Sync Import rejects a previously imported package or an existing object | Check the error message. Reimporting the same package and object conflicts may be blocked for security reasons; do not change trust or delete vault data as a shortcut. |

If problems persist, note the application version, Windows version, what you did, and the exact error message. **Never send Azure keys, vault passphrases, sync/export passwords, or sensitive transcripts to support.**

## Security and Privacy

- Key2Voice uses a locally encrypted vault for user-controlled storage and configuration.
- **Speech processed with Azure Speech is sent to Microsoft's cloud service.** This is not offline transcription. Read Microsoft's current terms and privacy information.
- Protect Azure keys and passwords; store backups securely.
- Do not share sync files or portable export files with unauthorized people, even though they are encrypted.
- Do not rely on automatically transcribed or translated text as the sole basis for important medical, legal, or safety-critical decisions.
- Microsoft's cloud services and Windows may process information under their respective terms and privacy policies.

## Updates and Support

Microsoft Store may offer Key2Voice updates. Consider making a **portable backup before major updates**, especially if your saved transcripts are important. Do not uninstall the application or delete its local data without first ensuring that you can restore them.

For questions, bug reports, and feedback: **[contact@eureka.nu](mailto:contact@eureka.nu)**. Please include the application version and a brief description of the problem, but never any secret information.

### Documents and Links

- [Azure Speech guide – create and configure an Azure account (Swedish)](https://per-ake-olsson.github.io/Support/Key2Voice/Azure/Swe/Skapa-Microsoft-Azure-konto)
- [Microsoft Azure portal](https://portal.azure.com/)
- [Microsoft Azure AI Speech – documentation](https://learn.microsoft.com/azure/ai-services/speech-service/)
- [Microsoft Azure – pricing](https://azure.microsoft.com/pricing/)
