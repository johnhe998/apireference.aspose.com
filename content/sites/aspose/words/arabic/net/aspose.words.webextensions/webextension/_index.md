---
title: Class WebExtension
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.WebExtensions.WebExtension فصل. يمثل كائن امتداد الويب .
type: docs
weight: 6430
url: /ar/net/aspose.words.webextensions/webextension/
---
## WebExtension class

يمثل كائن امتداد الويب .

```csharp
public class WebExtension
```

## الخصائص

| اسم | وصف |
| --- | --- |
| [AlternateReferences](../../aspose.words.webextensions/webextension/alternatereferences/) { get; } | تحديد مراجع بديلة لملحق الويب . |
| [Bindings](../../aspose.words.webextensions/webextension/bindings/) { get; } | يحدد قائمة روابط امتداد الويب. |
| [Id](../../aspose.words.webextensions/webextension/id/) { get; set; } | يعرّف بشكل فريد مثيل امتداد الويب في المستند الحالي. |
| [IsFrozen](../../aspose.words.webextensions/webextension/isfrozen/) { get; set; } | يحدد ما إذا كان يمكن للمستخدم التفاعل مع امتداد الويب أم لا. |
| [Properties](../../aspose.words.webextensions/webextension/properties/) { get; } | يمثل مجموعة من الخصائص المخصصة لإضافات الويب. |
| [Reference](../../aspose.words.webextensions/webextension/reference/) { get; } | يحدد المرجع الأساسي لملحق الويب . |

### أمثلة

يوضح كيفية إضافة امتداد ويب إلى مستند.

```csharp
Document doc = new Document();

// إنشاء جزء مهام باستخدام الوظيفة الإضافية "MyScript" ، والتي سيتم استخدامها بواسطة المستند ،
// ثم قم بتعيين موقعه الافتراضي.
TaskPane myScriptTaskPane = new TaskPane();
doc.WebExtensionTaskPanes.Add(myScriptTaskPane);
myScriptTaskPane.DockState = TaskPaneDockState.Right;
myScriptTaskPane.IsVisible = true;
myScriptTaskPane.Width = 300;
myScriptTaskPane.IsLocked = true;

// إذا كان هناك العديد من أجزاء المهام في نفس موقع الإرساء ، فيمكننا تعيين هذا الفهرس لترتيبها.
myScriptTaskPane.Row = 1;

// قم بإنشاء وظيفة إضافية تسمى "MyScript Math Sample" ، والتي سيتم عرض جزء المهام بداخلها.
WebExtension webExtension = myScriptTaskPane.WebExtension;

// تعيين المعلمات المرجعية لمتجر التطبيق للوظيفة الإضافية الخاصة بنا ، مثل المعرف.
webExtension.Reference.Id = "WA104380646";
webExtension.Reference.Version = "1.0.0.0";
webExtension.Reference.StoreType = WebExtensionStoreType.OMEX;
webExtension.Reference.Store = CultureInfo.CurrentCulture.Name;
webExtension.Properties.Add(new WebExtensionProperty("MyScript", "MyScript Math Sample"));
webExtension.Bindings.Add(new WebExtensionBinding("MyScript", WebExtensionBindingType.Text, "104380646"));

// السماح للمستخدم بالتفاعل مع الوظيفة الإضافية.
webExtension.IsFrozen = false;

// يمكننا الوصول إلى امتداد الويب في Microsoft Word عبر Developer - > الوظائف الإضافية.
doc.Save(ArtifactsDir + "Document.WebExtension.docx");

// قم بإزالة جميع أجزاء مهمة ملحق الويب مرة واحدة مثل هذا.
doc.WebExtensionTaskPanes.Clear();

Assert.AreEqual(0, doc.WebExtensionTaskPanes.Count);
```

### أنظر أيضا

* مساحة الاسم [Aspose.Words.WebExtensions](../../aspose.words.webextensions/)
* المجسم [Aspose.Words](../../)


