---
title: DocumentBuilder.Italic
second_title: Aspose.Words für .NET-API-Referenz
description: DocumentBuilder eigendom. Wahr wenn die Schriftart kursiv formatiert ist.
type: docs
weight: 120
url: /de/net/aspose.words/documentbuilder/italic/
---
## DocumentBuilder.Italic property

Wahr, wenn die Schriftart kursiv formatiert ist.

```csharp
public bool Italic { get; set; }
```

### Beispiele

Zeigt, wie MERGEFIELDs mit Daten mit einem Document Builder anstelle eines Seriendrucks gefüllt werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Einfügen einiger MERGEFIELDS, die Daten aus gleichnamigen Spalten in eine Datenquelle beim Seriendruck übernehmen,
// und füllen Sie sie dann manuell aus.
builder.InsertField(" MERGEFIELD Chairman ");
builder.InsertField(" MERGEFIELD ChiefFinancialOfficer ");
builder.InsertField(" MERGEFIELD ChiefTechnologyOfficer ");

builder.MoveToMergeField("Chairman");
builder.Bold = true;
builder.Writeln("John Doe");

builder.MoveToMergeField("ChiefFinancialOfficer");
builder.Italic = true;
builder.Writeln("Jane Doe");

builder.MoveToMergeField("ChiefTechnologyOfficer");
builder.Italic = true;
builder.Writeln("John Bloggs");

doc.Save(ArtifactsDir + "DocumentBuilder.FillMergeFields.docx");
```

### Siehe auch

* class [DocumentBuilder](../)
* namensraum [Aspose.Words](../../documentbuilder/)
* Montage [Aspose.Words](../../../)


