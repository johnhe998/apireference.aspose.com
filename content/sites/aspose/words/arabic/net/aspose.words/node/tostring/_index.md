---
title: Node.ToString
second_title: Aspose.Words لمراجع .NET API
description: Node طريقة. يصدر محتوى العقدة إلى سلسلة بالتنسيق المحدد.
type: docs
weight: 160
url: /ar/net/aspose.words/node/tostring/
---
## ToString(SaveFormat) {#tostring_1}

يصدر محتوى العقدة إلى سلسلة بالتنسيق المحدد.

```csharp
public string ToString(SaveFormat saveFormat)
```

### قيمة الإرجاع

محتوى العقدة بالتنسيق المحدد.

### أمثلة

يظهر الفرق بين استدعاء الأسلوبين GetText و ToString على العقدة.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("MERGEFIELD Field");

// سوف يقوم GetText باسترداد النص المرئي بالإضافة إلى رموز الحقول والأحرف الخاصة.
Assert.AreEqual("\u0013MERGEFIELD Field\u0014«Field»\u0015\u000c", doc.GetText());

// سيعطينا ToString مظهر المستند إذا تم حفظه بتنسيق حفظ تم تمريره.
Assert.AreEqual("«Field»\r\n", doc.ToString(SaveFormat.Text));
```

يصدر محتوى العقدة إلى سلسلة بتنسيق HTML.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Node node = doc.LastSection.Body.LastParagraph;

// عندما نستدعي طريقة ToString باستخدام التحميل الزائد html SaveFormat ،
// تقوم بتحويل محتويات العقدة إلى تمثيلها بصيغة html الخام.
Assert.AreEqual("<p style=\"margin-top:0pt; margin-bottom:8pt; line-height:108%; font-size:12pt\">" +
                "<span style=\"font-family:'Times New Roman'\">Hello World!</span>" +
                "</p>", node.ToString(SaveFormat.Html));

// يمكننا أيضًا تعديل نتيجة هذا التحويل باستخدام كائن SaveOptions.
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.ExportRelativeFontSize = true;

Assert.AreEqual("<p style=\"margin-top:0pt; margin-bottom:8pt; line-height:108%\">" +
                "<span style=\"font-family:'Times New Roman'\">Hello World!</span>" +
                "</p>", node.ToString(saveOptions));
```

يوضح كيفية استخراج تسميات القائمة لكل الفقرات التي تمثل عناصر قائمة.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
doc.UpdateListLabels();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

// ابحث عما إذا كان لدينا قائمة الفقرات. في وثيقتنا ، تستخدم قائمتنا أرقامًا عربية بسيطة ،
// التي تبدأ عند الثالثة وتنتهي عند السادسة.
foreach (Paragraph paragraph in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{
    Console.WriteLine($"List item paragraph #{paras.IndexOf(paragraph)}");

    // هذا هو النص الذي نحصل عليه عند إخراج هذه العقدة إلى تنسيق نصي.
    // سيحذف إخراج النص هذا تسميات القائمة. تقليم أي أحرف تنسيق الفقرة. 
    string paragraphText = paragraph.ToString(SaveFormat.Text).Trim();
    Console.WriteLine($"\tExported Text: {paragraphText}");

    ListLabel label = paragraph.ListLabel;

    // هذا يحصل على موضع الفقرة في المستوى الحالي من القائمة. إذا كانت لدينا قائمة بمستويات متعددة ،
    // سيخبرنا هذا بالموقع الذي وصلت إليه على هذا المستوى.
    Console.WriteLine($"\tNumerical Id: {label.LabelValue}");

    // اجمعها معًا لتضمين تسمية القائمة مع النص في الإخراج.
    Console.WriteLine($"\tList label combined with text: {label.LabelString} {paragraphText}");
}
```

### أنظر أيضا

* enum [SaveFormat](../../saveformat/)
* class [Node](../)
* مساحة الاسم [Aspose.Words](../../node/)
* المجسم [Aspose.Words](../../../)

---

## ToString(SaveOptions) {#tostring_2}

يصدر محتوى العقدة إلى سلسلة باستخدام خيارات الحفظ المحددة.

```csharp
public string ToString(SaveOptions saveOptions)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| saveOptions | SaveOptions | يحدد الخيارات التي تتحكم في كيفية حفظ العقدة. |

### قيمة الإرجاع

محتوى العقدة بالتنسيق المحدد.

### أمثلة

يصدر محتوى العقدة إلى سلسلة بتنسيق HTML.

```csharp
Document doc = new Document(MyDir + "Document.docx");

Node node = doc.LastSection.Body.LastParagraph;

// عندما نستدعي طريقة ToString باستخدام التحميل الزائد html SaveFormat ،
// تقوم بتحويل محتويات العقدة إلى تمثيلها بصيغة html الخام.
Assert.AreEqual("<p style=\"margin-top:0pt; margin-bottom:8pt; line-height:108%; font-size:12pt\">" +
                "<span style=\"font-family:'Times New Roman'\">Hello World!</span>" +
                "</p>", node.ToString(SaveFormat.Html));

// يمكننا أيضًا تعديل نتيجة هذا التحويل باستخدام كائن SaveOptions.
HtmlSaveOptions saveOptions = new HtmlSaveOptions();
saveOptions.ExportRelativeFontSize = true;

Assert.AreEqual("<p style=\"margin-top:0pt; margin-bottom:8pt; line-height:108%\">" +
                "<span style=\"font-family:'Times New Roman'\">Hello World!</span>" +
                "</p>", node.ToString(saveOptions));
```

### أنظر أيضا

* class [SaveOptions](../../../aspose.words.saving/saveoptions/)
* class [Node](../)
* مساحة الاسم [Aspose.Words](../../node/)
* المجسم [Aspose.Words](../../../)


