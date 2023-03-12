# Verify your translations

### Download your PO file[¶](broken-reference)

If your translations are on Launchpad, download them as a PO file, as explained in [Download the translations](broken-reference).

Create a `translations` directory in your home directory and put your PO file in it.

### Verify your PO file with mint-check-translations[¶](broken-reference)

To check your translations, open a terminal and type:

```
mint-check-translations ~/translations
```

This opens the translation checking tool and highlights errors in your PO file:

[![\_images/mint-check-translations.png](<../../../.gitbook/assets/mint check translations.png>)](<../../../.gitbook/assets/mint check translations.png>)

This tool won’t highlight translation mistakes you might make (grammar, spelling, etc.), but it will ensure your translations are properly structured and won’t affect the software you’re translating. Among other things, this tool checks that special meaningful characters are preserved, that variables are still there, etc.

Note

This tool can scan multiple PO files and recurse through sub-directories. It is used by the Linux Mint team to check all translations.

### Common mistakes[¶](broken-reference)

### In software applications[¶](broken-reference)

The most commonly made mistake when translating source code is not respecting variables.

Here are a few examples of wrong translations:

| Original                             | Translation                            | Error                     |
| ------------------------------------ | -------------------------------------- | ------------------------- |
| The file %s could not be found       | Le fichier % s est introuvable         | % s instead of %s         |
| The file %s could not be found       | Le fichier %d est introuvable          | %d instead of %s          |
| The file %s could not be found       | Le fichier est introuvable             | Missing variable          |
| The file %(file)s could not be found | Le fichier %(fichier)s est introuvable | Missing variable %(file)s |

If variables are malformed, missing, or if their name doesn’t match the original source code, the application you are translating could crash when run in your language.

### In documentation written in RST[¶](broken-reference)

The most commonly made mistake when translating RST documentation is not respecting double quotes, arrows or RST directives.

Here are a few examples of wrong translations:

| Original                              | Translation                                 | Error             |
| ------------------------------------- | ------------------------------------------- | ----------------- |
| Open a terminal and type \`\`ls\`\`   | Ouvrez un terminal et tapez “ls”            | ” instead of \`\` |
| Click :guilabel:\`Save\`              | Cliquez sur :guilabel:’Save’                | ‘ instead of \`   |
| Click :guilabel:\`Save\`              | Cliquez sur :guilabel:\`Save                | Missing one \`    |
| Click :guilabel:\`Save\`              | Cliquez sur guilabel:\`Save\`               | Missing one :     |
| Click :menuselection:\`Menu –> Save\` | Cliquez sur :menuselection:\`Menu -> Save\` | -> instead of –>  |

Special characters such as `` ` ``, `-->`, directives such as `:guilabel:`, `:menuselection::`, and links using `<` and `>` are important because they define the structure and the look of the document.

Make sure to respect them and translate content accurately.

If you think the original sentence is missing something, then propose a modification to the original documentation. You cannot deviate or add content to your translation which isn’t present in the original.

### Other mistakes[¶](broken-reference)

#### Politics[¶](broken-reference)

When translating content, your main worry should be the user.

The user experience is what matters the most.

Software and documentation should be easy to use and any text you translate should be easy to read and to understand.

The user experience is more important than any other consideration, including official language definitions, language preservation policies or politics in general.

If the official translation for a given word isn’t commonly known or used by users, you should not use it. Prefer the terms used by most people instead. The goal isn’t to educate users or to enforce anything. Correctness and exactitude are important but not as much as user experience.

If everyone around you says A and your government and/or dictionary says B, whether you agree with one side or the other isn’t relevant, go for A.

#### Translating content which shouldn’t be translated[¶](broken-reference)

If something is in English on the screen, refer to it in English as well.

For instance, the boot menu for Linux Mint says `Start Linux Mint`, no matter what language the user uses. So it should be refered to as `Start Linux Mint` in any documentation, whether that documentation is in English or not.
