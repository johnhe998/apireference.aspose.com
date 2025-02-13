---
title: Section.PrependContent
second_title: Aspose.Words لمراجع .NET API
description: Section طريقة. يتم إدراج نسخة من محتوى قسم المصدر في بداية هذا القسم.
type: docs
weight: 140
url: /ar/net/aspose.words/section/prependcontent/
---
## Section.PrependContent method

يتم إدراج نسخة من محتوى قسم المصدر في بداية هذا القسم.

```csharp
public void PrependContent(Section sourceSection)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| sourceSection | Section | قسم نسخ المحتوى منه. |

### ملاحظات

فقط محتوى[`Body`](../body/) من قسم المصدر ، إعداد الصفحة ، رؤوس وتذييلات لا يتم نسخها.

يتم استيراد العقد تلقائيًا إذا كان قسم المصدر ينتمي إلى مستند مختلف.

لم يتم إنشاء قسم جديد في المستند الوجهة.

### أمثلة

يوضح كيفية إلحاق محتويات قسم بقسم آخر.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 2");
builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.Write("Section 3");

Section section = doc.Sections[2];

Assert.AreEqual("Section 3" + ControlChar.SectionBreak, section.GetText());

// أدخل محتويات القسم الأول في بداية القسم الثالث.
Section sectionToPrepend = doc.Sections[0];
section.PrependContent(sectionToPrepend);

// أدخل محتويات القسم الثاني في نهاية القسم الثالث.
Section sectionToAppend = doc.Sections[1];
section.AppendContent(sectionToAppend);

// لم تُنشئ الطرق "PrependContent" و "AppendContent" أية أقسام جديدة.
Assert.AreEqual(3, doc.Sections.Count);
Assert.AreEqual("Section 1" + ControlChar.ParagraphBreak +
                "Section 3" + ControlChar.ParagraphBreak +
                "Section 2" + ControlChar.SectionBreak, section.GetText());
```

### أنظر أيضا

* class [Section](../)
* مساحة الاسم [Aspose.Words](../../section/)
* المجسم [Aspose.Words](../../../)


