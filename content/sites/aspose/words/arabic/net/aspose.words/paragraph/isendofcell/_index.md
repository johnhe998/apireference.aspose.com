---
title: Paragraph.IsEndOfCell
second_title: Aspose.Words لمراجع .NET API
description: Paragraph ملكية. صحيح إذا كانت هذه الفقرة هي الفقرة الأخيرة في ملفCell  خطأ بخلاف ذلك.
type: docs
weight: 50
url: /ar/net/aspose.words/paragraph/isendofcell/
---
## Paragraph.IsEndOfCell property

صحيح إذا كانت هذه الفقرة هي الفقرة الأخيرة في ملف[`Cell`](../../../aspose.words.tables/cell/) ؛ خطأ بخلاف ذلك.

```csharp
public bool IsEndOfCell { get; }
```

### أمثلة

يوضح كيفية إعداد جدول للبقاء معًا في نفس الصفحة.

```csharp
Document doc = new Document(MyDir + "Table spanning two pages.docx");
Table table = doc.FirstSection.Body.Tables[0];

// تمكين KeepWithNext لكل فقرة في الجدول باستثناء ملف
// الأخيرة في الصف الأخير ستمنع الجدول من الانقسام عبر صفحات متعددة.
foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true).OfType<Cell>())
    foreach (Paragraph para in cell.Paragraphs.OfType<Paragraph>())
    {
        Assert.True(para.IsInCell);

        if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
            para.ParagraphFormat.KeepWithNext = true;
    }

doc.Save(ArtifactsDir + "Table.KeepTableTogether.docx");
```

### أنظر أيضا

* class [Paragraph](../)
* مساحة الاسم [Aspose.Words](../../paragraph/)
* المجسم [Aspose.Words](../../../)


