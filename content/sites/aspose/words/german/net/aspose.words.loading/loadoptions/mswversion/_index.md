---
title: LoadOptions.MswVersion
second_title: Aspose.Words für .NET-API-Referenz
description: LoadOptions eigendom. Ermöglicht die Angabe dass der Dokumentladeprozess mit einer bestimmten MS WordVersion übereinstimmen soll. Der Standardwert istWord2019
type: docs
weight: 100
url: /de/net/aspose.words.loading/loadoptions/mswversion/
---
## LoadOptions.MswVersion property

Ermöglicht die Angabe, dass der Dokumentladeprozess mit einer bestimmten MS Word-Version übereinstimmen soll. Der Standardwert istWord2019

```csharp
public MsWordVersion MswVersion { get; set; }
```

### Bemerkungen

Unterschiedliche Word-Versionen handhaben möglicherweise bestimmte Aspekte des Dokumentinhalts und die Formatierung während des Ladevorgangs leicht unterschiedlich , was zu geringfügigen Unterschieden im Dokumentobjektmodell führen kann.

### Beispiele

Zeigt, wie der Ladevorgang einer bestimmten Microsoft Word-Version beim Laden von Dokumenten emuliert wird.

```csharp
// Standardmäßig lädt Aspose.Words Dokumente gemäß der Microsoft Word 2019-Spezifikation.
LoadOptions loadOptions = new LoadOptions();

Assert.AreEqual(MsWordVersion.Word2019, loadOptions.MswVersion);

// In diesem Dokument fehlt der standardmäßige Absatzformatierungsstil.
// Dieser Standardstil wird neu generiert, wenn wir das Dokument entweder mit Microsoft Word oder Aspose.Words laden.
loadOptions.MswVersion = MsWordVersion.Word2007;
Document doc = new Document(MyDir + "Document.docx", loadOptions);

// Der Zeilenabstand des Stils hat diesen Wert, wenn er von der Microsoft Word 2007-Spezifikation geladen wird.
Assert.AreEqual(12.95d, doc.Styles.DefaultParagraphFormat.LineSpacing, 0.01d);
```

### Siehe auch

* enum [MsWordVersion](../../../aspose.words.settings/mswordversion/)
* class [LoadOptions](../)
* namensraum [Aspose.Words.Loading](../../loadoptions/)
* Montage [Aspose.Words](../../../)


