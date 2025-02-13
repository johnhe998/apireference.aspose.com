---
title: ParagraphFormat.SpaceBeforeAuto
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. True إذا تم تعيين مقدار التباعد قبل الفقرة تلقائيًا.
type: docs
weight: 320
url: /ar/net/aspose.words/paragraphformat/spacebeforeauto/
---
## ParagraphFormat.SpaceBeforeAuto property

True إذا تم تعيين مقدار التباعد قبل الفقرة تلقائيًا.

```csharp
public bool SpaceBeforeAuto { get; set; }
```

### ملاحظات

عند التعيين على صواب ، يتم تجاوز تأثير[`SpaceBefore`](../spacebefore/).

عند تعيين المسافة قبل الفقرة والمسافة بعد على تلقائي ، يضيف Microsoft Word مسافة 14 نقطة بين الفقرات تلقائيًا وفقًا للقواعد التالية:

* عادة ، يتم إضافة المسافات بعد كل الفقرات.
* في قائمة ذات تعداد نقطي أو رقمي ، تتم إضافة التباعد فقط بعد العنصر الأخير في القائمة. لا تتم إضافة التباعد بين عناصر القائمة.
* في قائمة متداخلة ذات تعداد نقطي أو رقمي ، لا يتم إضافة التباعد.
* عادة ما يتم إضافة التباعد بعد الجدول.
* لا يتم إضافة التباعد بعد الجدول إذا كان آخر كتلة في خلية جدول.
* لا يتم إضافة التباعد بعد الفقرة الأخيرة في خلية جدول.

### أمثلة

يوضح كيفية تعيين التباعد التلقائي بين الفقرات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// قم بتطبيق قدر كبير من المسافات قبل وبعد الفقرات التي سينشئها هذا المنشئ.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// اضبط هذه العلامات على "صواب" لتطبيق تباعد تلقائي ،
// يتجاهل التباعد في الخصائص التي حددناها أعلاه بشكل فعال.
// اتركها على أنها "خطأ" ستطبق تباعد الفقرات المخصص.
builder.ParagraphFormat.SpaceAfterAuto = autoSpacing;
builder.ParagraphFormat.SpaceBeforeAuto = autoSpacing;

// أدخل فقرتين تحتوي على مسافات أعلى وأسفلهما واحفظ المستند.
builder.Writeln("Paragraph 1.");
builder.Writeln("Paragraph 2.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingAuto.docx");
```

### أنظر أيضا

* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


