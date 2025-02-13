---
title: LanguagePreferences.AddEditingLanguage
second_title: Referencia de API de Aspose.Words para .NET
description: LanguagePreferences método. Añade idioma de edición adicional.
type: docs
weight: 30
url: /es/net/aspose.words.loading/languagepreferences/addeditinglanguage/
---
## LanguagePreferences.AddEditingLanguage method

Añade idioma de edición adicional.

```csharp
public void AddEditingLanguage(EditingLanguage language)
```

### Ejemplos

Muestra cómo aplicar preferencias de idioma al cargar un documento.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(localeIdFarEast == (int)EditingLanguage.Japanese
    ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
    : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

### Ver también

* enum [EditingLanguage](../../editinglanguage/)
* class [LanguagePreferences](../)
* espacio de nombres [Aspose.Words.Loading](../../languagepreferences/)
* asamblea [Aspose.Words](../../../)


