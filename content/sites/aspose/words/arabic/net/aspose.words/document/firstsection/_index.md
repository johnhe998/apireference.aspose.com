---
title: Document.FirstSection
second_title: Aspose.Words لمراجع .NET API
description: Document ملكية. يحصل على القسم الأول في المستند.
type: docs
weight: 130
url: /ar/net/aspose.words/document/firstsection/
---
## Document.FirstSection property

يحصل على القسم الأول في المستند.

```csharp
public Section FirstSection { get; }
```

### ملاحظات

عوائد`لا شيء` إذا لم يكن هناك أقسام.

### أمثلة

يوضح كيفية استبدال النص في تذييل المستند.

```csharp
Document doc = new Document(MyDir + "Footer.docx");

HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

FindReplaceOptions options = new FindReplaceOptions
{
    MatchCase = false,
    FindWholeWordsOnly = false
};

int currentYear = DateTime.Now.Year;
footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", $"Copyright (C) {currentYear} by Aspose Pty Ltd.", options);

doc.Save(ArtifactsDir + "HeaderFooter.ReplaceText.docx");
```

يوضح كيفية إنشاء قسم جديد باستخدام منشئ المستندات.

```csharp
Document doc = new Document();

// يحتوي المستند الفارغ على قسم واحد افتراضيًا ،
// التي تحتوي على عقد فرعية يمكننا تعديلها.
Assert.AreEqual(1, doc.Sections.Count);

// استخدم منشئ المستندات لإضافة نص إلى القسم الأول.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world!");

// أنشئ قسمًا ثانيًا عن طريق إدخال فاصل مقطعي.
builder.InsertBreak(BreakType.SectionBreakNewPage);

Assert.AreEqual(2, doc.Sections.Count);

// لكل قسم إعدادات إعداد الصفحة الخاصة به.
// يمكننا تقسيم النص في القسم الثاني إلى عمودين.
// لن يؤثر هذا على النص في القسم الأول.
doc.LastSection.PageSetup.TextColumns.SetCount(2);
builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

Assert.AreEqual(1, doc.FirstSection.PageSetup.TextColumns.Count);
Assert.AreEqual(2, doc.LastSection.PageSetup.TextColumns.Count);

doc.Save(ArtifactsDir + "Section.Create.docx");
```

يوضح كيفية التكرار من خلال العناصر الفرعية لعقدة مركبة.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Section 1");
builder.MoveToHeaderFooter(HeaderFooterType.HeaderPrimary);
builder.Write("Primary header");
builder.MoveToHeaderFooter(HeaderFooterType.FooterPrimary);
builder.Write("Primary footer");

Section section = doc.FirstSection;

// A القسم هو عقدة مركبة ويمكن أن يحتوي على عقد فرعية ،
// ولكن فقط إذا كانت هذه العقد الفرعية من نوع العقدة "Body" أو "HeaderFooter".
foreach (Node node in section)
{
    switch (node.NodeType)
    {
        case NodeType.Body:
        {
            Body body = (Body)node;

            Console.WriteLine("Body:");
            Console.WriteLine($"\t\"{body.GetText().Trim()}\"");
            break;
        }
        case NodeType.HeaderFooter:
        {
            HeaderFooter headerFooter = (HeaderFooter)node;

            Console.WriteLine($"HeaderFooter type: {headerFooter.HeaderFooterType}:");
            Console.WriteLine($"\t\"{headerFooter.GetText().Trim()}\"");
            break;
        }
        default:
        {
            throw new Exception("Unexpected node type in a section.");
        }
    }
}
```

### أنظر أيضا

* class [Section](../../section/)
* class [Document](../)
* مساحة الاسم [Aspose.Words](../../document/)
* المجسم [Aspose.Words](../../../)


