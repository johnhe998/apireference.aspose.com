---
title: Class Metered
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Metered فصل. يوفر طرقًا لتعيين المفتاح الذي تم قياسه .
type: docs
weight: 3920
url: /ar/net/aspose.words/metered/
---
## Metered class

يوفر طرقًا لتعيين المفتاح الذي تم قياسه .

```csharp
public class Metered
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [Metered](metered/)() | تهيئة مثيل جديد لهذه الفئة. |

## طُرق

| اسم | وصف |
| --- | --- |
| [SetMeteredKey](../../aspose.words/metered/setmeteredkey/)(string, string) | مجموعات المفاتيح العامة والخاصة المقننة . إذا قمت بشراء ترخيص مقنن ، عند بدء التطبيق ، يجب استدعاء واجهة برمجة التطبيقات هذه ، عادةً ، هذا يكفي. ومع ذلك ، إذا فشلت دائمًا في تحميل بيانات الاستهلاك وتجاوزت 24 ساعة ، فسيتم تعيين الترخيص على حالة التقييم ، لتجنب مثل هذه الحالة ، يجب عليك التحقق بانتظام من حالة الترخيص ، إذا كانت حالة التقييم ، فاتصل بواجهة برمجة التطبيقات هذه مرة أخرى. |
| static [GetConsumptionCredit](../../aspose.words/metered/getconsumptioncredit/)() | يحصل على ائتمان الاستهلاك |
| static [GetConsumptionQuantity](../../aspose.words/metered/getconsumptionquantity/)() | يحصل على حجم ملف الاستهلاك |

### أمثلة

في هذا المثال ، ستُبذل محاولة لتعيين المفتاح العام والخاص الذي تم قياسه

```csharp
[C#]

Metered matered = new Metered();
matered.SetMeteredKey("PublicKey", "PrivateKey");


[Visual Basic]

Dim matered As Metered = New Metered
matered.SetMeteredKey("PublicKey", "PrivateKey")
```

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

* مساحة الاسم [Aspose.Words](../../aspose.words/)
* المجسم [Aspose.Words](../../)


