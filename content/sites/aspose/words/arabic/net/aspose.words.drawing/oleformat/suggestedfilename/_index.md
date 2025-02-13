---
title: OleFormat.SuggestedFileName
second_title: Aspose.Words لمراجع .NET API
description: OleFormat ملكية. يحصل على اسم الملف المقترح للكائن المضمن الحالي إذا كنت تريد حفظه في ملف.
type: docs
weight: 130
url: /ar/net/aspose.words.drawing/oleformat/suggestedfilename/
---
## OleFormat.SuggestedFileName property

يحصل على اسم الملف المقترح للكائن المضمن الحالي إذا كنت تريد حفظه في ملف.

```csharp
public string SuggestedFileName { get; }
```

### أمثلة

يوضح كيفية الحصول على اسم الملف المقترح لكائن OLE.

```csharp
Document doc = new Document(MyDir + "OLE shape.rtf");

Shape oleShape = (Shape) doc.FirstSection.Body.GetChild(NodeType.Shape, 0, true);

// يمكن أن توفر كائنات OLE اسم ملف وامتدادًا مقترحين ،
// التي يمكننا استخدامها عند حفظ محتويات الكائن في ملف في نظام الملفات المحلي.
string suggestedFileName = oleShape.OleFormat.SuggestedFileName;

Assert.AreEqual("CSV.csv", suggestedFileName);

using (FileStream fileStream = new FileStream(ArtifactsDir + suggestedFileName, FileMode.Create))
{
    oleShape.OleFormat.Save(fileStream);
}
```

### أنظر أيضا

* class [OleFormat](../)
* مساحة الاسم [Aspose.Words.Drawing](../../oleformat/)
* المجسم [Aspose.Words](../../../)


