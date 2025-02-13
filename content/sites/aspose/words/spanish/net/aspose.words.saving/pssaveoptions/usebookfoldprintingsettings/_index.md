---
title: PsSaveOptions.UseBookFoldPrintingSettings
second_title: Referencia de API de Aspose.Words para .NET
description: PsSaveOptions propiedad. Obtiene o establece un valor booleano que indica si el documento debe guardarse utilizando un diseño de impresión de folleto si se especifica medianteMultiplePages .
type: docs
weight: 30
url: /es/net/aspose.words.saving/pssaveoptions/usebookfoldprintingsettings/
---
## PsSaveOptions.UseBookFoldPrintingSettings property

Obtiene o establece un valor booleano que indica si el documento debe guardarse utilizando un diseño de impresión de folleto, si se especifica mediante[`MultiplePages`](../../../aspose.words/pagesetup/multiplepages/) .

```csharp
public bool UseBookFoldPrintingSettings { get; set; }
```

### Observaciones

Si se especifica esta opción,[`PageSet`](../../fixedpagesaveoptions/pageset/) se ignora al guardar. Este comportamiento coincide con MS Word. Si la configuración de impresión de plegado de libro no se especifica en la configuración de página, esta opción no tendrá efecto.

### Ejemplos

Muestra cómo guardar un documento en formato Postscript en forma de plegado de libro.

```csharp
Document doc = new Document(MyDir + "Paragraphs.docx");

// Crear un objeto "PsSaveOptions" que podamos pasar al método "Guardar" del documento
// para modificar cómo ese método convierte el documento a PostScript.
// Establecer la propiedad "UseBookFoldPrintingSettings" en "true" para organizar el contenido
// en el documento Postscript de salida de una manera que nos ayude a hacer un folleto a partir de él.
// Establezca la propiedad "UseBookFoldPrintingSettings" en "falso" para guardar el documento normalmente.
PsSaveOptions saveOptions = new PsSaveOptions
{
    SaveFormat = SaveFormat.Ps,
    UseBookFoldPrintingSettings = renderTextAsBookFold
};

// Si estamos renderizando el documento como un folleto, debemos configurar las "Páginas Múltiples"
// propiedades de los objetos de configuración de página de todas las secciones a "MultiplePagesType.BookFoldPrinting".
foreach (Section s in doc.Sections)
{
    s.PageSetup.MultiplePages = MultiplePagesType.BookFoldPrinting;
}

// Una vez que imprimamos este documento en ambos lados de las páginas, podemos doblar todas las páginas por la mitad a la vez,
// y el contenido se alineará de forma que se cree un folleto.
doc.Save(ArtifactsDir + "PsSaveOptions.UseBookFoldPrintingSettings.ps", saveOptions);
```

### Ver también

* class [PsSaveOptions](../)
* espacio de nombres [Aspose.Words.Saving](../../pssaveoptions/)
* asamblea [Aspose.Words](../../../)


