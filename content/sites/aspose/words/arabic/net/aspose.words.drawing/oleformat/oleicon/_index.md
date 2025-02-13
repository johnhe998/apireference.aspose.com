---
title: OleFormat.OleIcon
second_title: Aspose.Words لمراجع .NET API
description: OleFormat ملكية. الحصول على وجه الرسم لكائن OLE. متي حقيقي  يتم عرض كائن OLE كرمز. متى خاطئة  يتم عرض كائن OLE كمحتوى.
type: docs
weight: 70
url: /ar/net/aspose.words.drawing/oleformat/oleicon/
---
## OleFormat.OleIcon property

الحصول على وجه الرسم لكائن OLE. متي **حقيقي** ، يتم عرض كائن OLE كرمز. متى **خاطئة** ، يتم عرض كائن OLE كمحتوى.

```csharp
public bool OleIcon { get; }
```

### ملاحظات

لا يسمح Aspose.Words بتعيين هذه الخاصية لتجنب الالتباس. إذا كنت قادرًا على تغيير جانب الرسم في Aspose.Words ، فسيظل Microsoft Word يعرض كائن OLE في جانب الرسم الأصلي حتى تقوم بتحرير أو تحديث كائن OLE في Microsoft Word.

### أمثلة

يوضح كيفية إدراج كائنات OLE المرتبطة وغير المرتبطة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// تضمين رسم Microsoft Visio في المستند ككائن OLE.
builder.InsertOleObject(ImageDir + "Microsoft Visio drawing.vsd", "Package", false, false, null);

// أدخل رابطًا للملف في نظام الملفات المحلي واعرضه كرمز.
builder.InsertOleObject(ImageDir + "Microsoft Visio drawing.vsd", "Package", true, true, null);

// يؤدي إدراج كائنات OLE إلى إنشاء أشكال تخزن هذه الكائنات.
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);
Assert.AreEqual(2, shapes.Count(s => s.ShapeType == ShapeType.OleObject));

// إذا احتوى الشكل على كائن OLE ، فسيكون له خاصية "تنسيق OleFormat" صالحة ،
// التي يمكننا استخدامها للتحقق من بعض جوانب الشكل.
OleFormat oleFormat = shapes[0].OleFormat;

Assert.AreEqual(false, oleFormat.IsLink);
Assert.AreEqual(false, oleFormat.OleIcon);

oleFormat = shapes[1].OleFormat;

Assert.AreEqual(true, oleFormat.IsLink);
Assert.AreEqual(true, oleFormat.OleIcon);

Assert.True(oleFormat.SourceFullName.EndsWith(@"Images" + Path.DirectorySeparatorChar + "Microsoft Visio drawing.vsd"));
Assert.AreEqual("", oleFormat.SourceItem);

Assert.AreEqual("Microsoft Visio drawing.vsd", oleFormat.IconCaption);

doc.Save(ArtifactsDir + "Shape.OleLinks.docx");

// إذا كان الكائن يحتوي على بيانات OLE ، فيمكننا الوصول إليها باستخدام دفق.
using (MemoryStream stream = oleFormat.GetOleEntry("\x0001CompObj"))
{
    byte[] oleEntryBytes = stream.ToArray();
    Assert.AreEqual(76, oleEntryBytes.Length);
}
```

### أنظر أيضا

* class [OleFormat](../)
* مساحة الاسم [Aspose.Words.Drawing](../../oleformat/)
* المجسم [Aspose.Words](../../../)


