---
title: Class LanguagePreferences
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Loading.LanguagePreferences فصل. يسمح بإعداد تفضيلات اللغة .
type: docs
weight: 3450
url: /ar/net/aspose.words.loading/languagepreferences/
---
## LanguagePreferences class

يسمح بإعداد تفضيلات اللغة .

```csharp
public class LanguagePreferences
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [LanguagePreferences](languagepreferences/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [DefaultEditingLanguage](../../aspose.words.loading/languagepreferences/defaulteditinglanguage/) { get; set; } | الحصول على أو تعيين لغة التحرير الافتراضية. |

## طُرق

| اسم | وصف |
| --- | --- |
| [AddEditingLanguage](../../aspose.words.loading/languagepreferences/addeditinglanguage/)(EditingLanguage) | يضيف لغة تحرير إضافية . |
| [AddEditingLanguages](../../aspose.words.loading/languagepreferences/addeditinglanguages/)(EditingLanguage[]) | إضافة لغات تحرير إضافية . |

### ملاحظات

Implements "تعيين مربع حوار تفضيلات لغة Office" في Word.

### أمثلة

يوضح كيفية تطبيق تفضيلات اللغة عند تحميل مستند.

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

Document doc = new Document(MyDir + "No default editing language.docx", loadOptions);

int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(localeIdFarEast == (int)EditingLanguage.Japanese
    ? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
    : "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Loading](../../aspose.words.loading/)
* المجسم [Aspose.Words](../../)


