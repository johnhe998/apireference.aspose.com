---
title: Metered.SetMeteredKey
second_title: Aspose.Words لمراجع .NET API
description: Metered طريقة. مجموعات المفاتيح العامة والخاصة المقننة . إذا قمت بشراء ترخيص مقنن  عند بدء التطبيق  يجب استدعاء واجهة برمجة التطبيقات هذه  عادةً  هذا يكفي. ومع ذلك  إذا فشلت دائمًا في تحميل بيانات الاستهلاك وتجاوزت 24 ساعة  فسيتم تعيين الترخيص على حالة التقييم  لتجنب مثل هذه الحالة  يجب عليك التحقق بانتظام من حالة الترخيص  إذا كانت حالة التقييم  فاتصل بواجهة برمجة التطبيقات هذه مرة أخرى.
type: docs
weight: 20
url: /ar/net/aspose.words/metered/setmeteredkey/
---
## Metered.SetMeteredKey method

مجموعات المفاتيح العامة والخاصة المقننة . إذا قمت بشراء ترخيص مقنن ، عند بدء التطبيق ، يجب استدعاء واجهة برمجة التطبيقات هذه ، عادةً ، هذا يكفي. ومع ذلك ، إذا فشلت دائمًا في تحميل بيانات الاستهلاك وتجاوزت 24 ساعة ، فسيتم تعيين الترخيص على حالة التقييم ، لتجنب مثل هذه الحالة ، يجب عليك التحقق بانتظام من حالة الترخيص ، إذا كانت حالة التقييم ، فاتصل بواجهة برمجة التطبيقات هذه مرة أخرى.

```csharp
public void SetMeteredKey(string publicKey, string privateKey)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| publicKey | String | المفتاح العمومي |
| privateKey | String | مفتاح سري |

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


