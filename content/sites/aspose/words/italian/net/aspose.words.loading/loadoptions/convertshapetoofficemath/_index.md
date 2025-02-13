---
title: LoadOptions.ConvertShapeToOfficeMath
second_title: Aspose.Words per .NET API Reference
description: LoadOptions proprietà. Ottiene o imposta se convertire forme con EquationXML in oggetti Office Math.
type: docs
weight: 40
url: /it/net/aspose.words.loading/loadoptions/convertshapetoofficemath/
---
## LoadOptions.ConvertShapeToOfficeMath property

Ottiene o imposta se convertire forme con EquationXML in oggetti Office Math.

```csharp
public bool ConvertShapeToOfficeMath { get; set; }
```

### Esempi

Mostra come convertire le forme EquationXML in oggetti Office Math.

```csharp
LoadOptions loadOptions = new LoadOptions();

// Usa questo flag per specificare se convertire le forme con gli attributi EquationXML
// agli oggetti Office Math e quindi caricare il documento.
loadOptions.ConvertShapeToOfficeMath = isConvertShapeToOfficeMath;

Document doc = new Document(MyDir + "Math shapes.docx", loadOptions);

if (isConvertShapeToOfficeMath)
{
    Assert.AreEqual(16, doc.GetChildNodes(NodeType.Shape, true).Count);
    Assert.AreEqual(34, doc.GetChildNodes(NodeType.OfficeMath, true).Count);
}
else
{
    Assert.AreEqual(24, doc.GetChildNodes(NodeType.Shape, true).Count);
    Assert.AreEqual(0, doc.GetChildNodes(NodeType.OfficeMath, true).Count);
}
```

### Guarda anche

* class [LoadOptions](../)
* spazio dei nomi [Aspose.Words.Loading](../../loadoptions/)
* assemblea [Aspose.Words](../../../)


