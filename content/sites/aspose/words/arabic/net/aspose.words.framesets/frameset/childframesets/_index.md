---
title: Frameset.ChildFramesets
second_title: Aspose.Words لمراجع .NET API
description: Frameset ملكية. الحصول على مجموعة من الإطارات التابعة وصفحات الإطارات.
type: docs
weight: 20
url: /ar/net/aspose.words.framesets/frameset/childframesets/
---
## Frameset.ChildFramesets property

الحصول على مجموعة من الإطارات التابعة وصفحات الإطارات.

```csharp
public FramesetCollection ChildFramesets { get; }
```

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

* class [FramesetCollection](../../framesetcollection/)
* class [Frameset](../)
* مساحة الاسم [Aspose.Words.Framesets](../../frameset/)
* المجسم [Aspose.Words](../../../)


