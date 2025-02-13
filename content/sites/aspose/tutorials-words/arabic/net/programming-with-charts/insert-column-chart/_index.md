---
title: قم بإدراج مخطط عمودي في مستند Word
linktitle: قم بإدراج مخطط عمودي في مستند Word
second_title: واجهة برمجة تطبيقات معالجة المستندات Aspose.Words
description: تعرف على كيفية إدراج مخطط عمودي في مستند باستخدام Aspose.Words for .NET.
type: docs
weight: 10
url: /ar/net/programming-with-charts/insert-column-chart/
---

يشرح هذا البرنامج التعليمي كيفية استخدام Aspose.Words for .NET لإدراج مخطط عمودي في مستند. يوضح كود المصدر المقدم كيفية إنشاء مخطط وإضافة بيانات متسلسلة وحفظ المستند.

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

 بعد ذلك ، استخدم ملف`InsertChart` طريقة`DocumentBuilder` لإدراج مخطط عمودي في المستند.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## الخطوة 3: أضف بيانات السلسلة إلى الرسم البياني

أضف بيانات السلاسل إلى المخطط. في هذا المثال ، سنضيف فئتين والقيم المقابلة لهما.

```csharp
chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
```

## الخطوة 4: احفظ المستند

 أخيرًا ، احفظ المستند في الدليل المحدد باستخدام امتداد`Save` طريقة`Document` هدف.

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

هذا يكمل تنفيذ إدراج مخطط عمودي باستخدام Aspose.Words for .NET.

### مثال على شفرة المصدر لإدراج مخطط عمودي باستخدام Aspose.Words for .NET 

```csharp
	//المسار إلى دليل المستند الخاص بك
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new string[] { "Category 1", "Category 2" }, new double[] { 1, 2 });
	doc.Save(dataDir + "WorkingWithCharts.InsertColumnChart.docx");
```

## خاتمة

في هذا البرنامج التعليمي ، تعلمت كيفية إدراج مخطط عمودي في مستند Word باستخدام Aspose.Words for .NET. باتباع الدليل خطوة بخطوة واستخدام كود المصدر المقدم ، يمكنك إنشاء مستند جديد وإدراج مخطط عمودي وإضافة بيانات سلسلة وحفظ المستند مع المخطط.

يوفر Aspose.Words for .NET واجهة برمجة تطبيقات قوية لمعالجة الكلمات مع مخططات في مستندات Word. تُستخدم المخططات العمودية بشكل شائع لعرض البيانات ومقارنتها عبر فئات أو مجموعات مختلفة. باستخدام Aspose.Words for .NET ، يمكنك بسهولة إنشاء مخططات عمودية تصور بياناتك بشكل فعال وتوفر رؤى قيمة.

باستخدام Aspose.Words for .NET ، يمكنك أتمتة عملية إنشاء المستندات باستخدام مخططات عمودية ، مما يوفر الوقت والجهد في إنشاء المستندات يدويًا. تقدم المكتبة مجموعة واسعة من أنواع المخططات وخيارات التخصيص ، مما يسمح لك بإنشاء مخططات جذابة بصريًا وغنية بالبيانات في مستندات Word الخاصة بك.

### أسئلة وأجوبة

#### س 1. ما هو مخطط العمود؟
المخطط العمودي هو نوع من المخططات التي تمثل البيانات في أشرطة أو أعمدة عمودية. يمثل كل عمود عادةً فئة أو مجموعة ، ويشير ارتفاع العمود أو طوله إلى قيمة البيانات المرتبطة بهذه الفئة. تُستخدم المخططات العمودية بشكل شائع لمقارنة البيانات عبر فئات مختلفة أو لتعقب التغييرات بمرور الوقت.

#### س 2. هل يمكنني إضافة سلاسل متعددة إلى مخطط العمود؟
نعم ، يمكنك إضافة سلاسل متعددة إلى مخطط العمود باستخدام Aspose.Words for .NET. تمثل كل سلسلة مجموعة من نقاط البيانات مع فئاتها وقيمها. من خلال إضافة سلاسل متعددة ، يمكنك مقارنة مجموعات البيانات المختلفة وتحليلها في نفس المخطط ، مما يوفر عرضًا شاملاً لبياناتك.

#### س 3. هل يمكنني تخصيص مظهر المخطط العمودي؟
نعم ، باستخدام Aspose.Words for .NET ، يمكنك تخصيص جوانب مختلفة من مظهر مخطط العمود. يمكنك تعديل الخصائص مثل لون السلسلة وتسميات المحور وعرض العمود وتنسيق منطقة المخطط. توفر المكتبة مجموعة غنية من واجهات برمجة التطبيقات للتحكم في العناصر المرئية للمخطط وإنشاء مظهر مخصص يناسب احتياجاتك.

#### س 4. هل يمكنني حفظ المستند مع الرسم البياني العمودي المدرج بتنسيقات مختلفة؟
 نعم ، يسمح لك Aspose.Words for .NET بحفظ المستند مع الرسم البياني العمودي المدرج بتنسيقات مختلفة ، مثل DOCX و PDF و HTML والمزيد. يمكنك اختيار تنسيق الإخراج المطلوب بناءً على متطلباتك واستخدام ملف`Save` طريقة`Document` كائن لحفظ المستند. سيتم الاحتفاظ بالتخطيط العمودي المدرج في المستند المحفوظ.

#### س 5. هل يمكنني تعديل بيانات ومظهر مخطط العمود بعد إدراجه؟
نعم ، بعد إدراج مخطط العمود في المستند ، يمكنك تعديل بياناته ومظهره باستخدام واجهات برمجة التطبيقات التي توفرها Aspose.Words for .NET. يمكنك تحديث بيانات السلسلة وتغيير ألوان العمود وتخصيص خصائص المحور وتطبيق خيارات التنسيق لإنشاء مخططات ديناميكية وتفاعلية في مستندات Word الخاصة بك.