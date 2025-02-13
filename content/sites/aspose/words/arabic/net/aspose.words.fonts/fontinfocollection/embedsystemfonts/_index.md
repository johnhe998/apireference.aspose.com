---
title: FontInfoCollection.EmbedSystemFonts
second_title: Aspose.Words لمراجع .NET API
description: FontInfoCollection ملكية. يحدد ما إذا كان سيتم تضمين خطوط النظام في الوثيقة أم لا. القيمة الافتراضية لهذه الخاصية هي خاطئة.
type: docs
weight: 20
url: /ar/net/aspose.words.fonts/fontinfocollection/embedsystemfonts/
---
## FontInfoCollection.EmbedSystemFonts property

يحدد ما إذا كان سيتم تضمين خطوط النظام في الوثيقة أم لا. القيمة الافتراضية لهذه الخاصية هي **خاطئة**.

يعمل هذا الخيار فقط عندما[`EmbedTrueTypeFonts`](../embedtruetypefonts/) تم تعيين الخيار ل **حقيقي**.

```csharp
public bool EmbedSystemFonts { get; set; }
```

### ملاحظات

تعيين هذه الخاصية على`حقيقي`يكون مفيدًا إذا كان المستخدم على نظام شرق آسيوي system ويريد إنشاء مستند يمكن قراءته بواسطة الآخرين الذين ليس لديهم خطوط لهذه اللغة على نظامهم. على سبيل المثال ، يمكن لمستخدم على نظام ياباني أن يختار تضمين خطوط في مستند بحيث يكون المستند الياباني قابلاً للقراءة على جميع الأنظمة.

يعمل هذا الخيار مع تنسيقات DOC و DOCX و RTF فقط.

### أمثلة

يوضح كيفية حفظ مستند بخطوط TrueType المضمنة.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### أنظر أيضا

* class [FontInfoCollection](../)
* مساحة الاسم [Aspose.Words.Fonts](../../fontinfocollection/)
* المجسم [Aspose.Words](../../../)


