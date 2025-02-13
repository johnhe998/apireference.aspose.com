---
title: أدخل مخطط فقاعي في مستند Word
linktitle: أدخل مخطط فقاعي في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج مخطط فقاعي في مستند باستخدام Aspose.Words for .NET. أضف بيانات متسلسلة بقيم X و Y وقيم حجم الفقاعة.
type: docs
weight: 10
url: /ar/net/programming-with-charts/insert-bubble-chart/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإدراج مخطط فقاعي في مستند. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وحفظ المستند.

## الخطوة 1: قم بإعداد المشروع

تأكد من أن لديك المتطلبات الأساسية التالية:

- تثبيت Aspose.Words لمكتبة .NET. يمكنك تنزيله باستخدام مدير حزمة NuGet لتثبيته.
- مسار دليل المستند حيث سيتم حفظ المستند الناتج.

## الخطوة 2: أنشئ مستندًا جديدًا وأدخل مخططًا

 إنشاء ملف`Document` كائن و`DocumentBuilder` لبناء الوثيقة.

```csharp
// المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 بعد ذلك ، استخدم ملف`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط فقاعي في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف ثلاث نقاط بيانات مع قيم X و Y وقيم حجم الفقاعة.

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## الخطوة 4: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

هذا يكمل تنفيذ إدراج مخطط فقاعي باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لإدراج مخطط فقاعي باستخدام Aspose.Words for .NET 

```csharp
//المسار إلى دليل المستند الخاص بك
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إدراج مخطط فقاعي في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك إنشاء مستند جديد وإدراج مخطط فقاعي وإضافة بيانات سلسلة وحفظ المستند مع المخطط.

يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات مع مخططات في مستندات Word. تعد المخططات الفقاعية مثالية لتصور البيانات ثلاثية الأبعاد ، حيث يتم تمثيل كل نقطة بيانات بواسطة فقاعة بإحداثيات X و Y وقيمة حجم. باستخدام Aspose.Words for .NET ، يمكنك إنشاء مخططات فقاعية ديناميكية وغنية بالمعلومات تعزز التمثيل المرئي لبياناتك.

باستخدام Aspose.Words for .NET ، يمكنك أتمتة عملية إنشاء المستندات باستخدام مخططات فقاعية ، مما يوفر الوقت والجهد في إنشاء المستندات يدويًا. تقدم المكتبة مجموعة واسعة من أنواع المخططات وخيارات التخصيص ، مما يسمح لك بإنشاء مخططات جذابة بصريًا وغنية بالبيانات في مستندات Word الخاصة بك.

### أسئلة وأجوبة

#### س 1. ما هو مخطط الفقاعة؟
المخطط الفقاعي هو نوع من المخططات التي تعرض بيانات ثلاثية الأبعاد باستخدام الفقاعات أو المجالات. يتم تمثيل كل نقطة بيانات بواسطة فقاعة ، حيث يحدد الإحداثيان X و Y موضع الفقاعة على الرسم البياني ، ويمثل حجم الفقاعة البعد الثالث للبيانات. تعد المخططات الفقاعية مفيدة لتصور العلاقات والأنماط بين المتغيرات المتعددة.

#### س 2. هل يمكنني إضافة سلاسل متعددة إلى المخطط الفقاعي؟
نعم ، يمكنك إضافة سلاسل متعددة إلى المخطط الفقاعي باستخدام Aspose.Words for .NET. تمثل كل سلسلة مجموعة من نقاط البيانات بقيم حجمها X و Y والحجم الفقاعي. من خلال إضافة سلاسل متعددة ، يمكنك مقارنة مجموعات البيانات المختلفة وتحليلها في نفس المخطط ، مما يوفر عرضًا شاملاً لبياناتك.

#### س 3. هل يمكنني تخصيص مظهر المخطط الفقاعي؟
نعم ، باستخدام Aspose.Words for .NET ، يمكنك تخصيص جوانب مختلفة من مظهر المخطط الفقاعي. يمكنك تعديل الخصائص مثل لون السلسلة وحجم الفقاعة وتسميات المحور وتنسيق منطقة المخطط. توفر المكتبة مجموعة غنية من واجهات برمجة التطبيقات للتحكم في العناصر المرئية للمخطط وإنشاء مظهر مخصص يناسب احتياجاتك.

#### س 4. هل يمكنني حفظ المستند بالمخطط الفقاعي المدرج بتنسيقات مختلفة؟
نعم ، يسمح لك Aspose.Words for .NET بحفظ المستند مع مخطط الفقاعات المُدرج بتنسيقات مختلفة ، مثل DOCX و PDF و HTML والمزيد. يمكنك اختيار تنسيق الإخراج المطلوب بناءً على متطلباتك واستخدام ملف`Save` طريقة`Document` كائن لحفظ المستند. سيتم الاحتفاظ بالتخطيط الفقاعي المُدرج في المستند المحفوظ.

#### س 5. هل يمكنني تعديل البيانات ومظهر المخطط الفقاعي بعد إدراجه؟
نعم ، بعد إدراج المخطط الفقاعي في المستند ، يمكنك تعديل بياناته ومظهره باستخدام واجهات برمجة التطبيقات التي توفرها Aspose.Words for .NET. يمكنك تحديث بيانات السلسلة وتغيير حجم الفقاعة وتخصيص خصائص المحور وتطبيق خيارات التنسيق لإنشاء مخططات ديناميكية وتفاعلية في مستندات Word الخاصة بك.