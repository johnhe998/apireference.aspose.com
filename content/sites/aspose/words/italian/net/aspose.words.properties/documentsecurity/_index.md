---
title: Enum DocumentSecurity
second_title: Aspose.Words per .NET API Reference
description: Aspose.Words.Properties.DocumentSecurity enum. Usato come valore per ilSecurity proprietà. Specifica il livello di sicurezza di un documento come valore numerico.
type: docs
weight: 4240
url: /it/net/aspose.words.properties/documentsecurity/
---
## DocumentSecurity enumeration

Usato come valore per il[`Security`](../builtindocumentproperties/security/) proprietà. Specifica il livello di sicurezza di un documento come valore numerico.

```csharp
[Flags]
public enum DocumentSecurity
```

### I valori

| Nome | Valore | Descrizione |
| --- | --- | --- |
| None | `0` | Non ci sono stati di sicurezza specificati dalla proprietà. |
| PasswordProtected | `1` | Il documento è protetto da password. (Finora la nota non è mai stata vista in un documento). |
| ReadOnlyRecommended | `2` | Il documento da aprire in sola lettura, se possibile, ma l'impostazione può essere sovrascritta. |
| ReadOnlyEnforced | `4` | Il documento da aprire sempre in sola lettura. |
| ReadOnlyExceptAnnotations | `8` | Il documento da aprire sempre in sola lettura ad eccezione delle annotazioni. |

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

* spazio dei nomi [Aspose.Words.Properties](../../aspose.words.properties/)
* assemblea [Aspose.Words](../../)


