---
title: Class FontInfoCollection
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Fonts.FontInfoCollection فصل. يمثل مجموعة من الخطوط المستخدمة في المستند.
type: docs
weight: 2750
url: /ar/net/aspose.words.fonts/fontinfocollection/
---
## FontInfoCollection class

يمثل مجموعة من الخطوط المستخدمة في المستند.

```csharp
public class FontInfoCollection : IEnumerable<FontInfo>
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [Count](../../aspose.words.fonts/fontinfocollection/count/) { get; } | الحصول على عدد العناصر الموجودة في المجموعة. |
| [EmbedSystemFonts](../../aspose.words.fonts/fontinfocollection/embedsystemfonts/) { get; set; } | يحدد ما إذا كان سيتم تضمين خطوط النظام في الوثيقة أم لا. القيمة الافتراضية لهذه الخاصية هي **خاطئة**. |
| [EmbedTrueTypeFonts](../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) { get; set; } | يحدد ما إذا كان سيتم تضمين خطوط TrueType في مستند أم لا عند حفظه. القيمة الافتراضية لهذه الخاصية هي **خاطئة** . |
| [Item](../../aspose.words.fonts/fontinfocollection/item/) { get; } | يحصل على خط بالاسم المحدد . (2 indexers) |
| [SaveSubsetFonts](../../aspose.words.fonts/fontinfocollection/savesubsetfonts/) { get; set; } | يحدد ما إذا كان سيتم حفظ مجموعة فرعية من خطوط TrueType المضمنة مع المستند أم لا. **خاطئة**. |

## طُرق

| اسم | وصف |
| --- | --- |
| [Contains](../../aspose.words.fonts/fontinfocollection/contains/)(string) | لتحديد ما إذا كانت المجموعة تحتوي على خط بالاسم المحدد. |
| [GetEnumerator](../../aspose.words.fonts/fontinfocollection/getenumerator/)() | إرجاع كائن العداد الذي يمكن استخدامه للتكرار على كافة العناصر في المجموعة. |

### ملاحظات

العناصر[`FontInfo`](../fontinfo/) أشياء.

لا تقوم بإنشاء نسخ من هذه الفئة مباشرة. استخدم ملف[`FontInfos`](../../aspose.words/documentbase/fontinfos/) خاصية للوصول إلى مجموعة الخطوط المحددة في المستند.

### أمثلة

يوضح كيفية طباعة تفاصيل الخطوط الموجودة في المستند.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// طباعة جميع الخطوط المستخدمة وغير المستخدمة في المستند.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

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

* class [FontInfo](../fontinfo/)
* مساحة الاسم [Aspose.Words.Fonts](../../aspose.words.fonts/)
* المجسم [Aspose.Words](../../)


