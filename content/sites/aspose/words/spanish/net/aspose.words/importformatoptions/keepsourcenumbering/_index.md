---
title: ImportFormatOptions.KeepSourceNumbering
second_title: Referencia de API de Aspose.Words para .NET
description: ImportFormatOptions propiedad. Obtiene o establece un valor booleano que especifica cómo se importará la numeración cuando entre en conflicto en los documentos de origen y de destino. El valor predeterminado esfalso .
type: docs
weight: 50
url: /es/net/aspose.words/importformatoptions/keepsourcenumbering/
---
## ImportFormatOptions.KeepSourceNumbering property

Obtiene o establece un valor booleano que especifica cómo se importará la numeración cuando entre en conflicto en los documentos de origen y de destino. El valor predeterminado es`falso` .

```csharp
public bool KeepSourceNumbering { get; set; }
```

### Ejemplos

Muestra cómo resolver un conflicto al importar documentos que tienen listas con el mismo identificador de definición de lista.

```csharp
Document srcDoc = new Document(MyDir + "List with the same definition identifier - source.docx");
Document dstDoc = new Document(MyDir + "List with the same definition identifier - destination.docx");

// Establecer la propiedad "KeepSourceNumbering" en "true" para aplicar un ID de definición de lista diferente
// a estilos idénticos a los de Aspose.Words los importa a los documentos de destino.
ImportFormatOptions importFormatOptions = new ImportFormatOptions { KeepSourceNumbering = true };

dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles, importFormatOptions);
dstDoc.UpdateListLabels();
```

Muestra cómo importar un documento con listas numeradas.

```csharp
Document srcDoc = new Document(MyDir + "List source.docx");
Document dstDoc = new Document(MyDir + "List destination.docx");

Assert.AreEqual(4, dstDoc.Lists.Count);

ImportFormatOptions options = new ImportFormatOptions();

// Si hay un conflicto de estilos de lista, aplique el formato de lista del documento de origen.
// Establezca la propiedad "KeepSourceNumbering" en "false" para no importar ningún número de lista en el documento de destino.
// Establecer la propiedad "KeepSourceNumbering" en "true" importar todos los conflictos
// Numeración de estilo de lista con la misma apariencia que tenía en el documento fuente.
options.KeepSourceNumbering = isKeepSourceNumbering;

dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);
dstDoc.UpdateListLabels();

Assert.AreEqual(isKeepSourceNumbering ? 5 : 4, dstDoc.Lists.Count);
```

Muestra cómo resolver conflictos de numeración de listas en documentos de origen y destino.

```csharp
// Abra un documento con un esquema de numeración de lista personalizado y luego clónelo.
// Dado que ambos tienen el mismo formato de numeración, los formatos chocarán si importamos un documento en el otro.
Document srcDoc = new Document(MyDir + "Custom list numbering.docx");
Document dstDoc = srcDoc.Clone();

// Cuando importamos el clon del documento al original y luego lo agregamos,
// luego se unirán las dos listas con el mismo formato de lista.
// Si establecemos el indicador "KeepSourceNumbering" en "falso", entonces la lista del documento se clona
// que agregamos al original continuará con la numeración de la lista a la que lo agregamos.
// Esto fusionará efectivamente las dos listas en una sola.
// Si establecemos el indicador "KeepSourceNumbering" en "true", entonces el documento se clona
// la lista conservará su numeración original, haciendo que las dos listas aparezcan como listas separadas. 
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.KeepSourceNumbering = keepSourceNumbering;

NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KeepDifferentStyles, importFormatOptions);
foreach (Paragraph paragraph in srcDoc.FirstSection.Body.Paragraphs)
{
    Node importedNode = importer.ImportNode(paragraph, true);
    dstDoc.FirstSection.Body.AppendChild(importedNode);
}

dstDoc.UpdateListLabels();

if (keepSourceNumbering)
{
    Assert.AreEqual(
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4\r\n" +
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4", dstDoc.FirstSection.Body.ToString(SaveFormat.Text).Trim());
}
else
{
    Assert.AreEqual(
        "6. Item 1\r\n" +
        "7. Item 2 \r\n" +
        "8. Item 3\r\n" +
        "9. Item 4\r\n" +
        "10. Item 1\r\n" +
        "11. Item 2 \r\n" +
        "12. Item 3\r\n" +
        "13. Item 4", dstDoc.FirstSection.Body.ToString(SaveFormat.Text).Trim());
}
```

### Ver también

* class [ImportFormatOptions](../)
* espacio de nombres [Aspose.Words](../../importformatoptions/)
* asamblea [Aspose.Words](../../../)


