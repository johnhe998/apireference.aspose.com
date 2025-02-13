---
title: OleFormat.GetRawData
second_title: Aspose.Words per .NET API Reference
description: OleFormat metodo. Ottiene i dati grezzi delloggetto OLE.
type: docs
weight: 150
url: /it/net/aspose.words.drawing/oleformat/getrawdata/
---
## OleFormat.GetRawData method

Ottiene i dati grezzi dell'oggetto OLE.

```csharp
public byte[] GetRawData()
```

### Esempi

Mostra come accedere ai dati non elaborati di un oggetto OLE incorporato.

```csharp
Document doc = new Document(MyDir + "OLE objects.docx");

foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
{
    OleFormat oleFormat = shape.OleFormat;
    if (oleFormat != null)
    {
        Console.WriteLine($"This is {(oleFormat.IsLink ? "a linked" : "an embedded")} object");
        byte[] oleRawData = oleFormat.GetRawData();

        Assert.AreEqual(24576, oleRawData.Length);
    }
}
```

### Guarda anche

* class [OleFormat](../)
* spazio dei nomi [Aspose.Words.Drawing](../../oleformat/)
* assemblea [Aspose.Words](../../../)


