---
title: addClone
second_title: Aspose.Sildes for Node.js via Java API Reference
description: 
type: docs

url: /node-java/aspose.slides/globallayoutslidecollection/addclone/
---

## addClone([LayoutSlide](../../layoutslide) sourceLayout)  function

 Adds a copy of a specified layout slide to the presentation.
 

### Parameters

| Name | Type | Description |
| --- | --- | --- |
| sourceLayout | [LayoutSlide](../../layoutslide) | Slide to clone. When cloning a layout between different presentations layout's master can be cloned too to keep source formatting. Internal registry is used to track automatically cloned masters to prevent creation of multiple clones of the same master slide. Manual cloning of master slides will be neither prevented nor registered. |

### Result
[LayoutSlide](../../layoutslide)


---


## addClone([LayoutSlide](../../layoutslide) sourceLayout, [MasterSlide](../../masterslide) destMaster)  function

 Adds a copy of a specified layout slide to the presentation.
 

### Parameters

| Name | Type | Description |
| --- | --- | --- |
| sourceLayout | [LayoutSlide](../layoutslide) | Slide to clone. |
| destMaster | [MasterSlide](../../masterslide) | Master slide for a new layout. 1) New layout will be linked with defined master in destination presentation. So this is analogue of copy/paste with "Use Destination Theme" option in PowerPoint. 2) Analogue of this function is function IMasterLayoutSlideCollection#addClone(ILayoutSlide) accessed with ( IMasterSlide#getLayoutSlides) property. |

### Result
[LayoutSlide](../../layoutslide)


---


