---
title: BuiltInDocumentProperties.Company
second_title: Aspose.Words لمراجع .NET API
description: BuiltInDocumentProperties ملكية. الحصول على أو تعيين خاصية الشركة .
type: docs
weight: 70
url: /ar/net/aspose.words.properties/builtindocumentproperties/company/
---
## BuiltInDocumentProperties.Company property

الحصول على أو تعيين خاصية الشركة .

```csharp
public string Company { get; set; }
```

### أمثلة

يوضح كيفية العمل مع خصائص المستند في فئة "الأصل".

```csharp
// افتح مستندًا أنشأناه وحررناه باستخدام Microsoft Word.
Document doc = new Document(MyDir + "Properties.docx");
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;

// تحتوي الخصائص المضمنة التالية على معلومات تتعلق بإنشاء هذا المستند وتحريره.
// يمكننا النقر بزر الماوس الأيمن فوق هذا المستند في مستكشف Windows والعثور عليه
// هذه الخصائص عبر "خصائص" - >; "التفاصيل" - >. فئة "الأصل".
// يمكن للحقول مثل PRINTDATE و EDITTIME عرض هذه القيم في نص المستند.
Console.WriteLine($"Created using {properties.NameOfApplication}, on {properties.CreatedTime}");
Console.WriteLine($"Minutes spent editing: {properties.TotalEditingTime}");
Console.WriteLine($"Date/time last printed: {properties.LastPrinted}");
Console.WriteLine($"Template document: {properties.Template}");

// يمكننا أيضًا تغيير قيم الخصائص المضمنة.
properties.Company = "Doe Ltd.";
properties.Manager = "Jane Doe";
properties.Version = 5;
properties.RevisionNumber++;

// يقوم Microsoft Word بتحديث الخصائص التالية تلقائيًا عندما نحفظ المستند.
// لاستخدام هذه الخصائص مع Aspose.Words ، سنحتاج إلى تعيين قيم لها يدويًا.
properties.LastSavedBy = "John Doe";
properties.LastSavedTime = DateTime.Now;

// يمكننا النقر بزر الماوس الأيمن فوق هذا المستند في مستكشف Windows والعثور عليه these properties in "Properties" -> "Details" -> "Origin".
doc.Save(ArtifactsDir + "DocumentProperties.Origin.docx");
```

### أنظر أيضا

* class [BuiltInDocumentProperties](../)
* مساحة الاسم [Aspose.Words.Properties](../../builtindocumentproperties/)
* المجسم [Aspose.Words](../../../)


