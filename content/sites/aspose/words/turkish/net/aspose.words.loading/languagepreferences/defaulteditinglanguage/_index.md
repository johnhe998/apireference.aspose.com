---
title: LanguagePreferences.DefaultEditingLanguage
second_title: Aspose.Words for .NET API Referansı
description: LanguagePreferences mülk. Varsayılan düzenleme dilini alır veya ayarlar.
type: docs
weight: 20
url: /tr/net/aspose.words.loading/languagepreferences/defaulteditinglanguage/
---
## LanguagePreferences.DefaultEditingLanguage property

Varsayılan düzenleme dilini alır veya ayarlar.

Varsayılan değerEnglishUS.

```csharp
public EditingLanguage DefaultEditingLanguage { get; set; }
```

### Örnekler

Belge yüklerken varsayılan dilin nasıl ayarlanacağını gösterir.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(localeId == (int)EditingLanguage.Russian
    ? "The document either has no any language set in defaults or it was set to Russian originally."
    : "The document default language was set to another than Russian language originally, so it is not overridden.");
```

### Ayrıca bakınız

* enum [EditingLanguage](../../editinglanguage/)
* class [LanguagePreferences](../)
* ad alanı [Aspose.Words.Loading](../../languagepreferences/)
* toplantı [Aspose.Words](../../../)


