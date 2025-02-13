---
title: Class Metered
second_title: Справочник по API Aspose.Words для .NET
description: Aspose.Words.Metered сорт. Предоставляет методы для установки измеренного ключа.
type: docs
weight: 3920
url: /ru/net/aspose.words/metered/
---
## Metered class

Предоставляет методы для установки измеренного ключа.

```csharp
public class Metered
```

## Конструкторы

| Имя | Описание |
| --- | --- |
| [Metered](metered/)() | Инициализирует новый экземпляр этого класса. |

## Методы

| Имя | Описание |
| --- | --- |
| [SetMeteredKey](../../aspose.words/metered/setmeteredkey/)(string, string) | Устанавливает лимитный открытый и закрытый ключ. Если вы покупаете лимитную лицензию, при запуске приложения должен вызываться этот API, обычно этого достаточно. Однако, если всегда не удается загрузить данные о потреблении и время превышает 24 часа, лицензия будет установлена в ознакомительный статус, чтобы избежать этого, вы должны регулярно проверять статус лицензии, если это ознакомительный статус, снова вызывать этот API. |
| static [GetConsumptionCredit](../../aspose.words/metered/getconsumptioncredit/)() | Получает потребительский кредит |
| static [GetConsumptionQuantity](../../aspose.words/metered/getconsumptionquantity/)() | Получает размер файла потребления |

### Примеры

В этом примере будет предпринята попытка установить лимитированный открытый и закрытый ключ

```csharp
[C#]

Metered matered = new Metered();
matered.SetMeteredKey("PublicKey", "PrivateKey");


[Visual Basic]

Dim matered As Metered = New Metered
matered.SetMeteredKey("PublicKey", "PrivateKey")
```

Показывает, как активировать лицензию Metered и отслеживать кредит/потребление.

```csharp
// Создайте новую лицензию Metered, а затем распечатайте статистику ее использования.
Metered metered = new Metered();
metered.SetMeteredKey("MyPublicKey", "MyPrivateKey");

Console.WriteLine($"Credit before operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity before operation: {Metered.GetConsumptionQuantity()}");

// Работайте с Aspose.Words, а затем снова распечатайте нашу измеренную статистику, чтобы увидеть, сколько мы потратили.
Document doc = new Document(MyDir + "Document.docx");
doc.Save(ArtifactsDir + "Metered.Usage.pdf");

// Механизм Aspose Metered Licensing не отправляет данные об использовании на сервер покупки каждый раз,
// вам нужно использовать ожидание.
System.Threading.Thread.Sleep(10000);

Console.WriteLine($"Credit after operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity after operation: {Metered.GetConsumptionQuantity()}");
```

### Смотрите также

* пространство имен [Aspose.Words](../../aspose.words/)
* сборка [Aspose.Words](../../)


