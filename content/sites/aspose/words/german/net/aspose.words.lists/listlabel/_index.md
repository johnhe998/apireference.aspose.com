---
title: Class ListLabel
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.Lists.ListLabel klas. Definiert Eigenschaften die für eine Listenbezeichnung spezifisch sind.
type: docs
weight: 3290
url: /de/net/aspose.words.lists/listlabel/
---
## ListLabel class

Definiert Eigenschaften, die für eine Listenbezeichnung spezifisch sind.

```csharp
public class ListLabel
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Font](../../aspose.words.lists/listlabel/font/) { get; } | Ruft die Schriftart der Listenbeschriftung ab. |
| [LabelString](../../aspose.words.lists/listlabel/labelstring/) { get; } | Ruft eine Zeichenfolgendarstellung der Listenbezeichnung ab. |
| [LabelValue](../../aspose.words.lists/listlabel/labelvalue/) { get; } | Ruft einen numerischen Wert für dieses Label ab. |

### Beispiele

Zeigt, wie die Listenbeschriftungen aller Absätze extrahiert werden, die Listenelemente sind.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");
doc.UpdateListLabels();

NodeCollection paras = doc.GetChildNodes(NodeType.Paragraph, true);

// Finden Sie heraus, ob wir die Absatzliste haben. In unserem Dokument verwendet unsere Liste einfache arabische Zahlen,
// die um drei beginnen und um sechs enden.
foreach (Paragraph paragraph in paras.OfType<Paragraph>().Where(p => p.ListFormat.IsListItem))
{
    Console.WriteLine($"List item paragraph #{paras.IndexOf(paragraph)}");

    // Dies ist der Text, den wir erhalten, wenn wir diesen Knoten im Textformat ausgeben.
    // Diese Textausgabe lässt Listenlabels weg. Trimmen Sie alle Absatzformatierungszeichen. 
    string paragraphText = paragraph.ToString(SaveFormat.Text).Trim();
    Console.WriteLine($"\tExported Text: {paragraphText}");

    ListLabel label = paragraph.ListLabel;

    // Dadurch wird die Position des Absatzes in der aktuellen Ebene der Liste abgerufen. Wenn wir eine Liste mit mehreren Ebenen haben,
    // dies wird uns sagen, welche Position es auf dieser Ebene ist.
    Console.WriteLine($"\tNumerical Id: {label.LabelValue}");

    // Kombinieren Sie sie, um das Listenlabel mit dem Text in die Ausgabe aufzunehmen.
    Console.WriteLine($"\tList label combined with text: {label.LabelString} {paragraphText}");
}
```

### Siehe auch

* namensraum [Aspose.Words.Lists](../../aspose.words.lists/)
* Montage [Aspose.Words](../../)


