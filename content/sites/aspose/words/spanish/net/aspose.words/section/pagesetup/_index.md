---
title: Section.PageSetup
second_title: Referencia de API de Aspose.Words para .NET
description: Section propiedad. Devuelve un objeto que representa la configuración de la página y las propiedades de la sección.
type: docs
weight: 50
url: /es/net/aspose.words/section/pagesetup/
---
## Section.PageSetup property

Devuelve un objeto que representa la configuración de la página y las propiedades de la sección.

```csharp
public PageSetup PageSetup { get; }
```

### Ejemplos

Muestra cómo crear un borde ancho de banda azul en la parte superior de la primera página.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.BorderAlwaysInFront = false;
pageSetup.BorderDistanceFrom = PageBorderDistanceFrom.PageEdge;
pageSetup.BorderAppliesTo = PageBorderAppliesTo.FirstPage;

Border border = pageSetup.Borders[BorderType.Top];
border.LineStyle = LineStyle.Single;
border.LineWidth = 30;
border.Color = Color.Blue;
border.DistanceFromText = 0;

doc.Save(ArtifactsDir + "PageSetup.PageBorderProperties.docx");
```

Muestra cómo construir un documento de Aspose.Words a mano.

```csharp
Document doc = new Document();

// Un documento en blanco contiene una sección, un cuerpo y un párrafo.
// Llame al método "RemoveAllChildren" para eliminar todos esos nodos,
// y terminar con un nodo de documento sin hijos.
doc.RemoveAllChildren();

// Este documento ahora no tiene nodos secundarios compuestos a los que podamos agregar contenido.
// Si deseamos editarlo, necesitaremos volver a llenar su colección de nodos.
// Primero, cree una nueva sección y luego agréguela como elemento secundario al nodo del documento raíz.
Section section = new Section(doc);
doc.AppendChild(section);

// Establecer algunas propiedades de configuración de página para la sección.
section.PageSetup.SectionStart = SectionStart.NewPage;
section.PageSetup.PaperSize = PaperSize.Letter;

// Una sección necesita un cuerpo, que contendrá y mostrará todo su contenido
// en la página entre el encabezado y el pie de página de la sección.
Body body = new Body(doc);
section.AppendChild(body);

// Cree un párrafo, establezca algunas propiedades de formato y luego agréguelo como elemento secundario al cuerpo.
Paragraph para = new Paragraph(doc);

para.ParagraphFormat.StyleName = "Heading 1";
para.ParagraphFormat.Alignment = ParagraphAlignment.Center;

body.AppendChild(para);

// Finalmente, agregue algo de contenido para hacer el documento. Crear una carrera,
// establece su apariencia y contenido, y luego lo agrega como elemento secundario al párrafo.
Run run = new Run(doc);
run.Text = "Hello World!";
run.Font.Color = Color.Red;
para.AppendChild(run);

Assert.AreEqual("Hello World!", doc.GetText().Trim());

doc.Save(ArtifactsDir + "Section.CreateManually.docx");
```

### Ver también

* class [PageSetup](../../pagesetup/)
* class [Section](../)
* espacio de nombres [Aspose.Words](../../section/)
* asamblea [Aspose.Words](../../../)


