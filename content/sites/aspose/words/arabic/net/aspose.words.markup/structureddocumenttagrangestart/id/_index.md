---
title: StructuredDocumentTagRangeStart.Id
second_title: Aspose.Words لمراجع .NET API
description: StructuredDocumentTagRangeStart ملكية. يحدد معرّفًا رقميًا فريدًا للقراءة فقط مستمرًا لعلامة المستند المهيكلة هذه.
type: docs
weight: 40
url: /ar/net/aspose.words.markup/structureddocumenttagrangestart/id/
---
## StructuredDocumentTagRangeStart.Id property

يحدد معرّفًا رقميًا فريدًا للقراءة فقط مستمرًا لعلامة المستند المهيكلة هذه.

```csharp
public int Id { get; }
```

### ملاحظات

يجب أن تتبع سمة المعرّف القواعد التالية:

* يجب أن يحتفظ المستند بمعرفات وسم المستند المهيكلة فقط إذا تم استنساخ document بالكامل[`Clone`](../../../aspose.words/document/clone/).
* أثناء[`ImportNode`](../../../aspose.words/documentbase/importnode/) يجب الاحتفاظ بالمعرف إذا لم يتسبب الاستيراد في تعارض مع معرفات علامة المستند المنظمة الأخرى في المستند الهدف.
* إذا حددت العديد من عقد علامة المستند المهيكلة نفس قيمة الرقم العشري لسمة المعرف ، فإن علامة المستند المهيكلة الأولى في المستند يجب أن تحتفظ بهذا المعرف الأصلي ، وجميع عقد علامة المستند المهيكلة اللاحقة يجب تعيين معرفات جديدة لها عندما تم تحميل المستند.
* أثناء علامة مستند منظم مستقلINodeCloningListener) سيتم إنشاء المعرف الفريد الجديد للعملية be لعقدة علامة المستند المهيكلة المستنسخة.
* إذا لم يتم تحديد المعرف في المستند المصدر ، فيجب أن يكون لعقدة علامة المستند المنظم معرفًا فريدًا جديدًا يتم تعيينه لها عند تحميل المستند.

### أمثلة

يوضح كيفية الحصول على خصائص علامات المستندات المنظمة متعددة الأقسام.

```csharp
Document doc = new Document(MyDir + "Multi-section structured document tags.docx");

StructuredDocumentTagRangeStart rangeStartTag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeStart, true)[0] as StructuredDocumentTagRangeStart;
StructuredDocumentTagRangeEnd rangeEndTag =
    doc.GetChildNodes(NodeType.StructuredDocumentTagRangeEnd, true)[0] as StructuredDocumentTagRangeEnd;

Console.WriteLine("StructuredDocumentTagRangeStart values:");
Console.WriteLine($"\t|Id: {rangeStartTag.Id}");
Console.WriteLine($"\t|Title: {rangeStartTag.Title}");
Console.WriteLine($"\t|PlaceholderName: {rangeStartTag.PlaceholderName}");
Console.WriteLine($"\t|IsShowingPlaceholderText: {rangeStartTag.IsShowingPlaceholderText}");
Console.WriteLine($"\t|LockContentControl: {rangeStartTag.LockContentControl}");
Console.WriteLine($"\t|LockContents: {rangeStartTag.LockContents}");
Console.WriteLine($"\t|Level: {rangeStartTag.Level}");
Console.WriteLine($"\t|NodeType: {rangeStartTag.NodeType}");
Console.WriteLine($"\t|RangeEnd: {rangeStartTag.RangeEnd}");
Console.WriteLine($"\t|Color: {rangeStartTag.Color.ToArgb()}");
Console.WriteLine($"\t|SdtType: {rangeStartTag.SdtType}");
Console.WriteLine($"\t|FlatOpcContent: {rangeStartTag.WordOpenXML}");
Console.WriteLine($"\t|Tag: {rangeStartTag.Tag}\n");

Console.WriteLine("StructuredDocumentTagRangeEnd values:");
Console.WriteLine($"\t|Id: {rangeEndTag.Id}");
Console.WriteLine($"\t|NodeType: {rangeEndTag.NodeType}");
```

### أنظر أيضا

* class [StructuredDocumentTagRangeStart](../)
* مساحة الاسم [Aspose.Words.Markup](../../structureddocumenttagrangestart/)
* المجسم [Aspose.Words](../../../)


