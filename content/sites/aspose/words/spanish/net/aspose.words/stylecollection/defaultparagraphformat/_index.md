---
title: StyleCollection.DefaultParagraphFormat
second_title: Referencia de API de Aspose.Words para .NET
description: StyleCollection propiedad. Obtiene el formato de párrafo predeterminado del documento.
type: docs
weight: 30
url: /es/net/aspose.words/stylecollection/defaultparagraphformat/
---
## StyleCollection.DefaultParagraphFormat property

Obtiene el formato de párrafo predeterminado del documento.

```csharp
public ParagraphFormat DefaultParagraphFormat { get; }
```

### Observaciones

Tenga en cuenta que los valores predeterminados para todo el documento se introdujeron en Microsoft Word 2007 y son totalmente compatibles con los formatos OOXML (Docx) solamente. Los formatos de documentos anteriores no son compatibles con el formato de párrafo predeterminado del documento.

### Ejemplos

Muestra cómo agregar un estilo a la colección de estilos de un documento.

```csharp
Document doc = new Document();
StyleCollection styles = doc.Styles;

// Establecer parámetros predeterminados para nuevos estilos que luego podemos agregar a esta colección.
styles.DefaultFont.Name = "Courier New";

// Si agregamos un estilo del "StyleType.Paragraph", la colección aplicará los valores de
// su propiedad "DefaultParagraphFormat" a la propiedad "ParagraphFormat" del estilo.
styles.DefaultParagraphFormat.FirstLineIndent = 15.0;

// Agregue un estilo y luego verifique que tenga la configuración predeterminada.
styles.Add(StyleType.Paragraph, "MyStyle");

Assert.AreEqual("Courier New", styles[4].Font.Name);
Assert.AreEqual(15.0, styles["MyStyle"].ParagraphFormat.FirstLineIndent);
```

### Ver también

* class [ParagraphFormat](../../paragraphformat/)
* class [StyleCollection](../)
* espacio de nombres [Aspose.Words](../../stylecollection/)
* asamblea [Aspose.Words](../../../)


