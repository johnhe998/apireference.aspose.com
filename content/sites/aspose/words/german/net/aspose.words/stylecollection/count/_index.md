---
title: StyleCollection.Count
second_title: Aspose.Words für .NET-API-Referenz
description: StyleCollection eigendom. Ruft die Anzahl der Stile in der Sammlung ab.
type: docs
weight: 10
url: /de/net/aspose.words/stylecollection/count/
---
## StyleCollection.Count property

Ruft die Anzahl der Stile in der Sammlung ab.

```csharp
public int Count { get; }
```

### Beispiele

Zeigt, wie Sie der Stilsammlung eines Dokuments einen Stil hinzufügen.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Legen Sie Standardparameter für neue Stile fest, die wir später zu dieser Sammlung hinzufügen können.
styles.DefaultFont.Name = "Courier New";

// Wenn wir einen Stil des "StyleType.Paragraph" hinzufügen, wendet die Sammlung die Werte von an
// seine "DefaultParagraphFormat"-Eigenschaft auf die "ParagraphFormat"-Eigenschaft des Stils.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Füge einen Stil hinzu und vergewissere dich, dass er die Standardeinstellungen hat.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### Siehe auch

* class [StyleCollection](../)
* namensraum [Aspose.Words](../../stylecollection/)
* Montage [Aspose.Words](../../../)


