---
title: LanguagePreferences.AddEditingLanguage
second_title: Aspose.Words per .NET API Reference
description: LanguagePreferences metodo. Aggiunge un linguaggio di modifica aggiuntivo.
type: docs
weight: 30
url: /it/net/aspose.words.loading/languagepreferences/addeditinglanguage/
---
## LanguagePreferences.AddEditingLanguage method

Aggiunge un linguaggio di modifica aggiuntivo.

```csharp
public void AddEditingLanguage(EditingLanguage language)
```

### Esempi

Mostra come applicare le preferenze della lingua durante il caricamento di un documento.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(localeIdFarEast == (int)EditingLanguage.Japanese
    ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
    : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

### Guarda anche

* enum [EditingLanguage](../../editinglanguage/)
* class [LanguagePreferences](../)
* spazio dei nomi [Aspose.Words.Loading](../../languagepreferences/)
* assemblea [Aspose.Words](../../../)


