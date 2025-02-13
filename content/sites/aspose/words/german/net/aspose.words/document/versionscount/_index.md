---
title: Document.VersionsCount
second_title: Aspose.Words für .NET-API-Referenz
description: Document eigendom. Ruft die Anzahl der Dokumentversionen ab die im DOCDokument gespeichert wurde.
type: docs
weight: 440
url: /de/net/aspose.words/document/versionscount/
---
## Document.VersionsCount property

Ruft die Anzahl der Dokumentversionen ab, die im DOC-Dokument gespeichert wurde.

```csharp
public int VersionsCount { get; }
```

### Bemerkungen

Versionen in Microsoft Word werden über das Menü Datei/Versionen aufgerufen. Microsoft Word unterstützt -Versionen nur für DOC-Dateien.

Mit dieser Eigenschaft kann festgestellt werden, ob in diesem document Dokumentversionen gespeichert waren, bevor es in Aspose.Words geöffnet wurde. Aspose.Words bietet keine weitere Unterstützung für Dokumentversionen. Wenn Sie dieses Dokument mit Aspose.Words speichern, wird das Dokument ohne Versionen gespeichert.

### Beispiele

Zeigt, wie Sie mit der Versionszählerfunktion älterer Microsoft Word-Dokumente arbeiten.

```csharp
Document doc = new Document(MyDir + "Versions.doc");

// Wir können diese Eigenschaft eines Dokuments lesen, aber wir können sie beim Speichern nicht beibehalten.
Assert.AreEqual(4, doc.VersionsCount);

doc.Save(ArtifactsDir + "Document.VersionsCount.doc");      
doc = new Document(ArtifactsDir + "Document.VersionsCount.doc");

Assert.AreEqual(0, doc.VersionsCount);
```

### Siehe auch

* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


