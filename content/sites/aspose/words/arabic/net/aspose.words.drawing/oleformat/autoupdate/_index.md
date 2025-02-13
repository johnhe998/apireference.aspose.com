---
title: OleFormat.AutoUpdate
second_title: Aspose.Words لمراجع .NET API
description: OleFormat ملكية. يحدد ما إذا كان الارتباط إلى كائن OLE يتم تحديثه تلقائيًا أم لا في Microsoft Word.
type: docs
weight: 10
url: /ar/net/aspose.words.drawing/oleformat/autoupdate/
---
## OleFormat.AutoUpdate property

يحدد ما إذا كان الارتباط إلى كائن OLE يتم تحديثه تلقائيًا أم لا في Microsoft Word.

```csharp
public bool AutoUpdate { get; set; }
```

### ملاحظات

النظام الأساسي **خاطئة**.

### أمثلة

يوضح كيفية استخراج كائنات OLE المضمنة في الملفات.

```csharp
Document doc = new Document(MyDir + "OLE spreadsheet.docm");
Shape shape = (Shape)doc.GetChild(NodeType.Shape, 0, true);

// كائن OLE في الشكل الأول هو جدول بيانات Microsoft Excel.
OleFormat oleFormat = shape.OleFormat;

Assert.AreEqual("Excel.Sheet.12", oleFormat.ProgId);

// كائننا لا يتم تحديثه تلقائيًا ولا يتم قفله من التحديثات.
Assert.False(oleFormat.AutoUpdate);
Assert.AreEqual(false, oleFormat.IsLocked);

// إذا كنا نخطط لحفظ كائن OLE في ملف في نظام الملفات المحلي ،
// يمكننا استخدام خاصية "اقتراح ملحق" لتحديد امتداد الملف المطلوب تطبيقه على الملف.
Assert.AreEqual(".xlsx", oleFormat.SuggestedExtension);

// فيما يلي طريقتان لحفظ كائن OLE إلى ملف في نظام الملفات المحلي.
// 1 - احفظه عبر تيار:
using (FileStream fs = new FileStream(ArtifactsDir + "OLE spreadsheet extracted via stream" + oleFormat.SuggestedExtension, FileMode.Create))
{
    oleFormat.Save(fs);
}

// 2 - احفظه مباشرة في اسم ملف:
oleFormat.Save(ArtifactsDir + "OLE spreadsheet saved directly" + oleFormat.SuggestedExtension);
```

### أنظر أيضا

* class [OleFormat](../)
* مساحة الاسم [Aspose.Words.Drawing](../../oleformat/)
* المجسم [Aspose.Words](../../../)


