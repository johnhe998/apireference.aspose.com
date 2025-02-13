---
title: Font.NameAscii
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. إرجاع أو تعيين الخط المستخدم للنص اللاتيني الأحرف برموز الأحرف من 0 صفر إلى 127 .
type: docs
weight: 240
url: /ar/net/aspose.words/font/nameascii/
---
## Font.NameAscii property

إرجاع أو تعيين الخط المستخدم للنص اللاتيني (الأحرف برموز الأحرف من 0 (صفر) إلى 127) .

```csharp
public string NameAscii { get; set; }
```

### أمثلة

يوضح كيف يمكن لبرنامج Microsoft Word الجمع بين خطين مختلفين في تشغيل واحد.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// لنفترض تشغيلًا استخدمنا المنشئ لإدخاله أثناء استخدام تكوين الخط هذا
// يحتوي على أحرف ضمن نطاق أحرف ASCII. في هذه الحالة،
// سيعرض تلك الأحرف باستخدام هذا الخط.
builder.Font.NameAscii = "Calibri";

// مع عدم تحديد خط آخر ، سيقوم المنشئ أيضًا بتطبيق هذا الخط على جميع الأحرف التي يدرجها.
Assert.AreEqual("Calibri", builder.Font.Name);

// حدد خطًا لاستخدامه لجميع الأحرف خارج نطاق ASCII.
// من الناحية المثالية ، يجب أن يحتوي هذا الخط على حرف رسومي لكل رمز حرف غير ASCII مطلوب.
builder.Font.NameOther = "Courier New";

// أدخل سلسلة تتكون من كلمة واحدة تتكون من أحرف ASCII ، وكلمة واحدة بها جميع الأحرف خارج هذا النطاق.
// سيتم عرض كل حرف باستخدام أي من الخطوط ، اعتمادًا على.
builder.Writeln("Hello, Привет");

doc.Save(ArtifactsDir + "Font.NameAscii.docx");
```

### أنظر أيضا

* property [Name](../name/)
* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


