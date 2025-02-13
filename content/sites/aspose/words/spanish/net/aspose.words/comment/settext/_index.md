---
title: Comment.SetText
second_title: Referencia de API de Aspose.Words para .NET
description: Comment método. Este es un método conveniente que permite configurar fácilmente el texto del comentario.
type: docs
weight: 150
url: /es/net/aspose.words/comment/settext/
---
## Comment.SetText method

Este es un método conveniente que permite configurar fácilmente el texto del comentario.

```csharp
public void SetText(string text)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| text | String | El nuevo texto del comentario. |

### Observaciones

Este método permite establecer rápidamente el texto de un comentario de una cadena. La cadena puede contener saltos de párrafo, esto creará párrafos de texto en el comentario en consecuencia. Si desea insertar elementos más complejos en el comentario, por ejemplo marcadores o tablas, o aplicar un formato enriquecido, debe usar las clases de nodo adecuadas para construir el texto del comentario.

### Ejemplos

Muestra cómo agregar un comentario a un documento y luego responderlo.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Comment comment = new Comment(doc, "John Doe", "J.D.", DateTime.Now);
comment.SetText("My comment.");

// Coloque el comentario en un nodo en el cuerpo del documento.
// Este comentario se mostrará en la ubicación de su párrafo,
// fuera del margen derecho de la página y con una línea punteada que lo conecta con su párrafo.
builder.CurrentParagraph.AppendChild(comment);

// Agregue una respuesta, que aparecerá debajo de su comentario principal.
comment.AddReply("Joe Bloggs", "J.B.", DateTime.Now, "New reply");

// Los comentarios y las respuestas son ambos nodos de comentarios.
Assert.AreEqual(2, doc.GetChildNodes(NodeType.Comment, true).Count);

// Los comentarios que no responden a otros comentarios son de "nivel superior". No tienen comentarios de antepasados.
Assert.Null(comment.Ancestor);

// Las respuestas tienen un comentario de nivel superior antepasado.
Assert.AreEqual(comment, comment.Replies[0].Ancestor);

doc.Save(ArtifactsDir + "Comment.AddCommentWithReply.docx");
```

### Ver también

* class [Comment](../)
* espacio de nombres [Aspose.Words](../../comment/)
* asamblea [Aspose.Words](../../../)


