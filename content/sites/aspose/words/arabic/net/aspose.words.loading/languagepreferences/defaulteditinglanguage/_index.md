---
title: LanguagePreferences.DefaultEditingLanguage
second_title: Aspose.Words لمراجع .NET API
description: LanguagePreferences ملكية. الحصول على أو تعيين لغة التحرير الافتراضية.
type: docs
weight: 20
url: /ar/net/aspose.words.loading/languagepreferences/defaulteditinglanguage/
---
## LanguagePreferences.DefaultEditingLanguage property

الحصول على أو تعيين لغة التحرير الافتراضية.

النظام الأساسيEnglishUS.

```csharp
public EditingLanguage DefaultEditingLanguage { get; set; }
```

### أمثلة

يوضح كيفية تعيين لغة افتراضية عند تحميل مستند.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(localeId == (int)EditingLanguage.Russian
    ? "The document either has no any language set in defaults or it was set to Russian originally."
    : "The document default language was set to another than Russian language originally, so it is not overridden.");
```

### أنظر أيضا

* enum [EditingLanguage](../../editinglanguage/)
* class [LanguagePreferences](../)
* مساحة الاسم [Aspose.Words.Loading](../../languagepreferences/)
* المجسم [Aspose.Words](../../../)


