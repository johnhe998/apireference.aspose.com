---
title: FindReplaceOptions.UseSubstitutions
second_title: Справочник по API Aspose.Words для .NET
description: FindReplaceOptions свойство. Получает или задает логическое значение указывающее следует ли распознавать и использовать замены в шаблонах замены. Значение по умолчаниюЛОЖЬ .
type: docs
weight: 160
url: /ru/net/aspose.words.replacing/findreplaceoptions/usesubstitutions/
---
## FindReplaceOptions.UseSubstitutions property

Получает или задает логическое значение, указывающее, следует ли распознавать и использовать замены в шаблонах замены. Значение по умолчанию:`ЛОЖЬ` .

```csharp
public bool UseSubstitutions { get; set; }
```

### Примечания

Подробную информацию об элементах замены см. на странице: https://docs.microsoft.com/en-us/dotnet/standard/base-types/substitutions-in-regular-expressions.

### Примеры

Показывает, как распознавать и использовать замены в шаблонах замены.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Jason gave money to Paul.");

Regex regex = new Regex(@"([A-z]+) gave money to ([A-z]+)");

FindReplaceOptions options = new FindReplaceOptions();
options.UseSubstitutions = true;

// Использование устаревшего режима не поддерживает многие расширенные функции, поэтому нам нужно установить для него значение «false».
options.LegacyMode = false;

doc.Range.Replace(regex, @"$2 took money from $1", options);

Assert.AreEqual(doc.GetText(), "Paul took money from Jason.\f");
```

Показывает, как заменить текст заменами.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("John sold a car to Paul.");
builder.Writeln("Jane sold a house to Joe.");

// Мы можем использовать объект «FindReplaceOptions», чтобы изменить процесс поиска и замены.
FindReplaceOptions options = new FindReplaceOptions();

// Установите для свойства "UseSubstitutions" значение "true", чтобы получить
// операция поиска и замены для распознавания замещающих элементов.
// Установите для свойства "UseSubstitutions" значение "false", чтобы игнорировать элементы подстановки.
options.UseSubstitutions = useSubstitutions;

Regex regex = new Regex(@"([A-z]+) sold a ([A-z]+) to ([A-z]+)");
doc.Range.Replace(regex, @"$3 bought a $2 from $1", options);

Assert.AreEqual(
    useSubstitutions
        ? "Paul bought a car from John.\rJoe bought a house from Jane."
        : "$3 bought a $2 from $1.\r$3 bought a $2 from $1.", doc.GetText().Trim());
```

### Смотрите также

* class [FindReplaceOptions](../)
* пространство имен [Aspose.Words.Replacing](../../findreplaceoptions/)
* сборка [Aspose.Words](../../../)


