---
title: BuiltInDocumentProperties.HyperlinkBase
second_title: Справочник по API Aspose.Words для .NET
description: BuiltInDocumentProperties свойство. Указывает базовую строку используемую для оценки относительных гиперссылок в этом документе.
type: docs
weight: 120
url: /ru/net/aspose.words.properties/builtindocumentproperties/hyperlinkbase/
---
## BuiltInDocumentProperties.HyperlinkBase property

Указывает базовую строку, используемую для оценки относительных гиперссылок в этом документе.

```csharp
public string HyperlinkBase { get; set; }
```

### Примечания

Aspose.Words не использует это свойство.

### Примеры

Показывает, как сохранить базовую часть гиперссылки в свойствах документа.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставить относительную гиперссылку на документ в локальной файловой системе с именем "Document.docx".
// Щелчок по ссылке в Microsoft Word откроет указанный документ, если он доступен.
builder.InsertHyperlink("Relative hyperlink", "Document.docx", false);

// Эта ссылка относительная. Если в той же папке нет "Document.docx"
// как документ, содержащий эту ссылку, ссылка будет разорвана.
Assert.False(File.Exists(ArtifactsDir + "Document.docx"));
doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.BrokenLink.docx");

// Документ, на который мы пытаемся установить ссылку, находится в другом каталоге, чем тот, в котором мы планируем сохранить документ.
// Мы могли бы исправить такие ссылки, поместив в каждую из них абсолютное имя файла. 
// В качестве альтернативы мы могли бы предоставить базовую ссылку, по которой каждая гиперссылка с относительным именем файла
// будет добавлено к ссылке, когда мы нажмем на нее. 
BuiltInDocumentProperties properties = doc.BuiltInDocumentProperties;
properties.HyperlinkBase = MyDir;

Assert.True(File.Exists(properties.HyperlinkBase + ((FieldHyperlink)doc.Range.Fields[0]).Address));

doc.Save(ArtifactsDir + "DocumentProperties.HyperlinkBase.WorkingLink.docx");
```

### Смотрите также

* class [BuiltInDocumentProperties](../)
* пространство имен [Aspose.Words.Properties](../../builtindocumentproperties/)
* сборка [Aspose.Words](../../../)


