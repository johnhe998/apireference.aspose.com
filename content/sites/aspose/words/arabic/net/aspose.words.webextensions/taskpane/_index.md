---
title: Class TaskPane
second_title: Aspose.Words لمراجع .NET API
description: Aspose.Words.WebExtensions.TaskPane فصل. يمثل كائن جزء مهام الوظيفة الإضافية.
type: docs
weight: 6400
url: /ar/net/aspose.words.webextensions/taskpane/
---
## TaskPane class

يمثل كائن جزء مهام الوظيفة الإضافية.

```csharp
public class TaskPane
```

## المنشئون

| اسم | وصف |
| --- | --- |
| [TaskPane](taskpane/)() | Default_Constructor |

## الخصائص

| اسم | وصف |
| --- | --- |
| [DockState](../../aspose.words.webextensions/taskpane/dockstate/) { get; set; } | يحدد آخر مكان تم إرساؤه لعنصر جزء المهام هذا. |
| [IsLocked](../../aspose.words.webextensions/taskpane/islocked/) { get; set; } | يحدد ما إذا كان جزء المهام مؤمنًا على المستند في واجهة المستخدم ولا يمكن للمستخدم إغلاقه. |
| [IsVisible](../../aspose.words.webextensions/taskpane/isvisible/) { get; set; } | يحدد ما إذا كان جزء المهام سيظهر على أنه مرئي افتراضيًا عند فتح المستند. |
| [Row](../../aspose.words.webextensions/taskpane/row/) { get; set; } | يحدد الفهرس ، الذي يتم تعداده من الخارج إلى الداخل ، لجزء المهام هذا بين أجزاء المهام المستمرة الأخرى التي تم إرساؤها في نفس الموقع الافتراضي. |
| [WebExtension](../../aspose.words.webextensions/taskpane/webextension/) { get; } | يمثل كائن امتداد الويب . |
| [Width](../../aspose.words.webextensions/taskpane/width/) { get; set; } | يحدد قيمة العرض الافتراضية لمثيل جزء المهام هذا. |

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


