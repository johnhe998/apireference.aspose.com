---
title: OleFormat.IconCaption
second_title: Referencia de API de Aspose.Words para .NET
description: OleFormat propiedad. Obtiene el título del icono del objeto OLE.
type: docs
weight: 30
url: /es/net/aspose.words.drawing/oleformat/iconcaption/
---
## OleFormat.IconCaption property

Obtiene el título del icono del objeto OLE.

En caso de que el objeto OLE no esté incrustado como icono o título, no se pudo recuperar, devuelve una cadena vacía.

```csharp
public string IconCaption { get; }
```

### Ejemplos

Muestra cómo insertar objetos OLE vinculados y no vinculados.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Incruste un dibujo de Microsoft Visio en el documento como un objeto OLE.
builder.InsertOleObject(ImageDir + "Microsoft Visio drawing.vsd", "Package", false, false, null);

// Inserte un enlace al archivo en el sistema de archivos local y muéstrelo como un icono.
builder.InsertOleObject(ImageDir + "Microsoft Visio drawing.vsd", "Package", true, true, null);

// La inserción de objetos OLE crea formas que almacenan estos objetos.
Shape[] shapes = doc.GetChildNodes(NodeType.Shape, true).OfType<Shape>().ToArray();

Assert.AreEqual(2, shapes.Length);
Assert.AreEqual(2, shapes.Count(s => s.ShapeType == ShapeType.OleObject));

// Si una forma contiene un objeto OLE, tendrá una propiedad "OleFormat" válida,
// que podemos usar para verificar algunos aspectos de la forma.
OleFormat oleFormat = shapes[0].OleFormat;

Assert.AreEqual(false, oleFormat.IsLink);
Assert.AreEqual(false, oleFormat.OleIcon);

oleFormat = shapes[1].OleFormat;

Assert.AreEqual(true, oleFormat.IsLink);
Assert.AreEqual(true, oleFormat.OleIcon);

Assert.True(oleFormat.SourceFullName.EndsWith(@"Images" + Path.DirectorySeparatorChar + "Microsoft Visio drawing.vsd"));
Assert.AreEqual("", oleFormat.SourceItem);

Assert.AreEqual("Microsoft Visio drawing.vsd", oleFormat.IconCaption);

doc.Save(ArtifactsDir + "Shape.OleLinks.docx");

// Si el objeto contiene datos OLE, podemos acceder a él usando una secuencia.
using (MemoryStream stream = oleFormat.GetOleEntry("\x0001CompObj"))
{
    byte[] oleEntryBytes = stream.ToArray();
    Assert.AreEqual(76, oleEntryBytes.Length);
}
```

### Ver también

* class [OleFormat](../)
* espacio de nombres [Aspose.Words.Drawing](../../oleformat/)
* asamblea [Aspose.Words](../../../)


