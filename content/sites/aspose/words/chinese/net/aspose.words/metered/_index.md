---
title: Class Metered
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Metered 班级. 提供设置计量键的方法
type: docs
weight: 3920
url: /zh/net/aspose.words/metered/
---
## Metered class

提供设置计量键的方法。

```csharp
public class Metered
```

## 构造函数

| 姓名 | 描述 |
| --- | --- |
| [Metered](metered/)() | 初始化这个类的一个新实例。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| [SetMeteredKey](../../aspose.words/metered/setmeteredkey/)(string, string) | 设置计量公钥和私钥。 如果购买计量许可证，在启动应用程序时，应该调用此API，正常情况下，这就足够了。 但是，如果总是上传消费数据失败，超过24小时，License会被设置为评估状态， 为了避免这种情况，你应该定期检查License状态，如果是评估状态，再次调用这个API。 |
| static [GetConsumptionCredit](../../aspose.words/metered/getconsumptioncredit/)() | 获取消费额度 |
| static [GetConsumptionQuantity](../../aspose.words/metered/getconsumptionquantity/)() | 获取消费文件大小 |

### 例子

在此示例中，将尝试设置计量的公钥和私钥

```csharp
[C#]

Metered matered = new Metered();
matered.SetMeteredKey("PublicKey", "PrivateKey");


[Visual Basic]

Dim matered As Metered = New Metered
matered.SetMeteredKey("PublicKey", "PrivateKey")
```

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

* 命名空间 [Aspose.Words](../../aspose.words/)
* 部件 [Aspose.Words](../../)


