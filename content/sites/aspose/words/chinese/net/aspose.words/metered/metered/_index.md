---
title: Metered.Metered
second_title: Aspose.Words for .NET API 参考
description: Metered 构造函数. 初始化这个类的一个新实例
type: docs
weight: 10
url: /zh/net/aspose.words/metered/metered/
---
## Metered constructor

初始化这个类的一个新实例。

```csharp
public Metered()
```

### 例子

显示如何激活计量许可证和跟踪信用/消耗。

```csharp
// 创建一个新的计量许可证，然后打印其使用统计信息。
Metered metered = new Metered();
metered.SetMeteredKey("MyPublicKey", "MyPrivateKey");

Console.WriteLine($"Credit before operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity before operation: {Metered.GetConsumptionQuantity()}");

// 使用 Aspose.Words 操作，然后再次打印我们的计量统计数据，看看我们花了多少钱。
Document doc = new Document(MyDir + "Document.docx");
doc.Save(ArtifactsDir + "Metered.Usage.pdf");

// Aspose Metered Licensing 机制不会每次都将使用数据发送到购买服务器，
// 你需要使用等待。
System.Threading.Thread.Sleep(10000);

Console.WriteLine($"Credit after operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity after operation: {Metered.GetConsumptionQuantity()}");
```

### 也可以看看

* class [Metered](../)
* 命名空间 [Aspose.Words](../../metered/)
* 部件 [Aspose.Words](../../../)


