---
title: HtmlFixedSaveOptions.OptimizeOutput
second_title: Aspose.Words für .NET-API-Referenz
description: HtmlFixedSaveOptions eigendom. Flag gibt an ob es erforderlich ist die Ausgabe zu optimieren. Wenn dieses Flag gesetzt ist werden redundante verschachtelte Leinwände und leere Leinwände entfernt werden auch benachbarte Glyphen mit derselben Formatierung verkettet. Hinweis Die Genauigkeit der Inhaltsanzeige kann beeinträchtigt werden wenn diese Eigenschaft ist auf true gesetzt. Standard ist true.
type: docs
weight: 100
url: /de/net/aspose.words.saving/htmlfixedsaveoptions/optimizeoutput/
---
## HtmlFixedSaveOptions.OptimizeOutput property

Flag gibt an, ob es erforderlich ist, die Ausgabe zu optimieren. Wenn dieses Flag gesetzt ist, werden redundante verschachtelte Leinwände und leere Leinwände entfernt, werden auch benachbarte Glyphen mit derselben Formatierung verkettet. Hinweis: Die Genauigkeit der Inhaltsanzeige kann beeinträchtigt werden, wenn diese Eigenschaft ist auf true gesetzt. Standard ist true.

```csharp
public override bool OptimizeOutput { get; set; }
```

### Beispiele

Zeigt, wie ein Dokument vereinfacht wird, wenn es in HTML gespeichert wird, indem verschiedene redundante Objekte entfernt werden.

```csharp
Document doc = new Document(MyDir + "Rendering.docx");

HtmlFixedSaveOptions saveOptions = new HtmlFixedSaveOptions { OptimizeOutput = optimizeOutput };

doc.Save(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html", saveOptions);

// Die Größe der optimierten Version des Dokuments beträgt fast ein Drittel der Größe des nicht optimierten Dokuments.
Assert.AreEqual(optimizeOutput ? 62521 : 191770,
    new FileInfo(ArtifactsDir + "HtmlFixedSaveOptions.OptimizeGraphicsOutput.html").Length, 200);
```

### Siehe auch

* class [HtmlFixedSaveOptions](../)
* namensraum [Aspose.Words.Saving](../../htmlfixedsaveoptions/)
* Montage [Aspose.Words](../../../)


