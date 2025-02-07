---
title: TabStopCollection.GetPositionByIndex
second_title: Aspose.Words لمراجع .NET API
description: TabStopCollection طريقة. يحصل على موضع علامة الجدولة بالنقاط في الفهرس المحدد.
type: docs
weight: 100
url: /ar/net/aspose.words/tabstopcollection/getpositionbyindex/
---
## TabStopCollection.GetPositionByIndex method

يحصل على موضع علامة الجدولة (بالنقاط) في الفهرس المحدد.

```csharp
public double GetPositionByIndex(int index)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| index | Int32 | فهرس في مجموعة علامات الجدولة. |

### قيمة الإرجاع

موضع علامة الجدولة.

### أمثلة

يوضح كيفية العثور على علامة تبويب ، والتوقف عن طريق فهرسها والتحقق من موضعها.

```csharp
Document doc = new Document();
TabStopCollection tabStops = doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.TabStops;

tabStops.Add(ConvertUtil.MillimeterToPoint(30), TabAlignment.Left, TabLeader.Dashes);
tabStops.Add(ConvertUtil.MillimeterToPoint(60), TabAlignment.Left, TabLeader.Dashes);

// تحقق من موضع علامة الجدولة الثانية في المجموعة.
Assert.AreEqual(ConvertUtil.MillimeterToPoint(60), tabStops.GetPositionByIndex(1), 0.1d);
```

### أنظر أيضا

* class [TabStopCollection](../)
* مساحة الاسم [Aspose.Words](../../tabstopcollection/)
* المجسم [Aspose.Words](../../../)


