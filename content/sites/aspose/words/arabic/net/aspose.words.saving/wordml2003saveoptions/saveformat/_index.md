---
title: WordML2003SaveOptions.SaveFormat
second_title: Aspose.Words لمراجع .NET API
description: WordML2003SaveOptions ملكية. يحدد التنسيق الذي سيتم حفظ المستند به إذا تم استخدام كائن خيارات الحفظ . يمكن فقط أن يكونWordML .
type: docs
weight: 20
url: /ar/net/aspose.words.saving/wordml2003saveoptions/saveformat/
---
## WordML2003SaveOptions.SaveFormat property

يحدد التنسيق الذي سيتم حفظ المستند به إذا تم استخدام كائن خيارات الحفظ . يمكن فقط أن يكونWordML .

```csharp
public override SaveFormat SaveFormat { get; set; }
```

### أمثلة

يوضح كيفية إدارة المحتوى الأولي للمستند الناتج.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// قم بإنشاء كائن "WordML2003SaveOptions" لتمريره إلى أسلوب "حفظ" المستند
// لتعديل كيفية حفظ المستند بتنسيق حفظ WordML.
WordML2003SaveOptions options = new WordML2003SaveOptions();

Assert.AreEqual(SaveFormat.WordML, options.SaveFormat);

// عيّن خاصية "PrettyFormat" على "true" لتطبيق مسافة بادئة لأحرف الجدولة و
// newlines لتسهيل قراءة المحتوى الأولي للمستند الناتج.
// اضبط خاصية "PrettyFormat" على "false" لحفظ محتوى المستند الأولي في نص واحد مستمر من النص.
options.PrettyFormat = prettyFormat;

doc.Save(ArtifactsDir + "WordML2003SaveOptions.PrettyFormat.xml", options);

string fileContents = File.ReadAllText(ArtifactsDir + "WordML2003SaveOptions.PrettyFormat.xml");

if (prettyFormat)
    Assert.True(fileContents.Contains(
        "<o:DocumentProperties>\r\n\t\t" +
            "<o:Revision>1</o:Revision>\r\n\t\t" +
            "<o:TotalTime>0</o:TotalTime>\r\n\t\t" +
            "<o:Pages>1</o:Pages>\r\n\t\t" +
            "<o:Words>0</o:Words>\r\n\t\t" +
            "<o:Characters>0</o:Characters>\r\n\t\t" +
            "<o:Lines>1</o:Lines>\r\n\t\t" +
            "<o:Paragraphs>1</o:Paragraphs>\r\n\t\t" +
            "<o:CharactersWithSpaces>0</o:CharactersWithSpaces>\r\n\t\t" +
            "<o:Version>11.5606</o:Version>\r\n\t" +
        "</o:DocumentProperties>"));
else
    Assert.True(fileContents.Contains(
        "<o:DocumentProperties><o:Revision>1</o:Revision><o:TotalTime>0</o:TotalTime><o:Pages>1</o:Pages>" +
        "<o:Words>0</o:Words><o:Characters>0</o:Characters><o:Lines>1</o:Lines><o:Paragraphs>1</o:Paragraphs>" +
        "<o:CharactersWithSpaces>0</o:CharactersWithSpaces><o:Version>11.5606</o:Version></o:DocumentProperties>"));
```

### أنظر أيضا

* enum [SaveFormat](../../../aspose.words/saveformat/)
* class [WordML2003SaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../wordml2003saveoptions/)
* المجسم [Aspose.Words](../../../)


