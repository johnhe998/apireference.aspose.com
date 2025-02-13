---
title: Document.ProtectionType
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. Ruft den aktuell aktiven Dokumentenschutztyp ab.
type: docs
weight: 310
url: /de/net/aspose.words/document/protectiontype/
---
## Document.ProtectionType property

Ruft den aktuell aktiven Dokumentenschutztyp ab.

```csharp
public ProtectionType ProtectionType { get; }
```

### Bemerkungen

Diese Eigenschaft ermöglicht es, den aktuell eingestellten Dokumentenschutztyp abzurufen. Um den Dokumentenschutztyp zu ändern, verwenden Sie die[`Protect`](../protect/) und[`Unprotect`](../unprotect/)Methoden.

Wenn ein Dokument geschützt ist, kann der Benutzer nur begrenzte Änderungen vornehmen, wie z. B. Anmerkungen hinzufügen, Änderungen vornehmen oder ein Formular ausfüllen.

Beachten Sie, dass sich der Dokumentenschutz vom Schreibschutz unterscheidet. Der Schreibschutz wird mit angegeben[`WriteProtection`](../writeprotection/)

### Beispiele

Zeigt, wie ein Dokument geschützt und der Schutz aufgehoben wird.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "password");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// Wenn wir dieses Dokument mit Microsoft Word öffnen, um es zu bearbeiten,
// Wir müssen das Passwort anwenden, um den Schutz zu überwinden.
doc.Save(ArtifactsDir + "Document.Protect.docx");

// Beachten Sie, dass der Schutz nur für Microsoft Word-Benutzer gilt, die unser Dokument öffnen.
// Wir haben das Dokument in keiner Weise verschlüsselt und benötigen kein Passwort, um es programmgesteuert zu öffnen und zu bearbeiten.
Document protectedDoc = new Document(ArtifactsDir + "Document.Protect.docx");

Assert.AreEqual(ProtectionType.ReadOnly, protectedDoc.ProtectionType);

DocumentBuilder builder = new DocumentBuilder(protectedDoc);
builder.Writeln("Text added to a protected document.");
// Es gibt zwei Möglichkeiten, den Schutz von einem Dokument zu entfernen.
// 1 - Ohne Passwort:
doc.Unprotect();

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);

doc.Protect(ProtectionType.ReadOnly, "NewPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

doc.Unprotect("WrongPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 2 - Mit dem richtigen Passwort:
doc.Unprotect("NewPassword");

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);
```

### Siehe auch

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


