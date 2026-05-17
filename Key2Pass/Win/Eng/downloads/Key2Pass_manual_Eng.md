Key2Pass Win - User Manual
=================================
## Purpose
The purpose of Key2Pass is to support users of Windows and iOS devices in login situations. Users can create and use very strong passwords without storing them anywhere or needing to remember them. Instead, the user enters a logical, case-sensitive **alias** that is easier to remember, allowing Key2Pass to generate the correct password during login.

## Introduction
Key2Pass consists of a Windows application where, in addition to receiving login support, you can also create aliases and generate an encrypted database **[requires Premium]**. There is also an associated iOS app that can import this database to generate identical passwords associated with an alias. You export the database from the Windows version to a file **[requires Premium]**, which you then transfer yourself to your iOS device and import into the app. The transfer is performed manually – Key2Pass does not collect any personal data and does not send any information to external servers.

## Security Principles
Key2Pass is a tool for creating and recreating strong passwords based on an arbitrarily chosen **alias**, an associated **4-digit PIN code**, and your unique **userId**. All work is performed through the program icon in the system tray and global keyboard shortcuts. The program generates passwords in real time locally on your computer and does not store any secret keys or passwords in plain text. Passwords are reproducibly created from the alias, its PIN code, and your userId – they can be recreated when you need them, but are very difficult for others to guess. No data communication takes place and no passwords are stored, either in plain text or encrypted. For high security, you should choose original alias names and PIN codes, avoid sharing them with others, and make regular backups of the alias database.

## Installation and Startup
Key2Pass is delivered as an MSIX installer via the MS Store. Follow the instructions to get access to Key2Pass Basic free of charge. The program files are installed and a shortcut is added to the Start menu.

The first time after a new installation, you may need to start the program manually from the Start menu. You must also enter a passphrase for the database. This passphrase is your unique key to the database (the vault); without it, the vault cannot be opened. The passphrase is automatically saved in your Windows keychain and is used to open the vault automatically every time you log in to Windows. However, you must still be able to enter the correct passphrase yourself if you need to open the vault manually (after manually closing it), or if you want to change the passphrase or rotate the vault's encryption keys. THERE IS NO WAY TO RECOVER THE VAULT PASSPHRASE IF YOU LOSE IT, SO STORE IT SECURELY.

Thereafter, the program starts automatically every time you log in to Windows. You can also choose to prevent automatic startup (under Windows Settings) and instead start Key2Pass from the Start menu.

The program runs entirely in the background and only displays a key icon in the system tray. No window opens automatically; all interaction takes place through the icon's context menu and through hotkeys.

## Key2Pass (Main Window)
Right-click the Key2Pass icon and select **Open Key2Pass** to open the main window. Here you can see information about your database and license level. You can also open a dialog to create/edit your different login IDs (up to 5 different IDs), see below.

In the main window, you can also close and open (requires the correct passphrase) the vault (database), as well as export and import the database for backup and/or import to Key2Pass iOS.

Finally, from the main window you can also create and edit aliases and generate passwords, see below.

## Settings
Settings are accessed through the tray icon:

* Right-click the Key2Pass icon and select **Settings** to open the settings dialog.
* In the dialog, you can set how long a copied password should remain on the clipboard (copy duration), choose the encryption algorithm and language, and select the visual theme.
* In the settings dialog, you can also view and change the program license, and upgrade/downgrade. If a Premium license with more than 10 aliases in the database is downgraded, only the first 10 aliases will remain available for continued use.
* You can change the passphrase for the vault (database), after first entering the current passphrase.
* For security reasons, you can also change the encryption keys for the vault without affecting the generated passwords.

## Creating New Aliases
An alias functions as a label which, together with a 4-digit PIN code and your unique userId, generates a strong password according to the policy you selected (i.e. rules for password length and which characters may be used). With the **Basic** license, you can have a maximum of 10 aliases; with the **Premium** license, there is no limit. You can create a new alias from the alias window or from the main window:

1. Place the cursor in an input field.
2. Press the global keyboard shortcut **Ctrl+Shift+P** to open the alias window.
3. Enter the alias name (case sensitive). After entering the name, use the right-click menu to continue.
4. Right-click in the window and select **New Alias**. A dialog window opens where you can specify the alias policy (e.g. password length, character classes) and a 4-digit PIN code. You can also enter a domain name (optional). The PIN code and any domain name are used together with the alias to generate, on command, a unique password according to the defined policy.
5. When you save the alias, the program automatically generates the password according to the policy and copies it to the clipboard. The password is only visible through the clipboard for the amount of time you have set; after that, the clipboard is cleared.

You can also create a new alias from the main window. Click the **New Alias** button to open the dialog window for creating an alias as described in step 4 above.

## Editing Existing Aliases
An existing alias can be edited or deleted in the edit window, which can be opened from the alias window or the main window.

1. Place the cursor in an input field.
2. Open the alias window with **Ctrl+Shift+P** and enter the name of the existing alias (case sensitive).
3. Right-click in the alias window and select **Edit Alias**. A dialog window is displayed where you can change the alias policy (e.g. password length, character classes) and/or change or keep the 4-digit PIN code.
4. When you save the changes, the alias is updated. Each alias uses its own PIN code. If you do not enter a new PIN code, the previous PIN code for the alias is reused. There is no way to later see which PIN code was chosen for a particular alias, but the code does not need to be remembered and is never entered during use.

You can also edit an alias from the main window. Select an alias from the list, then click the **Edit Alias** button to open the dialog window for editing an alias as described in step 3 above.

## Using Stored Usernames (login IDs)
You can store up to five **login IDs** in the dialog accessible from the main window (User1–User5). These are easily copied to the clipboard with hotkeys. The purpose is to make your logins easier through faster input. Users are responsible for keeping track of which usernames should be used for different logins and which keyboard shortcuts they are assigned to:

* **Ctrl+Shift+1** to **Ctrl+Shift+5** (1–5 from the top number row) copy the usernames.
* **Ctrl+Alt+NumPad1** to **Ctrl+Alt+NumPad5** do the same thing through the numeric keypad.
* After using the keyboard shortcut, press **Ctrl+V** to paste the username into the corresponding field in the login dialog.

## Generating Passwords
You can generate passwords in the following two ways, both through the alias window. In both cases, the starting point is that you place the cursor in the input field where the password should be entered. The alias window always opens empty — type the alias you want to use. If the alias does not exist, an error message is displayed. Remember that the alias is case-sensitive.

* 1a) Press **Ctrl+Shift+P**, type the alias in the window, and press **Enter**, or
* 1b) Press **Ctrl+Shift+P**, type the alias in the window, **right-click** in the window, and select **Generate Password**.

You can also generate passwords from the main window by selecting the relevant alias from the list and then clicking the **Generate Password** button.

After the password has been generated, return to the password field in the login dialog and press **Ctrl+V**, after which the password is copied into the input field.

The program uses the alias policy and PIN code to create the password and copies it to the clipboard. The clipboard is automatically cleared after the time you have set.

## About Key2Pass
Right-click the Key2Pass icon and select **About Key2Pass** to open the information window. Here you can see information about the app, such as the version and current license level. From here, you can also initiate the purchase of a license upgrade or downgrade. There is also a link to the Key2Pass support page, where you can find more information and report issues.

## Exit
To temporarily exit Key2Pass, right-click the Key2Pass icon in the system tray and select **Exit**. The app can be restarted manually during the same Windows session by starting it from the Start menu. The vault passphrase is then retrieved from the Windows keychain.

## Backup and Restore
To protect your aliases, you should regularly export the alias list to a backup file and be able to import it later if needed. The backup contains all the information needed for you to use your aliases to generate the correct passwords after the file has been imported to one of the Key2Pass platforms. The backup file is encrypted using a password that you enter during export. BE VERY CAREFUL TO REMEMBER THIS PASSWORD. THERE IS NO WAY TO ACCESS THE CONTENTS OF THE FILE WITHOUT THIS PASSWORD, AND THERE IS NO WAY TO RECOVER THE PASSWORD IF YOU LOSE IT.

* **Export Portable File [Premium and Basic]:** For backup and/or transfer to another Windows installation. Open the main window and select the **Export Portable File** button. You choose the location and file name (the suggested name is *backup.portable.json*) and enter a file password twice. The file is encrypted and can be opened on other Key2Pass platforms with the file password. Store the file password securely – it cannot be recovered and the file cannot be opened without this password.

* **Sync Export [Premium]:** For export to another platform, including iOS, with AES-CBC + HMAC encryption. Open the main window and select the **Sync Export** button. You choose the file location and name (the suggested name is *sync.k2s*) and enter a file password twice. You also choose the encryption method (AES-CBC + HMAC for iOS). The file is encrypted and can be opened on other Key2Pass platforms with the file password. Store the file password securely – it cannot be recovered and the file cannot be opened without this password.

* **Import Portable File [Premium and Basic]:** To restore the entire database from a backup, or load the database onto a new device, select **Import Portable File** in the main window and choose the JSON file you want to load. The import should be performed into a newly installed version of Key2Pass with an empty database. Importing into an existing database will fail if aliases from the backup already exist in the database. If the backup only contains new aliases that are not already in the database, the import will be completed. However, the new aliases will likely generate different passwords than they did previously.

* **Sync Import [Premium and Basic]:** To update the database from a backup or load the database onto a new device, click **Sync Import** in the main window and choose the sync file you want to load. For existing aliases, the latest version will be retained in the database after import. If you want to load an older alias version from the backup, you must therefore first delete the later alias from the database.

## Installing a New Key2Pass Version
A new major program version can be installed without removing the previous version; this is then done automatically by the installer after your approval. A major program version means a change to one of the first three version numbers (e.g. from version 1.0.1 to version 1.0.2).

***Note that when installing a new major version without first uninstalling the previous version, the existing database is reused! As an extra precaution, you are nevertheless recommended to ALWAYS MAKE A CURRENT BACKUP using the export command BEFORE STARTING THE INSTALLATION!***

If you choose to first uninstall Key2Pass through the Start menu Settings, the database will also be deleted. To then reinstall Key2Pass and restore your alias data, you must have access to a backup file and its file password.

Backups should be stored in a secure place and the passwords for backup files should be kept securely.

After a new installation, Key2Pass may need to be started manually from the Start menu before the program icon appears in the system tray and the Ctrl+Shift+P keyboard shortcut works again.

## Complete Uninstallation of Key2Pass
If you no longer want to use Key2Pass, or for any other reason want to completely uninstall Key2Pass, do this through the Start menu. Open Settings - Apps - Key2Pass and select Uninstall. All parts of Key2Pass, except the backup files you created yourself and stored in a secure place, will then be deleted from the computer.

## Tips for Security and Use

* By being able to associate a specific, case-sensitive alias with a specific service login, you do not need to remember secure, complicated passwords; they are generated for you when needed.
* Always choose **unique alias names** and **strong 4-digit PIN codes**. Do not share your aliases or PIN codes with others.
* To change the generated password, if this is required for security reasons, it is enough to change the PIN code. A completely new password is then generated, associated with the same alias as before and with the same policy retained.
* Change alias policies (e.g. length or character classes) easily if security requirements change; the same alias can be retained.
* Be careful with global hotkeys if you share a computer; passwords are copied to the clipboard and cleared after a time limit, but do not leave the computer unattended during this period.
* Store your backup files in a secure place and remember the file passwords.
* Regularly check that you have the latest version of the program to receive security updates and new features.

This concludes the manual for the Key2Pass Windows version. All functions can be accessed through the system tray and keyboard shortcuts, making the tool discreet and efficient.
