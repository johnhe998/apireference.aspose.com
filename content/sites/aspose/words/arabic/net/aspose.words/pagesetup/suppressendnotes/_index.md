---
title: PageSetup.SuppressEndnotes
second_title: Aspose.Words لمراجع .NET API
description: PageSetup ملكية. حقيقي إذا تمت طباعة التعليقات الختامية في نهاية القسم التالي الذي لا يمنع التعليقات الختامية . تتم طباعة التعليقات الختامية قبل التعليقات الختامية في هذا القسم.
type: docs
weight: 400
url: /ar/net/aspose.words/pagesetup/suppressendnotes/
---
## PageSetup.SuppressEndnotes property

**حقيقي** إذا تمت طباعة التعليقات الختامية في نهاية القسم التالي الذي لا يمنع التعليقات الختامية . تتم طباعة التعليقات الختامية قبل التعليقات الختامية في هذا القسم.

```csharp
public bool SuppressEndnotes { get; set; }
```

### أمثلة

يوضح كيفية تخزين التعليقات الختامية في نهاية كل قسم وتعديل مواضعها.

```csharp
{
    Document doc = new Document();
    doc.RemoveAllChildren();

     // بشكل افتراضي ، يجمع المستند كل التعليقات الختامية في نهايته.
    Assert.AreEqual(EndnotePosition.EndOfDocument, doc.EndnoteOptions.Position);

    // نحن نستخدم خاصية "Position" لكائن "EndnoteOptions" الخاص بالمستند
     // لتجميع التعليقات الختامية في نهاية كل قسم بدلاً من ذلك.
    doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

    InsertSectionWithEndnote(doc, "Section 1", "Endnote 1, will stay in section 1");
    InsertSectionWithEndnote(doc, "Section 2", "Endnote 2, will be pushed down to section 3");
    InsertSectionWithEndnote(doc, "Section 3", "Endnote 3, will stay in section 3");

    // أثناء إحضار الأقسام لعرض التعليقات الختامية الخاصة بها ، يمكننا تعيين علامة "SuppressEndnotes"
    // من كائن "PageSetup" لقسم ما إلى "صحيح" للعودة إلى السلوك الافتراضي وتمرير التعليقات الختامية الخاصة به
    // في القسم التالي.
    PageSetup pageSetup = doc.Sections[1].PageSetup;
    pageSetup.SuppressEndnotes = true;

    doc.Save(ArtifactsDir + "PageSetup.SuppressEndnotes.docx");

/// <summary>
/// إلحاق قسم بنص وتعليق ختامي بمستند.
/// </summary>
private static void InsertSectionWithEndnote(Document doc, string sectionBodyText, string endnoteText)
{
    Section section = new Section(doc);

    doc.AppendChild(section);

    Body body = new Body(doc);
    section.AppendChild(body);

    Assert.AreEqual(section, body.ParentNode);

    Paragraph para = new Paragraph(doc);
    body.AppendChild(para);

    Assert.AreEqual(body, para.ParentNode);

    DocumentBuilder builder = new DocumentBuilder(doc);
    builder.MoveTo(para);
    builder.Write(sectionBodyText);
    builder.InsertFootnote(FootnoteType.Endnote, endnoteText);
}
```

### أنظر أيضا

* class [PageSetup](../)
* مساحة الاسم [Aspose.Words](../../pagesetup/)
* المجسم [Aspose.Words](../../../)


