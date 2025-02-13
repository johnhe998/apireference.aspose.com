---
title: Class LayoutEnumerator
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Layout.LayoutEnumerator clase. Enumera entidades de diseño de página de un documento. Puede utilizar esta clase para recorrer el modelo de diseño de página. Las propiedades disponibles son el tipo la geometría el texto y el índice de página donde se representa la entidad  así como la estructura general y las relaciones. Usar una combinación deGetEntity yCurrent mover a la entidad que corresponde a un documento node.
type: docs
weight: 3140
url: /es/net/aspose.words.layout/layoutenumerator/
---
## LayoutEnumerator class

Enumera entidades de diseño de página de un documento. Puede utilizar esta clase para recorrer el modelo de diseño de página. Las propiedades disponibles son el tipo, la geometría, el texto y el índice de página donde se representa la entidad, , así como la estructura general y las relaciones. Usar una combinación de[`GetEntity`](../layoutcollector/getentity/) y[`Current`](./current/) mover a la entidad que corresponde a un documento node.

```csharp
public class LayoutEnumerator
```

## Constructores

| Nombre | Descripción |
| --- | --- |
| [LayoutEnumerator](layoutenumerator/)(Document) | Inicializa una nueva instancia de esta clase. |

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [Current](../../aspose.words.layout/layoutenumerator/current/) { get; set; } | Obtiene o establece la posición actual en el modelo de diseño de página. Esta propiedad devuelve un objeto opaco que corresponde a la entidad de diseño actual. |
| [Document](../../aspose.words.layout/layoutenumerator/document/) { get; } | Obtiene el documento que enumera esta instancia. |
| [Kind](../../aspose.words.layout/layoutenumerator/kind/) { get; } | Obtiene el tipo de la entidad actual. Esta puede ser una cadena vacía pero nunca nula. |
| [PageIndex](../../aspose.words.layout/layoutenumerator/pageindex/) { get; } | Obtiene el índice basado en 1 de una página que contiene la entidad actual. |
| [Rectangle](../../aspose.words.layout/layoutenumerator/rectangle/) { get; } | Devuelve el rectángulo delimitador de la entidad actual en relación con la esquina superior izquierda de la página (en puntos). |
| [Text](../../aspose.words.layout/layoutenumerator/text/) { get; } | Obtiene el texto de la entidad de intervalo actual. Lanzamientos para otros tipos de entidades. |
| [Type](../../aspose.words.layout/layoutenumerator/type/) { get; } | Obtiene el tipo de la entidad actual. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [MoveFirstChild](../../aspose.words.layout/layoutenumerator/movefirstchild/)() | Se mueve a la primera entidad secundaria. |
| [MoveLastChild](../../aspose.words.layout/layoutenumerator/movelastchild/)() | Se mueve a la última entidad secundaria. |
| [MoveNext](../../aspose.words.layout/layoutenumerator/movenext/)() | Se mueve a la siguiente entidad hermana en orden visual. Al iterar líneas de un párrafo dividido en páginas, este método no se moverá a la página siguiente sino a la siguiente entidad en la misma página. |
| [MoveNextLogical](../../aspose.words.layout/layoutenumerator/movenextlogical/)() | Se mueve a la siguiente entidad hermana en un orden lógico. Al iterar líneas de un párrafo dividido en páginas, este método se moverá a la siguiente línea incluso si reside en otra página. |
| [MoveParent](../../aspose.words.layout/layoutenumerator/moveparent/#moveparent)() | Se mueve a la entidad padre. |
| [MoveParent](../../aspose.words.layout/layoutenumerator/moveparent/#moveparent_1)(LayoutEntityType) | Se mueve a la entidad principal del tipo especificado. |
| [MovePrevious](../../aspose.words.layout/layoutenumerator/moveprevious/)() | Se mueve a la entidad hermana anterior. |
| [MovePreviousLogical](../../aspose.words.layout/layoutenumerator/movepreviouslogical/)() | Se mueve a la entidad hermana anterior en un orden lógico. Al iterar líneas de un párrafo dividido en páginas, este método se moverá a la línea anterior incluso si reside en otra página. |
| [Reset](../../aspose.words.layout/layoutenumerator/reset/)() | Mueve el enumerador a la primera página del documento. |

### Ejemplos

Muestra formas de atravesar las entidades de diseño de un documento.

```csharp
public void LayoutEnumerator()
{
    // Abra un documento que contenga una variedad de entidades de diseño.
    // Las entidades de diseño son páginas, celdas, filas, líneas y otros objetos incluidos en la enumeración LayoutEntityType.
    // Cada entidad de diseño tiene un espacio rectangular que ocupa en el cuerpo del documento.
    Document doc = new Document(MyDir + "Layout entities.docx");

    // Cree un enumerador que pueda atravesar estas entidades como un árbol.
    LayoutEnumerator layoutEnumerator = new LayoutEnumerator(doc);

    Assert.AreEqual(doc, layoutEnumerator.Document);

    layoutEnumerator.MoveParent(LayoutEntityType.Page);

    Assert.AreEqual(LayoutEntityType.Page, layoutEnumerator.Type);
    Assert.Throws<InvalidOperationException>(() => Console.WriteLine(layoutEnumerator.Text));

    // Podemos llamar a este método para asegurarnos de que el enumerador estará en la primera entidad de diseño.
    layoutEnumerator.Reset();

    // Hay dos órdenes que determinan cómo el enumerador de diseño continúa atravesando las entidades de diseño
    // cuando encuentra entidades que abarcan varias páginas.
    // 1 - En orden visual:
    // Al moverse a través de los elementos secundarios de una entidad que abarcan varias páginas,
    // el diseño de la página tiene prioridad, y pasamos a otros elementos secundarios en esta página y evitamos los de la siguiente.
    Console.WriteLine("Traversing from first to last, elements between pages separated:");
    TraverseLayoutForward(layoutEnumerator, 1);

    // Nuestro enumerador ahora está al final de la colección. Podemos recorrer las entidades de diseño hacia atrás para volver al principio.
    Console.WriteLine("Traversing from last to first, elements between pages separated:");
    TraverseLayoutBackward(layoutEnumerator, 1);

    // 2 - En orden lógico:
    // Al moverse a través de los elementos secundarios de una entidad que abarcan varias páginas,
    // el enumerador se moverá entre las páginas para recorrer todas las entidades secundarias.
    Console.WriteLine("Traversing from first to last, elements between pages mixed:");
    TraverseLayoutForwardLogical(layoutEnumerator, 1);

    Console.WriteLine("Traversing from last to first, elements between pages mixed:");
    TraverseLayoutBackwardLogical(layoutEnumerator, 1);
}

/// <summary>
/// Enumerar a través de la colección de entidades de diseño de layoutEnumerator de adelante hacia atrás,
/// primero en profundidad y en el orden "Visual".
/// </summary>
private static void TraverseLayoutForward(LayoutEnumerator layoutEnumerator, int depth)
{
    do
    {
        PrintCurrentEntity(layoutEnumerator, depth);

        if (layoutEnumerator.MoveFirstChild())
        {
            TraverseLayoutForward(layoutEnumerator, depth + 1);
            layoutEnumerator.MoveParent();
        }
    } while (layoutEnumerator.MoveNext());
}

/// <summary>
/// Enumerar a través de la colección de entidades de diseño de layoutEnumerator de atrás hacia adelante,
/// primero en profundidad y en el orden "Visual".
/// </summary>
private static void TraverseLayoutBackward(LayoutEnumerator layoutEnumerator, int depth)
{
    do
    {
        PrintCurrentEntity(layoutEnumerator, depth);

        if (layoutEnumerator.MoveLastChild())
        {
            TraverseLayoutBackward(layoutEnumerator, depth + 1);
            layoutEnumerator.MoveParent();
        }
    } while (layoutEnumerator.MovePrevious());
}

/// <summary>
/// Enumerar a través de la colección de entidades de diseño de layoutEnumerator de adelante hacia atrás,
/// primero en profundidad y en el orden "Lógico".
/// </summary>
private static void TraverseLayoutForwardLogical(LayoutEnumerator layoutEnumerator, int depth)
{
    do
    {
        PrintCurrentEntity(layoutEnumerator, depth);

        if (layoutEnumerator.MoveFirstChild())
        {
            TraverseLayoutForwardLogical(layoutEnumerator, depth + 1);
            layoutEnumerator.MoveParent();
        }
    } while (layoutEnumerator.MoveNextLogical());
}

/// <summary>
/// Enumerar a través de la colección de entidades de diseño de layoutEnumerator de atrás hacia adelante,
/// primero en profundidad y en el orden "Lógico".
/// </summary>
private static void TraverseLayoutBackwardLogical(LayoutEnumerator layoutEnumerator, int depth)
{
    do
    {
        PrintCurrentEntity(layoutEnumerator, depth);

        if (layoutEnumerator.MoveLastChild())
        {
            TraverseLayoutBackwardLogical(layoutEnumerator, depth + 1);
            layoutEnumerator.MoveParent();
        }
    } while (layoutEnumerator.MovePreviousLogical());
}

/// <summary>
/// Imprimir información sobre la entidad actual de layoutEnumerator en la consola, mientras se sangra el texto con caracteres de tabulación
/// según su profundidad relativa al nodo raíz que proporcionamos en la instancia del constructor LayoutEnumerator.
/// El rectángulo que procesamos al final representa el área y la ubicación que ocupa la entidad en el documento.
/// </summary>
private static void PrintCurrentEntity(LayoutEnumerator layoutEnumerator, int indent)
{
    string tabs = new string('\t', indent);

    Console.WriteLine(layoutEnumerator.Kind == string.Empty
        ? $"{tabs}-> Entity type: {layoutEnumerator.Type}"
        : $"{tabs}-> Entity type & kind: {layoutEnumerator.Type}, {layoutEnumerator.Kind}");

    // Solo los intervalos pueden contener texto.
    if (layoutEnumerator.Type == LayoutEntityType.Span)
        Console.WriteLine($"{tabs}   Span contents: \"{layoutEnumerator.Text}\"");

    RectangleF leRect = layoutEnumerator.Rectangle;
    Console.WriteLine($"{tabs}   Rectangle dimensions {leRect.Width}x{leRect.Height}, X={leRect.X} Y={leRect.Y}");
    Console.WriteLine($"{tabs}   Page {layoutEnumerator.PageIndex}");
}
```

### Ver también

* espacio de nombres [Aspose.Words.Layout](../../aspose.words.layout/)
* asamblea [Aspose.Words](../../)


