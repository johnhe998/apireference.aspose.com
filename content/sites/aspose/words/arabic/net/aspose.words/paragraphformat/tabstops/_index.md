---
title: ParagraphFormat.TabStops
second_title: Aspose.Words لمراجع .NET API
description: ParagraphFormat ملكية. الحصول على مجموعة علامات الجدولة المخصصة المحددة لهذا الكائن.
type: docs
weight: 380
url: /ar/net/aspose.words/paragraphformat/tabstops/
---
## ParagraphFormat.TabStops property

الحصول على مجموعة علامات الجدولة المخصصة المحددة لهذا الكائن.

```csharp
public TabStopCollection TabStops { get; }
```

### أمثلة

يوضح كيفية تعديل موضع علامة الجدولة اليمنى في الفقرات المتعلقة بجداول المحتويات.

```csharp
Document doc = new Document(MyDir + "Table of contents.docx");

// التكرار خلال جميع الفقرات باستخدام الأنماط القائمة على جدول المحتويات ; هذا هو أي نمط بين TOC و TOC9.
foreach (Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true).OfType<Paragraph>())
    if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
        para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
    {
        // احصل على أول علامة تبويب مستخدمة في هذه الفقرة ، يجب أن تكون هذه هي علامة التبويب المستخدمة لمحاذاة أرقام الصفحات.
        TabStop tab = para.ParagraphFormat.TabStops[0];

        // استبدل أول علامة تبويب افتراضية ، توقف بعلامة جدولة مخصصة.
        para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
        para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
    }

doc.Save(ArtifactsDir + "Styles.ChangeTocsTabStops.docx");
```

### أنظر أيضا

* class [TabStopCollection](../../tabstopcollection/)
* class [ParagraphFormat](../)
* مساحة الاسم [Aspose.Words](../../paragraphformat/)
* المجسم [Aspose.Words](../../../)


