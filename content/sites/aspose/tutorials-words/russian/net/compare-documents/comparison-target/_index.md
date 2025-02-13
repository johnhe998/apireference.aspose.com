---
title: Цель сравнения
linktitle: Цель сравнения
second_title: API обработки документов Aspose.Words
description: Изучите целевую функцию сравнения Aspose.Words для .NET, которая позволяет сравнивать документы и создавать новый документ, содержащий внесенные изменения.
type: docs
weight: 10
url: /ru/net/compare-documents/comparison-target/
---

Ниже приведено пошаговое руководство по объяснению приведенного ниже исходного кода C#, в котором используются целевые функции сравнения Aspose.Words для .NET.

## Шаг 1: Введение

Функция сравнения целевого объекта Aspose.Words для .NET позволяет сравнивать два документа и создавать новый документ, содержащий изменения, внесенные в целевой документ. Это может быть полезно для отслеживания изменений, сделанных между разными версиями документа.

## Шаг 2. Настройка среды

Прежде чем начать, вам необходимо настроить среду разработки для работы с Aspose.Words for .NET. Убедитесь, что у вас установлена библиотека Aspose.Words и есть подходящий проект C# для встраивания кода.

## Шаг 3: Добавьте необходимые сборки

Чтобы использовать функцию сравнения целей Aspose.Words для .NET, вы должны добавить в свой проект необходимые сборки. Убедитесь, что в вашем проекте есть правильные ссылки на Aspose.Words.

```csharp
using Aspose.Words;
```

## Шаг 4: Инициализация документа

На этом шаге мы инициализируем два документа для сравнения. Вы должны указать путь к каталогу, в котором находятся ваши документы, а также имя исходного документа.

```csharp
// Путь к каталогу документов.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Инициализация документа A для сравнения.
Document docA = new Document(dataDir + "DocumentA.docx");

// Клонируйте документ A, чтобы создать идентичную копию документа B.
Document docB = docA.Clone();
```

## Шаг 5: Настройка параметров сравнения

На этом шаге мы настроим параметры сравнения, чтобы указать поведение сравнения. Параметры включают возможность игнорировать форматирование, а также цель сравнения, которая является параметром «Показать изменения в» в диалоговом окне «Сравнить документы» Microsoft Word.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Шаг 6: Сравнение документов

Теперь мы сравним документы и сгенерируем результат в новом документе.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

`Compare` метод сравнивает документ A с документом B и сохраняет изменения в документе A. Вы можете указать имя пользователя и дату сравнения для справки.

### Пример исходного кода для Comparison Target с использованием Aspose.Words для .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Относится к параметру Microsoft Word «Показать изменения в» в диалоговом окне «Сравнить документы».
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Заключение

В этой статье мы рассмотрели функцию diff target в Aspose.Words для .NET. Эта функция позволяет сравнить два документа и создать новый документ, содержащий внесенные изменения. Вы можете использовать эти знания для отслеживания изменений между различными версиями ваших документов.

