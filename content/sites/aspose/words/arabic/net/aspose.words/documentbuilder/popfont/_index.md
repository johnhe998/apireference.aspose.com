---
title: DocumentBuilder.PopFont
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. استرداد تنسيق الأحرف المحفوظة مسبقًا في المكدس.
type: docs
weight: 560
url: /ar/net/aspose.words/documentbuilder/popfont/
---
## DocumentBuilder.PopFont method

استرداد تنسيق الأحرف المحفوظة مسبقًا في المكدس.

```csharp
public void PopFont()
```

### أمثلة

يوضح كيفية استخدام مكدس التنسيق الخاص بمنشئ المستندات.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// إعداد تنسيق الخط ، ثم اكتب النص الذي يسبق الارتباط التشعبي.
builder.Font.Name = "Arial";
builder.Font.Size = 24;
builder.Write("To visit Google, hold Ctrl and click ");

// احتفظ بتكوين التنسيق الحالي الخاص بنا على المكدس.
builder.PushFont();

// قم بتعديل التنسيق الحالي للمنشئ من خلال تطبيق نمط جديد.
builder.Font.StyleIdentifier = StyleIdentifier.Hyperlink;
builder.InsertHyperlink("here", "http://www.google.com "، خطأ) ;

Assert.AreEqual(Color.Blue.ToArgb(), builder.Font.Color.ToArgb());
Assert.AreEqual(Underline.Single, builder.Font.Underline);

// استعادة تنسيق الخط الذي حفظناه سابقًا وإزالة العنصر من المكدس.
builder.PopFont();

Assert.AreEqual(Color.Empty.ToArgb(), builder.Font.Color.ToArgb());
Assert.AreEqual(Underline.None, builder.Font.Underline);

builder.Write(". We hope you enjoyed the example.");

doc.Save(ArtifactsDir + "DocumentBuilder.PushPopFont.docx");
```

### أنظر أيضا

* property [Font](../font/)
* method [PushFont](../pushfont/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


