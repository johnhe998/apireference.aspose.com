---
title: FieldGreetingLine.GetFieldNames
second_title: Aspose.Words för .NET API Referens
description: FieldGreetingLine metod. Returnerar en samling av kopplingsfältnamn som används av fältet.
type: docs
weight: 50
url: /sv/net/aspose.words.fields/fieldgreetingline/getfieldnames/
---
## FieldGreetingLine.GetFieldNames method

Returnerar en samling av kopplingsfältnamn som används av fältet.

```csharp
public string[] GetFieldNames()
```

### Exempel

Visar hur man infogar ett HÄLSNINGSLINJE-fält.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Skapa en allmän hälsning med ett HÄLSNINGSLINJE-fält och lite text efter det.
FieldGreetingLine field = (FieldGreetingLine)builder.InsertField(FieldType.FieldGreetingLine, true);
builder.Writeln("\n\n\tThis is your custom greeting, created programmatically using Aspose Words!");

// Ett GREETINGLINE-fält accepterar värden från en datakälla under en e-postkoppling, som ett MERGEFIELD.
// Det kan också formatera hur källans data skrivs på sin plats när sammanslagningen är klar.
// Fältnamnssamlingen motsvarar kolumnerna från datakällan
// som fältet kommer att ta värden från.
Assert.AreEqual(0, field.GetFieldNames().Length);

// För att fylla den arrayen måste vi ange ett format för vår hälsningsrad.
field.NameFormat = "<< _BEFORE_ Dear >><< _TITLE0_ >><< _LAST0_ >><< _AFTER_ ,>> ";

// Nu kommer vårt fält att acceptera värden från dessa två kolumner i datakällan.
Assert.AreEqual("Courtesy Title", field.GetFieldNames()[0]);
Assert.AreEqual("Last Name", field.GetFieldNames()[1]);
Assert.AreEqual(2, field.GetFieldNames().Length);

// Denna sträng kommer att täcka alla fall där datatabellsdata är ogiltiga
// genom att ersätta det felaktiga namnet med en sträng.
field.AlternateText = "Sir or Madam";

// Ställ in ett språk för att formatera resultatet.
field.LanguageId = new CultureInfo("en-US").LCID.ToString();

Assert.AreEqual(" GREETINGLINE  \\f \"<< _BEFORE_ Dear >><< _TITLE0_ >><< _LAST0_ >><< _AFTER_ ,>> \" \\e \"Sir or Madam\" \\l 1033", 
    field.GetFieldCode());

// Skapa en datatabell med kolumner vars namn matchar element
// från fältets samling av fältnamn och utför sedan brevkopplingen.
DataTable table = new DataTable("Employees");
table.Columns.Add("Courtesy Title");
table.Columns.Add("First Name");
table.Columns.Add("Last Name");
table.Rows.Add("Mr.", "John", "Doe");
table.Rows.Add("Mrs.", "Jane", "Cardholder");

// Den här raden har ett ogiltigt värde i kolumnen Courtesy Title, så vår hälsning kommer som standard till den alternativa texten.
table.Rows.Add("", "No", "Name");

doc.MailMerge.Execute(table);

Assert.That(doc.Range.Fields, Is.Empty);
Assert.AreEqual("Dear Mr. Doe,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!\r" +
                "\fDear Mrs. Cardholder,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!\r" +
                "\fDear Sir or Madam,\r\r\tThis is your custom greeting, created programmatically using Aspose Words!",
    doc.GetText().Trim());
```

### Se även

* class [FieldGreetingLine](../)
* namnutrymme [Aspose.Words.Fields](../../fieldgreetingline/)
* hopsättning [Aspose.Words](../../../)


