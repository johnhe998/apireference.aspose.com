---
title: PageSetup.FirstPageTray
second_title: Referencia de API de Aspose.Words para .NET
description: PageSetup propiedad. Obtiene o establece la bandeja de papel bin que se usará para la primera página de una sección. El valor es específico de la implementación impresora.
type: docs
weight: 130
url: /es/net/aspose.words/pagesetup/firstpagetray/
---
## PageSetup.FirstPageTray property

Obtiene o establece la bandeja de papel (bin) que se usará para la primera página de una sección. El valor es específico de la implementación (impresora).

```csharp
public int FirstPageTray { get; set; }
```

### Ejemplos

Muestra cómo hacer que todas las secciones de un documento utilicen la bandeja de papel predeterminada de la impresora seleccionada.

```csharp
Document doc = new Document();

// Encuentra la impresora predeterminada que usaremos para imprimir este documento.
// Puede definir una impresora específica usando la propiedad "PrinterName" del objeto PrinterSettings.
PrinterSettings settings = new PrinterSettings();

// El valor de la bandeja de papel almacenado en los documentos es específico de la impresora.
// Esto significa que el siguiente código restablece todos los valores de la bandeja de páginas para usar la bandeja predeterminada de la impresora actual.
// Puede enumerar PrinterSettings.PaperSources para encontrar los otros valores de bandeja de papel válidos de la impresora seleccionada.
foreach (Section section in doc.Sections.OfType<Section>())
{
    section.PageSetup.FirstPageTray = settings.DefaultPageSettings.PaperSource.RawKind;
    section.PageSetup.OtherPagesTray = settings.DefaultPageSettings.PaperSource.RawKind;
}
```

Muestra cómo configurar la impresión usando diferentes bandejas de impresora para diferentes tamaños de papel.

```csharp
Document doc = new Document();

// Encuentra la impresora predeterminada que usaremos para imprimir este documento.
// Puede definir una impresora específica usando la propiedad "PrinterName" del objeto PrinterSettings.
PrinterSettings settings = new PrinterSettings();

// Esta es la bandeja que usaremos para las páginas en el tamaño de papel "A4".
int printerTrayForA4 = settings.PaperSources[0].RawKind;

// Esta es la bandeja que usaremos para las páginas en el tamaño de papel "Carta".
int printerTrayForLetter = settings.PaperSources[1].RawKind;

// Modifique el objeto PageSettings de esta sección para que Microsoft Word instruya a la impresora
// para usar una de las bandejas que identificamos arriba, dependiendo del tamaño de papel de esta sección.
foreach (Section section in doc.Sections.OfType<Section>())
{
    if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.Letter)
    {
        section.PageSetup.FirstPageTray = printerTrayForLetter;
        section.PageSetup.OtherPagesTray = printerTrayForLetter;
    }
    else if (section.PageSetup.PaperSize == Aspose.Words.PaperSize.A4)
    {
        section.PageSetup.FirstPageTray = printerTrayForA4;
        section.PageSetup.OtherPagesTray = printerTrayForA4;
    }
}
```

### Ver también

* class [PageSetup](../)
* espacio de nombres [Aspose.Words](../../pagesetup/)
* asamblea [Aspose.Words](../../../)


