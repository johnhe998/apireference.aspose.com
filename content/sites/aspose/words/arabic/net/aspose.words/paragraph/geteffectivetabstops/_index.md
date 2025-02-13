---
title: Paragraph.GetEffectiveTabStops
second_title: Aspose.Words لمراجع .NET API
description: Paragraph طريقة. إرجاع مصفوفة لجميع علامات الجدولة المطبقة على هذه الفقرة  بما في ذلك تطبيقها بشكل غير مباشر بواسطة الأنماط أو القوائم.
type: docs
weight: 250
url: /ar/net/aspose.words/paragraph/geteffectivetabstops/
---
## Paragraph.GetEffectiveTabStops method

إرجاع مصفوفة لجميع علامات الجدولة المطبقة على هذه الفقرة ، بما في ذلك تطبيقها بشكل غير مباشر بواسطة الأنماط أو القوائم.

```csharp
public TabStop[] GetEffectiveTabStops()
```

### أمثلة

يوضح كيفية تعيين علامات الجدولة المخصصة لفقرة.

```csharp
Document doc = new Document();
Paragraph para = doc.FirstSection.Body.FirstParagraph;

// إذا كنا في فقرة بدون علامات جدولة في هذه المجموعة ،
// سيقفز المؤشر 36 نقطة في كل مرة نضغط فيها على مفتاح Tab في Microsoft Word.
Assert.AreEqual(0, doc.FirstSection.Body.FirstParagraph.GetEffectiveTabStops().Length);

// يمكننا إضافة علامات جدولة مخصصة في Microsoft Word إذا قمنا بتمكين المسطرة عبر علامة التبويب "عرض".
// كل وحدة في هذه المسطرة عبارة عن محطتي توقف افتراضيتين ، أي 72 نقطة.
// يمكننا إضافة علامات جدولة مخصصة برمجيًا مثل هذا.
TabStopCollection tabStops = doc.FirstSection.Body.FirstParagraph.ParagraphFormat.TabStops;
tabStops.Add(72, TabAlignment.Left, TabLeader.Dots);
tabStops.Add(216, TabAlignment.Center, TabLeader.Dashes);
tabStops.Add(360, TabAlignment.Right, TabLeader.Line);

// يمكننا رؤية علامات الجدولة هذه في Microsoft Word عن طريق تمكين المسطرة عبر "عرض" - > "عرض" - >. "مسطرة".
Assert.AreEqual(3, para.GetEffectiveTabStops().Length);

// أي أحرف جدولة نضيفها ستستفيد من علامات الجدولة على المسطرة ويمكن ،
// بناءً على قيمة قائد علامة التبويب ، اترك خطاً بين وجهات المغادرة والوصول إلى علامة التبويب.
para.AppendChild(new Run(doc, "\tTab 1\tTab 2\tTab 3"));

doc.Save(ArtifactsDir + "Paragraph.TabStops.docx");
```

### أنظر أيضا

* class [TabStop](../../tabstop/)
* class [Paragraph](../)
* مساحة الاسم [Aspose.Words](../../paragraph/)
* المجسم [Aspose.Words](../../../)


