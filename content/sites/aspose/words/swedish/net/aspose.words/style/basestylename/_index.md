---
title: Style.BaseStyleName
second_title: Aspose.Words för .NET API Referens
description: Style fast egendom. Hämtar/ställer in namnet på stilen som denna stil är baserad på.
type: docs
weight: 20
url: /sv/net/aspose.words/style/basestylename/
---
## Style.BaseStyleName property

Hämtar/ställer in namnet på stilen som denna stil är baserad på.

```csharp
public string BaseStyleName { get; set; }
```

### Anmärkningar

Detta kommer att vara en tom sträng om stilen inte är baserad på någon annan stil och den kan sättas till en tom sträng.

### Exempel

Visar hur man använder stilalias.

```csharp
Document doc = new Document(MyDir + "Style with alias.docx");

// Det här dokumentet innehåller en stil som heter "MyStyle, MyStyle Alias 1, MyStyle Alias 2".
// Om en stils namn har flera värden separerade med kommatecken, är varje sats ett separat alias.
Style style = doc.Styles["MyStyle"];
Assert.AreEqual(new [] { "MyStyle Alias 1", "MyStyle Alias 2" }, style.Aliases);
Assert.AreEqual("Title", style.BaseStyleName);
Assert.AreEqual("MyStyle Char", style.LinkedStyleName);

// Vi kan referera till en stil med dess alias, såväl som dess namn.
Assert.AreEqual(doc.Styles["MyStyle Alias 1"], doc.Styles["MyStyle Alias 2"]);

DocumentBuilder builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.ParagraphFormat.Style = doc.Styles["MyStyle Alias 1"];
builder.Writeln("Hello world!");
builder.ParagraphFormat.Style = doc.Styles["MyStyle Alias 2"];
builder.Write("Hello again!");

Assert.AreEqual(doc.FirstSection.Body.Paragraphs[0].ParagraphFormat.Style, 
    doc.FirstSection.Body.Paragraphs[1].ParagraphFormat.Style);
```

### Se även

* class [Style](../)
* namnutrymme [Aspose.Words](../../style/)
* hopsättning [Aspose.Words](../../../)


