---
title: FixedPageSaveOptions.OptimizeOutput
second_title: Aspose.Words für .NET-API-Referenz
description: FixedPageSaveOptions eigendom. Flag gibt an ob es erforderlich ist die Ausgabe zu optimieren. Wenn dieses Flag gesetzt ist werden redundante verschachtelte Leinwände und leere Leinwände entfernt werden auch benachbarte Glyphen mit derselben Formatierung verkettet. Hinweis Die Genauigkeit der Inhaltsanzeige kann beeinträchtigt werden wenn diese Eigenschaft ist auf true gesetzt. Standard ist false.
type: docs
weight: 50
url: /de/net/aspose.words.saving/fixedpagesaveoptions/optimizeoutput/
---
## FixedPageSaveOptions.OptimizeOutput property

Flag gibt an, ob es erforderlich ist, die Ausgabe zu optimieren. Wenn dieses Flag gesetzt ist, werden redundante verschachtelte Leinwände und leere Leinwände entfernt, werden auch benachbarte Glyphen mit derselben Formatierung verkettet. Hinweis: Die Genauigkeit der Inhaltsanzeige kann beeinträchtigt werden, wenn diese Eigenschaft ist auf true gesetzt. Standard ist false.

```csharp
public virtual bool OptimizeOutput { get; set; }
```

### Beispiele

Zeigt, wie Dokumentobjekte beim Speichern in xps optimiert werden.

```csharp
Document doc = new Document(MyDir + "Unoptimized document.docx");

// Erstellen Sie ein "XpsSaveOptions"-Objekt, das an die "Save"-Methode des Dokuments übergeben wird
// um zu ändern, wie diese Methode das Dokument in .XPS konvertiert.
XpsSaveOptions saveOptions = new XpsSaveOptions();

// Setzen Sie die Eigenschaft „OptimizeOutput“ auf „true“, um Maßnahmen wie das Entfernen verschachtelter oder leerer Leinwände zu ergreifen
// und Verketten benachbarter Läufe mit identischer Formatierung, um den Inhalt des Ausgabedokuments zu optimieren.
// Dies kann das Erscheinungsbild des Dokuments beeinträchtigen.
// Setzen Sie die Eigenschaft "OptimizeOutput" auf "false", um das Dokument normal zu speichern.
saveOptions.OptimizeOutput = optimizeOutput;

doc.Save(ArtifactsDir + "XpsSaveOptions.OptimizeOutput.xps", saveOptions);
```

### Siehe auch

* class [FixedPageSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../fixedpagesaveoptions/)
* Montage [Aspose.Words](../../../)


