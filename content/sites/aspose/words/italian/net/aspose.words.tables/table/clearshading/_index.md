---
title: Table.ClearShading
second_title: Aspose.Words per .NET API Reference
description: Table metodo. Rimuove tutta lombreggiatura sulla tabella.
type: docs
weight: 380
url: /it/net/aspose.words.tables/table/clearshading/
---
## Table.ClearShading method

Rimuove tutta l'ombreggiatura sulla tabella.

```csharp
public void ClearShading()
```

### Esempi

Mostra come applicare un bordo del contorno a una tabella.

```csharp
Document doc = new Document(MyDir + "Tables.docx");
Table table = doc.FirstSection.Body.Tables[0];

// Allinea la tabella al centro della pagina.
table.Alignment = TableAlignment.Center;

// Cancella i bordi e l'ombreggiatura esistenti dalla tabella.
table.ClearBorders();
table.ClearShading();

// Aggiungi bordi verdi al contorno della tabella.
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);

// Riempi le celle con un colore solido verde chiaro.
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);

doc.Save(ArtifactsDir + "Table.SetOutlineBorders.docx");
```

### Guarda anche

* class [Table](../)
* spazio dei nomi [Aspose.Words.Tables](../../table/)
* assemblea [Aspose.Words](../../../)


