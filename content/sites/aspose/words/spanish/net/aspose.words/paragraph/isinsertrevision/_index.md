---
title: Paragraph.IsInsertRevision
second_title: Referencia de API de Aspose.Words para .NET
description: Paragraph propiedad. Devuelve verdadero si este objeto se insertó en Microsoft Word mientras el seguimiento de cambios estaba habilitado.
type: docs
weight: 110
url: /es/net/aspose.words/paragraph/isinsertrevision/
---
## Paragraph.IsInsertRevision property

Devuelve verdadero si este objeto se insertó en Microsoft Word mientras el seguimiento de cambios estaba habilitado.

```csharp
public bool IsInsertRevision { get; }
```

### Ejemplos

Muestra cómo trabajar con párrafos de revisión.

```csharp
Document doc = new Document();
Body body = doc.FirstSection.Body;
Paragraph para = body.FirstParagraph;

para.AppendChild(new Run(doc, "Paragraph 1. "));
body.AppendParagraph("Paragraph 2. ");
body.AppendParagraph("Paragraph 3. ");

// Los párrafos anteriores no son revisiones.
// Los párrafos que agreguemos después de iniciar el seguimiento de revisiones se registrarán como revisiones de "Insertar".
doc.StartTrackRevisions("John Doe", DateTime.Now);

para = body.AppendParagraph("Paragraph 4. ");

Assert.True(para.IsInsertRevision);

// Los párrafos que eliminemos después de iniciar el seguimiento de revisiones se registrarán como revisiones "Eliminar".
ParagraphCollection paragraphs = body.Paragraphs;

Assert.AreEqual(4, paragraphs.Count);

para = paragraphs[2];
para.Remove();

// Dichos párrafos permanecerán hasta que aceptemos o rechacemos la revisión de eliminación.
// Aceptar la revisión eliminará el párrafo para siempre,
// y rechazar la revisión la dejará en el documento como si nunca la hubiéramos borrado.
Assert.AreEqual(4, paragraphs.Count);
Assert.True(para.IsDeleteRevision);

// Acepte la revisión y luego verifique que el párrafo haya desaparecido.
doc.AcceptAllRevisions();

Assert.AreEqual(3, paragraphs.Count);
Assert.That(para, Is.Empty);
Assert.AreEqual(
    "Paragraph 1. \r" +
    "Paragraph 2. \r" +
    "Paragraph 4.", doc.GetText().Trim());
```

### Ver también

* class [Paragraph](../)
* espacio de nombres [Aspose.Words](../../paragraph/)
* asamblea [Aspose.Words](../../../)


