---
title: FieldHyperlink.ScreenTip
second_title: Aspose.Words لمراجع .NET API
description: FieldHyperlink ملكية. الحصول على نص تلميح الشاشة للارتباط التشعبي أو تعيينه.
type: docs
weight: 50
url: /ar/net/aspose.words.fields/fieldhyperlink/screentip/
---
## FieldHyperlink.ScreenTip property

الحصول على نص تلميح الشاشة للارتباط التشعبي أو تعيينه.

```csharp
public string ScreenTip { get; set; }
```

### أمثلة

يوضح كيفية استخدام حقول HYPERLINK للارتباط بالمستندات في نظام الملفات المحلي.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldHyperlink field = (FieldHyperlink)builder.InsertField(FieldType.FieldHyperlink, true);

// عندما نضغط على حقل HYPERLINK هذا في Microsoft Word ،
// سيفتح المستند المرتبط ثم يضع المؤشر على الإشارة المرجعية المحددة.
field.Address = MyDir + "Bookmarks.docx";
field.SubAddress = "MyBookmark3";
field.ScreenTip = "Open " + field.Address + " on bookmark " + field.SubAddress + " in a new window";

builder.Writeln();

// عندما نضغط على حقل HYPERLINK هذا في Microsoft Word ،
// سيفتح المستند المرتبط ، وينتقل تلقائيًا لأسفل إلى إطار iframe المحدد.
field = (FieldHyperlink)builder.InsertField(FieldType.FieldHyperlink, true);
field.Address = MyDir + "Iframes.html";
field.ScreenTip = "Open " + field.Address;
field.Target = "iframe_3";
field.OpenInNewWindow = true;
field.IsImageMap = false;

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.HYPERLINK.docx");
```

### أنظر أيضا

* class [FieldHyperlink](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldhyperlink/)
* المجسم [Aspose.Words](../../../)


