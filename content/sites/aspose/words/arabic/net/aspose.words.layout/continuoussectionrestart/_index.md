---
title: Enum ContinuousSectionRestart
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.Layout.ContinuousSectionRestart تعداد. يمثل سلوكيات مختلفة عند حساب أرقام الصفحات في قسم مستمر يقوم بإعادة تشغيل ترقيم الصفحات.
type: docs
weight: 3100
url: /ar/net/aspose.words.layout/continuoussectionrestart/
---
## ContinuousSectionRestart enumeration

يمثل سلوكيات مختلفة عند حساب أرقام الصفحات في قسم مستمر يقوم بإعادة تشغيل ترقيم الصفحات.

```csharp
public enum ContinuousSectionRestart
```

### قيم

| اسم | قيمة | وصف |
| --- | --- | --- |
| Always | `0` | يتم دائمًا إعادة تشغيل ترقيم الصفحات بغض النظر عن تدفق المحتوى. |
| FromNewPageOnly | `1` | يتم إعادة تشغيل ترقيم الصفحات فقط في حالة عدم وجود محتوى آخر قبل القسم الموجود على الصفحة حيث يبدأ القسم. |

### أمثلة

يوضح كيفية التحكم في ترقيم الصفحات في قسم مستمر.

```csharp
Document doc = new Document(MyDir + "Continuous section page numbering.docx");

// افتراضيًا ، يتطابق سلوك Aspose.Words مع Microsoft Word 2019.
// إذا كنت بحاجة إلى سلوك Aspose.Words القديم ، Microsoft Word 2016 المتكرر ، استخدم "ContinuousSectionRestart.FromNewPageOnly".
// يتم إعادة تشغيل ترقيم الصفحات فقط إذا لم يكن هناك محتوى آخر قبل القسم الموجود على الصفحة حيث يبدأ القسم ،
// بسبب ذلك سيتم إعادة تعيين الترقيم إلى 2 من الصفحة الثانية.
doc.LayoutOptions.ContinuousSectionPageNumberingRestart = ContinuousSectionRestart.FromNewPageOnly;
doc.UpdatePageLayout();

doc.Save(ArtifactsDir + "Layout.RestartPageNumberingInContinuousSection.pdf");
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.Layout](../../aspose.words.layout/)
* المجسم [Aspose.Words](../../)


