---
title: ParagraphCollection.ToArray
second_title: Aspose.Words für .NET-API-Referenz
description: ParagraphCollection methode. Kopiert alle Absätze aus der Sammlung in ein neues Array von Absätzen.
type: docs
weight: 20
url: /de/net/aspose.words/paragraphcollection/toarray/
---
## ParagraphCollection.ToArray method

Kopiert alle Absätze aus der Sammlung in ein neues Array von Absätzen.

```csharp
public Paragraph[] ToArray()
```

### Rückgabewert

Eine Reihe von Absätzen.

### Beispiele

Zeigt, wie ein Array aus einer NodeCollection erstellt wird.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

Paragraph[] paras = doc.FirstSection.Body.Paragraphs.ToArray();

Assert.AreEqual(22, paras.Length);
```

Zeigt die Verwendung von "Hot Remove", um einen Knoten während der Aufzählung zu entfernen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("The first paragraph");
builder.Writeln("The second paragraph");
builder.Writeln("The third paragraph");
builder.Writeln("The fourth paragraph");

// Entfernen Sie einen Knoten aus der Sammlung mitten in einer Aufzählung.
foreach (Paragraph para in doc.FirstSection.Body.Paragraphs.ToArray())
    if (para.Range.Text.Contains("third"))
        para.Remove();

Assert.False(doc.GetText().Contains("The third paragraph"));
```

### Siehe auch

* class [Paragraph](../../paragraph/)
* class [ParagraphCollection](../)
* namensraum [Aspose.Words](../../paragraphcollection/)
* Montage [Aspose.Words](../../../)


