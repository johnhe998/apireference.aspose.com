---
title: Section.Clone
second_title: Aspose.Words لمراجع .NET API
description: Section طريقة. لإنشاء نسخة مكررة من هذا القسم.
type: docs
weight: 110
url: /ar/net/aspose.words/section/clone/
---
## Section.Clone method

لإنشاء نسخة مكررة من هذا القسم.

```csharp
public Section Clone()
```

### أمثلة

يوضح كيفية إضافة وإزالة أقسام في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");

Assert.AreEqual("Section 1\x000cSection 2", doc.GetText().Trim());

// احذف القسم الأول من المستند.
doc.Sections.RemoveAt(0);

Assert.AreEqual("Section 2", doc.GetText().Trim());

// قم بإلحاق نسخة مما هو الآن القسم الأول بنهاية المستند.
int lastSectionIdx = doc.Sections.Count - 1;
Section newSection = doc.Sections[lastSectionIdx].Clone();
doc.Sections.Add(newSection);

Assert.AreEqual("Section 2\x000cSection 2", doc.GetText().Trim());
```

### أنظر أيضا

* class [Section](../)
* مساحة الاسم [Aspose.Words](../../section/)
* المجسم [Aspose.Words](../../../)


