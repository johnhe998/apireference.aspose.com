---
title: INodeChangingCallback.NodeInserted
second_title: Referencia de API de Aspose.Words para .NET
description: INodeChangingCallback método. Llamado cuando un nodo perteneciente a este documento ha sido insertado en otro nodo.
type: docs
weight: 10
url: /es/net/aspose.words/inodechangingcallback/nodeinserted/
---
## INodeChangingCallback.NodeInserted method

Llamado cuando un nodo perteneciente a este documento ha sido insertado en otro nodo.

```csharp
public void NodeInserted(NodeChangingArgs args)
```

### Ejemplos

Muestra cómo personalizar el cambio de nodo con una devolución de llamada.

```csharp
{
    Document doc = new Document();
    DocumentBuilder builder = new DocumentBuilder(doc);

    // Establecer la devolución de llamada de cambio de nodo a la implementación personalizada,
    // luego agregue/elimine nodos para que genere un registro.
    HandleNodeChangingFontChanger callback = new HandleNodeChangingFontChanger();
    doc.NodeChangingCallback = callback;

    builder.Writeln("Hello world!");
    builder.Writeln("Hello again!");
    builder.InsertField(" HYPERLINK \"https://www.google.com/\" ");
    builder.InsertShape(ShapeType.Rectangle, 300, 300);

    doc.Range.Fields[0].Remove();

    Console.WriteLine(callback.GetLog());

/// <summary>
/// Registra la fecha y la hora de inserción y eliminación de cada nodo.
/// Establece un nombre/tamaño de fuente personalizado para el contenido de texto de los nodos de ejecución.
/// </summary>
public class HandleNodeChangingFontChanger : INodeChangingCallback
{
    void INodeChangingCallback.NodeInserted(NodeChangingArgs args)
    {
        mLog.AppendLine($"\tType:\t{args.Node.NodeType}");
        mLog.AppendLine($"\tHash:\t{args.Node.GetHashCode()}");

        if (args.Node.NodeType == NodeType.Run)
        {
            Aspose.Words.Font font = ((Run) args.Node).Font;
            mLog.Append($"\tFont:\tChanged from \"{font.Name}\" {font.Size}pt");

            font.Size = 24;
            font.Name = "Arial";

            mLog.AppendLine($" to \"{font.Name}\" {font.Size}pt");
            mLog.AppendLine($"\tContents:\n\t\t\"{args.Node.GetText()}\"");
        }
    }

    void INodeChangingCallback.NodeInserting(NodeChangingArgs args)
    {
        mLog.AppendLine($"\n{DateTime.Now:dd/MM/yyyy HH:mm:ss:fff}\tNode insertion:");
    }

    void INodeChangingCallback.NodeRemoved(NodeChangingArgs args)
    {
        mLog.AppendLine($"\tType:\t{args.Node.NodeType}");
        mLog.AppendLine($"\tHash code:\t{args.Node.GetHashCode()}");
    }

    void INodeChangingCallback.NodeRemoving(NodeChangingArgs args)
    {
        mLog.AppendLine($"\n{DateTime.Now:dd/MM/yyyy HH:mm:ss:fff}\tNode removal:");
    }

    public string GetLog()
    {
        return mLog.ToString();
    }

    private readonly StringBuilder mLog = new StringBuilder();
}
```

### Ver también

* class [NodeChangingArgs](../../nodechangingargs/)
* interface [INodeChangingCallback](../)
* espacio de nombres [Aspose.Words](../../inodechangingcallback/)
* asamblea [Aspose.Words](../../../)


