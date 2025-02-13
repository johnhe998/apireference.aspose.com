---
title: Enum JsonSimpleValueParseMode
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Reporting.JsonSimpleValueParseMode перечисление. Определяет режим анализа простых значений JSON null boolean number integer и string при загрузке JSON. Такой режим не влияет на синтаксический анализ значений даты и времени.
type: docs
weight: 4440
url: /ru/net/aspose.words.reporting/jsonsimplevalueparsemode/
---
## JsonSimpleValueParseMode enumeration

Определяет режим анализа простых значений JSON (null, boolean, number, integer и string) при загрузке JSON. Такой режим не влияет на синтаксический анализ значений даты и времени.

```csharp
public enum JsonSimpleValueParseMode
```

### Ценности

| Имя | Ценность | Описание |
| --- | --- | --- |
| Loose | `0` | Указывает режим, в котором типы простых значений JSON определяются при анализе их строковых представлений. Например, тип 'prop' из фрагмента JSON '{ prop: "123" }' в этом режиме определяется как целое число. |
| Strict | `1` | Указывает режим, в котором типы простых значений JSON определяются из самой нотации JSON. |

### Смотрите также

* пространство имен [Aspose.Words.Reporting](../../aspose.words.reporting/)
* сборка [Aspose.Words](../../)


