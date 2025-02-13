---
title: ControlChar.ColumnBreak
second_title: Aspose.Words لمراجع .NET API
description: ControlChar مجال. نهاية حرف العمود  x000e .
type: docs
weight: 30
url: /ar/net/aspose.words/controlchar/columnbreak/
---
## ControlChar.ColumnBreak field

نهاية حرف العمود: "\ x000e" .

```csharp
public static readonly string ColumnBreak;
```

### أمثلة

يوضح كيفية إضافة أحرف تحكم متنوعة إلى مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أضف مسافة عادية.
builder.Write("Before space." + ControlChar.SpaceChar + "After space.");

// أضف NBSP ، وهي مساحة غير منقسمة.
// على عكس المساحة العادية ، لا يمكن أن تحتوي هذه المساحة على فاصل أسطر تلقائي في موضعها.
builder.Write("Before space." + ControlChar.NonBreakingSpace + "After space.");

// أضف حرف جدولة.
builder.Write("Before tab." + ControlChar.Tab + "After tab.");

// أضف فاصل أسطر.
builder.Write("Before line break." + ControlChar.LineBreak + "After line break.");

// إضافة سطر جديد وبدء فقرة جديدة.
Assert.AreEqual(1, doc.FirstSection.Body.GetChildNodes(NodeType.Paragraph, true).Count);
builder.Write("Before line feed." + ControlChar.LineFeed + "After line feed.");
Assert.AreEqual(2, doc.FirstSection.Body.GetChildNodes(NodeType.Paragraph, true).Count);

// يحتوي حرف تغذية السطر على نسختين.
Assert.AreEqual(ControlChar.LineFeed, ControlChar.Lf);

// يمكن تمثيل إرجاع السطر وموجزات الأسطر معًا بحرف واحد.
Assert.AreEqual(ControlChar.CrLf, ControlChar.Cr + ControlChar.Lf);

// أضف فاصل فقرة ، والذي سيبدأ فقرة جديدة.
builder.Write("Before paragraph break." + ControlChar.ParagraphBreak + "After paragraph break.");
Assert.AreEqual(3, doc.FirstSection.Body.GetChildNodes(NodeType.Paragraph, true).Count);

// أضف فاصل مقطعي. هذا لا يجعل قسم أو فقرة جديدة.
Assert.AreEqual(1, doc.Sections.Count);
builder.Write("Before section break." + ControlChar.SectionBreak + "After section break.");
Assert.AreEqual(1, doc.Sections.Count);

// إضافة فاصل صفحة.
builder.Write("Before page break." + ControlChar.PageBreak + "After page break.");

// فاصل الصفحة هو نفس قيمة الفاصل المقطعي.
Assert.AreEqual(ControlChar.PageBreak, ControlChar.SectionBreak);

// أدخل قسمًا جديدًا ، ثم اضبط عدد الأعمدة على اثنين.
doc.AppendChild(new Section(doc));
builder.MoveToSection(1);
builder.CurrentSection.PageSetup.TextColumns.SetCount(2);

// يمكننا استخدام حرف التحكم لتحديد النقطة التي ينتقل فيها النص إلى العمود التالي.
builder.Write("Text at end of column 1." + ControlChar.ColumnBreak + "Text at beginning of column 2.");

doc.Save(ArtifactsDir + "ControlChar.InsertControlChars.docx");

// هناك نظائر حرف وسلسلة لمعظم الأحرف.
Assert.AreEqual(Convert.ToChar(ControlChar.Cell), ControlChar.CellChar);
Assert.AreEqual(Convert.ToChar(ControlChar.NonBreakingSpace), ControlChar.NonBreakingSpaceChar);
Assert.AreEqual(Convert.ToChar(ControlChar.Tab), ControlChar.TabChar);
Assert.AreEqual(Convert.ToChar(ControlChar.LineBreak), ControlChar.LineBreakChar);
Assert.AreEqual(Convert.ToChar(ControlChar.LineFeed), ControlChar.LineFeedChar);
Assert.AreEqual(Convert.ToChar(ControlChar.ParagraphBreak), ControlChar.ParagraphBreakChar);
Assert.AreEqual(Convert.ToChar(ControlChar.SectionBreak), ControlChar.SectionBreakChar);
Assert.AreEqual(Convert.ToChar(ControlChar.PageBreak), ControlChar.SectionBreakChar);
Assert.AreEqual(Convert.ToChar(ControlChar.ColumnBreak), ControlChar.ColumnBreakChar);
```

### أنظر أيضا

* class [ControlChar](../)
* مساحة الاسم [Aspose.Words](../../controlchar/)
* المجسم [Aspose.Words](../../../)


