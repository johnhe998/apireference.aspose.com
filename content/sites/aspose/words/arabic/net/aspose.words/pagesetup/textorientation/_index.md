---
title: PageSetup.TextOrientation
second_title: Aspose.Words لمراجع .NET API
description: PageSetup ملكية. يسمح بالتحديدTextOrientation للصفحة بأكملها. القيمة الافتراضية هيHorizontal
type: docs
weight: 420
url: /ar/net/aspose.words/pagesetup/textorientation/
---
## PageSetup.TextOrientation property

يسمح بالتحديد`TextOrientation` للصفحة بأكملها. القيمة الافتراضية هيHorizontal

```csharp
public TextOrientation TextOrientation { get; set; }
```

### ملاحظات

هذه الخاصية مدعومة فقط لتنسيقات MS Word الأصلية DOCX و WML و RTF و DOC.

### أمثلة

يوضح كيفية ضبط اتجاه النص.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// اضبط خاصية "TextOrientation" على "TextOrientation.Upward" لتدوير كل النص بمقدار 90 درجة
// إلى اليمين بحيث ينتقل الآن كل النص من اليسار إلى اليمين من أعلى إلى أسفل.
PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.TextOrientation = TextOrientation.Upward;

doc.Save(ArtifactsDir + "PageSetup.SetTextOrientation.docx");
```

### أنظر أيضا

* enum [TextOrientation](../../textorientation/)
* class [PageSetup](../)
* مساحة الاسم [Aspose.Words](../../pagesetup/)
* المجسم [Aspose.Words](../../../)


