---
title: UpdateDocumentProperties
second_title: Aspose.Slides für .NET-API-Referenz
description: Aktualisiert die Eigenschaften der gebundenen Präsentation.
type: docs
weight: 80
url: /de/net/aspose.slides/ipresentationinfo/updatedocumentproperties/
---
## IPresentationInfo.UpdateDocumentProperties method

Aktualisiert die Eigenschaften der gebundenen Präsentation.

```csharp
public void UpdateDocumentProperties(IDocumentProperties documentProperties)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| documentProperties | IDocumentProperties | Dokumenteigenschaften[`IDocumentProperties`](../../idocumentproperties) |

### Beispiele

Dieses Beispiel zeigt, wie die aufgerufen wird`UpdateDocumentProperties` Methode to aktualisiert die Dokumenteigenschaften, die durch den Aufruf von zurückgegeben werden[`ReadDocumentProperties`](../readdocumentproperties) Methode.

```csharp
IPresentationInfo info = PresentationFactory.Instance.GetPresentationInfo("pres.pptx");
IDocumentProperties props = info.ReadDocumentProperties();
props.Subject = "New subject";
props.LastSavedTime = DateTime.UtcNow;
info.UpdateDocumentProperties(props);
info.WriteBindedPresentation("new_pres.pptx");
```

### Siehe auch

* interface [IDocumentProperties](../../idocumentproperties)
* interface [IPresentationInfo](../../ipresentationinfo)
* namensraum [Aspose.Slides](../../ipresentationinfo)
* Montage [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
