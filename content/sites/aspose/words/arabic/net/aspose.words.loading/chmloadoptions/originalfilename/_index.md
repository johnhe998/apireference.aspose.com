---
title: ChmLoadOptions.OriginalFileName
second_title: Aspose.Words لمراجع .NET API
description: ChmLoadOptions ملكية. اسم ملف CHM. القيمة الافتراضية هيلا شيء .
type: docs
weight: 20
url: /ar/net/aspose.words.loading/chmloadoptions/originalfilename/
---
## ChmLoadOptions.OriginalFileName property

اسم ملف CHM. القيمة الافتراضية هي`لا شيء` .

```csharp
public string OriginalFileName { get; set; }
```

### ملاحظات

قد تحتوي مستندات CHM على روابط تشير إلى نفس المستند بواسطة اسم الملف. تدعم Aspose.Words مثل هذه الروابط وتستخدم عادةً[`OriginalFileName`](../../../aspose.words/document/originalfilename/) للتحقق مما إذا كان الملف المشار إليه بواسطة link هو الملف الذي يتم تحميله. إذا تم تحميل مستند من دفق ، فيجب تحديد اسم الملف الأصلي الخاص به بشكل صريح من خلال هذه الخاصية ، حيث لا يمكن تحديده تلقائيًا.

إذا تم تحميل مستند CHM من ملف وتم تحديد قيمة غير فارغة لهذه الخاصية ، فستأخذ القيمة الأولوية على الاسم الفعلي للملف المخزن في[`OriginalFileName`](../../../aspose.words/document/originalfilename/) .

### أمثلة

يوضح كيفية حل عناوين URL مثل "ms-its: myfile.chm :: / index.htm".

```csharp
// يحتوي المستند على عناوين URL مثل "ms-its: amhelp.chm :: .... htm" ، ولكن له اسم مختلف ،
// لذلك لا تعمل روابط الملفات بعد حفظها في HTML.
// نحتاج إلى تحديد اسم الملف الأصلي في 'ChmLoadOptions' لتجنب هذا السلوك.
ChmLoadOptions loadOptions = new ChmLoadOptions { OriginalFileName = "amhelp.chm" };

Document doc = new Document(new MemoryStream(File.ReadAllBytes(MyDir + "Document with ms-its links.chm")),
    loadOptions);

doc.Save(ArtifactsDir + "ExChmLoadOptions.OriginalFileName.html");
```

### أنظر أيضا

* class [ChmLoadOptions](../)
* مساحة الاسم [Aspose.Words.Loading](../../chmloadoptions/)
* المجسم [Aspose.Words](../../../)


