---
title: Body.ParentSection
second_title: Aspose.Words for .NET API Referansı
description: Body mülk. Bu hikayenin üst bölümünü alır.
type: docs
weight: 30
url: /tr/net/aspose.words/body/parentsection/
---
## Body.ParentSection property

Bu hikayenin üst bölümünü alır.

```csharp
public Section ParentSection { get; }
```

### Notlar

**Ebeveyn Bölümü** eşdeğerdir`(Bölüm)Üst Düğüm`.

### Örnekler

Her bölümün sonunda son notların nasıl saklanacağını ve konumlarının nasıl değiştirileceğini gösterir.

```csharp
{
    Document doc = new Document();
    doc.RemoveAllChildren();

     // Varsayılan olarak, bir belge sonunda tüm son notları derler.
    Assert.AreEqual(EndnotePosition.EndOfDocument, doc.EndnoteOptions.Position);

    // Belgenin "EndnoteOptions" nesnesinin "Position" özelliğini kullanıyoruz
     // bunun yerine her bölümün sonunda son notları toplamak için.
    doc.EndnoteOptions.Position = EndnotePosition.EndOfSection;

    InsertSectionWithEndnote(doc, "Section 1", "Endnote 1, will stay in section 1");
    InsertSectionWithEndnote(doc, "Section 2", "Endnote 2, will be pushed down to section 3");
    InsertSectionWithEndnote(doc, "Section 3", "Endnote 3, will stay in section 3");

    // Bölümleri ilgili son notlarını gösterecek şekilde alırken "SuppressEndnotes" bayrağını ayarlayabiliriz
    // varsayılan davranışa geri dönmek ve son notlarını iletmek için bir bölümün "PageSetup" nesnesinin "true" değerine
    // sonraki bölüme geçiyoruz.
    PageSetup pageSetup = doc.Sections[1].PageSetup;
    pageSetup.SuppressEndnotes = true;

    doc.Save(ArtifactsDir + "PageSetup.SuppressEndnotes.docx");

/// <summary>
/// Belgeye metin ve son not içeren bir bölüm ekleyin.
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

### Ayrıca bakınız

* class [Section](../../section/)
* class [Body](../)
* ad alanı [Aspose.Words](../../body/)
* toplantı [Aspose.Words](../../../)


