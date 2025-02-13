---
title: Class LanguagePreferences
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Loading.LanguagePreferences klas. Ermöglicht die Einrichtung von Spracheinstellungen.
type: docs
weight: 3450
url: /de/net/aspose.words.loading/languagepreferences/
---
## LanguagePreferences class

Ermöglicht die Einrichtung von Spracheinstellungen.

```csharp
public class LanguagePreferences
```

## Konstrukteure

| Name | Beschreibung |
| --- | --- |
| [LanguagePreferences](languagepreferences/)() | Default_Constructor |

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [DefaultEditingLanguage](../../aspose.words.loading/languagepreferences/defaulteditinglanguage/) { get; set; } | Ruft die Standardbearbeitungssprache ab oder legt sie fest. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [AddEditingLanguage](../../aspose.words.loading/languagepreferences/addeditinglanguage/)(EditingLanguage) | Fügt eine zusätzliche Bearbeitungssprache hinzu. |
| [AddEditingLanguages](../../aspose.words.loading/languagepreferences/addeditinglanguages/)(EditingLanguage[]) | Fügt zusätzliche Bearbeitungssprachen hinzu. |

### Bemerkungen

Implementiert das Dialogfeld „Office-Spracheinstellungen festlegen“ in Word.

### Beispiele

Zeigt, wie Spracheinstellungen beim Laden eines Dokuments angewendet werden.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(localeIdFarEast == (int)EditingLanguage.Japanese
    ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
    : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

### Siehe auch

* namensraum [Aspose.Words.Loading](../../aspose.words.loading/)
* Montage [Aspose.Words](../../)


