---
title: DocumentBuilder.InsertShape
second_title: Aspose.Words لمراجع .NET API
description: DocumentBuilder طريقة. إدراج شكل مضمّن بنوع وحجم محددين.
type: docs
weight: 410
url: /ar/net/aspose.words/documentbuilder/insertshape/
---
## InsertShape(ShapeType, double, double) {#insertshape_1}

إدراج شكل مضمّن بنوع وحجم محددين.

```csharp
public Shape InsertShape(ShapeType shapeType, double width, double height)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| shapeType | ShapeType | نوع الشكل المراد إدراجه في المستند. |
| width | Double | عرض الشكل بالنقاط. |
| height | Double | ارتفاع الشكل بالنقاط. |

### قيمة الإرجاع

عقدة الشكل التي تم إدراجها.

### أمثلة

يوضح كيفية إدراج أشكال DML في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يوجد أدناه نوعان من أنواع التغليف التي قد تحتوي عليها الأشكال.
// 1 - عائم:
builder.InsertShape(ShapeType.TopCornersRounded, RelativeHorizontalPosition.Page, 100, 
        RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// 2 - مضمنة:
builder.InsertShape(ShapeType.DiagonalCornersRounded, 50, 50);

// إذا كنت تريد إنشاء أشكال "غير بدائية" ، مثل SingleCornerSnipped و TopCornersSnipped و DiagonalCornersSnipped ،
// TopCornersOneRoundedOneSnipped أو SingleCornerRounded أو TopCornersRounded أو DiagonalCornersRounded
// ثم احفظ المستند بامتثال "صارم" أو "انتقالي" ، مما يسمح بحفظ الشكل بتنسيق DML.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.Compliance = OoxmlCompliance.Iso29500_2008_Transitional;

doc.Save(ArtifactsDir + "Shape.ShapeInsertion.docx", saveOptions);
```

### أنظر أيضا

* class [Shape](../../../aspose.words.drawing/shape/)
* enum [ShapeType](../../../aspose.words.drawing/shapetype/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)

---

## InsertShape(ShapeType, RelativeHorizontalPosition, double, RelativeVerticalPosition, double, double, double, WrapType) {#insertshape}

إدراج شكل عائم مع موضع وحجم ونوع التفاف النص المحدد.

```csharp
public Shape InsertShape(ShapeType shapeType, RelativeHorizontalPosition horzPos, double left, 
    RelativeVerticalPosition vertPos, double top, double width, double height, WrapType wrapType)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| shapeType | ShapeType | نوع الشكل المراد إدراجه في المستند |
| horzPos | RelativeHorizontalPosition | يحدد مكان قياس المسافة الأفقية للشكل منه. |
| left | Double | المسافة بالنقاط من الأصل إلى الجانب الأيسر من الشكل. |
| vertPos | RelativeVerticalPosition | يحدد المكان الذي يتم قياس المسافة العمودية منه إلى الشكل. |
| top | Double | المسافة بالنقاط من الأصل إلى الجانب العلوي للشكل. |
| width | Double | عرض الشكل بالنقاط. |
| height | Double | عرض الشكل بالنقاط. |
| wrapType | WrapType | يحدد كيفية التفاف النص حول الشكل. |

### قيمة الإرجاع

عقدة الشكل التي تم إدراجها.

### أمثلة

يوضح كيفية إدراج أشكال DML في مستند.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// يوجد أدناه نوعان من أنواع التغليف التي قد تحتوي عليها الأشكال.
// 1 - عائم:
builder.InsertShape(ShapeType.TopCornersRounded, RelativeHorizontalPosition.Page, 100, 
        RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);

// 2 - مضمنة:
builder.InsertShape(ShapeType.DiagonalCornersRounded, 50, 50);

// إذا كنت تريد إنشاء أشكال "غير بدائية" ، مثل SingleCornerSnipped و TopCornersSnipped و DiagonalCornersSnipped ،
// TopCornersOneRoundedOneSnipped أو SingleCornerRounded أو TopCornersRounded أو DiagonalCornersRounded
// ثم احفظ المستند بامتثال "صارم" أو "انتقالي" ، مما يسمح بحفظ الشكل بتنسيق DML.
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx);
saveOptions.Compliance = OoxmlCompliance.Iso29500_2008_Transitional;

doc.Save(ArtifactsDir + "Shape.ShapeInsertion.docx", saveOptions);
```

### أنظر أيضا

* class [Shape](../../../aspose.words.drawing/shape/)
* enum [ShapeType](../../../aspose.words.drawing/shapetype/)
* enum [RelativeHorizontalPosition](../../../aspose.words.drawing/relativehorizontalposition/)
* enum [RelativeVerticalPosition](../../../aspose.words.drawing/relativeverticalposition/)
* enum [WrapType](../../../aspose.words.drawing/wraptype/)
* class [DocumentBuilder](../)
* مساحة الاسم [Aspose.Words](../../documentbuilder/)
* المجسم [Aspose.Words](../../../)


