---
title: Class FontInfoCollection
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Fonts.FontInfoCollection classe. Rappresenta una raccolta di caratteri utilizzati in un documento.
type: docs
weight: 2750
url: /it/net/aspose.words.fonts/fontinfocollection/
---
## FontInfoCollection class

Rappresenta una raccolta di caratteri utilizzati in un documento.

```csharp
public class FontInfoCollection : IEnumerable<FontInfo>
```

## Proprietà

| Nome | Descrizione |
| --- | --- |
| [Count](../../aspose.words.fonts/fontinfocollection/count/) { get; } | Ottiene il numero di elementi contenuti nella raccolta. |
| [EmbedSystemFonts](../../aspose.words.fonts/fontinfocollection/embedsystemfonts/) { get; set; } | Specifica se incorporare o meno i caratteri di sistema nel documento. Il valore predefinito per questa proprietà è **falso**. |
| [EmbedTrueTypeFonts](../../aspose.words.fonts/fontinfocollection/embedtruetypefonts/) { get; set; } | Specifica se incorporare o meno i caratteri TrueType in un documento quando viene salvato. Il valore predefinito per questa proprietà è **falso** . |
| [Item](../../aspose.words.fonts/fontinfocollection/item/) { get; } | Ottiene un font con il nome specificato. (2 indexers) |
| [SaveSubsetFonts](../../aspose.words.fonts/fontinfocollection/savesubsetfonts/) { get; set; } | Specifica se salvare o meno un sottoinsieme dei caratteri TrueType incorporati con il documento. Il valore predefinito per questa proprietà è **falso**. |

## Metodi

| Nome | Descrizione |
| --- | --- |
| [Contains](../../aspose.words.fonts/fontinfocollection/contains/)(string) | Determina se la raccolta contiene un font con il nome specificato. |
| [GetEnumerator](../../aspose.words.fonts/fontinfocollection/getenumerator/)() | Restituisce un oggetto enumeratore che può essere utilizzato per scorrere tutti gli elementi della raccolta. |

### Osservazioni

Gli articoli sono[`FontInfo`](../fontinfo/) oggetti.

Non crei direttamente istanze di questa classe. Usa il[`FontInfos`](../../aspose.words/documentbase/fontinfos/) per accedere alla raccolta di font definiti nel documento.

### Esempi

Mostra come stampare i dettagli di quali font sono presenti in un documento.

```csharp
Document doc = new Document(MyDir + "Embedded font.docx");

FontInfoCollection allFonts = doc.FontInfos;
// Stampa tutti i caratteri usati e non utilizzati nel documento.
for (int i = 0; i < allFonts.Count; i++)
{
    Console.WriteLine($"Font index #{i}");
    Console.WriteLine($"\tName: {allFonts[i].Name}");
    Console.WriteLine($"\tIs {(allFonts[i].IsTrueType ? "" : "not ")}a trueType font");
}
```

Mostra come salvare un documento con i caratteri TrueType incorporati.

```csharp
Document doc = new Document(MyDir + "Document.docx");

FontInfoCollection fontInfos = doc.FontInfos;
fontInfos.EmbedTrueTypeFonts = embedAllFonts;
fontInfos.EmbedSystemFonts = embedAllFonts;
fontInfos.SaveSubsetFonts = embedAllFonts;

doc.Save(ArtifactsDir + "Font.FontInfoCollection.docx");

if (embedAllFonts)
    Assert.That(25000, Is.LessThan(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
else
    Assert.That(15000, Is.AtLeast(new FileInfo(ArtifactsDir + "Font.FontInfoCollection.docx").Length));
```

### Guarda anche

* class [FontInfo](../fontinfo/)
* spazio dei nomi [Aspose.Words.Fonts](../../aspose.words.fonts/)
* assemblea [Aspose.Words](../../)


