---
title: Class Bookmark
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Bookmark clase. Representa un solo marcador.
type: docs
weight: 30
url: /es/net/aspose.words/bookmark/
---
## Bookmark class

Representa un solo marcador.

```csharp
public class Bookmark
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [BookmarkEnd](../../aspose.words/bookmark/bookmarkend/) { get; } | Obtiene el nodo que representa el final del marcador. |
| [BookmarkStart](../../aspose.words/bookmark/bookmarkstart/) { get; } | Obtiene el nodo que representa el inicio del marcador. |
| [FirstColumn](../../aspose.words/bookmark/firstcolumn/) { get; } | Obtiene el índice de base cero de la primera columna del rango de columnas de la tabla asociado con el marcador. |
| [IsColumn](../../aspose.words/bookmark/iscolumn/) { get; } | Devoluciones **verdadero** si este marcador es un marcador de columna de tabla. |
| [LastColumn](../../aspose.words/bookmark/lastcolumn/) { get; } | Obtiene el índice de base cero de la última columna del rango de columnas de la tabla asociado con el marcador. |
| [Name](../../aspose.words/bookmark/name/) { get; set; } | Obtiene o establece el nombre del marcador. |
| [Text](../../aspose.words/bookmark/text/) { get; set; } | Obtiene o establece el texto encerrado en el marcador. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| [Remove](../../aspose.words/bookmark/remove/)() | Elimina el marcador del documento. No elimina el texto dentro del marcador. |

### Observaciones

`Bookmark` es un objeto de "fachada" que encapsula dos nodos[`BookmarkStart`](./bookmarkstart/) y[`BookmarkEnd`](./bookmarkend/) en un árbol de documentos y permite trabajar con un marcador como un solo objeto.

### Ejemplos

Muestra cómo agregar marcadores y actualizar su contenido.

```csharp
public void CreateUpdateAndPrintBookmarks()
{
    // Cree un documento con tres marcadores, luego use una implementación de visitante de documentos personalizada para imprimir su contenido.
    Document doc = CreateDocumentWithBookmarks(3);
    BookmarkCollection bookmarks = doc.Range.Bookmarks;

    PrintAllBookmarkInfo(bookmarks);

    // Se puede acceder a los marcadores en la colección de marcadores por índice o nombre, y sus nombres se pueden actualizar.
    bookmarks[0].Name = $"{bookmarks[0].Name}_NewName";
    bookmarks["MyBookmark_2"].Text = $"Updated text contents of {bookmarks[1].Name}";

    // Imprime todos los marcadores de nuevo para ver los valores actualizados.
    PrintAllBookmarkInfo(bookmarks);
}

/// <summary>
/// Crea un documento con un número determinado de marcadores.
/// </summary>
private static Document CreateDocumentWithBookmarks(int numberOfBookmarks)
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    for (int i = 1; i <= numberOfBookmarks; i++)
    {
        string bookmarkName = "MyBookmark_" + i;

        builder.Write("Text before bookmark.");
        builder.StartBookmark(bookmarkName);
        builder.Write($"Text inside {bookmarkName}.");
        builder.EndBookmark(bookmarkName);
        builder.Writeln("Text after bookmark.");
    }

    return doc;
}

/// <summary>
/// Use un iterador y un visitante para imprimir información de cada marcador en la colección.
/// </summary>
private static void PrintAllBookmarkInfo(BookmarkCollection bookmarks)
{
    BookmarkInfoPrinter bookmarkVisitor = new BookmarkInfoPrinter();

    // Obtenga cada marcador en la colección para aceptar un visitante que imprimirá su contenido.
    using (IEnumerator<Bookmark> enumerator = bookmarks.GetEnumerator())
    {
        while (enumerator.MoveNext())
        {
            Bookmark currentBookmark = enumerator.Current;

            if (currentBookmark != null)
            {
                currentBookmark.BookmarkStart.Accept(bookmarkVisitor);
                currentBookmark.BookmarkEnd.Accept(bookmarkVisitor);

                Console.WriteLine(currentBookmark.BookmarkStart.GetText());
            }
        }
    }
}

/// <summary>
/// Imprime el contenido de cada marcador visitado en la consola.
/// </summary>
public class BookmarkInfoPrinter : DocumentVisitor
{
    public override VisitorAction VisitBookmarkStart(BookmarkStart bookmarkStart)
    {
        Console.WriteLine($"BookmarkStart name: \"{bookmarkStart.Name}\", Contents: \"{bookmarkStart.Bookmark.Text}\"");
        return VisitorAction.Continue;
    }

    public override VisitorAction VisitBookmarkEnd(BookmarkEnd bookmarkEnd)
    {
        Console.WriteLine($"BookmarkEnd name: \"{bookmarkEnd.Name}\"");
        return VisitorAction.Continue;
    }
}
```

### Ver también

* espacio de nombres [Aspose.Words](../../aspose.words/)
* asamblea [Aspose.Words](../../)


