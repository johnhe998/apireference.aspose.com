---
title: Class LanguagePreferences
second_title: Aspose.Words for .NET API Referansı
description: Aspose.Words.Loading.LanguagePreferences sınıf. Dil tercihlerini ayarlamanıza izin verir.
type: docs
weight: 3450
url: /tr/net/aspose.words.loading/languagepreferences/
---
## LanguagePreferences class

Dil tercihlerini ayarlamanıza izin verir.

```csharp
public class LanguagePreferences
```

## yapıcılar

| İsim | Tanım |
| --- | --- |
| [LanguagePreferences](languagepreferences/)() | Default_Constructor |

## Özellikleri

| İsim | Tanım |
| --- | --- |
| [DefaultEditingLanguage](../../aspose.words.loading/languagepreferences/defaulteditinglanguage/) { get; set; } | Varsayılan düzenleme dilini alır veya ayarlar. |

## yöntemler

| İsim | Tanım |
| --- | --- |
| [AddEditingLanguage](../../aspose.words.loading/languagepreferences/addeditinglanguage/)(EditingLanguage) | Ek düzenleme dili ekler. |
| [AddEditingLanguages](../../aspose.words.loading/languagepreferences/addeditinglanguages/)(EditingLanguage[]) | Ek düzenleme dilleri ekler. |

### Notlar

Word'de 'Ofis Dil Tercihlerini Ayarla' iletişim kutusunu uygular.

### Örnekler

Belge yüklerken dil tercihlerinin nasıl uygulanacağını gösterir.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(localeIdFarEast == (int)EditingLanguage.Japanese
    ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
    : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

### Ayrıca bakınız

* ad alanı [Aspose.Words.Loading](../../aspose.words.loading/)
* toplantı [Aspose.Words](../../)


