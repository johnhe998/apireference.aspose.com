---
title: HtmlSaveOptions.ExportShapesAsSvg
second_title: Aspose.Words per .NET API Reference
description: HtmlSaveOptions proprietà. Controlla seShape i nodi vengono convertiti in immagini SVG durante il salvataggio in HTML MHTML o EPUB. Il valore predefinito èfalso .
type: docs
weight: 260
url: /it/net/aspose.words.saving/htmlsaveoptions/exportshapesassvg/
---
## HtmlSaveOptions.ExportShapesAsSvg property

Controlla se[`Shape`](../../../aspose.words.drawing/shape/) i nodi vengono convertiti in immagini SVG durante il salvataggio in HTML, MHTML o EPUB. Il valore predefinito è`falso` .

```csharp
public bool ExportShapesAsSvg { get; set; }
```

### Osservazioni

Se questa opzione è impostata su`VERO` ,[`Shape`](../../../aspose.words.drawing/shape/) i nodi vengono esportati come elementi &lt;svg&gt;. In caso contrario, vengono visualizzati in bitmap ed esportati come elementi &lt;img&gt;.

Nota che questa opzione ha effetto anche sulle caselle di testo, perché sono rappresentate da[`Shape`](../../../aspose.words.drawing/shape/) nodes. Di conseguenza, se questa opzione è impostata su`VERO` , sovrascrive ilExportTextBoxAsSvgproperty e fa convertire le caselle di testo in SVG.

### Esempi

Mostra come esportare la forma come grafica vettoriale scalabile.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Shape textBox = builder.InsertShape(ShapeType.TextBox, 100.0, 60.0);
builder.MoveTo(textBox.FirstParagraph);
builder.Write("My text box");

// Quando salviamo il documento in HTML, possiamo passare un oggetto SaveOptions
// per determinare in che modo l'operazione di salvataggio esporterà le forme delle caselle di testo.
// Se impostiamo il flag "ExportTextBoxAsSvg" su "true",
// l'operazione di salvataggio converte le forme con il testo in oggetti SVG.
// Se impostiamo il flag "ExportTextBoxAsSvg" su "false",
// l'operazione di salvataggio converte le forme con il testo in immagini.
HtmlSaveOptions options = new HtmlSaveOptions { ExportShapesAsSvg = exportShapesAsSvg };

doc.Save(ArtifactsDir + "HtmlSaveOptions.ExportTextBox.html", options);

string outDocContents = File.ReadAllText(ArtifactsDir + "HtmlSaveOptions.ExportTextBox.html");

if (exportShapesAsSvg)
{
    Assert.True(outDocContents.Contains(
        "<span style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\">" +
        "<svg xmlns=\"http://www.w3.org/2000/svg\" xmlns:xlink=\"http://www.w3.org/1999/xlink\" version=\"1.1\" width=\"133\" height= \"80\">"));
}
else
{
    Assert.True(outDocContents.Contains(
        "<p style=\"margin-top:0pt; margin-bottom:0pt\">" +
            "<img src=\"HtmlSaveOptions.ExportTextBox.001.png\" width=\"136\" height=\"83\" alt=\"\" " +
            "style=\"-aw-left-pos:0pt; -aw-rel-hpos:column; -aw-rel-vpos:paragraph; -aw-top-pos:0pt; -aw-wrap-type:inline\" />" +
        "</p>"));
}
```

### Guarda anche

* class [HtmlSaveOptions](../)
* spazio dei nomi [Aspose.Words.Saving](../../htmlsaveoptions/)
* assemblea [Aspose.Words](../../../)


