---
title: FontInfo.Panose
second_title: Aspose.Words per .NET API Reference
description: FontInfo proprietà. Ottiene o imposta il numero di classificazione del carattere tipografico PANOSE.
type: docs
weight: 60
url: /it/net/aspose.words.fonts/fontinfo/panose/
---
## FontInfo.Panose property

Ottiene o imposta il numero di classificazione del carattere tipografico PANOSE.

```csharp
public byte[] Panose { get; set; }
```

### Osservazioni

PANOSE è una descrizione compatta di 10 byte di caratteristiche visive critiche dei caratteri, come contrasto, peso e stile serif. Le cifre rappresentano Tipo famiglia, Stile Serif, Peso , Proporzione, Contrasto, Variazione tratto, Stile braccio, Forma lettera, Linea mediana e Altezza X.

Può essere`nullo`.

### Esempi

Mostra come accedere e stampare i dettagli di ogni font in un documento.

```csharp
Document doc = new Document(MyDir + "Document.docx");

IEnumerator<FontInfo> fontCollectionEnumerator = doc.FontInfos.GetEnumerator();
while (fontCollectionEnumerator.MoveNext())
{
    FontInfo fontInfo = fontCollectionEnumerator.Current;
    if (fontInfo != null)
    {
        Console.WriteLine("Font name: " + fontInfo.Name);

        // I nomi alternativi di solito sono vuoti.
        Console.WriteLine("Alt name: " + fontInfo.AltName);
        Console.WriteLine("\t- Family: " + fontInfo.Family);
        Console.WriteLine("\t- " + (fontInfo.IsTrueType ? "Is TrueType" : "Is not TrueType"));
        Console.WriteLine("\t- Pitch: " + fontInfo.Pitch);
        Console.WriteLine("\t- Charset: " + fontInfo.Charset);
        Console.WriteLine("\t- Panose:");
        Console.WriteLine("\t\tFamily Kind: " + fontInfo.Panose[0]);
        Console.WriteLine("\t\tSerif Style: " + fontInfo.Panose[1]);
        Console.WriteLine("\t\tWeight: " + fontInfo.Panose[2]);
        Console.WriteLine("\t\tProportion: " + fontInfo.Panose[3]);
        Console.WriteLine("\t\tContrast: " + fontInfo.Panose[4]);
        Console.WriteLine("\t\tStroke Variation: " + fontInfo.Panose[5]);
        Console.WriteLine("\t\tArm Style: " + fontInfo.Panose[6]);
        Console.WriteLine("\t\tLetterform: " + fontInfo.Panose[7]);
        Console.WriteLine("\t\tMidline: " + fontInfo.Panose[8]);
        Console.WriteLine("\t\tX-Height: " + fontInfo.Panose[9]);
    }
}
```

### Guarda anche

* class [FontInfo](../)
* spazio dei nomi [Aspose.Words.Fonts](../../fontinfo/)
* assemblea [Aspose.Words](../../../)


