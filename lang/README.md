# NiceHash QuickMiner Multilanguage Support

From  **[version 0.5.0.0 NiceHash QuickMiner](https://github.com/nicehash/NiceHashQuickMiner/releases)** features comprehensive multilanguage support. This guide provides the workflow for creating, testing, and updating language files.
---

## 🏗️ How to Create a Language File

1.  **Download the Base:** Download [dump_en.json](/lang/dump_en.json).
2.  **Edit Strings:** All strings are marked with a token (the first element of the array). **Modify only the second element.**
3.  **Naming Convention:** Use the two-letter language code (e.g., `en`, `de`, `pt`, `es`, `ru`) plus the `.json` extension.
4.  **Requirements:** * **Format:** Must be valid JSON.
    * **Encoding:** Must be **UTF-8**.
    * **Validation:** Use tools like [JSON Formatter](https://jsonformatter.curiousconcept.com/) to verify your file.
5.  **Submit:** Submit a Pull Request for your translation to be reviewed and accepted.

---

## 🧪 How to Test a Language File

1.  Pick an existing language (other than **en**) and quit NiceHash QuickMiner.
2.  Navigate to the `.\\langs\\` directory.
3.  Identify the chosen language file, open it, and copy the `version` value into your new language file.
4.  Delete the original language file, copy your new file into the directory, and rename it to match the deleted file.
5.  Start NiceHash QuickMiner; the selected language will now display your translations.

### UI Testing Commands
Append these command line arguments to view specific dialogs:

| Command Line | Dialog Shown |
| :--- | :--- |
| `--install` | Download & Installer |
| `--uninstall` | Uninstall Dialog |
| `--count` | Windows start-up counter before standard launch |
| `--updatedfrom 0.3.0.0` | Update-related message boxes before launch |

**Example:** `NiceHashQuickMiner.exe --install`

*To revert, simply delete your custom language file.*

---

## 🔄 How to Update a Language File

When strings are added or modified, the version number increases. To sync:

1. Set your language in the config file.
2. Execute: `NiceHashQuickMiner.exe --language-dump`
3. This will dump your language file and print missing strings to the console. 
4. Check [UPDATES.md](/lang/UPDATES.md) for a list of modified existing strings.
5. Ensure the final file remains valid JSON and UTF-8 encoded before submitting your Pull Request.

---

## 🖋️ Special: Translating EULA RTF

> [!IMPORTANT]
> Requires the latest `NiceHashQuickMiner.exe`. [Download here](https://github.com/nicehash/NiceHashQuickMiner/releases).

1. Write and style your text in **WordPad**.
2. Save it as an RTF file (e.g., `example.rtf`).
3. Run the conversion command:
   `NiceHashQuickMiner.exe --port-rtf example.rtf translated.txt`
4. Copy the content from `translated.txt` and paste it into your language JSON file.

---


file_path = "NiceHash_Multilanguage_Guide_v6.md"
