---
title: Font.Kerning
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. الحصول على أو تحديد حجم الخط الذي يبدأ عنده تقنين الأحرف.
type: docs
weight: 180
url: /ar/net/aspose.words/font/kerning/
---
## Font.Kerning property

الحصول على أو تحديد حجم الخط الذي يبدأ عنده تقنين الأحرف.

```csharp
public double Kerning { get; set; }
```

### أمثلة

يوضح كيفية تحديد حجم الخط الذي يبدأ عنده تأثير تقنين الأحرف.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial Black";

// عيّن حجم خط المنشئ ، والحد الأدنى لحجم المسافات بين الحروف التي سيتم تفعيلها.
// يقع حجم الخط أقل من حد المسافة بين الحروف ، لذلك لن يحتوي التشغيل أدناه على تقنين الأحرف.
builder.Font.Size = 18;
builder.Font.Kerning = 24;

builder.Writeln("TALLY. (Kerning not applied)");

// عيّن حد المسافة بين الحروف بحيث يكون حجم الخط الحالي للمنشئ أعلى منه.
// أي نص نضيفه من هذه النقطة سيطبق عليه تقنين الأحرف. المسافات بين الشخصيات
سيتم ضبط // ، مما يؤدي عادةً إلى تشغيل نص أكثر إرضاءً من الناحية الجمالية.
builder.Font.Kerning = 12;

builder.Writeln("TALLY. (Kerning applied)");

doc.Save(ArtifactsDir + "Font.Kerning.docx");
```

### أنظر أيضا

* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


