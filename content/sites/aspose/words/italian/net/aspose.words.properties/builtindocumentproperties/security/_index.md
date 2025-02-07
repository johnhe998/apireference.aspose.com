---
title: BuiltInDocumentProperties.Security
second_title: Aspose.Words per .NET API Reference
description: BuiltInDocumentProperties proprietà. Specifica il livello di sicurezza di un documento come valore numerico.
type: docs
weight: 250
url: /it/net/aspose.words.properties/builtindocumentproperties/security/
---
## BuiltInDocumentProperties.Security property

Specifica il livello di sicurezza di un documento come valore numerico.

```csharp
public DocumentSecurity Security { get; set; }
```

### Osservazioni

Utilizzare questa proprietà solo a scopo informativo perché Microsoft Word non sempre imposta questa proprietà. Questa proprietà è disponibile solo nei documenti DOC e OOXML.

Per proteggere o annullare la protezione di un documento, utilizzare il [`Protect`](../../../aspose.words/document/protect/) e[`Unprotect`](../../../aspose.words/document/unprotect/)metodi.

Aspose.Words aggiorna questa proprietà a un valore corretto prima di salvare un documento.

### Esempi

Mostra come utilizzare le proprietà del documento per visualizzare il livello di sicurezza di un documento.

```csharp
Document doc = new Document();

Assert.AreEqual(DocumentSecurity.None, doc.BuiltInDocumentProperties.Security);

// Se configuriamo un documento in sola lettura, visualizzerà questo stato utilizzando la proprietà incorporata "Sicurezza".
doc.WriteProtection.ReadOnlyRecommended = true;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyRecommended, 
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyRecommended.docx").BuiltInDocumentProperties.Security);

// Proteggi in scrittura un documento, quindi verifica il suo livello di sicurezza.
doc = new Document();

Assert.False(doc.WriteProtection.IsWriteProtected);

doc.WriteProtection.SetPassword("MyPassword");

Assert.True(doc.WriteProtection.ValidatePassword("MyPassword"));
Assert.True(doc.WriteProtection.IsWriteProtected);

doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyEnforced,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyEnforced.docx").BuiltInDocumentProperties.Security);

// "Sicurezza" è una proprietà descrittiva. Possiamo modificarne il valore manualmente.
doc = new Document();

doc.Protect(ProtectionType.AllowOnlyComments, "MyPassword");
doc.BuiltInDocumentProperties.Security = DocumentSecurity.ReadOnlyExceptAnnotations;
doc.Save(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx");

Assert.AreEqual(DocumentSecurity.ReadOnlyExceptAnnotations,
    new Document(ArtifactsDir + "DocumentProperties.Security.ReadOnlyExceptAnnotations.docx").BuiltInDocumentProperties.Security);
```

### Guarda anche

* enum [DocumentSecurity](../../documentsecurity/)
* class [BuiltInDocumentProperties](../)
* spazio dei nomi [Aspose.Words.Properties](../../builtindocumentproperties/)
* assemblea [Aspose.Words](../../../)


