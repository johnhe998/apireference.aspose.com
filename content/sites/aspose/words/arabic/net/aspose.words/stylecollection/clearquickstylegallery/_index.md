---
title: StyleCollection.ClearQuickStyleGallery
second_title: Aspose.Words لمراجع .NET API
description: StyleCollection طريقة. يزيل كل الأنماط من لوحة معرض الأنماط السريعة.
type: docs
weight: 80
url: /ar/net/aspose.words/stylecollection/clearquickstylegallery/
---
## StyleCollection.ClearQuickStyleGallery method

يزيل كل الأنماط من لوحة معرض الأنماط السريعة.

```csharp
public void ClearQuickStyleGallery()
```

### أمثلة

يوضح كيفية إزالة الأنماط من لوحة Style Gallery.

```csharp
Document doc = new Document();

// لاحظ أن إزالة الأنماط تعمل فقط مع تنسيق DOCX في الوقت الحالي.
doc.Styles.ClearQuickStyleGallery();

doc.Save(ArtifactsDir + "Styles.RemoveStylesFromStyleGallery.docx");
```

### أنظر أيضا

* class [StyleCollection](../)
* مساحة الاسم [Aspose.Words](../../stylecollection/)
* المجسم [Aspose.Words](../../../)


