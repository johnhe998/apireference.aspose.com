---
title: SmartTag.SmartTag
second_title: Aspose.Words لمراجع .NET API
description: SmartTag البناء. يقوم بتهيئة مثيل جديد لملفSmartTag فئة .
type: docs
weight: 10
url: /ar/net/aspose.words.markup/smarttag/smarttag/
---
## SmartTag constructor

يقوم بتهيئة مثيل جديد لملف[`SmartTag`](../) فئة .

```csharp
public SmartTag(DocumentBase doc)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| doc | DocumentBase | وثيقة المالك. |

### ملاحظات

عندما تقوم بإنشاء عقدة جديدة ، فأنت بحاجة إلى تحديد مستند تنتمي إليه العقدة . لا يمكن أن توجد العقدة بدون مستند لأنها تعتمد على الهياكل على مستوى المستند مثل القوائم والأنماط. على الرغم من أن العقدة تنتمي دائمًا إلى مستند ، فقد تكون العقدة أو قد لا تكون جزءًا من شجرة المستند.

عندما يتم إنشاء عقدة ، فإنها تنتمي إلى مستند ، ولكنها ليست بعد جزءًا من شجرة المستند و[`ParentNode`](../../../aspose.words/node/parentnode/) باطل. لإدراج عقدة في المستند ، استخدم the [`InsertAfter`](../../../aspose.words/compositenode/insertafter/) أو[`InsertBefore`](../../../aspose.words/compositenode/insertbefore/) طرق على العقدة الأصل.

### أمثلة

يوضح كيفية إنشاء العلامات الذكية.

```csharp
public void Create()
{
    Document doc = new Document();

    // تظهر علامة ذكية في مستند مع Microsoft Word يتعرف على جزء من نصه كشكل من أشكال البيانات ،
    // مثل الاسم أو التاريخ أو العنوان ، ويحوله إلى ارتباط تشعبي يعرض تسطيرًا منقطًا بنفسجي اللون.
    SmartTag smartTag = new SmartTag(doc);

    // العلامات الذكية عبارة عن عقد مركبة تحتوي على نص تم التعرف عليه بالكامل.
    // أضف محتويات إلى هذه العلامة الذكية يدويًا.
    smartTag.AppendChild(new Run(doc, "May 29, 2019"));

    // قد يتعرف Microsoft Word على المحتويات المذكورة أعلاه على أنها تاريخ.
    // تستخدم العلامات الذكية خاصية "العنصر" لتعكس نوع البيانات التي تحتوي عليها.
    smartTag.Element = "date";

    // تقوم بعض أنواع العلامات الذكية بمعالجة محتوياتها بشكل أكبر في خصائص XML المخصصة.
    smartTag.Properties.Add(new CustomXmlProperty("Day", string.Empty, "29"));
    smartTag.Properties.Add(new CustomXmlProperty("Month", string.Empty, "5"));
    smartTag.Properties.Add(new CustomXmlProperty("Year", string.Empty, "2019"));

    // اضبط عنوان URI للعلامة الذكية على القيمة الافتراضية.
    smartTag.Uri = "urn:schemas-microsoft-com:office:smarttags";

    doc.FirstSection.Body.FirstParagraph.AppendChild(smartTag);
    doc.FirstSection.Body.FirstParagraph.AppendChild(new Run(doc, " is a date. "));

    // إنشاء علامة ذكية أخرى لمؤشر الأسهم.
    smartTag = new SmartTag(doc);
    smartTag.Element = "stockticker";
    smartTag.Uri = "urn:schemas-microsoft-com:office:smarttags";

    smartTag.AppendChild(new Run(doc, "MSFT"));

    doc.FirstSection.Body.FirstParagraph.AppendChild(smartTag);
    doc.FirstSection.Body.FirstParagraph.AppendChild(new Run(doc, " is a stock ticker."));

    // طباعة جميع العلامات الذكية في وثيقتنا باستخدام زائر المستند.
    doc.Accept(new SmartTagPrinter());

    // تدعم الإصدارات القديمة من Microsoft Word العلامات الذكية.
    doc.Save(ArtifactsDir + "SmartTag.Create.doc");

    // استخدم طريقة "RemoveSmartTags" لإزالة كافة العلامات الذكية من المستند.
    Assert.AreEqual(2, doc.GetChildNodes(NodeType.SmartTag, true).Count);

    doc.RemoveSmartTags();

    Assert.AreEqual(0, doc.GetChildNodes(NodeType.SmartTag, true).Count);
}

/// <summary>
/// تمت زيارة المطبوعات للعلامات الذكية ومحتوياتها.
/// </summary>
private class SmartTagPrinter : DocumentVisitor
{
    /// <summary>
    /// يتم الاستدعاء عند مواجهة عقدة SmartTag في المستند.
    /// </summary>
    public override VisitorAction VisitSmartTagStart(SmartTag smartTag)
    {
        Console.WriteLine($"Smart tag type: {smartTag.Element}");
        return VisitorAction.Continue;
    }

    /// <summary>
    /// يتم الاستدعاء عند انتهاء زيارة عقدة SmartTag.
    /// </summary>
    public override VisitorAction VisitSmartTagEnd(SmartTag smartTag)
    {
        Console.WriteLine($"\tContents: \"{smartTag.ToString(SaveFormat.Text)}\"");

        if (smartTag.Properties.Count == 0)
        {
            Console.WriteLine("\tContains no properties");
        }
        else
        {
            Console.Write("\tProperties: ");
            string[] properties = new string[smartTag.Properties.Count];
            int index = 0;

            foreach (CustomXmlProperty cxp in smartTag.Properties)
                properties[index++] = $"\"{cxp.Name}\" = \"{cxp.Value}\"";

            Console.WriteLine(string.Join(", ", properties));
        }

        return VisitorAction.Continue;
    }
}
```

### أنظر أيضا

* class [DocumentBase](../../../aspose.words/documentbase/)
* class [SmartTag](../)
* مساحة الاسم [Aspose.Words.Markup](../../smarttag/)
* المجسم [Aspose.Words](../../../)


