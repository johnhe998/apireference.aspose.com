---
title: PageSetup.BorderAlwaysInFront
second_title: Aspose.Words per .NET API Reference
description: PageSetup proprietà. Specifica dove è posizionato il bordo della pagina rispetto a testi e oggetti intersecanti.
type: docs
weight: 20
url: /it/net/aspose.words/pagesetup/borderalwaysinfront/
---
## PageSetup.BorderAlwaysInFront property

Specifica dove è posizionato il bordo della pagina rispetto a testi e oggetti intersecanti.

```csharp
public bool BorderAlwaysInFront { get; set; }
```

### Esempi

Mostra come creare un ampio bordo a banda blu nella parte superiore della prima pagina.

```csharp
Document doc = new Document();

PageSetup pageSetup = doc.Sections[0].PageSetup;
pageSetup.BorderAlwaysInFront = false;
pageSetup.BorderDistanceFrom = PageBorderDistanceFrom.PageEdge;
pageSetup.BorderAppliesTo = PageBorderAppliesTo.FirstPage;

Border border = pageSetup.Borders[BorderType.Top];
border.LineStyle = LineStyle.Single;
border.LineWidth = 30;
border.Color = Color.Blue;
border.DistanceFromText = 0;

doc.Save(ArtifactsDir + "PageSetup.PageBorderProperties.docx");
```

### Guarda anche

* class [PageSetup](../)
* spazio dei nomi [Aspose.Words](../../pagesetup/)
* assemblea [Aspose.Words](../../../)


