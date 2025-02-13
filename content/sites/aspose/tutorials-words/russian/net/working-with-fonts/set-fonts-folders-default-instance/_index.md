---
title: Установить экземпляр папки шрифтов по умолчанию
linktitle: Установить экземпляр папки шрифтов по умолчанию
second_title: API обработки документов Aspose.Words
description: Пошаговое руководство по настройке папки шрифтов по умолчанию при рендеринге документа с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-fonts/set-fonts-folders-default-instance/
---

В этом руководстве мы пошагово проведем вас через процесс установки папки шрифтов по умолчанию при рендеринге документа с использованием Aspose.Words для .NET. Мы объясним прилагаемый исходный код C# и предоставим вам исчерпывающее руководство, которое поможет вам понять и реализовать эту функцию в ваших собственных проектах. В конце этого руководства вы узнаете, как установить папку шрифтов по умолчанию для использования при рендеринге ваших документов с помощью Aspose.Words для .NET.

## Шаг 1: Определите каталог документов
Во-первых, вам нужно указать путь к каталогу ваших документов. Это место, где вы хотите сохранить отредактированный визуализированный документ. Замените «КАТАЛОГ ВАШИХ ДОКУМЕНТОВ» на соответствующий путь.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Шаг 2: Установите папку шрифтов по умолчанию
Затем вы можете установить папку шрифтов по умолчанию, используя`FontSettings.DefaultInstance` класс и`SetFontsFolder()` метод. Укажите путь к папке шрифтов, которую вы хотите использовать в качестве папки по умолчанию.

```csharp
FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
```

## Шаг 3: Загрузите документ для рендеринга
 Теперь вы можете загрузить документ для рендеринга с помощью`Document` сорт. Обязательно укажите правильный путь к документу.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Шаг 4: Сохраните визуализированный документ
 Наконец, вы можете сохранить визуализированный документ в файл, используя`Save()` метод`Document` сорт. Обязательно укажите правильный путь и имя файла.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

### Пример исходного кода для установки экземпляра папки шрифтов по умолчанию с использованием Aspose.Words для .NET 

```csharp
//Путь к вашему каталогу документов
string dataDir = "YOUR DOCUMENT DIRECTORY";

FontSettings.DefaultInstance.SetFontsFolder("C:\\MyFonts\\", true);
Document doc = new Document(dataDir + "Rendering.docx");
doc.Save(dataDir + "WorkingWithFonts.SetFontsFoldersDefaultInstance.pdf");
```

## Заключение
В этом руководстве мы узнали, как установить папку шрифтов по умолчанию при рендеринге документа с использованием Aspose.Words для .NET. Следуя этому пошаговому руководству, вы можете легко указать, какую папку со шрифтами использовать в качестве папки по умолчанию при рендеринге ваших документов. Aspose.Words предлагает мощный и гибкий API для обработки слов со шрифтами в ваших документах. Обладая этими знаниями, вы можете контролировать и настраивать источники шрифтов, используемые при рендеринге ваших документов, в соответствии с вашими конкретными потребностями.

### Часто задаваемые вопросы

#### Q: Как установить папки шрифтов по умолчанию в Aspose.Words?

 A: Чтобы установить папки шрифтов по умолчанию в Aspose.Words, вы должны использовать`Fonts` класс и`SetFontsFolders` способ указать расположение папок пользовательских шрифтов.

#### В: Влияет ли установка папок шрифтов по умолчанию на все документы Word, обрабатываемые с помощью Aspose.Words?

О: Да, установка папок шрифтов по умолчанию влияет на все документы Word, обрабатываемые с помощью Aspose.Words. После того, как вы установили папки со шрифтами по умолчанию, Aspose.Words будет использовать эти папки для поиска шрифтов во всех документах.

#### В: Могу ли я установить несколько папок шрифтов по умолчанию в Aspose.Words?

 О: Да, вы можете установить несколько папок шрифтов по умолчанию в Aspose.Words. Вам просто нужно указать расположение папок пользовательских шрифтов с помощью`SetFontsFolders` метод`Fonts` сорт.

#### Q: Как я могу проверить папки шрифтов по умолчанию, установленные в настоящее время в Aspose.Words?

 A: Чтобы проверить папки шрифтов по умолчанию, определенные в Aspose.Words, вы можете использовать`GetFolders` метод`Fonts` class, чтобы получить расположение настроенных папок шрифтов.

#### В: Позволяет ли настройка папок шрифтов по умолчанию использовать пользовательские шрифты в моих документах Word?

О: Да, установив папки шрифтов по умолчанию, вы можете использовать пользовательские шрифты в своих документах Word. Вам просто нужно поместить шрифты в указанные папки, и Aspose.Words будет использовать их при создании или манипулировании документами.