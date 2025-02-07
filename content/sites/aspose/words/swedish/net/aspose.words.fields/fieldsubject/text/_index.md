---
title: FieldSubject.Text
second_title: Aspose.Words för .NET API Referens
description: FieldSubject fast egendom. Hämtar eller ställer in texten i ämnet.
type: docs
weight: 20
url: /sv/net/aspose.words.fields/fieldsubject/text/
---
## FieldSubject.Text property

Hämtar eller ställer in texten i ämnet.

```csharp
public string Text { get; set; }
```

### Exempel

Visar hur man använder fältet SUBJECT.

```csharp
Document doc = new Document();

// Ställ in ett värde för dokumentets inbyggda egenskap "Ämne".
doc.BuiltInDocumentProperties.Subject = "My subject";

// Skapa ett SUBJECT-fält för att visa värdet på den inbyggda egenskapen.
DocumentBuilder builder = new DocumentBuilder(doc);
FieldSubject field = (FieldSubject)builder.InsertField(FieldType.FieldSubject, true);
field.Update();

Assert.AreEqual(" SUBJECT ", field.GetFieldCode());
Assert.AreEqual("My subject", field.Result);

// Om vi ger SUBJECT-fältets Text-egenskapsvärde och uppdaterar det kommer fältet att göra det
// skriv över det aktuella värdet av den inbyggda "Subject"-egenskapen med värdet på dess Text-egenskap,
// och visa sedan det nya värdet.
field.Text = "My new subject";
field.Update();

Assert.AreEqual(" SUBJECT  \"My new subject\"", field.GetFieldCode());
Assert.AreEqual("My new subject", field.Result);

Assert.AreEqual("My new subject", doc.BuiltInDocumentProperties.Subject);

doc.Save(ArtifactsDir + "Field.SUBJECT.docx");
```

### Se även

* class [FieldSubject](../)
* namnutrymme [Aspose.Words.Fields](../../fieldsubject/)
* hopsättning [Aspose.Words](../../../)


