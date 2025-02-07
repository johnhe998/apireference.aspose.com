---
title: Enum CompressionLevel
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Saving.CompressionLevel تعداد. مستوى الضغط لملفات OOXML.
type: docs
weight: 4610
url: /ar/net/aspose.words.saving/compressionlevel/
---
## CompressionLevel enumeration

مستوى الضغط لملفات OOXML.

(ملفات DOCX و DOTX هي أرشيف ZIP داخليًا ، وتتحكم هذه الخاصية في مستوى ضغط الأرشيف.

لاحظ أن ملف FlatOpc ليس أرشيفًا مضغوطًا ، وبالتالي ، لا تؤثر هذه الخاصية على ملفات FlatOpc.)

```csharp
public enum CompressionLevel
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Normal | `0` | مستوى ضغط عادي. مستوى الضغط الافتراضي المستخدم بواسطة Aspose.Words. |
| Maximum | `1` | الحد الأقصى لمستوى الضغط . |
| Fast | `2` | مستوى ضغط سريع . |
| SuperFast | `3` | مستوى ضغط فائق السرعة. يستخدم Microsoft Word مستوى الضغط هذا. |

### أمثلة

يوضح كيفية تحديد مستوى الضغط لاستخدامه أثناء حفظ مستند OOXML.

```csharp
Document doc = new Document(MyDir + "Big document.docx");

// عندما نحفظ المستند بتنسيق OOXML ، يمكننا إنشاء كائن OoxmlSaveOptions
// ثم قم بتمريره إلى طريقة حفظ المستند لتعديل كيفية حفظ المستند.
// قم بتعيين خاصية "CompressionLevel" إلى "CompressionLevel.Maximum" لتطبيق أقوى وأبطأ ضغط.
// قم بتعيين خاصية "CompressionLevel" إلى "CompressionLevel.Normal" لتطبيقها
// الضغط الافتراضي الذي يستخدمه Aspose.Words أثناء حفظ مستندات OOXML.
// قم بتعيين خاصية "CompressionLevel" إلى "CompressionLevel.Fast" لتطبيق ضغط أسرع وأضعف.
// قم بتعيين خاصية "CompressionLevel" إلى "CompressionLevel.SuperFast" لتطبيقها
// الضغط الافتراضي الذي يستخدمه Microsoft Word.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.CompressionLevel = compressionLevel;

Stopwatch st = Stopwatch.StartNew();
doc.Save(ArtifactsDir + "OoxmlSaveOptions.DocumentCompression.docx", saveOptions);
st.Stop();

FileInfo fileInfo = new FileInfo(ArtifactsDir + "OoxmlSaveOptions.DocumentCompression.docx");

Console.WriteLine($"Saving operation done using the \"{compressionLevel}\" compression level:");
Console.WriteLine($"\tDuration:\t{st.ElapsedMilliseconds} ms");
Console.WriteLine($"\tFile Size:\t{fileInfo.Length} bytes");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Saving](../../aspose.words.saving/)
* المجسم [Aspose.Words](../../)


