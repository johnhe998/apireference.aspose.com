---
title: Paragraph.JoinRunsWithSameFormatting
second_title: Aspose.Words لمراجع .NET API
description: Paragraph طريقة. تعمل الصلات بنفس التنسيق في الفقرة.
type: docs
weight: 280
url: /ar/net/aspose.words/paragraph/joinrunswithsameformatting/
---
## Paragraph.JoinRunsWithSameFormatting method

تعمل الصلات بنفس التنسيق في الفقرة.

```csharp
public int JoinRunsWithSameFormatting()
```

### قيمة الإرجاع

عدد الصلات التي تم أداؤها. متي **ن** يتم ضم الأشواط المجاورة التي يعتبرونها **ن - 1** ينضم.

### أمثلة

يوضح كيفية تبسيط الفقرات عن طريق دمج عمليات التشغيل الزائدة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// أدخل أربع مجموعات من النص في الفقرة.
builder.Write("Run 1. ");
builder.Write("Run 2. ");
builder.Write("Run 3. ");
builder.Write("Run 4. ");

// إذا فتحنا هذا المستند في Microsoft Word ، فستبدو الفقرة وكأنها نص واحد غير متماسك.
// ومع ذلك ، ستتألف من أربعة عمليات تشغيل منفصلة بنفس التنسيق. فقرات مجزأة مثل هذا
// قد يحدث عندما نقوم بتحرير أجزاء من فقرة واحدة يدويًا عدة مرات في Microsoft Word.
Paragraph para = builder.CurrentParagraph;

Assert.AreEqual(4, para.Runs.Count);

// قم بتغيير نمط التشغيل الأخير لتمييزه عن الثلاثة الأولى.
para.Runs[3].Font.StyleIdentifier = StyleIdentifier.Emphasis;

// يمكننا تشغيل طريقة "JoinRunsWithSameFormatting" لتحسين محتويات المستند
// من خلال دمج عمليات التشغيل المتشابهة في واحدة ، مما يقلل من عددها الإجمالي.
// تُرجع هذه الطريقة أيضًا عدد عمليات التشغيل التي دمجتها هذه الطريقة.
// حدث هذان الدمجان للجمع بين عمليات التشغيل رقم 1 ورقم 2 ورقم 3 ،
// أثناء ترك Run # 4 لأنه يحتوي على نمط غير متوافق.
Assert.AreEqual(2, para.JoinRunsWithSameFormatting());

// سيساوي عدد الأشواط المتبقية العدد الأصلي
// ناقص عدد عمليات دمج التشغيل التي نفذتها طريقة "JoinRunsWithSameFormatting".
Assert.AreEqual(2, para.Runs.Count);
Assert.AreEqual("Run 1. Run 2. Run 3. ", para.Runs[0].Text);
Assert.AreEqual("Run 4. ", para.Runs[1].Text);
```

### أنظر أيضا

* class [Paragraph](../)
* مساحة الاسم [Aspose.Words](../../paragraph/)
* المجسم [Aspose.Words](../../../)


