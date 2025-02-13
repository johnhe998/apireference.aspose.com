---
title: WebExtensionBinding.WebExtensionBinding
second_title: Aspose.Words لمراجع .NET API
description: WebExtensionBinding البناء. إنشاء ارتباط امتداد الويب بمعلمات محددة .
type: docs
weight: 10
url: /ar/net/aspose.words.webextensions/webextensionbinding/webextensionbinding/
---
## WebExtensionBinding constructor

إنشاء ارتباط امتداد الويب بمعلمات محددة .

```csharp
public WebExtensionBinding(string id, WebExtensionBindingType bindingType, string appRef)
```

| معامل | يكتب | وصف |
| --- | --- | --- |
| id | String | معرف ملزم. |
| bindingType | WebExtensionBindingType | نوع ملزم. |
| appRef | String | مفتاح الربط المستخدم لتعيين إدخال الربط في هذه القائمة بالبيانات المرتبطة في المستند. |

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

* enum [WebExtensionBindingType](../../webextensionbindingtype/)
* class [WebExtensionBinding](../)
* مساحة الاسم [Aspose.Words.WebExtensions](../../webextensionbinding/)
* المجسم [Aspose.Words](../../../)


