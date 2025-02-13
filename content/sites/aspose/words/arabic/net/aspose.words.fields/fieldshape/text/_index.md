---
title: FieldShape.Text
second_title: Aspose.Words لمراجع .NET API
description: FieldShape ملكية. الحصول على النص المراد استرداده أو تعيينه .
type: docs
weight: 20
url: /ar/net/aspose.words.fields/fieldshape/text/
---
## FieldShape.Text property

الحصول على النص المراد استرداده أو تعيينه .

```csharp
public string Text { get; set; }
```

### أمثلة

يوضح كيفية إنشاء قوائم متوافقة مع اللغة ذات الاتجاه من اليمين إلى اليسار باستخدام حقول BIDIOUTLINE.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// فقرات أرقام الحقول BIDIOUTLINE مثل حقول AUTONUM / LISTNUM ،
// ولكنه يكون مرئيًا فقط عند تمكين لغة تحرير من اليمين إلى اليسار ، مثل العبرية أو العربية.
// سيعرض الحقل التالي ".1" ، المكافئ RTL لرقم القائمة "1.".
FieldBidiOutline field = (FieldBidiOutline)builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

Assert.AreEqual(" BIDIOUTLINE ", field.GetFieldCode());

// أضف حقلين BIDIOUTLINE آخرين ، والذي سيعرض ".2" و ".3".
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");
builder.InsertField(FieldType.FieldBidiOutline, true);
builder.Writeln("שלום");

// اضبط محاذاة النص الأفقي لكل فقرة في المستند على RTL.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.Bidi = true;
}

// إذا قمنا بتمكين لغة تحرير من اليمين إلى اليسار في Microsoft Word ، فستعرض الحقول الخاصة بنا الأرقام.
// وإلا فسيتم عرض "###".
doc.Save(ArtifactsDir + "Field.BIDIOUTLINE.docx");
```

يوضح كيفية معالجة بعض حقول Microsoft Word القديمة مثل SHAPE و EMBED أثناء التحميل.

```csharp
// افتح مستندًا تم إنشاؤه في Microsoft Word 2003.
Document doc = new Document(MyDir + "Legacy fields.doc");

// إذا فتحنا مستند Word وضغطنا على Alt + F9 ، فسنرى شكل وحقل EMBED.
// حقل الشكل هو نقطة الارتساء / قماش الرسم لكائن شكل تلقائي مع تمكين نمط التفاف "سطري مع النص".
// يحتوي حقل EMBED على نفس الوظيفة ، ولكن بالنسبة لكائن مضمن ،
// مثل جدول بيانات من مستند Excel خارجي.
// ومع ذلك ، لن تظهر هذه الحقول في مجموعة الحقول الخاصة بالمستند.
Assert.AreEqual(0, doc.Range.Fields.Count);

// تدعم الإصدارات القديمة من Microsoft Word هذه الحقول فقط.
// ستؤدي عملية تحميل المستند إلى تحويل هذه الحقول إلى كائنات شكل ،
// التي يمكننا الوصول إليها في مجموعة عقدة المستند.
NodeCollection shapes = doc.GetChildNodes(NodeType.Shape, true);
Assert.AreEqual(3, shapes.Count);

// تتوافق عقدة الشكل الأولى مع حقل الشكل في مستند الإدخال ،
// وهي اللوحة القماشية المضمنة للشكل التلقائي.
Shape shape = (Shape)shapes[0];
Assert.AreEqual(ShapeType.Image, shape.ShapeType);

// عقدة الشكل الثانية هي الشكل التلقائي نفسه.
shape = (Shape)shapes[1];
Assert.AreEqual(ShapeType.Can, shape.ShapeType);

// الشكل الثالث هو ما كان حقل EMBED الذي يحتوي على جدول البيانات الخارجي.
shape = (Shape)shapes[2];
Assert.AreEqual(ShapeType.OleObject, shape.ShapeType);
```

### أنظر أيضا

* class [FieldShape](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldshape/)
* المجسم [Aspose.Words](../../../)


