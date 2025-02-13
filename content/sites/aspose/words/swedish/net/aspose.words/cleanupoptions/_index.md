---
title: Class CleanupOptions
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.CleanupOptions klass. Tillåter att ange alternativ för dokumentrengöring.
type: docs
weight: 200
url: /sv/net/aspose.words/cleanupoptions/
---
## CleanupOptions class

Tillåter att ange alternativ för dokumentrengöring.

```csharp
public class CleanupOptions
```

## Konstruktörer

| namn | Beskrivning |
| --- | --- |
| [CleanupOptions](cleanupoptions/)() | Default_Constructor |

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [DuplicateStyle](../../aspose.words/cleanupoptions/duplicatestyle/) { get; set; } | Hämtar/ställer in en flagga som indikerar om dubblettstilar ska tas bort från dokumentet. Standardvärdet är **falsk** . |
| [UnusedBuiltinStyles](../../aspose.words/cleanupoptions/unusedbuiltinstyles/) { get; set; } | Anger att oanvänd[`BuiltIn`](../style/builtin/) stilar bör tas bort från document. |
| [UnusedLists](../../aspose.words/cleanupoptions/unusedlists/) { get; set; } | Anger om oanvända list- och listdefinitioner ska tas bort från dokumentet. Standardvärdet är **Sann** . |
| [UnusedStyles](../../aspose.words/cleanupoptions/unusedstyles/) { get; set; } | Anger om oanvända formatmallar ska tas bort från dokumentet. Standardvärdet är **Sann** . |

### Exempel

Visar hur man tar bort alla oanvända anpassade stilar från ett dokument.

```csharp
Document doc = new Document();

doc.Styles.Add(StyleType.List, "MyListStyle1");
doc.Styles.Add(StyleType.List, "MyListStyle2");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle1");
doc.Styles.Add(StyleType.Character, "MyParagraphStyle2");

// I kombination med de inbyggda stilarna har dokumentet nu åtta stilar.
// En anpassad stil markeras som "använd" medan det finns någon text i dokumentet
// formaterad i den stilen. Det betyder att de 4 stilarna vi har lagt till för närvarande är oanvända.
Assert.AreEqual(8, doc.Styles.Count);

// Använd en anpassad teckenstil och sedan en anpassad liststil. Om du gör det kommer de att markeras som "använda".
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Style = doc.Styles["MyParagraphStyle1"];
builder.Writeln("Hello world!");

Aspose.Words.Lists.List list = doc.Lists.Add(doc.Styles["MyListStyle1"]);
builder.ListFormat.List = list;
builder.Writeln("Item 1");
builder.Writeln("Item 2");

// Nu finns det en oanvänd teckenstil och en oanvänd liststil.
// Cleanup()-metoden, när den är konfigurerad med ett CleanupOptions-objekt, kan rikta in sig på oanvända stilar och ta bort dem.
CleanupOptions cleanupOptions = new CleanupOptions
{
    UnusedLists = true, UnusedStyles = true, UnusedBuiltinStyles = true
};

doc.Cleanup(cleanupOptions);

Assert.AreEqual(4, doc.Styles.Count);

// Om du tar bort varje nod som en anpassad stil tillämpas på markeras den som "oanvänd" igen. 
// Kör rengöringsmetoden igen för att ta bort dem.
doc.FirstSection.Body.RemoveAllChildren();
doc.Cleanup(cleanupOptions);

Assert.AreEqual(2, doc.Styles.Count);
```

### Se även

* namnutrymme [Aspose.Words](../../aspose.words/)
* hopsättning [Aspose.Words](../../)


