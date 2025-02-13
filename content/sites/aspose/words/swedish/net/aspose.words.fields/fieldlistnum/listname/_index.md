---
title: FieldListNum.ListName
second_title: Aspose.Words för .NET API Referens
description: FieldListNum fast egendom. Hämtar eller ställer in namnet på den abstrakta numreringsdefinitionen som används för numreringen.
type: docs
weight: 40
url: /sv/net/aspose.words.fields/fieldlistnum/listname/
---
## FieldListNum.ListName property

Hämtar eller ställer in namnet på den abstrakta numreringsdefinitionen som används för numreringen.

```csharp
public string ListName { get; set; }
```

### Exempel

Visar hur man numrerar stycken med LISTNUM-fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// LISTNUM-fält visar ett tal som ökar vid varje LISTNUM-fält.
// Dessa fält har också en mängd olika alternativ som gör att vi kan använda dem för att efterlikna numrerade listor.
FieldListNum field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);

// Listor börjar räknas vid 1 som standard, men vi kan ställa in detta nummer till ett annat värde, till exempel 0.
// Detta fält kommer att visa "0)".
field.StartingNumber = "0";
builder.Writeln("Paragraph 1");

Assert.AreEqual(" LISTNUM  \\s 0", field.GetFieldCode());

  // LISTNUM-fält upprätthåller separata räkningar för varje listnivå.
// Infoga ett LISTNUM-fält i samma stycke som ett annat LISTNUM-fält
// ökar listnivån istället för antalet.
// Nästa fält kommer att fortsätta räkningen vi startade ovan och visa värdet "1" på listnivå 1.
builder.InsertField(FieldType.FieldListNum, true);

// Detta fält kommer att starta en räkning på listnivå 2. Det kommer att visa värdet "1".
builder.InsertField(FieldType.FieldListNum, true);

// Detta fält startar en räkning på listnivå 3. Det kommer att visa värdet "1".
// Olika listnivåer har olika formatering,
// så dessa fält kombinerade kommer att visa värdet "1)a)i)".
builder.InsertField(FieldType.FieldListNum, true);
builder.Writeln("Paragraph 2");

// Nästa LISTNUM-fält som vi infogar fortsätter räkningen på listnivå
// att det tidigare LISTNUM-fältet var på.
// Vi kan använda egenskapen "ListLevel" för att hoppa till en annan listnivå.
// Om detta LISTNUM-fält stannade på listnivå 3, skulle det visa "ii)",
// men eftersom vi har flyttat den till listnivå 2 fortsätter den räkningen på den nivån och visar "b)".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListLevel = "2";
builder.Writeln("Paragraph 3");

Assert.AreEqual(" LISTNUM  \\l 2", field.GetFieldCode());

// Vi kan ställa in egenskapen ListName för att få fältet att emulera en annan AUTONUM-fälttyp.
// "NumberDefault" emulerar AUTONUM, "OutlineDefault" emulerar AUTONUMOUT,
// och "LegalDefault" emulerar AUTONUMLGL-fält.
// Listnamnet "OutlineDefault" med 1 som startnummer kommer att resultera i att "I." visas.
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.StartingNumber = "1";
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 4");

Assert.IsTrue(field.HasListName);
Assert.AreEqual(" LISTNUM  OutlineDefault \\s 1", field.GetFieldCode());

// Listnamnet överförs inte från föregående fält, så vi måste ställa in det för varje nytt fält.
// Detta fält fortsätter räkningen med det olika listnamnet och visar "II.".
field = (FieldListNum)builder.InsertField(FieldType.FieldListNum, true);
field.ListName = "OutlineDefault";
builder.Writeln("Paragraph 5");

doc.UpdateFields();
doc.Save(ArtifactsDir + "Field.LISTNUM.docx");
```

### Se även

* class [FieldListNum](../)
* namnutrymme [Aspose.Words.Fields](../../fieldlistnum/)
* hopsättning [Aspose.Words](../../../)


