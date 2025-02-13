---
title: DocumentBuilder.InsertTableOfContents
second_title: Справочник по API Aspose.Words для .NET
description: DocumentBuilder метод. Вставляет поле TOC оглавление в документ.
type: docs
weight: 440
url: /ru/net/aspose.words/documentbuilder/inserttableofcontents/
---
## DocumentBuilder.InsertTableOfContents method

Вставляет поле TOC (оглавление) в документ.

```csharp
public Field InsertTableOfContents(string switches)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| switches | String | Поле TOC переключается. |

### Примечания

Этот метод вставляет поле TOC (оглавление) в документ по адресу текущей позиции.

Оглавление в документе Word может быть построено несколькими способами и отформатировано с использованием различных параметров. То, как таблица строится и отображается в Microsoft Word, управляется переключателями поля.

Самый простой способ указать переключатели — вставить и настроить таблицу содержимого в документ Word с помощью меню Вставка-&gt;Справочник-&gt;Указатель и таблицы, затем включить отображение кодов полей, чтобы увидеть переключатели. Вы можете нажать Alt+F9 в Microsoft Word, чтобы включить или выключить отображение кодов полей.

Например, после создания оглавления в документ вставляется следующее поле: **{ ТОС \o "1-3" \h \z \u }** . Вы можете скопировать **\o "1-3" \h \z \u** и используйте его как параметр переключателей.

Обратите внимание, что **Вставить Таблицу Содержимого** только вставит поле TOC, но фактически не создаст оглавление. Оглавление строится Microsoft Word при обновлении поля.

Если вы вставите оглавление с помощью этого метода, а затем откроете файл в Microsoft Word, вы не увидите оглавление, поскольку оглавление field еще не обновлено.

В Microsoft Word поля не обновляются автоматически при открытии документа, , но вы можете обновить поля в документе в любое время, нажав F9.

### Примеры

Показывает, как вставить оглавление (TOC) в документ, используя стили заголовков в качестве записей.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Вставляем оглавление для первой страницы документа.
// Настройте таблицу так, чтобы она выбирала абзацы с заголовками уровней от 1 до 3.
// Кроме того, установите его записи в качестве гиперссылок, которые приведут нас
// к местоположению заголовка при щелчке левой кнопкой мыши в Microsoft Word.
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
builder.InsertBreak(BreakType.PageBreak);

// Заполняем оглавление, добавляя абзацы со стилями заголовков.
// Каждый такой заголовок с уровнем от 1 до 3 создаст запись в таблице.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading4;
builder.Writeln("Heading 3.1.3.1");
builder.Writeln("Heading 3.1.3.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");

// Оглавление — это поле типа, которое необходимо обновить для отображения актуального результата.
doc.UpdateFields();
doc.Save(ArtifactsDir + "DocumentBuilder.InsertToc.docx");
```

### Смотрите также

* class [Field](../../../aspose.words.fields/field/)
* class [DocumentBuilder](../)
* пространство имен [Aspose.Words](../../documentbuilder/)
* сборка [Aspose.Words](../../../)


