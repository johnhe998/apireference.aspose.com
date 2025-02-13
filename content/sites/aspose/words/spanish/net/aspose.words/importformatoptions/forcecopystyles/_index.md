---
title: ImportFormatOptions.ForceCopyStyles
second_title: Referencia de API de Aspose.Words para .NET
description: ImportFormatOptions propiedad. Obtiene o establece un valor booleano que indica copiar estilos conflictivos enKeepSourceFormatting mode. El valor predeterminado esfalso .
type: docs
weight: 20
url: /es/net/aspose.words/importformatoptions/forcecopystyles/
---
## ImportFormatOptions.ForceCopyStyles property

Obtiene o establece un valor booleano que indica copiar estilos conflictivos enKeepSourceFormatting mode. El valor predeterminado es`falso` .

```csharp
public bool ForceCopyStyles { get; set; }
```

### Observaciones

De forma predeterminada, si ya existe un estilo coincidente en un documento de destino, el formato de estilo de origen se expande en atributos de nodo directo y el estilo de este nodo se restablece a su valor predeterminado.

Cuando esta opción se establece en`verdadero`, el estilo de origen se copiará a la fuerza en el documento de destino con un nombre único y se aplicará al nodo importado.

Tenga en cuenta que, en este caso, no se garantiza que se conserve el formato del nodo importado en el documento de destino .

### Ejemplos

Muestra cómo copiar estilos de origen con nombres únicos a la fuerza.

```csharp
// Ambos documentos contienen MyStyle1 y MyStyle2, MyStyle3 solo existe en un documento de origen.
Document srcDoc = new Document(MyDir + "Styles source.docx");
Document dstDoc = new Document(MyDir + "Styles destination.docx");

ImportFormatOptions options = new ImportFormatOptions { ForceCopyStyles = true };
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);

ParagraphCollection paras = dstDoc.Sections[1].Body.Paragraphs;

Assert.AreEqual(paras[0].ParagraphFormat.Style.Name, "MyStyle1_0");
Assert.AreEqual(paras[1].ParagraphFormat.Style.Name, "MyStyle2_0");
Assert.AreEqual(paras[2].ParagraphFormat.Style.Name, "MyStyle3");
```

### Ver también

* class [ImportFormatOptions](../)
* espacio de nombres [Aspose.Words](../../importformatoptions/)
* asamblea [Aspose.Words](../../../)


