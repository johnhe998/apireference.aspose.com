---
title: Range.UnlinkFields
second_title: Aspose.Words för .NET API Referens
description: Range metod. Tar bort länkar till fält i det här intervallet.
type: docs
weight: 100
url: /sv/net/aspose.words/range/unlinkfields/
---
## Range.UnlinkFields method

Tar bort länkar till fält i det här intervallet.

```csharp
public void UnlinkFields()
```

### Anmärkningar

Ersätter alla fält i det här intervallet med deras senaste resultat.

För att ta bort länkar till fält i hela dokumentet använd`UnlinkFields`.

### Exempel

Visar hur man tar bort länken till alla fält i ett intervall.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");

Section newSection = (Section)doc.Sections[0].Clone(true);
doc.Sections.Add(newSection);

doc.Sections[1].Range.UnlinkFields();
```

### Se även

* class [Range](../)
* namnutrymme [Aspose.Words](../../range/)
* hopsättning [Aspose.Words](../../../)


