---
title: Bookmark.Name
second_title: Referencia de API de Aspose.Words para .NET
description: Bookmark propiedad. Obtiene o establece el nombre del marcador.
type: docs
weight: 60
url: /es/net/aspose.words/bookmark/name/
---
## Bookmark.Name property

Obtiene o establece el nombre del marcador.

```csharp
public string Name { get; set; }
```

### Observaciones

Tenga en cuenta que si cambia el nombre de un marcador a un nombre que ya existe en el documento, no se dará ningún error y solo se almacenará el primer marcador cuando guarde el documento.

### Ejemplos

Muestra cómo insertar un marcador.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Un marcador válido tiene un nombre, un BookmarkStart y un nodo BookmarkEnd.
// Cualquier espacio en blanco en los nombres de los marcadores se convertirá en guiones bajos si abrimos el documento guardado con Microsoft Word. 
// Si resaltamos el nombre del marcador en Microsoft Word mediante Insertar -> Enlaces -> Marque como favorito y presione "Ir a",
// el cursor saltará al texto encerrado entre los nodos BookmarkStart y BookmarkEnd.
builder.StartBookmark("My Bookmark");
builder.Write("Contents of MyBookmark.");
builder.EndBookmark("My Bookmark");

// Los marcadores se almacenan en esta colección.
Assert.AreEqual("My Bookmark", doc.Range.Bookmarks[0].Name);

doc.Save(ArtifactsDir + "Bookmarks.Insert.docx");
```

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

* class [Bookmark](../)
* espacio de nombres [Aspose.Words](../../bookmark/)
* asamblea [Aspose.Words](../../../)


