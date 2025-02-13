---
title: Document.AppendDocument
second_title: Aspose.Words für .NET-API-Referenz
description: Document methode. Hängt das angegebene Dokument an das Ende dieses Dokuments an.
type: docs
weight: 510
url: /de/net/aspose.words/document/appenddocument/
---
## AppendDocument(Document, ImportFormatMode) {#appenddocument}

Hängt das angegebene Dokument an das Ende dieses Dokuments an.

```csharp
public void AppendDocument(Document srcDoc, ImportFormatMode importFormatMode)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| srcDoc | Document | Das anzuhängende Dokument. |
| importFormatMode | ImportFormatMode | Gibt an, wie kollidierende Stilformatierungen zusammengeführt werden. |

### Beispiele

Zeigt, wie ein Dokument an das Ende eines anderen Dokuments angehängt wird.

```csharp
Document srcDoc = new Document();
srcDoc.FirstSection.Body.AppendParagraph("Source document text. ");

Document dstDoc = new Document();
dstDoc.FirstSection.Body.AppendParagraph("Destination document text. ");

// Quelldokument unter Beibehaltung der Formatierung an das Zieldokument anhängen,
// dann das Quelldokument im lokalen Dateisystem speichern.
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
dstDoc.Save(ArtifactsDir + "Document.AppendDocument.docx");
```

Zeigt, wie alle Dokumente in einem Ordner an das Ende eines Vorlagendokuments angehängt werden.

```csharp
Document dstDoc = new Document();

DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Template Document");
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Normal;
builder.Writeln("Some content here");

// Alle unverschlüsselten Dokumente mit der Erweiterung .doc anhängen
// von unserem lokalen Dateisystemverzeichnis zum Basisdokument.
List<string> docFiles = Directory.GetFiles(MyDir, "*.doc").Where(item => item.EndsWith(".doc")).ToList();
foreach (string fileName in docFiles)
{
    FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);
    if (info.IsEncrypted)
        continue;

    Document srcDoc = new Document(fileName);
    dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
}

dstDoc.Save(ArtifactsDir + "Document.AppendAllDocumentsInFolder.doc");
```

### Siehe auch

* enum [ImportFormatMode](../../importformatmode/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)

---

## AppendDocument(Document, ImportFormatMode, ImportFormatOptions) {#appenddocument_1}

Hängt das angegebene Dokument an das Ende dieses Dokuments an.

```csharp
public void AppendDocument(Document srcDoc, ImportFormatMode importFormatMode, 
    ImportFormatOptions importFormatOptions)
```

| Parameter | Typ | Beschreibung |
| --- | --- | --- |
| srcDoc | Document | Das anzuhängende Dokument. |
| importFormatMode | ImportFormatMode | Gibt an, wie kollidierende Stilformatierungen zusammengeführt werden. |
| importFormatOptions | ImportFormatOptions | Ermöglicht die Angabe von Optionen, die sich auf die Formatierung eines Ergebnisdokuments auswirken. |

### Beispiele

Zeigt, wie Konflikte im Listenstil verwaltet werden, während ein Klon eines Dokuments an sich selbst angehängt wird.

```csharp
Document srcDoc = new Document(MyDir + "List item.docx");
Document dstDoc = new Document(MyDir + "List item.docx");

// Wenn es einen Konflikt zwischen Listenstilen gibt, wenden Sie das Listenformat des Quelldokuments an.
// Setzen Sie die Eigenschaft "KeepSourceNumbering" auf "false", um keine Listennummern in das Zieldokument zu importieren.
// Setzen Sie die Eigenschaft "KeepSourceNumbering" auf "true", importieren Sie alle Konflikte
// Nummerierung im Listenstil mit dem gleichen Aussehen wie im Quelldokument.
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.MoveToDocumentEnd();
builder.InsertBreak(BreakType.SectionBreakNewPage);

ImportFormatOptions options = new ImportFormatOptions();
options.KeepSourceNumbering = keepSourceNumbering;
builder.InsertDocument(srcDoc, ImportFormatMode.KeepSourceFormatting, options);

dstDoc.UpdateListLabels();
```

Zeigt, wie Konflikte im Listenstil beim Einfügen eines Dokuments verwaltet werden.

```csharp
Document dstDoc = new Document();
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.InsertBreak(BreakType.ParagraphBreak);

dstDoc.Lists.Add(ListTemplate.NumberDefault);
Aspose.Words.Lists.List list = dstDoc.Lists[0];

builder.ListFormat.List = list;

for (int i = 1; i <= 15; i++)
    builder.Write($"List Item {i}\n");

Document attachDoc = (Document)dstDoc.Clone(true);

// Wenn es einen Konflikt zwischen Listenstilen gibt, wenden Sie das Listenformat des Quelldokuments an.
// Setzen Sie die Eigenschaft "KeepSourceNumbering" auf "false", um keine Listennummern in das Zieldokument zu importieren.
// Setzen Sie die Eigenschaft "KeepSourceNumbering" auf "true", importieren Sie alle Konflikte
// Nummerierung im Listenstil mit dem gleichen Aussehen wie im Quelldokument.
ImportFormatOptions importOptions = new ImportFormatOptions();
importOptions.KeepSourceNumbering = keepSourceNumbering;

builder.InsertBreak(BreakType.SectionBreakNewPage);
builder.InsertDocument(attachDoc, ImportFormatMode.KeepSourceFormatting, importOptions);

dstDoc.Save(ArtifactsDir + "DocumentBuilder.InsertDocumentAndResolveStyles.docx");
```

Zeigt, wie Konflikte im Listenstil beim Anhängen eines Dokuments verwaltet werden.

```csharp
// Laden Sie ein Dokument mit Text in einem benutzerdefinierten Stil und klonen Sie es.
Document srcDoc = new Document(MyDir + "Custom list numbering.docx");
Document dstDoc = srcDoc.Clone();

// Wir haben jetzt zwei Dokumente, jedes mit einem identischen Stil namens "CustomStyle".
// Ändern Sie die Textfarbe für einen der Stile, um ihn vom anderen abzuheben.
dstDoc.Styles["CustomStyle"].Font.Color = Color.DarkRed;

// Wenn es einen Konflikt zwischen Listenstilen gibt, wenden Sie das Listenformat des Quelldokuments an.
// Setzen Sie die Eigenschaft "KeepSourceNumbering" auf "false", um keine Listennummern in das Zieldokument zu importieren.
// Setzen Sie die Eigenschaft "KeepSourceNumbering" auf "true", importieren Sie alle Konflikte
// Nummerierung im Listenstil mit dem gleichen Aussehen wie im Quelldokument.
ImportFormatOptions options = new ImportFormatOptions();
options.KeepSourceNumbering = keepSourceNumbering;

// Das Zusammenfügen zweier Dokumente mit unterschiedlichen Stilen, die denselben Namen haben, führt zu einem Stilkonflikt.
// Wir können einen Importformatmodus angeben, während wir Dokumente anhängen, um diesen Konflikt zu lösen.
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepDifferentStyles, options);
dstDoc.UpdateListLabels();

dstDoc.Save(ArtifactsDir + "DocumentBuilder.AppendDocumentAndResolveStyles.docx");
```

### Siehe auch

* enum [ImportFormatMode](../../importformatmode/)
* class [ImportFormatOptions](../../importformatoptions/)
* class [Document](../)
* namensraum [Aspose.Words](../../document/)
* Montage [Aspose.Words](../../../)


