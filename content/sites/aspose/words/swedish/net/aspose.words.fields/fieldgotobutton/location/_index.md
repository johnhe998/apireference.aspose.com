---
title: FieldGoToButton.Location
second_title: Aspose.Words för .NET API Referens
description: FieldGoToButton fast egendom. Hämtar eller ställer in namnet på ett bokmärke ett sidnummer eller något annat objekt att hoppa till.
type: docs
weight: 30
url: /sv/net/aspose.words.fields/fieldgotobutton/location/
---
## FieldGoToButton.Location property

Hämtar eller ställer in namnet på ett bokmärke, ett sidnummer eller något annat objekt att hoppa till.

```csharp
public string Location { get; set; }
```

### Exempel

Visar för att infoga ett GOTOBUTTON-fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Lägg till ett GOTOBUTTON-fält. När vi dubbelklickar på det här fältet i Microsoft Word,
// det tar textmarkören till bokmärket vars namn platsegenskapen refererar till.
FieldGoToButton field = (FieldGoToButton)builder.InsertField(FieldType.FieldGoToButton, true);
field.DisplayText = "My Button";
field.Location = "MyBookmark";

Assert.AreEqual(" GOTOBUTTON  MyBookmark My Button", field.GetFieldCode());

// Infoga ett giltigt bokmärke för fältet att referera till.
builder.InsertBreak(BreakType.PageBreak);
builder.StartBookmark(field.Location);
builder.Writeln("Bookmark text contents.");
builder.EndBookmark(field.Location);

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.GOTOBUTTON.docx");
```

### Se även

* class [FieldGoToButton](../)
* namnutrymme [Aspose.Words.Fields](../../fieldgotobutton/)
* hopsättning [Aspose.Words](../../../)


