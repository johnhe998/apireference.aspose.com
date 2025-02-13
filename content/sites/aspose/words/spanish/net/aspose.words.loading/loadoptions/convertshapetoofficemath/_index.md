---
title: LoadOptions.ConvertShapeToOfficeMath
second_title: Referencia de API de Aspose.Words para .NET
description: LoadOptions propiedad. Obtiene o establece si convertir formas con EquationXML en objetos de Office Math.
type: docs
weight: 40
url: /es/net/aspose.words.loading/loadoptions/convertshapetoofficemath/
---
## LoadOptions.ConvertShapeToOfficeMath property

Obtiene o establece si convertir formas con EquationXML en objetos de Office Math.

```csharp
public bool ConvertShapeToOfficeMath { get; set; }
```

### Ejemplos

Muestra cómo convertir formas EquationXML en objetos de Office Math.

```csharp
LoadOptions loadOptions = new LoadOptions();

// Use este indicador para especificar si desea convertir las formas con atributos EquationXML
// a los objetos de Office Math y luego cargue el documento.
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

### Ver también

* class [LoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../loadoptions/)
* asamblea [Aspose.Words](../../../)


