---
title: Неограниченные редактируемые области в документе Word
linktitle: Неограниченные редактируемые области в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как создавать неограниченные редактируемые области в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/document-protection/unrestricted-editable-regions/
---
В этом руководстве мы покажем вам, как использовать функцию неограниченных редактируемых областей Aspose.Words для .NET. Эта функция позволяет определить области в документе Word, содержимое которых можно редактировать без ограничений, даже если остальная часть документа доступна только для чтения. Выполните следующие действия:

## Шаг 1: Загрузка документа и установка защиты

Начните с загрузки существующего документа:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
doc.Protect(ProtectionType.ReadOnly, "MyPassword");
```

Защитите документ, установив тип защиты только для чтения и пароль

## Шаг 2: Создание редактируемой области

Начните с создания редактируемой области с помощью объектов EditableRangeStart и EditableRangeEnd:

```csharp
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Объект EditableRange создается для только что созданного EditableRangeStart.
EditableRange editableRange = edRangeStart.EditableRange;

// Поместите что-нибудь в редактируемый диапазон.
builder.Writeln("Paragraph inside first editable range");

// Редактируемый диапазон является корректным, если у него есть начало и конец.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

```

## Шаг 3. Добавьте содержимое за пределы редактируемых областей.

Вы можете добавить контент за пределы редактируемых областей, которые останутся доступными только для чтения:

```csharp
builder.Writeln("This paragraph is outside of all editable areas and cannot be edited.");
```

## Шаг 4: Сохраните документ

Наконец, сохраните измененный документ:

```csharp
doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");
```

Обязательно укажите правильный путь и имя файла для сохранения документа с редактируемыми областями.

### Пример исходного кода для неограниченных редактируемых областей с использованием Aspose.Words для .NET

Вот полный исходный код для неограниченных редактируемых областей с использованием Aspose.Words для .NET:

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Загрузите документ и сделайте его доступным только для чтения.
Document doc = new Document(MyDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

doc.Protect(ProtectionType.ReadOnly, "MyPassword");

builder.Writeln("Hello world! Since we have set the document's protection level to read-only, " + "we cannot edit this paragraph without the password.");

// Запустите редактируемый диапазон.
EditableRangeStart edRangeStart = builder.StartEditableRange();
// Объект EditableRange создается для только что созданного EditableRangeStart.
EditableRange editableRange = edRangeStart.EditableRange;

// Поместите что-нибудь в редактируемый диапазон.
builder.Writeln("Paragraph inside first editable range");

// Редактируемый диапазон является корректным, если у него есть начало и конец.
EditableRangeEnd edRangeEnd = builder.EndEditableRange();

builder.Writeln("This paragraph is outside any editable ranges, and cannot be edited.");

doc.Save(dataDir + "DocumentProtection.UnrestrictedEditableRegions.docx");

```
Следуя этим шагам, вы можете легко создавать неограниченные редактируемые области в документе Word с помощью Aspose.Words для .NET.

## Заключение
В этом руководстве мы узнали, как создавать неограниченные редактируемые области в документе Word с помощью Aspose.Words для .NET. Следуя предоставленным шагам, вы можете определить определенные области в документе, где пользователи могут свободно редактировать содержимое, сохраняя при этом остальную часть документа доступной только для чтения. Aspose.Words для .NET предлагает мощные функции для защиты и настройки документов, предоставляя вам контроль над возможностями редактирования ваших документов Word.

### Часто задаваемые вопросы о неограниченных редактируемых областях в документе Word

#### В: Что такое неограниченные редактируемые области в Aspose.Words для .NET?

О: Неограниченные редактируемые области в Aspose.Words для .NET — это области в документе Word, содержимое которых можно редактировать без каких-либо ограничений, даже если остальная часть документа установлена как доступная только для чтения. Эти области позволяют определить определенные части документа, которые пользователи могут изменять, сохраняя при этом общую защиту документа.

#### Q: Как я могу создать неограниченные редактируемые регионы, используя Aspose.Words для .NET?

О: Чтобы создать неограниченные редактируемые области в документе Word с помощью Aspose.Words for .NET, выполните следующие действия:
1.  Загрузите существующий документ с помощью`Document` сорт.
2.  Установите защиту документа только для чтения с помощью`Protect` метод`Document` объект.
3.  Использовать`DocumentBuilder` класс, чтобы создать редактируемый диапазон, добавив`EditableRangeStart` объект и`EditableRangeEnd` объект.
4.  Добавьте содержимое в пределах редактируемого диапазона, используя кнопку`DocumentBuilder`.
5.  Сохраните измененный документ с помощью`Save` метод`Document` объект.

#### В: Могу ли я иметь несколько неограниченных редактируемых областей в документе Word?

О: Да, в документе Word может быть несколько неограниченных редактируемых областей. Для этого можно создать несколько наборов`EditableRangeStart` и`EditableRangeEnd` объекты с помощью`DocumentBuilder` сорт. Каждый набор объектов будет определять отдельную редактируемую область, где пользователи могут изменять содержимое без каких-либо ограничений.

#### В: Могу ли я вкладывать редактируемые регионы друг в друга?

 О: Нет, вы не можете вкладывать редактируемые области друг в друга, используя Aspose.Words для .NET. Каждая редактируемая область, определяемая`EditableRangeStart` и`EditableRangeEnd` пара должна быть независимой, не перекрываться и не вкладываться в другую редактируемую область. Вложенные редактируемые области не поддерживаются.

#### В: Могу ли я снять защиту только для чтения с документа в редактируемой области?

О: Нет, вы не можете снять защиту только для чтения с документа в редактируемой области. Защита только для чтения применяется ко всему документу и не может быть выборочно удалена в определенных редактируемых областях. Редактируемые области предназначены для того, чтобы разрешить изменение содержимого, сохраняя при этом весь документ доступным только для чтения.