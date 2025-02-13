---
title: Font.NameFarEast
second_title: Aspose.Words لمراجع .NET API
description: Font ملكية. إرجاع أو تعيين اسم خط شرق آسيوي.
type: docs
weight: 260
url: /ar/net/aspose.words/font/namefareast/
---
## Font.NameFarEast property

إرجاع أو تعيين اسم خط شرق آسيوي.

```csharp
public string NameFarEast { get; set; }
```

### أمثلة

يوضح كيفية إدراج نص وتنسيقه بلغة الشرق الأقصى.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// حدد إعدادات الخط التي سيطبقها منشئ المستندات على أي نص يتم إدراجه.
builder.Font.Name = "Courier New";
builder.Font.LocaleId = new CultureInfo("en-US", false).LCID;

// اسم مكافئات "FarEast" للخط والإعدادات المحلية.
// إذا قام المنشئ بإدراج الأحرف الآسيوية مع تكوين الخط هذا ، فحينئذٍ تحتوي كل عملية تشغيل على
// ستعرض هذه الأحرف لهم باستخدام الخط / اللغة "FarEast" بدلاً من الافتراضي.
// قد يكون هذا مفيدًا عندما لا يحتوي الخط الغربي على تمثيلات مثالية للأحرف الآسيوية.
builder.Font.NameFarEast = "SimSun";
builder.Font.LocaleIdFarEast = new CultureInfo("zh-CN", false).LCID;

// سيتم عرض هذا النص بالخط الافتراضي / اللغة المحلية.
builder.Writeln("Hello world!");

// نظرًا لأن هذه أحرف آسيوية ، فسيؤدي هذا التشغيل إلى تطبيق مكافئات الخط / الإعدادات المحلية الخاصة بنا "FarEast".
builder.Writeln("你好世界");

doc.Save(ArtifactsDir + "Font.FarEast.docx");
```

### أنظر أيضا

* property [Name](../name/)
* class [Font](../)
* مساحة الاسم [Aspose.Words](../../font/)
* المجسم [Aspose.Words](../../../)


