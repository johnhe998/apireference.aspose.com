---
title: Metered.SetMeteredKey
second_title: Справочник по API Aspose.Words для .NET
description: Metered метод. Устанавливает лимитный открытый и закрытый ключ. Если вы покупаете лимитную лицензию при запуске приложения должен вызываться этот API обычно этого достаточно. Однако если всегда не удается загрузить данные о потреблении и время превышает 24 часа лицензия будет установлена в ознакомительный статус чтобы избежать этого вы должны регулярно проверять статус лицензии если это ознакомительный статус снова вызывать этот API.
type: docs
weight: 20
url: /ru/net/aspose.words/metered/setmeteredkey/
---
## Metered.SetMeteredKey method

Устанавливает лимитный открытый и закрытый ключ. Если вы покупаете лимитную лицензию, при запуске приложения должен вызываться этот API, обычно этого достаточно. Однако, если всегда не удается загрузить данные о потреблении и время превышает 24 часа, лицензия будет установлена в ознакомительный статус, чтобы избежать этого, вы должны регулярно проверять статус лицензии, если это ознакомительный статус, снова вызывать этот API.

```csharp
public void SetMeteredKey(string publicKey, string privateKey)
```

| Параметр | Тип | Описание |
| --- | --- | --- |
| publicKey | String | открытый ключ |
| privateKey | String | закрытый ключ |

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


