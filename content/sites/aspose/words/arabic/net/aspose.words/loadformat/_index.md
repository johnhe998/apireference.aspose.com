---
title: Enum LoadFormat
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.LoadFormat تعداد. يشير إلى تنسيق المستند الذي سيتم تحميله.
type: docs
weight: 3350
url: /ar/net/aspose.words/loadformat/
---
## LoadFormat enumeration

يشير إلى تنسيق المستند الذي سيتم تحميله.

```csharp
public enum LoadFormat
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Auto | `0` | يوجه Aspose. Words للتعرف على التنسيق تلقائيًا. |
| Doc | `10` | مستند Microsoft Word 95 أو Word 97-2003 . |
| Dot | `11` | Microsoft Word 95 أو Word 97-2003 Template. |
| DocPreWord60 | `12` | المستند بتنسيق ما قبل Word 95. Aspose. لا تدعم AdWords حاليًا تحميل مثل هذه المستندات. |
| Docx | `20` | Office Open XML WordprocessingML Document (خالٍ من الماكرو) . |
| Docm | `21` | Office Open XML WordprocessingML مستند ممكّن بماكرو . |
| Dotx | `22` | Office Open XML WordprocessingML Template (خالٍ من الماكرو) . |
| Dotm | `23` | Office Open XML WordprocessingML قالب ممكّن بماكرو . |
| FlatOpc | `24` | Office Open XML WordprocessingML المخزنة في ملف XML ثابت بدلاً من حزمة ZIP. |
| FlatOpcMacroEnabled | `25` | Office Open XML WordprocessingML مستند ممكن بماكرو مخزن في ملف XML مسطح بدلاً من حزمة ZIP. |
| FlatOpcTemplate | `26` | Office Open XML WordprocessingML Template (خالٍ من الماكرو) المخزن في ملف XML مسطح بدلاً من حزمة ZIP. |
| FlatOpcTemplateMacroEnabled | `27` | Office Open XML WordprocessingML قالب ممكّن بماكرو مخزن في ملف XML مسطح بدلاً من حزمة ZIP. |
| Rtf | `30` | تنسيق RTF . |
| WordML | `31` | تنسيق Microsoft Word 2003 WordprocessingML . |
| Html | `50` | تنسيق HTML. |
| Mhtml | `51` | تنسيق MHTML (أرشيف الويب). |
| Mobi | `52` | تنسيق MOBI. يستخدمه قارئ MobiPocket وقارئي Amazon Kindle. |
| Chm | `53` | تنسيق CHM (تعليمات HTML المجمعة). |
| Azw3 | `54` | تنسيق AZW3. مستخدم من قبل قراء أمازون كيندل. |
| Epub | `55` | تنسيق EPUB . |
| Odt | `60` | مستند نصي ODF . |
| Ott | `61` | قالب مستند نصي ODF . |
| Text | `62` | نص عادي. |
| Markdown | `63` | مستند نص Markdown . |
| Pdf | `64` | مستند PDF . |
| Xml | `65` | مستند XML . |
| Unknown | `255` | تنسيق غير معروف ، لا يمكن تحميله بواسطة Aspose.Words. |

### أمثلة

يوضح كيفية حفظ صفحة ويب كملف docx.

```csharp
const string url = "http://www.aspose.com/ ";

using (WebClient client = new WebClient()) 
{ 
    using (MemoryStream stream = new MemoryStream(client.DownloadData(url)))
    {
        // يتم استخدام عنوان URL مرة أخرى باعتباره baseUri لضمان استرداد أي مسارات صور ذات صلة بشكل صحيح.
        LoadOptions options = new LoadOptions(LoadFormat.Html, "", url);

        // قم بتحميل مستند HTML من الدفق وتمرير كائن LoadOptions.
        Document doc = new Document(stream, options);

        // في هذه المرحلة ، يمكننا قراءة محتويات المستند وتحريرها ثم حفظها في نظام الملفات المحلي.
        doc.Save(ArtifactsDir + "Document.InsertHtmlFromWebPage.docx");
    }
}
```

يوضح كيفية تحديد عنوان URI أساسي عند فتح مستند html.

```csharp
// لنفترض أننا نريد تحميل مستند .html يحتوي على صورة مرتبطة بواسطة URI نسبي
// أثناء وجود الصورة في موقع مختلف. في هذه الحالة ، سنحتاج إلى حل URI النسبي إلى واحد مطلق.
 // يمكننا توفير URI أساسي باستخدام كائن HtmlLoadOptions.
HtmlLoadOptions loadOptions = new HtmlLoadOptions(LoadFormat.Html, "", ImageDir);

Assert.AreEqual(LoadFormat.Html, loadOptions.LoadFormat);

Document doc = new Document(MyDir + "Missing image.html", loadOptions);

// بينما كانت الصورة معطلة في الإدخال .html ، ساعدنا URI المخصص في إصلاح الرابط.
Shape imageShape = (Shape)doc.GetChildNodes(NodeType.Shape, true)[0];
Assert.True(imageShape.IsImage);

// سيعرض هذا المستند الناتج الصورة المفقودة.
doc.Save(ArtifactsDir + "HtmlLoadOptions.BaseUri.docx");
```

يوضح كيفية استخدام أساليب FileFormatUtil لاكتشاف تنسيق المستند.

```csharp
// قم بتحميل مستند من ملف يفتقد إلى امتداد الملف ، ثم اكتشف تنسيق الملف الخاص به.
using (FileStream docStream = File.OpenRead(MyDir + "Word document with missing file extension"))
{
    FileFormatInfo info = FileFormatUtil.DetectFileFormat(docStream);
    LoadFormat loadFormat = info.LoadFormat;

    Assert.AreEqual(LoadFormat.Doc, loadFormat);

    // فيما يلي طريقتان لتحويل LoadFormat إلى SaveFormat المقابل له.
    // 1 - احصل على سلسلة امتداد الملف لـ LoadFormat ، ثم احصل على تنسيق SaveFormat المقابل من تلك السلسلة:
    string fileExtension = FileFormatUtil.LoadFormatToExtension(loadFormat);
    SaveFormat saveFormat = FileFormatUtil.ExtensionToSaveFormat(fileExtension);

    // 2 - تحويل LoadFormat مباشرة إلى SaveFormat الخاص به:
    saveFormat = FileFormatUtil.LoadFormatToSaveFormat(loadFormat);

    // قم بتحميل مستند من الدفق ، ثم احفظه في امتداد الملف المكتشف تلقائيًا.
    Document doc = new Document(docStream);

    Assert.AreEqual(".doc", FileFormatUtil.SaveFormatToExtension(saveFormat));

    doc.Save(ArtifactsDir + "File.SaveToDetectedFileFormat" + FileFormatUtil.SaveFormatToExtension(saveFormat));
}
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


