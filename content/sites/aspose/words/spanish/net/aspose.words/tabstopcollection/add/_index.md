---
title: TabStopCollection.Add
second_title: Referencia de API de Aspose.Words para .NET
description: TabStopCollection método. Agrega o reemplaza una tabulación en la colección.
type: docs
weight: 30
url: /es/net/aspose.words/tabstopcollection/add/
---
## Add(TabStop) {#add}

Agrega o reemplaza una tabulación en la colección.

```csharp
public void Add(TabStop tabStop)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| tabStop | TabStop | Un objeto de tabulación para agregar. |

### Observaciones

Si ya existe una tabulación en la posición especificada, se reemplaza.

### Ejemplos

Muestra cómo agregar tabulaciones personalizadas a un documento.

```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// A continuación se muestran dos formas de agregar tabulaciones a la colección de tabulaciones de un párrafo a través de la propiedad "ParagraphFormat".
// 1 - Cree un objeto "TabStop" y luego agréguelo a la colección:
TabStop tabStop = new TabStop(ConvertUtil.InchToPoint(3), TabAlignment.Left, TabLeader.Dashes);
paragraph.ParagraphFormat.TabStops.Add(tabStop);

// 2 - Pase los valores de las propiedades de una nueva tabulación al método "Agregar":
paragraph.ParagraphFormat.TabStops.Add(ConvertUtil.MillimeterToPoint(100), TabAlignment.Left,
    TabLeader.Dashes);

// Agregar tabulaciones a 5 cm a todos los párrafos.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
{
    para.ParagraphFormat.TabStops.Add(ConvertUtil.MillimeterToPoint(50), TabAlignment.Left,
        TabLeader.Dashes);
}

// Cada carácter de "tabulador" lleva el cursor del constructor a la ubicación de la siguiente tabulación.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Start\tTab 1\tTab 2\tTab 3\tTab 4");

doc.Save(ArtifactsDir + "TabStopCollection.AddTabStops.docx");
```

### Ver también

* class [TabStop](../../tabstop/)
* class [TabStopCollection](../)
* espacio de nombres [Aspose.Words](../../tabstopcollection/)
* asamblea [Aspose.Words](../../../)

---

## Add(double, TabAlignment, TabLeader) {#add_1}

Agrega o reemplaza una tabulación en la colección.

```csharp
public void Add(double position, TabAlignment alignment, TabLeader leader)
```

| Parámetro | Escribe | Descripción |
| --- | --- | --- |
| position | Double | Una posición (en puntos) donde agregar la tabulación. |
| alignment | TabAlignment | A[`TabAlignment`](../../tabalignment/)valor that especifica la alineación del texto en la tabulación. |
| leader | TabLeader | A[`TabLeader`](../../tableader/) el valor that especifica el tipo de línea directriz que se muestra debajo del carácter de tabulación. |

### Observaciones

Si ya existe una tabulación en la posición especificada, se reemplaza.

### Ejemplos

Muestra cómo agregar tabulaciones personalizadas a un documento.

```csharp
Document doc = new Document();
Paragraph paragraph = (Paragraph)doc.GetChild(NodeType.Paragraph, 0, true);

// A continuación se muestran dos formas de agregar tabulaciones a la colección de tabulaciones de un párrafo a través de la propiedad "ParagraphFormat".
// 1 - Cree un objeto "TabStop" y luego agréguelo a la colección:
TabStop tabStop = new TabStop(ConvertUtil.InchToPoint(3), TabAlignment.Left, TabLeader.Dashes);
paragraph.ParagraphFormat.TabStops.Add(tabStop);

// 2 - Pase los valores de las propiedades de una nueva tabulación al método "Agregar":
paragraph.ParagraphFormat.TabStops.Add(ConvertUtil.MillimeterToPoint(100), TabAlignment.Left,
    TabLeader.Dashes);

// Agregar tabulaciones a 5 cm a todos los párrafos.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
{
    para.ParagraphFormat.TabStops.Add(ConvertUtil.MillimeterToPoint(50), TabAlignment.Left,
        TabLeader.Dashes);
}

// Cada carácter de "tabulador" lleva el cursor del constructor a la ubicación de la siguiente tabulación.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Start\tTab 1\tTab 2\tTab 3\tTab 4");

doc.Save(ArtifactsDir + "TabStopCollection.AddTabStops.docx");
```

### Ver también

* enum [TabAlignment](../../tabalignment/)
* enum [TabLeader](../../tableader/)
* class [TabStopCollection](../)
* espacio de nombres [Aspose.Words](../../tabstopcollection/)
* asamblea [Aspose.Words](../../../)


