---
title: FormField.RemoveField
second_title: Aspose.Words für .NET-API-Referenz
description: FormField methode. Entfernt das komplette Formularfeld nicht nur das Sonderzeichen des Formularfelds.
type: docs
weight: 240
url: /de/net/aspose.words.fields/formfield/removefield/
---
## FormField.RemoveField method

Entfernt das komplette Formularfeld, nicht nur das Sonderzeichen des Formularfelds.

```csharp
public void RemoveField()
```

### Bemerkungen

Wenn dem Formularfeld ein Lesezeichen zugeordnet ist, wird das Lesezeichen nicht entfernt.

### Beispiele

Zeigt, wie ein Formularfeld gelöscht wird.

```csharp
Document doc = new Document(MyDir + "Form fields.docx");

FormField formField = doc.Range.FormFields[3];
formField.RemoveField();
```

### Siehe auch

* class [FormField](../)
* namensraum [Aspose.Words.Fields](../../formfield/)
* Montage [Aspose.Words](../../../)


