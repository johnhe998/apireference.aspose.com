---
title: OoxmlSaveOptions.Password
second_title: Aspose.Words لمراجع .NET API
description: OoxmlSaveOptions ملكية. الحصول على / تعيين كلمة مرور لتشفير المستند باستخدام خوارزمية التشفير القياسي ECMA376.
type: docs
weight: 50
url: /ar/net/aspose.words.saving/ooxmlsaveoptions/password/
---
## OoxmlSaveOptions.Password property

الحصول على / تعيين كلمة مرور لتشفير المستند باستخدام خوارزمية التشفير القياسي ECMA376.

```csharp
public string Password { get; set; }
```

### ملاحظات

لحفظ المستند بدون تشفير ، يجب أن تكون هذه الخاصية خالية أو سلسلة فارغة.

### أمثلة

يوضح كيفية إنشاء مستند Office Open XML مشفر بكلمة مرور.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions();
saveOptions.Password = "MyPassword";

doc.Save(ArtifactsDir + "OoxmlSaveOptions.Password.docx", saveOptions);

// لن نتمكن من فتح هذا المستند باستخدام Microsoft Word أو
// Aspose.Words بدون توفير كلمة المرور الصحيحة.
Assert.Throws<IncorrectPasswordException>(() =>
    doc = new Document(ArtifactsDir + "OoxmlSaveOptions.Password.docx"));

// افتح المستند المشفر عن طريق تمرير كلمة المرور الصحيحة في كائن LoadOptions.
doc = new Document(ArtifactsDir + "OoxmlSaveOptions.Password.docx", new LoadOptions("MyPassword"));

Assert.AreEqual("Hello world!", doc.GetText().Trim());
```

### أنظر أيضا

* class [OoxmlSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../ooxmlsaveoptions/)
* المجسم [Aspose.Words](../../../)


