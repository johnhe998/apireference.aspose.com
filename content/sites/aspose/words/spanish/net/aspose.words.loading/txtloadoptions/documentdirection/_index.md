---
title: TxtLoadOptions.DocumentDirection
second_title: Referencia de API de Aspose.Words para .NET
description: TxtLoadOptions propiedad. Obtiene o establece la dirección de un documento. El valor predeterminado esLeftToRight .
type: docs
weight: 30
url: /es/net/aspose.words.loading/txtloadoptions/documentdirection/
---
## TxtLoadOptions.DocumentDirection property

Obtiene o establece la dirección de un documento. El valor predeterminado esLeftToRight .

```csharp
public DocumentDirection DocumentDirection { get; set; }
```

### Ejemplos

Muestra cómo detectar la dirección del texto del documento de texto sin formato.

```csharp
// Crear un objeto "TxtLoadOptions", que podemos pasar al constructor de un documento
// para modificar cómo cargamos un documento de texto sin formato.
TxtLoadOptions loadOptions = new TxtLoadOptions();

// Establecer la propiedad "DocumentDirection" en "DocumentDirection.Auto" detecta automáticamente
// la dirección de cada párrafo de texto que Aspose.Words carga desde texto sin formato.
// La propiedad "Bidi" de cada párrafo almacenará su dirección.
loadOptions.DocumentDirection = DocumentDirection.Auto;

// Detectar texto hebreo como de derecha a izquierda.
Document doc = new Document(MyDir + "Hebrew text.txt", loadOptions);

Assert.True(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);

// Detectar texto en inglés como de derecha a izquierda.
doc = new Document(MyDir + "English text.txt", loadOptions);

Assert.False(doc.FirstSection.Body.FirstParagraph.ParagraphFormat.Bidi);
```

### Ver también

* enum [DocumentDirection](../../documentdirection/)
* class [TxtLoadOptions](../)
* espacio de nombres [Aspose.Words.Loading](../../txtloadoptions/)
* asamblea [Aspose.Words](../../../)


