---
title: Document.Protect
second_title: Aspose.Words för .NET API Referens
description: Document metod. Skyddar dokumentet från ändringar utan att ändra det befintliga lösenordet eller tilldelar ett slumpmässigt lösenord.
type: docs
weight: 630
url: /sv/net/aspose.words/document/protect/
---
## Protect(ProtectionType) {#protect}

Skyddar dokumentet från ändringar utan att ändra det befintliga lösenordet eller tilldelar ett slumpmässigt lösenord.

```csharp
public void Protect(ProtectionType type)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| type | ProtectionType | Anger skyddstypen för dokumentet. |

### Anmärkningar

När ett dokument är skyddat kan användaren endast göra begränsade ändringar, som att lägga till kommentarer, göra ändringar eller fylla i ett formulär.

När du skyddar ett dokument och dokumentet redan har ett skyddslösenord, ändras inte det befintliga skyddslösenordet.

När du skyddar ett dokument och dokumentet inte har ett skyddslösenord, tilldelar den här metoden ett slumpmässigt lösenord som gör det omöjligt att avskydda dokument i Microsoft Word, men du kan fortfarande avskydda dokumentet i Aspose.Words eftersom det inte kräva ett lösenord när du tar bort skyddet.

### Exempel

Visar hur man stänger av skyddet för en sektion.

```csharp
Document doc = new Document();

DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Section 1. Hello world!");
builder.InsertBreak(BreakType.SectionBreakNewPage);

builder.Writeln("Section 2. Hello again!");
builder.Write("Please enter text here: ");
builder.InsertTextInput("TextInput1", TextFormFieldType.Regular, "", "Placeholder text", 0);

// Använd skrivskydd på varje avsnitt i dokumentet.
doc.Protect(ProtectionType.AllowOnlyFormFields);

// Stäng av skrivskyddet för det första avsnittet.
doc.Sections[0].ProtectedForForms = false;

// I detta utdatadokument kommer vi att kunna redigera det första avsnittet fritt,
// och vi kommer bara att kunna redigera innehållet i formulärfältet i det andra avsnittet.
doc.Save(ArtifactsDir + "Section.Protect.docx");
```

### Se även

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)

---

## Protect(ProtectionType, string) {#protect_1}

Skyddar dokumentet från ändringar och anger valfritt ett skyddslösenord.

```csharp
public void Protect(ProtectionType type, string password)
```

| Parameter | Typ | Beskrivning |
| --- | --- | --- |
| type | ProtectionType | Anger skyddstypen för dokumentet. |
| password | String | Lösenordet att skydda dokumentet med. Ange null eller tom sträng om du vill skydda dokumentet utan lösenord. |

### Anmärkningar

När ett dokument är skyddat kan användaren endast göra begränsade ändringar, som att lägga till kommentarer, göra ändringar eller fylla i ett formulär.

Observera att dokumentskydd skiljer sig från skrivskydd. Skrivskydd specificeras med hjälp av[`WriteProtection`](../writeprotection/).

### Exempel

Visar hur man skyddar och avskyddar ett dokument.

```csharp
Document doc = new Document();
doc.Protect(ProtectionType.ReadOnly, "password");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// Om vi öppnar det här dokumentet med Microsoft Word för att redigera det,
// vi kommer att behöva använda lösenordet för att komma igenom skyddet.
doc.Save(ArtifactsDir + "Document.Protect.docx");

// Observera att skyddet endast gäller för Microsoft Word-användare som öppnar vårt dokument.
// Vi har inte krypterat dokumentet på något sätt, och vi behöver inte lösenordet för att öppna och redigera det programmatiskt.
Document protectedDoc = new Document(ArtifactsDir + "Document.Protect.docx");

Assert.AreEqual(ProtectionType.ReadOnly, protectedDoc.ProtectionType);

DocumentBuilder builder = new DocumentBuilder(protectedDoc);
builder.Writeln("Text added to a protected document.");
// Det finns två sätt att ta bort skydd från ett dokument.
// 1 - Utan lösenord:
doc.Unprotect();

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);

doc.Protect(ProtectionType.ReadOnly, "NewPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

doc.Unprotect("WrongPassword");

Assert.AreEqual(ProtectionType.ReadOnly, doc.ProtectionType);

// 2 - Med rätt lösenord:
doc.Unprotect("NewPassword");

Assert.AreEqual(ProtectionType.NoProtection, doc.ProtectionType);
```

### Se även

* enum [ProtectionType](../../protectiontype/)
* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


