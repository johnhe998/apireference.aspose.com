---
title: FieldAddressBlock.FormatAddressOnCountryOrRegion
second_title: Aspose.Words لمراجع .NET API
description: FieldAddressBlock ملكية. الحصول على أو تحديد ما إذا كان سيتم تنسيق العنوان وفقًا للبلد / المنطقة الخاصة بالمستلم كما هو محدد بواسطة POST  CODE الاتحاد البريدي العالمي 2006 .
type: docs
weight: 30
url: /ar/net/aspose.words.fields/fieldaddressblock/formataddressoncountryorregion/
---
## FieldAddressBlock.FormatAddressOnCountryOrRegion property

الحصول على أو تحديد ما إذا كان سيتم تنسيق العنوان وفقًا للبلد / المنطقة الخاصة بالمستلم كما هو محدد بواسطة POST * CODE (الاتحاد البريدي العالمي 2006) .

```csharp
public bool FormatAddressOnCountryOrRegion { get; set; }
```

### أمثلة

يوضح كيفية إدراج حقل ADDRESSBLOCK.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

FieldAddressBlock field = (FieldAddressBlock)builder.InsertField(FieldType.FieldAddressBlock, true);

Assert.AreEqual(" ADDRESSBLOCK ", field.GetFieldCode());

// سيتضمن تعيين هذا على "2" جميع البلدان والمناطق ،
// ما لم يكن هو المحدد في خاصية ExcludedCountryOrRegionName.
field.IncludeCountryOrRegionName = "2";
field.FormatAddressOnCountryOrRegion = true;
field.ExcludedCountryOrRegionName = "United States";
field.NameAndAddressFormat = "<Title> <Forename> <Surname> <Address Line 1> <Region> <Postcode> <Country>";

// بشكل افتراضي ، ستحتوي هذه الخاصية على معرف اللغة للحرف الأول من المستند.
// يمكننا تعيين ثقافة مختلفة للمجال لتنسيق النتيجة بهذا الشكل.
field.LanguageId = new CultureInfo("en-US").LCID.ToString();

Assert.AreEqual(
    " ADDRESSBLOCK  \\c 2 \\d \\e \"United States\" \\f \"<Title> <Forename> <Surname> <Address Line 1> <Region> <Postcode> <Country>\" \\l 1033",
    field.GetFieldCode());
```

### أنظر أيضا

* class [FieldAddressBlock](../)
* مساحة الاسم [Aspose.Words.Fields](../../fieldaddressblock/)
* المجسم [Aspose.Words](../../../)


