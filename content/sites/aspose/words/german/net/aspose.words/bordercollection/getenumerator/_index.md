---
title: BorderCollection.GetEnumerator
second_title: Aspose.Words für .NET-API-Referenz
description: BorderCollection methode. Gibt ein Aufzählungsobjekt zurück das verwendet werden kann um über alle Grenzen in der Sammlung zu iterieren.
type: docs
weight: 160
url: /de/net/aspose.words/bordercollection/getenumerator/
---
## BorderCollection.GetEnumerator method

Gibt ein Aufzählungsobjekt zurück, das verwendet werden kann, um über alle Grenzen in der Sammlung zu iterieren.

```csharp
public IEnumerator<Border> GetEnumerator()
```

### Beispiele

Zeigt, wie alle Rahmen in einem Absatzformatobjekt durchlaufen und bearbeitet werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Konfigurieren Sie die Absatzformateinstellungen des Builders, um auf allen Seiten einen grünen Wellenrahmen zu erstellen.
BorderCollection borders = builder.ParagraphFormat.Borders;

using (IEnumerator<Border> enumerator = borders.GetEnumerator())
{
    while (enumerator.MoveNext())
    {
        Border border = enumerator.Current;
        border.Color = Color.Green;
        border.LineStyle = LineStyle.Wave;
        border.LineWidth = 3;
    }
}

// Einen Absatz einfügen. Unsere Randeinstellungen bestimmen das Aussehen des Randes.
builder.Writeln("Hello world!");

doc.Save(ArtifactsDir + "BorderCollection.GetBordersEnumerator.docx");
```

### Siehe auch

* class [Border](../../border/)
* class [BorderCollection](../)
* namensraum [Aspose.Words](../../bordercollection/)
* Montage [Aspose.Words](../../../)


