---
title: TextColumnCollection.SetCount
second_title: Aspose.Words لمراجع .NET API
description: TextColumnCollection طريقة. يرتب النص في العدد المحدد من أعمدة النص.
type: docs
weight: 70
url: /ar/net/aspose.words/textcolumncollection/setcount/
---
## TextColumnCollection.SetCount method

يرتب النص في العدد المحدد من أعمدة النص.

```csharp
public void SetCount(int newCount)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| newCount | Int32 | عدد الأعمدة التي سيتم ترتيب النص فيها. |

### ملاحظات

متي[`EvenlySpaced`](../evenlyspaced/) هو **خاطئة** وقمت بزيادة عدد الأعمدة جديد[`TextColumn`](../../textcolumn/) يتم إنشاء الكائنات بعرض صفر وتباعد . تحتاج إلى ضبط العرض والتباعد للأعمدة الجديدة.

### أمثلة

يوضح كيفية إنشاء عدة أعمدة متباعدة بشكل متساوٍ في قسم.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### أنظر أيضا

* class [TextColumnCollection](../)
* مساحة الاسم [Aspose.Words](../../textcolumncollection/)
* المجسم [Aspose.Words](../../../)


