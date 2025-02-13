---
title: MarkdownSaveOptions.ImagesFolder
second_title: Aspose.Words لمراجع .NET API
description: MarkdownSaveOptions ملكية. يحدد المجلد الفعلي حيث يتم حفظ الصور عند تصدير مستند إلى Markdown صيغة. الافتراضي هو عبارة عن سلسلة فارغة.
type: docs
weight: 40
url: /ar/net/aspose.words.saving/markdownsaveoptions/imagesfolder/
---
## MarkdownSaveOptions.ImagesFolder property

يحدد المجلد الفعلي حيث يتم حفظ الصور عند تصدير مستند إلى Markdown صيغة. الافتراضي هو عبارة عن سلسلة فارغة.

```csharp
public string ImagesFolder { get; set; }
```

### ملاحظات

عند حفظ ملف[`Document`](../../../aspose.words/document/) فيMarkdown بتنسيق ، Aspose.word يحتاج إلى حفظ جميع الصور المضمنة في المستند كملفات مستقلة . `ImagesFolder` يسمح لك بتحديد مكان حفظ الصور.

إذا قمت بحفظ مستند في ملف وقدمت اسم ملف ، Aspose.Words ، افتراضيًا ، يحفظ الصور في نفس المجلد حيث تم حفظ ملف المستند. يستخدم`ImagesFolder` لتجاوز هذا السلوك.

إذا قمت بحفظ مستند في دفق ، فإن Aspose.words لا يحتوي على folder حيث يتم حفظ الصور ، ولكنه لا يزال بحاجة إلى حفظ الصور في مكان ما. في هذه الحالة ، تحتاج إلى تحديد مجلد يمكن الوصول إليه في ملف`ImagesFolder` الملكية .

إذا كان المجلد المحدد بواسطة`ImagesFolder` غير موجود ، سيتم إنشاؤه تلقائيًا .

### أنظر أيضا

* class [MarkdownSaveOptions](../)
* مساحة الاسم [Aspose.Words.Saving](../../markdownsaveoptions/)
* المجسم [Aspose.Words](../../../)


