---
title: LoadOptions.LanguagePreferences
second_title: Aspose.Words för .NET API Referens
description: LoadOptions fast egendom. Får språkinställningar som kommer att användas när dokumentet laddas.
type: docs
weight: 80
url: /sv/net/aspose.words.loading/loadoptions/languagepreferences/
---
## LoadOptions.LanguagePreferences property

Får språkinställningar som kommer att användas när dokumentet laddas.

```csharp
public LanguagePreferences LanguagePreferences { get; }
```

### Exempel

Visar hur du använder språkinställningar när du laddar ett dokument.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(localeIdFarEast == (int)EditingLanguage.Japanese
    ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
    : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

### Se även

* class [LanguagePreferences](../../languagepreferences/)
* class [LoadOptions](../)
* namnutrymme [Aspose.Words.Loading](../../loadoptions/)
* hopsättning [Aspose.Words](../../../)


