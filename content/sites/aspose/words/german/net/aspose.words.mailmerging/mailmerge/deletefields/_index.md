---
title: MailMerge.DeleteFields
second_title: Aspose.Words für .NET-API-Referenz
description: MailMerge methode. Entfernt Serienbrieffelder aus dem Dokument.
type: docs
weight: 170
url: /de/net/aspose.words.mailmerging/mailmerge/deletefields/
---
## MailMerge.DeleteFields method

Entfernt Serienbrieffelder aus dem Dokument.

```csharp
public void DeleteFields()
```

### Bemerkungen

Diese Methode entfernt die Felder MERGEFIELD und NEXT aus dem Dokument.

Diese Methode kann nützlich sein, wenn Ihre Seriendruckoperation nicht immer benötigt, um alle Felder im Dokument auszufüllen. Verwenden Sie diese Methode, um alle verbleibenden Seriendruckfelder zu entfernen.

### Beispiele

Zeigt, wie alle MERGEFIELDs aus einem Dokument gelöscht werden.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Dear ");
builder.InsertField(" MERGEFIELD FirstName ");
builder.Write(" ");
builder.InsertField(" MERGEFIELD LastName ");
builder.Writeln(",");
builder.Writeln("Greetings!");

Assert.AreEqual(
    "Dear \u0013 MERGEFIELD FirstName \u0014«FirstName»\u0015 \u0013 MERGEFIELD LastName \u0014«LastName»\u0015,\rGreetings!", 
    doc.GetText().Trim());

doc.MailMerge.DeleteFields();

Assert.AreEqual("Dear  ,\rGreetings!", doc.GetText().Trim());
```

### Siehe auch

* class [MailMerge](../)
* namensraum [Aspose.Words.MailMerging](../../mailmerge/)
* Montage [Aspose.Words](../../../)


