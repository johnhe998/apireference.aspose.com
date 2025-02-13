---
title: TabStop.Equals
second_title: Aspose.Words لمراجع .NET API
description: TabStop طريقة. يقارن مع TabStop المحدد .
type: docs
weight: 60
url: /ar/net/aspose.words/tabstop/equals/
---
## TabStop.Equals method

يقارن مع TabStop المحدد .

```csharp
public bool Equals(TabStop rhs)
```

### أمثلة

يوضح كيفية العمل مع مجموعة من علامات الجدولة الخاصة بالمستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TabStopCollection tabStops = builder.ParagraphFormat.TabStops;

// 72 نقطة هي بوصة واحدة على مسطرة توقف علامة التبويب Microsoft Word.
tabStops.Add(new TabStop(72.0));
tabStops.Add(new TabStop(432.0, TabAlignment.Right, TabLeader.Dashes));

Assert.AreEqual(2, tabStops.Count);
Assert.IsFalse(tabStops[0].IsClear);
Assert.IsFalse(tabStops[0].Equals(tabStops[1]));

// كل حرف "علامة تبويب" يأخذ مؤشر المنشئ إلى موقع علامة الجدولة التالية.
builder.Writeln("Start\tTab 1\tTab 2");

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;

Assert.AreEqual(2, paragraphs.Count);

// تحصل كل فقرة على مجموعة علامات الجدولة الخاصة بها ، والتي تستنسخ قيمها من مجموعة علامات الجدولة الخاصة بمنشئ المستندات.
Assert.AreEqual(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);
Assert.AreNotSame(paragraphs[0].ParagraphFormat.TabStops, paragraphs[1].ParagraphFormat.TabStops);

// يمكن لمجموعة علامات الجدولة أن توجهنا إلى TabStops قبل وبعد مواقف معينة.
Assert.AreEqual(72.0, tabStops.Before(100.0).Position);
Assert.AreEqual(432.0, tabStops.After(100.0).Position);

// يمكننا مسح مجموعة علامات الجدولة للفقرة للعودة إلى سلوك الجدولة الافتراضي.
paragraphs[1].ParagraphFormat.TabStops.Clear();

Assert.AreEqual(0, paragraphs[1].ParagraphFormat.TabStops.Count);

doc.Save(ArtifactsDir + "TabStopCollection.TabStopCollection.docx");
```

### أنظر أيضا

* class [TabStop](../)
* مساحة الاسم [Aspose.Words](../../tabstop/)
* المجسم [Aspose.Words](../../../)


