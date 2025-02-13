---
title: Enum RevisionsView
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.RevisionsView uppräkning. Låter dig ange om du vill arbeta med den ursprungliga eller reviderade versionen av ett dokument.
type: docs
weight: 4550
url: /sv/net/aspose.words/revisionsview/
---
## RevisionsView enumeration

Låter dig ange om du vill arbeta med den ursprungliga eller reviderade versionen av ett dokument.

```csharp
public enum RevisionsView
```

### Värderingar

| namn | Värde | Beskrivning |
| --- | --- | --- |
| Original | `0` | Anger originalversionen av ett dokument. |
| Final | `1` | Anger reviderad version av ett dokument. |

### Exempel

Visar hur du växlar mellan den reviderade och den ursprungliga vyn av ett dokument.

```csharp
Document doc = new Document(MyDir + "Revisions at list levels.docx");
doc.UpdateListLabels();

ParagraphCollection paragraphs = doc.FirstSection.Body.Paragraphs;
Assert.AreEqual("1.", paragraphs[0].ListLabel.LabelString);
Assert.AreEqual("a.", paragraphs[1].ListLabel.LabelString);
Assert.AreEqual(string.Empty, paragraphs[2].ListLabel.LabelString);

// Visa dokumentobjektet som om alla revisioner är accepterade. Stöder för närvarande listetiketter.
doc.RevisionsView = RevisionsView.Final;

Assert.AreEqual(string.Empty, paragraphs[0].ListLabel.LabelString);
Assert.AreEqual("1.", paragraphs[1].ListLabel.LabelString);
Assert.AreEqual("a.", paragraphs[2].ListLabel.LabelString);
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


