---
title: Class BorderCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.BorderCollection classe. Una raccolta di oggetti Border.
type: docs
weight: 80
url: /it/net/aspose.words/bordercollection/
---
## BorderCollection class

Una raccolta di oggetti Border.

```csharp
public sealed class BorderCollection : IEnumerable<Border>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Bottom](../../aspose.words/bordercollection/bottom/) { get; } | Ottiene il bordo inferiore. |
| [Color](../../aspose.words/bordercollection/color/) { get; set; } | Ottiene o imposta il colore del bordo. |
| [Count](../../aspose.words/bordercollection/count/) { get; } | Ottiene il numero di bordi nella raccolta. |
| [DistanceFromText](../../aspose.words/bordercollection/distancefromtext/) { get; set; } | Ottiene o imposta la distanza del bordo dal testo in punti. |
| [Horizontal](../../aspose.words/bordercollection/horizontal/) { get; } | Ottiene il bordo orizzontale utilizzato tra le celle o i paragrafi conformi. |
| [Item](../../aspose.words/bordercollection/item/) { get; } | Recupera un oggetto Border in base al tipo di bordo. (2 indexers) |
| [Left](../../aspose.words/bordercollection/left/) { get; } | Ottiene il bordo sinistro. |
| [LineStyle](../../aspose.words/bordercollection/linestyle/) { get; set; } | Ottiene o imposta lo stile del bordo. |
| [LineWidth](../../aspose.words/bordercollection/linewidth/) { get; set; } | Ottiene o imposta la larghezza del bordo in punti. |
| [Right](../../aspose.words/bordercollection/right/) { get; } | Ottiene il bordo giusto. |
| [Shadow](../../aspose.words/bordercollection/shadow/) { get; set; } | Ottiene o imposta un valore che indica se il bordo ha un'ombra. |
| [Top](../../aspose.words/bordercollection/top/) { get; } | Ottiene il bordo superiore. |
| [Vertical](../../aspose.words/bordercollection/vertical/) { get; } | Ottiene il bordo verticale utilizzato tra le celle. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [ClearFormatting](../../aspose.words/bordercollection/clearformatting/)() | Rimuove tutti i bordi di un oggetto. |
| [Equals](../../aspose.words/bordercollection/equals/#equals)(BorderCollection) | Confronta raccolte di bordi. |
| [GetEnumerator](../../aspose.words/bordercollection/getenumerator/)() | Restituisce un oggetto enumeratore che può essere utilizzato per eseguire iterazioni su tutti i bordi della raccolta. |

### Osservazioni

Elementi di documento diversi hanno bordi diversi. Ad esempio, ParagraphFormat ha bordi inferiore, sinistro, destro e superiore. È possibile specificare una formattazione diversa per ciascun bordo indipendentemente o enumerare tutti i bordi e applicare la stessa formattazione.

### Esempi

Mostra come inserire un paragrafo con un bordo superiore.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Border topBorder = builder.ParagraphFormat.Borders[BorderType.Top];
topBorder.Color = Color.Red;
topBorder.LineWidth = 4.0d;
topBorder.LineStyle = LineStyle.DashSmallGap;

builder.Writeln("Text with a red top border.");

doc.Save(ArtifactsDir + "Border.ParagraphTopBorder.docx");
```

### Guarda anche

* class [Border](../border/)
* spazio dei nomi [Aspose.Words](../../aspose.words/)
* assemblea [Aspose.Words](../../)


