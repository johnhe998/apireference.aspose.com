---
title: FieldMacroButton.DisplayText
second_title: Aspose.Words för .NET API Referens
description: FieldMacroButton fast egendom. Hämtar eller ställer in texten så att den visas som knappen som är vald för att köra makrot eller kommandot.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fieldmacrobutton/displaytext/
---
## FieldMacroButton.DisplayText property

Hämtar eller ställer in texten så att den visas som "knappen" som är vald för att köra makrot eller kommandot.

```csharp
public string DisplayText { get; set; }
```

### Exempel

Visar hur man använder MACROBUTTON-fält för att tillåta oss att köra ett dokuments makron genom att klicka.

```csharp
Document doc = new Document(MyDir + "Macro.docm");
DocumentBuilder builder = new DocumentBuilder(doc);

Assert.IsTrue(doc.HasMacros);

// Infoga ett MACROBUTTON-fält och referera till ett av dokumentets makron efter namn i egenskapen MacroName.
FieldMacroButton field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "MyMacro";
field.DisplayText = "Double click to run macro: " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  MyMacro Double click to run macro: MyMacro", field.GetFieldCode());

// Använd egenskapen för att referera till "ViewZoom200", ett makro som levereras med Microsoft Word.
// Vi kan hitta alla andra makron via Visa -> Makron (rullgardinsmeny) -> Visa makron.
// I den menyn väljer du "Word Commands" från rullgardinsmenyn "Makron i:".
// Om vårt dokument innehåller ett anpassat makro med samma namn som ett aktiemakro,
// vårt makro kommer att vara det som fältet MACROBUTTON körs.
builder.InsertParagraph();
field = (FieldMacroButton)builder.InsertField(FieldType.FieldMacroButton, true);
field.MacroName = "ViewZoom200";
field.DisplayText = "Run " + field.MacroName;

Assert.AreEqual(" MACROBUTTON  ViewZoom200 Run ViewZoom200", field.GetFieldCode());

// Spara dokumentet som en makroaktiverad dokumenttyp.
doc.Save(ArtifactsDir + "Field.MACROBUTTON.docm");
```

### Se även

* class [FieldMacroButton](../)
* namnutrymme [Aspose.Words.Fields](../../fieldmacrobutton/)
* hopsättning [Aspose.Words](../../../)


