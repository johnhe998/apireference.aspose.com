---
title: LanguagePreferences.DefaultEditingLanguage
second_title: Aspose.Words für .NET-API-Referenz
description: LanguagePreferences eigendom. Ruft die Standardbearbeitungssprache ab oder legt sie fest.
type: docs
weight: 20
url: /de/net/aspose.words.loading/languagepreferences/defaulteditinglanguage/
---
## LanguagePreferences.DefaultEditingLanguage property

Ruft die Standardbearbeitungssprache ab oder legt sie fest.

Der Standardwert istEnglishUS.

```csharp
public EditingLanguage DefaultEditingLanguage { get; set; }
```

### Beispiele

Zeigt, wie eine Standardsprache beim Laden eines Dokuments festgelegt wird.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(localeId == (int)EditingLanguage.Russian
    ? "The document either has no any language set in defaults or it was set to Russian originally."
    : "The document default language was set to another than Russian language originally, so it is not overridden.");
```

### Siehe auch

* enum [EditingLanguage](../../editinglanguage/)
* class [LanguagePreferences](../)
* namensraum [Aspose.Words.Loading](../../languagepreferences/)
* Montage [Aspose.Words](../../../)


