---
title: TxtSaveOptions.AddBidiMarks
second_title: Aspose.Words لمراجع .NET API
description: TxtSaveOptions ملكية. يحدد ما إذا كان سيتم إضافة علامات ثنائية الاتجاه قبل كل تشغيل ثنائي الاتجاه عند التصدير بتنسيق نص عادي.
type: docs
weight: 20
url: /ar/net/aspose.words.saving/txtsaveoptions/addbidimarks/
---
## TxtSaveOptions.AddBidiMarks property

يحدد ما إذا كان سيتم إضافة علامات ثنائية الاتجاه قبل كل تشغيل ثنائي الاتجاه عند التصدير بتنسيق نص عادي.

النظام الأساسي **خاطئة**.

```csharp
public bool AddBidiMarks { get; set; }
```

### أمثلة

يوضح كيفية إدراج حرف Unicode "علامة من اليمين إلى اليسار" (U + 200F) قبل كل تشغيل ثنائي الاتجاه في النص.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Hello world!");
builder.ParagraphFormat.Bidi = true;
builder.Writeln("שלום עולם!");
builder.Writeln("مرحبا بالعالم!");

// قم بإنشاء كائن "TxtSaveOptions" ، والذي يمكننا تمريره إلى طريقة "Save" الخاصة بالمستند
// لتعديل كيفية حفظ المستند على نص عادي.
TxtSaveOptions saveOptions = new TxtSaveOptions { Encoding = System.Text.Encoding.Unicode};

// اضبط خاصية "AddBidiMarks" على "true" لإضافة علامات قبل التشغيل
// مع نص من اليمين إلى اليسار للإشارة إلى الحقيقة.
// اضبط خاصية "AddBidiMarks" على "false" لكتابة الكل من اليسار إلى اليمين
// والتشغيل من اليمين إلى اليسار بالتساوي مع عدم وجود أي شيء للإشارة إلى أيهما.
saveOptions.AddBidiMarks = addBidiMarks;

doc.Save(ArtifactsDir + "TxtSaveOptions.AddBidiMarks.txt", saveOptions);

string docText = System.Text.Encoding.Unicode.GetString(File.ReadAllBytes(ArtifactsDir + "TxtSaveOptions.AddBidiMarks.txt"));

if (addBidiMarks)
{
    Assert.AreEqual("\uFEFFHello world!‎\r\nשלום עולם!‏\r\nمرحبا بالعالم!‏\r\n\r\n", docText);
    Assert.True(docText.Contains("\u200f"));
}
else
{
    Assert.AreEqual("\uFEFFHello world!\r\nשלום עולם!\r\nمرحبا بالعالم!\r\n\r\n", docText);
    Assert.False(docText.Contains("\u200f"));
}
```

### أنظر أيضا

* class [TxtSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../txtsaveoptions/)
* المجسم [Aspose.Words](../../../)


