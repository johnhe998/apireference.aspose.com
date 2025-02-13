---
title: Разорвать прямую ссылку в документе Word
linktitle: Разорвать прямую ссылку в документе Word
second_title: API обработки документов Aspose.Words
description: Узнайте, как разбивать ссылки вперед в документе Word с помощью Aspose.Words для .NET.
type: docs
weight: 10
url: /ru/net/working-with-textboxes/break-a-link/
---

Aspose.Words for .NET — это мощная библиотека, которая предлагает различные функции для обработки слов с документами Microsoft Word программными средствами. Одной из его полезных функций является возможность разбивать прямые ссылки в текстовом документе. В этом руководстве мы рассмотрим исходный код на C#, демонстрирующий, как разорвать прямую ссылку в документе Word с помощью Aspose.Words для .NET.

## Шаг 1. Предварительный просмотр исходного кода C#

Предоставленный исходный код C# фокусируется на функции «Разорвать связь» Aspose.Words для .NET. В нем показано, как разорвать ссылку в форме TextBox внутри документа. Код представляет различные сценарии разрыва ссылок и дает четкие инструкции о том, как добиться желаемых результатов.

## Шаг 2. Настройка документа и создание формы TextBox

 Для начала нам нужно настроить документ и создать фигуру TextBox. Следующий код инициализирует новый экземпляр класса`Document` класс и создает форму текстового поля:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Шаг 3: разорвать прямую ссылку в текстовом поле

 Чтобы сломать прямую ссылку в TextBox, мы можем использовать`BreakForwardLink()` метод. Этот метод разрывает ссылку на следующую фигуру в последовательности. Следующий код показывает, как сломать прямую ссылку:

```csharp
textBox.BreakForwardLink();
```

## Шаг 4. Разорвите прямую ссылку, установив нулевое значение

 Кроме того, мы можем разорвать прямую ссылку, установив TextBox's`Next` собственность на`null`. Это эффективно удаляет связь со следующей формой. Следующий код демонстрирует этот подход:

```csharp
textBox. Next = null;
```

## Шаг 5. Разорвите ссылку, ведущую к TextBox

 В некоторых случаях нам нужно разорвать ссылку, ведущую к фигуре TextBox. Мы можем добиться этого, позвонив`BreakForwardLink()` метод на`Previous` form, который разрывает ссылку на TextBox. Вот пример того, как разбить такую ссылку:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Пример исходного кода для разрыва связи с Aspose.Words для .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Разорвать прямую ссылку.
textBox.BreakForwardLink();

// Разорвите прямую ссылку, установив нулевое значение.
textBox. Next = null;

// Разорвите ссылку, ведущую к этому текстовому полю.
textBox.Previous?.BreakForwardLink();
```

## Заключение

Поздравляем! Теперь вы узнали, как разорвать ссылки перенаправления в документе Word с помощью библиотеки Aspose.Words для .NET. Выполнив действия, описанные в этом руководстве, вы смогли настроить документ, создать фигуру TextBox и разорвать ссылки перенаправления, используя различные методы.

### Часто задаваемые вопросы по разрыву прямой ссылки в документе Word

#### В: Какая библиотека используется для разрыва ссылок перенаправления в документе Word с помощью Aspose.Words for .NET?

О: Чтобы разорвать ссылки перенаправления в документе Word с помощью Aspose.Words для .NET, используется библиотека Aspose.Words для .NET.

#### Q: Как сломать ссылку перенаправления в TextBox?

 A: Чтобы сломать прямую ссылку в текстовом поле, вы можете использовать`BreakForwardLink()` метод. Этот метод разрывает ссылку на следующую фигуру в последовательности.

#### В: Как сломать ссылку перенаправления, установив нулевое значение?

A: Кроме того, вы можете разорвать ссылку перенаправления, установив`Next` свойство TextBox для`null`. Это эффективно удаляет связь со следующей формой.

#### В: Как сломать ссылку, ведущую в TextBox?

 A: В некоторых случаях вам нужно разорвать ссылку, ведущую к TextBox. Вы можете добиться этого, позвонив в`BreakForwardLink()` метод на`Previous` форма, которая разрывает ссылку на TextBox.

#### В: Можем ли мы сломать ссылки перенаправления на элементах, отличных от текстовых полей?

О: Да, с помощью Aspose.Words для .NET можно разорвать ссылки перенаправления на различные элементы, такие как абзацы, таблицы, изображения и т. д. Процесс может различаться в зависимости от конкретного элемента, на который вы хотите разорвать ссылку.