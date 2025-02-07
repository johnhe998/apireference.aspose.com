---
title: Class ImportFormatOptions
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.ImportFormatOptions فصل. يسمح بتحديد خيارات استيراد متنوعة لتنسيق الإخراج.
type: docs
weight: 3040
url: /ar/net/aspose.words/importformatoptions/
---
## ImportFormatOptions class

يسمح بتحديد خيارات استيراد متنوعة لتنسيق الإخراج.

```csharp
public class ImportFormatOptions
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [ImportFormatOptions](importformatoptions/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [ForceCopyStyles](../../aspose.words/importformatoptions/forcecopystyles/) { get; set; } | الحصول على أو تعيين قيمة منطقية تشير إما إلى نسخ الأنماط المتعارضة_ فيKeepSourceFormatting mode. القيمة الافتراضية هي`خاطئة` . |
| [IgnoreHeaderFooter](../../aspose.words/importformatoptions/ignoreheaderfooter/) { get; set; } | الحصول على أو تعيين قيمة منطقية تحدد تنسيق المصدر لمحتوى الرؤوس / التذييلات الذي تم تجاهله_ إذاKeepSourceFormatting الوضع المستخدم . القيمة الافتراضية هي`حقيقي` . |
| [IgnoreTextBoxes](../../aspose.words/importformatoptions/ignoretextboxes/) { get; set; } | الحصول على أو تعيين قيمة منطقية تحدد تنسيق المصدر لمحتوى مربعات النص الذي تم تجاهله_ إذاKeepSourceFormatting الوضع المستخدم . القيمة الافتراضية هي`حقيقي` . |
| [KeepSourceNumbering](../../aspose.words/importformatoptions/keepsourcenumbering/) { get; set; } | الحصول على أو تعيين قيمة منطقية تحدد كيفية استيراد الترقيم عندما يتعارض في مستندات المصدر و_ المستندات . القيمة الافتراضية هي`خاطئة` . |
| [MergePastedLists](../../aspose.words/importformatoptions/mergepastedlists/) { get; set; } | الحصول على أو تعيين قيمة منطقية تحدد ما إذا كان سيتم دمج القوائم الملصقة مع القوائم المحيطة.`خاطئة` . |
| [SmartStyleBehavior](../../aspose.words/importformatoptions/smartstylebehavior/) { get; set; } | الحصول على أو تعيين قيمة منطقية تحدد كيفية استيراد الأنماط _ عندما يكون لها أسماء متساوية في مستندات المصدر والوجهة. _ القيمة الافتراضية هي`خاطئة` . |

### أمثلة

يوضح كيفية حل الأنماط المكررة أثناء إدراج المستندات.

```csharp
Document dstDoc = new Document();
DocumentBuilder builder = new DocumentBuilder(dstDoc);

Style myStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyStyle");
myStyle.Font.Size = 14;
myStyle.Font.Name = "Courier New";
myStyle.Font.Color = Color.Blue;

builder.ParagraphFormat.StyleName = myStyle.Name;
builder.Writeln("Hello world!");

// استنساخ المستند وتعديل نمط "MyStyle" الخاص بالنسخة ، بحيث يكون لونه مختلفًا عن اللون الأصلي.
// إذا أدخلنا النسخة في المستند الأصلي ، فإن النمطين اللذين يحملان الاسم نفسه سيتسببان في حدوث تضارب.
Document srcDoc = dstDoc.Clone();
srcDoc.Styles["MyStyle"].Font.Color = Color.Red;

// عندما نقوم بتمكين SmartStyleBehavior واستخدام وضع تنسيق الاستيراد KeepSourceFormatting ،
// Aspose.Words سوف تحل تضارب الأنماط عن طريق تحويل أنماط الوثيقة المصدر.
// بنفس أسماء أنماط الوجهة في سمات الفقرة المباشرة.
ImportFormatOptions options = new ImportFormatOptions();
options.SmartStyleBehavior = true;

builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);

dstDoc.Save(ArtifactsDir + "DocumentBuilder.SmartStyleBehavior.docx");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


