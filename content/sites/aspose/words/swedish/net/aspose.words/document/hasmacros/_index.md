---
title: Document.HasMacros
second_title: Aspose.Words för .NET API Referens
description: Document fast egendom. Returnerar Sann om dokumentet har ett VBAprojekt makron.
type: docs
weight: 190
url: /sv/net/aspose.words/document/hasmacros/
---
## Document.HasMacros property

Returnerar **Sann** om dokumentet har ett VBA-projekt (makron).

```csharp
public bool HasMacros { get; }
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

* method [RemoveMacros](../removemacros/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


