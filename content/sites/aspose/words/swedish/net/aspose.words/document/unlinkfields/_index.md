---
title: Document.UnlinkFields
second_title: Aspose.Words för .NET API Referens
description: Document metod. Tar bort länkar till fält i hela dokumentet.
type: docs
weight: 710
url: /sv/net/aspose.words/document/unlinkfields/
---
## Document.UnlinkFields method

Tar bort länkar till fält i hela dokumentet.

```csharp
public void UnlinkFields()
```

### Anmärkningar

Ersätter alla fält i hela dokumentet med deras senaste resultat.

För att ta bort länkar till fält i en specifik del av dokumentet använd[`UnlinkFields`](../../range/unlinkfields/).

### Exempel

Visar hur man tar bort länken till alla fält i dokumentet.

```csharp
Document doc = new Document(MyDir + "Linked fields.docx");

doc.UnlinkFields();
```

### Se även

* class [Document](../)
* namnutrymme [Aspose.Words](../../document/)
* hopsättning [Aspose.Words](../../../)


