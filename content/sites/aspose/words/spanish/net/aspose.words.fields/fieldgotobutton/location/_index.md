---
title: FieldGoToButton.Location
second_title: Referencia de API de Aspose.Words para .NET
description: FieldGoToButton propiedad. Obtiene o establece el nombre de un marcador un número de página o algún otro elemento al que saltar.
type: docs
weight: 30
url: /es/net/aspose.words.fields/fieldgotobutton/location/
---
## FieldGoToButton.Location property

Obtiene o establece el nombre de un marcador, un número de página o algún otro elemento al que saltar.

```csharp
public string Location { get; set; }
```

### Ejemplos

Muestra para insertar un campo GOTOBUTTON.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Agrega un campo GOTOBUTTON. Cuando hacemos doble clic en este campo en Microsoft Word,
// llevará el cursor de texto al marcador cuyo nombre hace referencia la propiedad Ubicación.
FieldGoToButton field = (FieldGoToButton)builder.InsertField(FieldType.FieldGoToButton, true);
field.DisplayText = "My Button";
field.Location = "MyBookmark";

Assert.AreEqual(" GOTOBUTTON  MyBookmark My Button", field.GetFieldCode());

// Inserta un marcador válido para el campo al que se hace referencia.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark(field.Location);
builder.Writeln("Bookmark text contents.");
builder.EndBookmark(field.Location);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.GOTOBUTTON.docx");
```

### Ver también

* class [FieldGoToButton](../)
* espacio de nombres [Aspose.Words.Fields](../../fieldgotobutton/)
* asamblea [Aspose.Words](../../../)


