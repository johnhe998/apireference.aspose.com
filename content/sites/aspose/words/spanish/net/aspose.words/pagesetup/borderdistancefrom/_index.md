---
title: PageSetup.BorderDistanceFrom
second_title: Referencia de API de Aspose.Words para .NET
description: PageSetup propiedad. Obtiene o establece un valor que indica si el borde de la página especificada se mide desde el borde de la página o desde el texto que rodea.
type: docs
weight: 40
url: /es/net/aspose.words/pagesetup/borderdistancefrom/
---
## PageSetup.BorderDistanceFrom property

Obtiene o establece un valor que indica si el borde de la página especificada se mide desde el borde de la página o desde el texto que rodea.

```csharp
public PageBorderDistanceFrom BorderDistanceFrom { get; set; }
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

### Ver también

* enum [PageBorderDistanceFrom](../../pageborderdistancefrom/)
* class [PageSetup](../)
* espacio de nombres [Aspose.Words](../../pagesetup/)
* asamblea [Aspose.Words](../../../)


