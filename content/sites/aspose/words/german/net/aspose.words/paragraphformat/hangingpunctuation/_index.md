---
title: ParagraphFormat.HangingPunctuation
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphFormat eigendom. Ruft ein Flag ab oder setzt es das angibt ob hängende Interpunktion für den aktuellen Absatz aktiviert ist.
type: docs
weight: 120
url: /de/net/aspose.words/paragraphformat/hangingpunctuation/
---
## ParagraphFormat.HangingPunctuation property

Ruft ein Flag ab oder setzt es, das angibt, ob hängende Interpunktion für den aktuellen Absatz aktiviert ist.

```csharp
public bool HangingPunctuation { get; set; }
```

### Beispiele

Zeigt, wie spezielle Eigenschaften für asiatische Typografie festgelegt werden.

```csharp
Document doc = new Document(MyDir + "Document.docx");

ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.FarEastLineBreakControl = true;
format.WordWrap = false;
format.HangingPunctuation = true;

doc.Save(ArtifactsDir + "ParagraphFormat.AsianTypographyProperties.docx");
```

### Siehe auch

* class [ParagraphFormat](../)
* namensraum [Aspose.Words](../../paragraphformat/)
* Montage [Aspose.Words](../../../)


