---
title: PdfSaveOptions.CreateNoteHyperlinks
second_title: Справочник по API Aspose.Words для .NET
description: PdfSaveOptions свойство. Указывает следует ли преобразовывать ссылки на сноску/концевую сноску в основном текстовом материале в активные гиперссылки. При щелчке гиперссылка приведет к соответствующей сноске/концевой сноске. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 40
url: /ru/net/aspose.words.saving/pdfsaveoptions/createnotehyperlinks/
---
## PdfSaveOptions.CreateNoteHyperlinks property

Указывает, следует ли преобразовывать ссылки на сноску/концевую сноску в основном текстовом материале в активные гиперссылки. При щелчке гиперссылка приведет к соответствующей сноске/концевой сноске. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool CreateNoteHyperlinks { get; set; }
```

### Примеры

Показывает, как сделать обычные и концевые сноски гиперссылками.

```csharp
Document doc = new Document(MyDir + "Footnotes and endnotes.docx");

// Создаем объект "PdfSaveOptions", который мы можем передать в метод "Сохранить" документа
// для изменения того, как этот метод преобразует документ в .PDF.
PdfSaveOptions options = new PdfSaveOptions();

// Установите для свойства "CreateNoteHyperlinks" значение "true", чтобы включить все символы сносок/концевых сносок
// в тексте действуют как ссылки, которые при нажатии переносят нас к соответствующим сноскам/концевым сноскам.
// Установите для свойства "CreateNoteHyperlinks" значение "false", чтобы символы сносок/концевых сносок не ссылались ни на что.
options.CreateNoteHyperlinks = createNoteHyperlinks;

doc.Save(ArtifactsDir + "PdfSaveOptions.NoteHyperlinks.pdf", options);
```

### Смотрите также

* class [PdfSaveOptions](../)
* пространство имен [Aspose.Words.Saving](../../pdfsaveoptions/)
* сборка [Aspose.Words](../../../)


