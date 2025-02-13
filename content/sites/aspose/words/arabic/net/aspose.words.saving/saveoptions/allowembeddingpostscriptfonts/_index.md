---
title: SaveOptions.AllowEmbeddingPostScriptFonts
second_title: Aspose.Words لمراجع .NET API
description: SaveOptions ملكية. الحصول على أو تعيين قيمة منطقية تشير إلى ما إذا كان سيتم السماح بدمج الخطوط مع مخططات PostScript عند حفظ خطوط TrueType في مستند ما . القيمة الافتراضية هي خاطئة .
type: docs
weight: 20
url: /ar/net/aspose.words.saving/saveoptions/allowembeddingpostscriptfonts/
---
## SaveOptions.AllowEmbeddingPostScriptFonts property

الحصول على أو تعيين قيمة منطقية تشير إلى ما إذا كان سيتم السماح بدمج الخطوط مع مخططات PostScript عند حفظ خطوط TrueType في مستند ما . القيمة الافتراضية هي **خاطئة** .

```csharp
public bool AllowEmbeddingPostScriptFonts { get; set; }
```

### ملاحظات

ملاحظة ، لا يقوم Word بتضمين خطوط PostScript ، ولكن يمكنه فتح المستندات ذات الخطوط المضمنة من هذا النوع.

هذا الخيار يعمل فقط عندما[`EmbedTrueTypeFonts`](../../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) من [`FontInfos`](../../../aspose.words/documentbase/fontinfos/) تم تعيين الخاصية على`حقيقي`.

### أمثلة

يوضح كيفية حفظ المستند بخط PostScript.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Font.Name = "PostScriptFont";
builder.Writeln("Some text with PostScript font.");

// قم بتحميل الخط باستخدام PostScript لاستخدامه في المستند.
MemoryFontSource otf = new MemoryFontSource(File.ReadAllBytes(FontsDir + "AllegroOpen.otf"));
doc.FontSettings = new FontSettings();
doc.FontSettings.SetFontsSources(new FontSourceBase[] { otf });

// تضمين خطوط تروتايب.
doc.FontInfos.EmbedTrueTypeFonts = true;

// السماح بدمج خطوط PostScript أثناء دمج خطوط TrueType.
// لا يقوم Microsoft Word بتضمين خطوط PostScript ، ولكن يمكنه فتح المستندات ذات الخطوط المضمنة من هذا النوع.
SaveOptions saveOptions = SaveOptions.CreateSaveOptions(SaveFormat.Docx);
saveOptions.AllowEmbeddingPostScriptFonts = true;

doc.Save(ArtifactsDir + "Document.AllowEmbeddingPostScriptFonts.docx", saveOptions);
```

### أنظر أيضا

* class [SaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../saveoptions/)
* المجسم [Aspose.Words](../../../)


