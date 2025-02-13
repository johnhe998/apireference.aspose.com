---
title: Document.JoinRunsWithSameFormatting
second_title: Referencia de API de Aspose.Words para .NET
description: Document método. Une tiradas con el mismo formato en todos los párrafos del documento.
type: docs
weight: 600
url: /es/net/aspose.words/document/joinrunswithsameformatting/
---
## Document.JoinRunsWithSameFormatting method

Une tiradas con el mismo formato en todos los párrafos del documento.

```csharp
public int JoinRunsWithSameFormatting()
```

### Valor_devuelto

Número de uniones realizadas. Cuando **norte** se están uniendo tramos adyacentes, cuentan como **n-1** Uniones.

### Observaciones

Este es un método de optimización. Algunos documentos contienen tiradas adyacentes con el mismo formato. Por lo general, esto ocurre si un documento se editó manualmente de forma intensiva. Puede reducir el tamaño del documento y acelerar el procesamiento adicional uniendo estas tiradas.

La operación comprueba cada[`Paragraph`](../../paragraph/) nodo en el documento para adyacente[`Run`](../../run/) nodos con propiedades idénticas. Ignora los identificadores únicos utilizados para realizar un seguimiento de las sesiones de edición de la creación y modificación de run . La primera ejecución en cada secuencia de unión acumula todo el texto. Las ejecuciones restantes se eliminan del documento.

### Ejemplos

Muestra cómo unir tiradas en un documento para reducir tiradas innecesarias.

```csharp
// Abre un documento que contiene tiradas de texto adyacentes con formato idéntico,
// lo que comúnmente ocurre si editamos el mismo párrafo varias veces en Microsoft Word.
Document doc = new Document(MyDir + "Rendering.docx");

// Si alguna cantidad de estas ejecuciones son adyacentes con formato idéntico,
// entonces el documento puede simplificarse.
Assert.AreEqual(317, doc.GetChildNodes(NodeType.Run, true).Count);

// Combine dichas ejecuciones con este método y verifique el número de uniones de ejecución que se llevarán a cabo.
Assert.AreEqual(121, doc.JoinRunsWithSameFormatting());

// El número de uniones y el número de carreras que tenemos después de la unión
// debería sumar el número de ejecuciones que tuvimos inicialmente.
Assert.AreEqual(196, doc.GetChildNodes(NodeType.Run, true).Count);
```

### Ver también

* class [Document](../)
* espacio de nombres [Aspose.Words](../../document/)
* asamblea [Aspose.Words](../../../)


