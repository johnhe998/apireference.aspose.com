---
title: Metered.GetConsumptionCredit
second_title: Справочник по API Aspose.Words для .NET
description: Metered метод. Получает потребительский кредит
type: docs
weight: 30
url: /ru/net/aspose.words/metered/getconsumptioncredit/
---
## Metered.GetConsumptionCredit method

Получает потребительский кредит

```csharp
public static decimal GetConsumptionCredit()
```

### Возвращаемое значение

объем потребления

### Примеры

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

* class [Metered](../)
* пространство имен [Aspose.Words](../../metered/)
* сборка [Aspose.Words](../../../)


