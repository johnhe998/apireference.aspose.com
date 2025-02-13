---
title: FieldKeywords.Text
second_title: Aspose.Words für .NET-API-Referenz
description: FieldKeywords eigendom. Ruft den Text der Schlüsselwörter ab oder setzt ihn.
type: docs
weight: 20
url: /de/net/aspose.words.fields/fieldkeywords/text/
---
## FieldKeywords.Text property

Ruft den Text der Schlüsselwörter ab oder setzt ihn.

```csharp
public string Text { get; set; }
```

### Beispiele

Zeigt an, dass ein KEYWORDS-Feld eingefügt werden soll.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Fügen Sie einige Schlüsselwörter hinzu, die im Datei-Explorer auch als "Tags" bezeichnet werden.
doc.BuiltInDocumentProperties.Keywords = "Keyword1, Keyword2";

// Das Feld KEYWORDS zeigt den Wert dieser Eigenschaft an.
FieldKeywords field = (FieldKeywords)builder.InsertField(FieldType.FieldKeyword, true);
field.Update();

Assert.AreEqual(" KEYWORDS ", field.GetFieldCode());
Assert.AreEqual("Keyword1, Keyword2", field.Result);

// Festlegen eines Werts für die Text-Eigenschaft des Felds,
// und das anschließende Aktualisieren des Felds überschreibt auch die entsprechende integrierte Eigenschaft mit dem neuen Wert.
field.Text = "OverridingKeyword";
field.Update();

Assert.AreEqual(" KEYWORDS  OverridingKeyword", field.GetFieldCode());
Assert.AreEqual("OverridingKeyword", field.Result);
Assert.AreEqual("OverridingKeyword", doc.BuiltInDocumentProperties.Keywords);

doc.Save(ArtifactsDir + "Field.KEYWORDS.docx");
```

### Siehe auch

* class [FieldKeywords](../)
* namensraum [Aspose.Words.Fields](../../fieldkeywords/)
* Montage [Aspose.Words](../../../)


