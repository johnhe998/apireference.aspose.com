---
title: Class Frameset
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Framesets.Frameset فصل. يمثل صفحة إطارات أو إطارًا واحدًا على صفحة إطارات .
type: docs
weight: 2900
url: /ar/net/aspose.words.framesets/frameset/
---
## Frameset class

يمثل صفحة إطارات أو إطارًا واحدًا على صفحة إطارات .

```csharp
public class Frameset
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [Frameset](frameset/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [ChildFramesets](../../aspose.words.framesets/frameset/childframesets/) { get; } | الحصول على مجموعة من الإطارات التابعة وصفحات الإطارات. |
| [FrameDefaultUrl](../../aspose.words.framesets/frameset/framedefaulturl/) { get; set; } | الحصول على أو تحديد عنوان URL لصفحة الويب أو اسم ملف المستند ليتم عرضه في هذا الإطار. |
| [IsFrameLinkToFile](../../aspose.words.framesets/frameset/isframelinktofile/) { get; set; } | الحصول على أو تعيين قيمة تشير إلى ما إذا كانت صفحة الويب أو اسم ملف المستند المحدد في [`FrameDefaultUrl`](./framedefaulturl/) الخاصية هي مورد خارجي يرتبط به الإطار . |

### ملاحظات

إذا كان ملف[`ChildFramesets`](./childframesets/) تحتوي الخاصية على عناصر ، هذا المثال عبارة عن صفحة إطارات ، وإلا فسيكون إطارًا واحدًا.

### أمثلة

يوضح كيفية الوصول إلى الإطارات على الصفحة.

```csharp
// يحتوي المستند على عدة إطارات مع روابط لمستندات أخرى.
Document doc = new Document(MyDir + "Frameset.docx");

// يمكننا التحقق من عنوان URL الافتراضي (عنوان URL لصفحة ويب أو مستند محلي) أو إذا كان الإطار مصدرًا خارجيًا.
Assert.AreEqual("https://file-examples-com.github.io/uploads/2017/02/file-sample_100kB.docx "،
    doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl);
Assert.True(doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile);

Assert.AreEqual("Document.docx", doc.Frameset.ChildFramesets[1].FrameDefaultUrl);
Assert.False(doc.Frameset.ChildFramesets[1].IsFrameLinkToFile);

// تغيير خصائص أحد إطاراتنا.
doc.Frameset.ChildFramesets[0].ChildFramesets[0].FrameDefaultUrl =
    "https://github.com/aspose-words/Aspose.Words-for-.NET/blob/master/Examples/Data/Absolute٪20position٪20tab.docx ";
doc.Frameset.ChildFramesets[0].ChildFramesets[0].IsFrameLinkToFile = false;
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Framesets](../../aspose.words.framesets/)
* المجسم [Aspose.Words](../../)


