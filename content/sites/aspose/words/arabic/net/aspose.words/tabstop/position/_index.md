---
title: TabStop.Position
second_title: Aspose.Words لمراجع .NET API
description: TabStop ملكية. يحصل على موضع علامة الجدولة بالنقاط.
type: docs
weight: 50
url: /ar/net/aspose.words/tabstop/position/
---
## TabStop.Position property

يحصل على موضع علامة الجدولة بالنقاط.

```csharp
public double Position { get; }
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

* class [TabStop](../)
* مساحة الاسم [Aspose.Words](../../tabstop/)
* المجسم [Aspose.Words](../../../)


