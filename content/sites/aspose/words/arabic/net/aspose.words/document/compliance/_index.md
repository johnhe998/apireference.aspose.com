---
title: Document.Compliance
second_title: Aspose.Words لمراجع .NET API
description: Document ملكية. الحصول على إصدار التوافق OOXML المحدد من محتوى المستند الذي تم تحميله. يكون منطقيًا فقط لمستندات OOXML .
type: docs
weight: 60
url: /ar/net/aspose.words/document/compliance/
---
## Document.Compliance property

الحصول على إصدار التوافق OOXML المحدد من محتوى المستند الذي تم تحميله. يكون منطقيًا فقط لمستندات OOXML .

```csharp
public OoxmlCompliance Compliance { get; }
```

### ملاحظات

إذا أنشأت مستندًا جديدًا فارغًا أو قمت بتحميل مستند غير OOXML ، فتُرجع document ملفEcma376_2006 القيمة.

### أمثلة

يوضح كيفية قراءة إصدار التوافق مع Open Office XML للمستند الذي تم تحميله.

```csharp
// يختلف إصدار التوافق بين المستندات التي تم إنشاؤها بواسطة إصدارات مختلفة من Microsoft Word.
Document doc = new Document(MyDir + "Document.doc");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Ecma376_2006);

doc = new Document(MyDir + "Document.docx");

Assert.AreEqual(doc.Compliance, OoxmlCompliance.Iso29500_2008_Transitional);
```

### أنظر أيضا

* enum [OoxmlCompliance](../../../aspose.words.saving/ooxmlcompliance/)
* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


