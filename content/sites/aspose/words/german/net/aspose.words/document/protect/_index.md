---
title: Document.Protect
second_title: Aspose.Words für .NET-API-Referenz
description: Document methode. Schützt das Dokument vor Änderungen ohne das bestehende Passwort zu ändern oder vergibt ein zufälliges Passwort.
type: docs
weight: 630
url: /de/net/aspose.words/document/protect/
---
## Protect(ProtectionType) {#protect}

Schützt das Dokument vor Änderungen ohne das bestehende Passwort zu ändern oder vergibt ein zufälliges Passwort.

```csharp
public void Protect(ProtectionType type)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| type | ProtectionType | Gibt den Schutztyp für das Dokument an. |

### Bemerkungen

Wenn ein Dokument geschützt ist, kann der Benutzer nur begrenzte Änderungen vornehmen, wie z. B. Anmerkungen hinzufügen, Änderungen vornehmen oder ein Formular ausfüllen.

Wenn Sie ein Dokument schützen und das Dokument bereits über ein Schutzkennwort verfügt, wird das vorhandene Schutzkennwort nicht geändert.

Wenn Sie ein Dokument schützen und das Dokument kein Schutzpasswort hat, weist diese Methode ein zufälliges Passwort zu, das es unmöglich macht, den Schutz des Dokuments in Microsoft Word aufzuheben, aber Sie können den Schutz des Dokuments in Aspose.Words immer noch aufheben, da es kein hat. erfordern ein Passwort, wenn der Schutz aufgehoben wird.

### Beispiele

Zeigt, wie der Schutz für einen Abschnitt deaktiviert wird.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Section 1. Hello world!");
builder.InsertBreak(BreakType.SectionBreakNewPage);

builder.Writeln("Section 2. Hello again!");
builder.Write("Please enter text here: ");
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// Schreibschutz auf jeden Abschnitt im Dokument anwenden.
doc.Protect(ProtectionType.AllowOnlyFormFields);

// Schreibschutz für den ersten Abschnitt deaktivieren.
doc.Sections[0].ProtectedForForms = false;

// In diesem Ausgabedokument können wir den ersten Abschnitt frei bearbeiten,
// und wir können nur den Inhalt des Formularfelds im zweiten Abschnitt bearbeiten.
doc.Save(ArtifactsDir + "Section.Protect.docx");
```

### Siehe auch

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)

---

## Protect(ProtectionType, string) {#protect_1}

Schützt das Dokument vor Änderungen und setzt optional ein Schutzkennwort.

```csharp
public void Protect(ProtectionType type, string password)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| type | ProtectionType | Gibt den Schutztyp für das Dokument an. |
| password | String | Das Passwort, mit dem das Dokument geschützt werden soll. Geben Sie null oder eine leere Zeichenfolge an, wenn Sie das Dokument ohne Passwort schützen möchten. |

### Bemerkungen

Wenn ein Dokument geschützt ist, kann der Benutzer nur begrenzte Änderungen vornehmen, wie z. B. Anmerkungen hinzufügen, Änderungen vornehmen oder ein Formular ausfüllen.

Beachten Sie, dass sich der Dokumentenschutz vom Schreibschutz unterscheidet. Der Schreibschutz wird mit angegeben[`WriteProtection`](../writeprotection/).

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


