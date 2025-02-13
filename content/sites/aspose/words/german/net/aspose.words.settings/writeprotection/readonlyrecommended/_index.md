---
title: WriteProtection.ReadOnlyRecommended
second_title: Aspose.Words für .NET-API-Referenz
description: WriteProtection eigendom. Gibt an ob der Autor des Dokuments empfohlen hat das Dokument schreibgeschützt zu öffnen.
type: docs
weight: 20
url: /de/net/aspose.words.settings/writeprotection/readonlyrecommended/
---
## WriteProtection.ReadOnlyRecommended property

Gibt an, ob der Autor des Dokuments empfohlen hat, das Dokument schreibgeschützt zu öffnen.

```csharp
public bool ReadOnlyRecommended { get; set; }
```

### Beispiele

Zeigt, wie Sie ein Dokument mit einem Kennwort schützen.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello world! This document is protected.");

// Geben Sie ein Passwort mit einer Länge von bis zu 15 Zeichen ein und überprüfen Sie dann den Schutzstatus des Dokuments.
doc.WriteProtection.SetPassword("MyPassword");
doc.WriteProtection.ReadOnlyRecommended = true;

Assert.IsTrue(doc.WriteProtection.IsWriteProtected);
Assert.IsTrue(doc.WriteProtection.ValidatePassword("MyPassword"));

// Der Schutz verhindert weder die programmatische Bearbeitung des Dokuments noch verschlüsselt er den Inhalt.
doc.Save(ArtifactsDir + "Document.WriteProtection.docx");
doc = new Document(ArtifactsDir + "Document.WriteProtection.docx");

Assert.IsTrue(doc.WriteProtection.IsWriteProtected);

builder = new DocumentBuilder(doc);
builder.MoveToDocumentEnd();
builder.Writeln("Writing text in a protected document.");

Assert.AreEqual("Hello world! This document is protected." +
                "\rWriting text in a protected document.", doc.GetText().Trim());
```

### Siehe auch

* class [WriteProtection](../)
* namensraum [Aspose.Words.Settings](../../writeprotection/)
* Montage [Aspose.Words](../../../)


