---
title: TaskPane.IsLocked
second_title: Aspose.Words لمراجع .NET API
description: TaskPane ملكية. يحدد ما إذا كان جزء المهام مؤمنًا على المستند في واجهة المستخدم ولا يمكن للمستخدم إغلاقه.
type: docs
weight: 30
url: /ar/net/aspose.words.webextensions/taskpane/islocked/
---
## TaskPane.IsLocked property

يحدد ما إذا كان جزء المهام مؤمنًا على المستند في واجهة المستخدم ولا يمكن للمستخدم إغلاقه.

```csharp
public bool IsLocked { get; set; }
```

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

* class [TaskPane](../)
* مساحة الاسم [Aspose.Words.WebExtensions](../../taskpane/)
* المجسم [Aspose.Words](../../../)


