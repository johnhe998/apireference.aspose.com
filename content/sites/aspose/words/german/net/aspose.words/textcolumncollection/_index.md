---
title: Class TextColumnCollection
second_title: Aspose.Words für .NET-API-Referenz
description: Aspose.Words.TextColumnCollection klas. Eine Sammlung vonTextColumn Objekte die alle Textspalten in einem Abschnitt eines Dokuments darstellen.
type: docs
weight: 6100
url: /de/net/aspose.words/textcolumncollection/
---
## TextColumnCollection class

Eine Sammlung von[`TextColumn`](../textcolumn/) Objekte, die alle Textspalten in einem Abschnitt eines Dokuments darstellen.

```csharp
public class TextColumnCollection
```

## Eigenschaften

| Name | Beschreibung |
| --- | --- |
| [Count](../../aspose.words/textcolumncollection/count/) { get; } | Ruft die Anzahl der Spalten im Abschnitt eines Dokuments ab. |
| [EvenlySpaced](../../aspose.words/textcolumncollection/evenlyspaced/) { get; set; } | **WAHR** wenn Textspalten gleich breit und gleichmäßig verteilt sind. |
| [Item](../../aspose.words/textcolumncollection/item/) { get; } | Gibt eine Textspalte am angegebenen Index zurück. |
| [LineBetween](../../aspose.words/textcolumncollection/linebetween/) { get; set; } | Wann **Stimmt** , fügt eine vertikale Linie zwischen Spalten hinzu. |
| [Spacing](../../aspose.words/textcolumncollection/spacing/) { get; set; } | Ruft bei gleichmäßigen Spaltenabständen den Abstand zwischen den einzelnen Spalten in Punkten ab oder legt ihn fest. |
| [Width](../../aspose.words/textcolumncollection/width/) { get; } | Wenn die Spalten gleichmäßig verteilt sind, wird die Breite der Spalten abgerufen. |

## Methoden

| Name | Beschreibung |
| --- | --- |
| [SetCount](../../aspose.words/textcolumncollection/setcount/)(int) | Ordnet Text in der angegebenen Anzahl von Textspalten an. |

### Bemerkungen

Verwenden[`SetCount`](./setcount/) um die Anzahl der Textspalten einzustellen.

Um alle Spalten gleich breit und gleichmäßig verteilt zu machen, legen Sie fest[`EvenlySpaced`](./evenlyspaced/) zu **Stimmt** und geben Sie den Abstand zwischen den Spalten an in[`Spacing`](./spacing/). MS Word wird Spaltenbreiten automatisch berechnen.

Wenn Sie haben **Gleichmäßig verteilt** einstellen **FALSCH** müssen Sie die Breite und den Abstand für jede -Spalte einzeln angeben. Verwenden Sie den Indexer, um auf einzelne Personen zuzugreifen[`TextColumn`](../textcolumn/) Objekte.

Wenn Sie benutzerdefinierte Spaltenbreiten verwenden, stellen Sie sicher, dass die Summe aller Spaltenbreiten und Abstände zwischen ihnen gleich der Seitenbreite abzüglich linker und rechter Seitenränder ist.

### Beispiele

Zeigt, wie mehrere gleichmäßig verteilte Spalten in einem Abschnitt erstellt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

TextColumnCollection columns = builder.PageSetup.TextColumns;
columns.Spacing = 100;
columns.SetCount(2);

builder.Writeln("Column 1.");
builder.InsertBreak(BreakType.ColumnBreak);
builder.Writeln("Column 2.");

doc.Save(ArtifactsDir + "PageSetup.ColumnsSameWidth.docx");
```

### Siehe auch

* namensraum [Aspose.Words](../../aspose.words/)
* Montage [Aspose.Words](../../)


