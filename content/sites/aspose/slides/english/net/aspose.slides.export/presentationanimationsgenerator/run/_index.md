---
title: Run
second_title: Aspose.Sildes for .NET API Reference
description: Run the animation events generation for each slide.
type: docs
weight: 80
url: /net/aspose.slides.export/presentationanimationsgenerator/run/
---
## Run(IEnumerable&lt;ISlide&gt;) {#run}

Run the animation events generation for each slide.

```csharp
public void Run(IEnumerable<ISlide> slides)
```

### Examples

```csharp
[C#]
using (Presentation presentation = new Presentation("animated.pptx"))
{
    using (var animationsGenerator = new PresentationAnimationsGenerator(presentation.SlideSize.Size.ToSize()))
    using (var player = new PresentationPlayer(animationsGenerator, 33))
    {
        animationsGenerator.NewAnimation += animationPlayer =>
        {
            // handle new animation
        };
        
        player.FrameTick += (sender, args) =>
        {
            // handle frame tick within the new animation
        };
        
        animationsGenerator.Run(presentation.Slides);
    }
}
```

### See Also

* interface [ISlide](../../../aspose.slides/islide)
* class [PresentationAnimationsGenerator](../../presentationanimationsgenerator)
* namespace [Aspose.Slides.Export](../../presentationanimationsgenerator)
* assembly [Aspose.Slides](../../../)

---

## Run(IEnumerable&lt;ISlide&gt;, int, FrameTickHandler) {#run_1}

Run the animation events generation for each slide.

```csharp
public void Run(IEnumerable<ISlide> slides, int fps, FrameTickHandler onFrame)
```

### Examples

```csharp
[C#]
using (Presentation presentation = new Presentation("animated.pptx"))
{
    using (var animationsGenerator = new PresentationAnimationsGenerator(presentation.SlideSize.Size.ToSize()))
    {
        animationsGenerator.Run(presentation.Slides, 33, (sender, args) =>
        {
            sender.FrameTick += (sender, args) =>
            {
                args.GetFrame().Save($"frame_{sender.FrameIndex}.png");
            };
        });
    }
}
```

### See Also

* interface [ISlide](../../../aspose.slides/islide)
* delegate [FrameTickHandler](../../presentationplayer.frametickhandler)
* class [PresentationAnimationsGenerator](../../presentationanimationsgenerator)
* namespace [Aspose.Slides.Export](../../presentationanimationsgenerator)
* assembly [Aspose.Slides](../../../)

<!-- DO NOT EDIT: generated by xmldocmd for Aspose.Slides.dll -->
