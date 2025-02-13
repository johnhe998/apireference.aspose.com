---
title: ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle
second_title: Aspose.Words for .NET API Referansı
description: ParagraphFormat mülk. Doğru olduğundaSpaceBefore veSpaceAfter aynı stildeki paragraflar arasında yok sayılır .
type: docs
weight: 230
url: /tr/net/aspose.words/paragraphformat/nospacebetweenparagraphsofsamestyle/
---
## ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle property

Doğru olduğunda,[`SpaceBefore`](../spacebefore/) ve[`SpaceAfter`](../spaceafter/) aynı stildeki paragraflar arasında yok sayılır .

```csharp
public bool NoSpaceBetweenParagraphsOfSameStyle { get; set; }
```

### Notlar

Bu ayar yalnızca bir paragraf stiline uygulandığında etkili olur. Doğrudan bir paragrafa uygulanırsa, hiçbir etkisi olmaz.

### Örnekler

Aynı stile sahip paragraflar arasında nasıl boşluk uygulanacağını gösterir.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Bu oluşturucunun oluşturacağı paragraflardan önce ve sonra büyük miktarda boşluk uygulayın.
builder.ParagraphFormat.SpaceBefore = 24;
builder.ParagraphFormat.SpaceAfter = 24;

// Uygulamak için "NoSpaceBetweenParagraphsOfSameStyle" bayrağını "true" olarak ayarlayın
// benzer paragrafları gruplayacak aynı stile sahip paragraflar arasında boşluk yok.
// "NoSpaceBetweenParagraphsOfSameStyle" bayrağını "false" olarak bırakın
// her paragrafa eşit aralık uygulamak için.
builder.ParagraphFormat.NoSpaceBetweenParagraphsOfSameStyle = noSpaceBetweenParagraphsOfSameStyle;

builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Quote"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.ParagraphFormat.Style = doc.Styles["Normal"];
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");
builder.Writeln($"Paragraph in the \"{builder.ParagraphFormat.Style.Name}\" style.");

doc.Save(ArtifactsDir + "ParagraphFormat.ParagraphSpacingSameStyle.docx");
```

### Ayrıca bakınız

* class [ParagraphFormat](../)
* ad alanı [Aspose.Words](../../paragraphformat/)
* toplantı [Aspose.Words](../../../)


