---
title: Metered.GetConsumptionCredit
second_title: Aspose.Words لمراجع .NET API
description: Metered طريقة. يحصل على ائتمان الاستهلاك
type: docs
weight: 30
url: /ar/net/aspose.words/metered/getconsumptioncredit/
---
## Metered.GetConsumptionCredit method

يحصل على ائتمان الاستهلاك

```csharp
public static decimal GetConsumptionCredit()
```

### قيمة الإرجاع

كمية الاستهلاك

### أمثلة

يوضح كيفية تنشيط الترخيص المقنن وتتبع الائتمان / الاستهلاك.

```csharp
// أنشئ ترخيصًا جديدًا مقننًا ، ثم اطبع إحصائيات الاستخدام الخاصة به.
Metered metered = new Metered();
metered.SetMeteredKey("MyPublicKey", "MyPrivateKey");

Console.WriteLine($"Credit before operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity before operation: {Metered.GetConsumptionQuantity()}");

// التشغيل باستخدام Aspose.Words ، ثم اطبع إحصائياتنا المقننة مرة أخرى لترى كم أنفقنا.
Document doc = new Document(MyDir + "Document.docx");
doc.Save(ArtifactsDir + "Metered.Usage.pdf");

لا ترسل آلية الترخيص Aspose Metered Licensing بيانات الاستخدام لشراء الخادم في كل مرة ،
// تحتاج إلى استخدام الانتظار.
System.Threading.Thread.Sleep(10000);

Console.WriteLine($"Credit after operation: {Metered.GetConsumptionCredit()}");
Console.WriteLine($"Consumption quantity after operation: {Metered.GetConsumptionQuantity()}");
```

### أنظر أيضا

* class [Metered](../)
* مساحة الاسم [Aspose.Words](../../metered/)
* المجسم [Aspose.Words](../../../)


