---
title: BuiltInDocumentProperties.HyperlinkBase
second_title: Aspose.Words för .NET API Referens
description: BuiltInDocumentProperties fast egendom. Anger bassträngen som används för att utvärdera relativa hyperlänkar i detta dokument.
type: docs
weight: 120
url: /sv/net/aspose.words.properties/builtindocumentproperties/hyperlinkbase/
---
## BuiltInDocumentProperties.HyperlinkBase property

Anger bassträngen som används för att utvärdera relativa hyperlänkar i detta dokument.

```csharp
public string HyperlinkBase { get; set; }
```

### Anmärkningar

Aspose.Words använder inte den här egenskapen.

### Exempel

Visar hur man lagrar basdelen av en hyperlänk i dokumentets egenskaper.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en relativ hyperlänk till ett dokument i det lokala filsystemet med namnet "Document.docx".
// Genom att klicka på länken i Microsoft Word öppnas det angivna dokumentet, om det är tillgängligt.
builder.InsertHyperlink("Relative hyperlink", "Document.docx", false);

// Denna länk är relativ. Om det inte finns något "Document.docx" i samma mapp
// som dokumentet som innehåller denna länk kommer länken att brytas.
Assert.False(File.Exists(ArtifactsDir + "Document.docx"));
doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.BrokenLink.docx");

// Dokumentet vi försöker länka till finns i en annan katalog än den vi planerar att spara dokumentet i.
// Vi skulle kunna fixa sådana här länkar genom att ange ett absolut filnamn i var och en. 
// Alternativt kan vi tillhandahålla en baslänk som varje hyperlänk med ett relativt filnamn
// kommer att läggas till länken när vi klickar på den. 
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;
properties.HyperlinkBase = MyDir;

Assert.True(File.Exists(properties.HyperlinkBase + ((FieldHyperlink)doc.Range.Fields[0]).Address));

doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.WorkingLink.docx");
```

### Se även

* class [BuiltInDocumentProperties](../)
* namnutrymme [Aspose.Words.Properties](../../builtindocumentproperties/)
* hopsättning [Aspose.Words](../../../)


