---
title: WriteProtection.SetPassword
second_title: Aspose.Words för .NET API Referens
description: WriteProtection metod. Ställer in skrivskyddslösenordet för dokumentet.
type: docs
weight: 30
url: /sv/net/aspose.words.settings/writeprotection/setpassword/
---
## WriteProtection.SetPassword method

Ställer in skrivskyddslösenordet för dokumentet.

```csharp
public void SetPassword(string password)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| password | String | Lösenordet att ställa in. Kan inte vara null, men kan vara en tom sträng. |

### Anmärkningar

Om ett lösenord är inställt kommer Microsoft Word att kräva att användaren anger det eller öppnar dokumentet som skrivskyddat.

### Exempel

Visar hur man skyddar ett dokument med ett lösenord.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! This document is protected.");

// Ange ett lösenord på upp till 15 tecken och verifiera sedan dokumentets skyddsstatus.
doc.WriteProtection.SetPassword("MyPassword");
doc.WriteProtection.ReadOnlyRecommended = true;

Assert.IsTrue(doc.WriteProtection.IsWriteProtected);
Assert.IsTrue(doc.WriteProtection.ValidatePassword("MyPassword"));

// Skyddet hindrar inte dokumentet från att redigeras programmatiskt, och det krypterar inte heller innehållet.
doc.Save(ArtifactsDir + "Document.WriteProtection.docx");
doc = new Document(ArtifactsDir + "Document.WriteProtection.docx");

Assert.IsTrue(doc.WriteProtection.IsWriteProtected);

builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.Writeln("Writing text in a protected document.");

Assert.AreEqual("Hello world! This document is protected." +
                "\rWriting text in a protected document.", doc.GetText().Trim());
```

### Se även

* class [WriteProtection](../)
* namnutrymme [Aspose.Words.Settings](../../writeprotection/)
* hopsättning [Aspose.Words](../../../)


