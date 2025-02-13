---
title: BuiltInDocumentProperties.Security
second_title: Aspose.Words für .NET-API-Referenz
description: BuiltInDocumentProperties eigendom. Gibt die Sicherheitsstufe eines Dokuments als Zahlenwert an.
type: docs
weight: 250
url: /de/net/aspose.words.properties/builtindocumentproperties/security/
---
## BuiltInDocumentProperties.Security property

Gibt die Sicherheitsstufe eines Dokuments als Zahlenwert an.

```csharp
public DocumentSecurity Security { get; set; }
```

### Bemerkungen

Verwenden Sie diese Eigenschaft nur zu Informationszwecken, da Microsoft Word diese Eigenschaft nicht immer festlegt. Diese Eigenschaft ist nur in DOC- und OOXML-Dokumenten verfügbar.

Um ein Dokument zu schützen oder den Schutz aufzuheben, verwenden Sie the [`Protect`](../../../aspose.words/document/protect/) und[`Unprotect`](../../../aspose.words/document/unprotect/)Methoden.

Aspose.Words aktualisiert diese Eigenschaft auf einen korrekten Wert, bevor ein Dokument gespeichert wird.

### Beispiele

Zeigt, wie Dokumenteigenschaften verwendet werden, um die Sicherheitsstufe eines Dokuments anzuzeigen.

```csharp
Document doc = new Document();

Assert.AreEqual(DocumentSecurity.None, doc.BuiltInDocumentProperties.Security);

// Wenn wir ein Dokument als schreibgeschützt konfigurieren, zeigt es diesen Status mit der eingebauten Eigenschaft "Sicherheit" an.
doc.WriteProtection.ReadOnlyRecommended = true;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyRecommended, 
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx").BuiltInDocumentProperties.Security);

// Ein Dokument schreibschützen und dann seine Sicherheitsstufe überprüfen.
doc = new Document();

Assert.False(doc.WriteProtection.IsWriteProtected);

doc.WriteProtection.SetPassword("MyPassword");

Assert.True(doc.WriteProtection.ValidatePassword("MyPassword"));
Assert.True(doc.WriteProtection.IsWriteProtected);

doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyEnforced,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx").BuiltInDocumentProperties.Security);

// "Sicherheit" ist eine beschreibende Eigenschaft. Wir können seinen Wert manuell bearbeiten.
doc = new Document();

doc.Protect(ProtectionType.AllowOnlyComments, "MyPassword");
doc.BuiltInDocumentProperties.Security = DocumentSecurity.ReadOnlyExceptAnnotations;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyExceptAnnotations,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx").BuiltInDocumentProperties.Security);
```

### Siehe auch

* enum [DocumentSecurity](../../documentsecurity/)
* class [BuiltInDocumentProperties](../)
* namensraum [Aspose.Words.Properties](../../builtindocumentproperties/)
* Montage [Aspose.Words](../../../)


