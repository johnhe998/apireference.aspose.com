---
title: EditableRange.Id
second_title: Aspose.Words för .NET API Referens
description: EditableRange fast egendom. Hämtar den redigerbara intervallidentifieraren.
type: docs
weight: 40
url: /sv/net/aspose.words/editablerange/id/
---
## EditableRange.Id property

Hämtar den redigerbara intervallidentifieraren.

```csharp
public int Id { get; }
```

### Anmärkningar

Regionen måste avgränsas med hjälp av[`EditableRangeStart`](../editablerangestart/) och[`EditableRangeEnd`](../editablerangeend/)

Redigerbara intervallidentifierare ska vara unika i ett dokument och Aspose.Words bibehåller automatiskt redigerbara intervallidentifierare när dokument laddas, sparas och kombineras.

### Exempel

Visar hur man arbetar med ett redigerbart område.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "MyPassword");

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! Since we have set the document's protection level to read-only," +
                " we cannot edit this paragraph without the password.");

// Redigerbara intervall tillåter oss att lämna delar av skyddade dokument öppna för redigering.
EditableRangeStart editableRangeStart = builder.StartEditableRange();
builder.Writeln("This paragraph is inside an editable range, and can be edited.");
EditableRangeEnd editableRangeEnd = builder.EndEditableRange();

// Ett välformat redigerbart område har en startnod och en slutnod.
// Dessa noder har matchande ID:n och omfattar redigerbara noder.
EditableRange editableRange = editableRangeStart.EditableRange;

Assert.AreEqual(editableRangeStart.Id, editableRange.Id);
Assert.AreEqual(editableRangeEnd.Id, editableRange.Id);

// Olika delar av det redigerbara intervallet länkar till varandra.
Assert.AreEqual(editableRangeStart.Id, editableRange.EditableRangeStart.Id);
Assert.AreEqual(editableRangeStart.Id, editableRangeEnd.EditableRangeStart.Id);
Assert.AreEqual(editableRange.Id, editableRangeStart.EditableRange.Id);
Assert.AreEqual(editableRangeEnd.Id, editableRange.EditableRangeEnd.Id);

// Vi kan komma åt nodtyperna för varje del så här. Det redigerbara området i sig är inte en nod,
// men en enhet som består av en början, ett slut och deras inneslutna innehåll.
Assert.AreEqual(NodeType.EditableRangeStart, editableRangeStart.NodeType);
Assert.AreEqual(NodeType.EditableRangeEnd, editableRangeEnd.NodeType);

builder.Writeln("This paragraph is outside the editable range, and cannot be edited.");

doc.Save(ArtifactsDir + "EditableRange.CreateAndRemove.docx");

// Ta bort ett redigerbart område. Alla noder som fanns inom intervallet kommer att förbli intakta.
editableRange.Remove();
```

### Se även

* class [EditableRange](../)
* namnutrymme [Aspose.Words](../../editablerange/)
* hopsättning [Aspose.Words](../../../)


