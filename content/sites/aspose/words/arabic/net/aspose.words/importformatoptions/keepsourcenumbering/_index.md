---
title: ImportFormatOptions.KeepSourceNumbering
second_title: Aspose.Words لمراجع .NET API
description: ImportFormatOptions ملكية. الحصول على أو تعيين قيمة منطقية تحدد كيفية استيراد الترقيم عندما يتعارض في مستندات المصدر و_ المستندات . القيمة الافتراضية هيخاطئة .
type: docs
weight: 50
url: /ar/net/aspose.words/importformatoptions/keepsourcenumbering/
---
## ImportFormatOptions.KeepSourceNumbering property

الحصول على أو تعيين قيمة منطقية تحدد كيفية استيراد الترقيم عندما يتعارض في مستندات المصدر و_ المستندات . القيمة الافتراضية هي`خاطئة` .

```csharp
public bool KeepSourceNumbering { get; set; }
```

### أمثلة

يعرض كيفية حل التعارض عند استيراد المستندات التي تحتوي على قوائم بنفس معرف تعريف القائمة.

```csharp
Document srcDoc = new Document(MyDir + "List with the same definition identifier - source.docx");
Document dstDoc = new Document(MyDir + "List with the same definition identifier - destination.docx");

// اضبط خاصية "KeepSourceNumbering" على "true" لتطبيق معرف تعريف قائمة مختلف
// إلى أنماط متطابقة مثل Aspose.Words تستوردها إلى مستندات الوجهة.
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };

dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, importFormatOptions);
dstDoc.UpdateListLabels();
```

يوضح كيفية استيراد مستند بقوائم مرقمة.

```csharp
Document srcDoc = new Document(MyDir + "List source.docx");
Document dstDoc = new Document(MyDir + "List destination.docx");

Assert.AreEqual(4, dstDoc.Lists.Count);

ImportFormatOptions options = new ImportFormatOptions();

// إذا كان هناك تضارب في أنماط القائمة ، فقم بتطبيق تنسيق القائمة الخاص بالمستند المصدر.
// اضبط خاصية "KeepSourceNumbering" على "false" لعدم استيراد أي أرقام قائمة إلى المستند الوجهة.
// اضبط خاصية "KeepSourceNumbering" على "true" لاستيراد كل التعارضات
// قائمة ترقيم نمط مع نفس المظهر الذي كان عليه في المستند المصدر.
options.KeepSourceNumbering = isKeepSourceNumbering;

dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);
dstDoc.UpdateListLabels();

Assert.AreEqual(isKeepSourceNumbering ? 5 : 4, dstDoc.Lists.Count);
```

يوضح كيفية حل تعارضات ترقيم القائمة في مستندات المصدر والوجهة.

```csharp
// افتح مستندًا بنظام ترقيم قائمة مخصص ، ثم انسخه.
// نظرًا لأن كلاهما لهما نفس تنسيق الترقيم ، فستتعارض التنسيقات إذا قمنا باستيراد مستند إلى الآخر.
Document srcDoc = new Document(MyDir + "Custom list numbering.docx");
Document dstDoc = srcDoc.Clone();

// عندما نستورد نسخة المستند إلى النسخة الأصلية ثم نلحقها ،
// ثم ستنضم القائمتان بنفس تنسيق القائمة.
// إذا قمنا بتعيين علامة "KeepSourceNumbering" على "خطأ" ، فسيتم استنساخ القائمة من المستند
// التي نلحقها بالأصل ستستمر في ترقيم القائمة التي نلحقها بها.
// سيؤدي هذا إلى دمج القائمتين في قائمة واحدة.
// إذا قمنا بتعيين علامة "KeepSourceNumbering" على "true" ، فسيتم استنساخ المستند
// ستحتفظ القائمة بترقيمها الأصلي ، مما يجعل القائمتين تظهران كقائمتين منفصلتين. 
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.KeepSourceNumbering = keepSourceNumbering;

NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepDifferentStyles, importFormatOptions);
foreach (Paragraph paragraph in srcDoc.FirstSection.Body.Paragraphs)
{
    Node importedNode = importer.ImportNode(paragraph, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}

dstDoc.UpdateListLabels();

if (keepSourceNumbering)
{
    Assert.AreEqual(
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4\r\n" +
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4", dstDoc.FirstSection.Body.ToString(SaveFormat.Text).Trim());
}
else
{
    Assert.AreEqual(
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4\r\n" +
        "10. Item 1\r\n" +
        "11. Item 2 \r\n" +
        "12. Item 3\r\n" +
        "13. Item 4", dstDoc.FirstSection.Body.ToString(SaveFormat.Text).Trim());
}
```

### أنظر أيضا

* class [ImportFormatOptions](../)
* مساحة الاسم [Aspose.Words](../../importformatoptions/)
* المجسم [Aspose.Words](../../../)


