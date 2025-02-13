---
title: Class ShapeBase
second_title: Aspose.Words for .NET API 参考
description: Aspose.Words.Drawing.ShapeBase 班级. 绘图层中对象的基类例如自选图形自由格式OLE 对象ActiveX 控件或图片
type: docs
weight: 1110
url: /zh/net/aspose.words.drawing/shapebase/
---
## ShapeBase class

绘图层中对象的基类，例如自选图形、自由格式、OLE 对象、ActiveX 控件或图片。

```csharp
public abstract class ShapeBase : CompositeNode
```

## 特性

| 姓名 | 描述 |
| --- | --- |
| [AllowOverlap](../../aspose.words.drawing/shapebase/allowoverlap/) { get; set; } | 获取或设置一个值，该值指定此形状是否可以与其他形状重叠。 |
| [AlternativeText](../../aspose.words.drawing/shapebase/alternativetext/) { get; set; } | 定义要显示的替代文本而不是图形。 |
| [AnchorLocked](../../aspose.words.drawing/shapebase/anchorlocked/) { get; set; } | 指定形状的锚点是否被锁定。 |
| [AspectRatioLocked](../../aspose.words.drawing/shapebase/aspectratiolocked/) { get; set; } | 指定形状的纵横比是否被锁定。 |
| [BehindText](../../aspose.words.drawing/shapebase/behindtext/) { get; set; } | 指定形状是低于还是高于文本。 |
| [Bottom](../../aspose.words.drawing/shapebase/bottom/) { get; } | 获取形状包含块的底边位置。 |
| [Bounds](../../aspose.words.drawing/shapebase/bounds/) { get; set; } | 获取或设置形状的包含块的位置和大小。 |
| [BoundsInPoints](../../aspose.words.drawing/shapebase/boundsinpoints/) { get; } | 获取形状包含块的位置和大小，以点为单位，相对于最顶部形状的锚点。 |
| [BoundsWithEffects](../../aspose.words.drawing/shapebase/boundswitheffects/) { get; } | 获取此形状对象在应用绘图效果后的最终范围。 值以点为单位。 |
| [CanHaveImage](../../aspose.words.drawing/shapebase/canhaveimage/) { get; } | 如果形状类型允许形状具有图像，则返回 true。 |
| [ChildNodes](../../aspose.words/compositenode/childnodes/) { get; } | 获取该节点的所有直接子节点。 |
| [CoordOrigin](../../aspose.words.drawing/shapebase/coordorigin/) { get; set; } | 此形状的包含块左上角的坐标。 |
| [CoordSize](../../aspose.words.drawing/shapebase/coordsize/) { get; set; } | 此形状的包含块内坐标空间的宽度和高度。 |
| [Count](../../aspose.words/compositenode/count/) { get; } | 获取此节点的直接子节点数。 |
| [CustomNodeId](../../aspose.words/node/customnodeid/) { get; set; } | 指定自定义节点标识符。 |
| [DistanceBottom](../../aspose.words.drawing/shapebase/distancebottom/) { get; set; } | 返回或设置文档文本和形状底部边缘之间的距离（以磅为单位）。 |
| [DistanceLeft](../../aspose.words.drawing/shapebase/distanceleft/) { get; set; } | 返回或设置文档文本和形状左边缘之间的距离（以磅为单位）。 |
| [DistanceRight](../../aspose.words.drawing/shapebase/distanceright/) { get; set; } | 返回或设置文档文本和形状右边缘之间的距离（以磅为单位）。 |
| [DistanceTop](../../aspose.words.drawing/shapebase/distancetop/) { get; set; } | 返回或设置文档文本和形状上边缘之间的距离（以磅为单位）。 |
| virtual [Document](../../aspose.words/node/document/) { get; } | 获取该节点所属的文档。 |
| [Fill](../../aspose.words.drawing/shapebase/fill/) { get; } | 获取形状的填充格式。 |
| [FirstChild](../../aspose.words/compositenode/firstchild/) { get; } | 获取节点的第一个子节点。 |
| [FlipOrientation](../../aspose.words.drawing/shapebase/fliporientation/) { get; set; } | 切换形状的方向。 |
| [Font](../../aspose.words.drawing/shapebase/font/) { get; } | 提供对此对象的字体格式的访问。 |
| [HasChildNodes](../../aspose.words/compositenode/haschildnodes/) { get; } | 如果此节点有任何子节点，则返回 true。 |
| [Height](../../aspose.words.drawing/shapebase/height/) { get; set; } | 获取或设置形状包含块的高度。 |
| [HorizontalAlignment](../../aspose.words.drawing/shapebase/horizontalalignment/) { get; set; } | 指定形状如何水平放置。 |
| [HRef](../../aspose.words.drawing/shapebase/href/) { get; set; } | 获取或设置形状的完整超链接地址。 |
| override [IsComposite](../../aspose.words/compositenode/iscomposite/) { get; } | 返回真，因为该节点可以有子节点。 |
| [IsDecorative](../../aspose.words.drawing/shapebase/isdecorative/) { get; set; } | 获取或设置指定形状在文档中是否具有装饰性的标志。 |
| [IsDeleteRevision](../../aspose.words.drawing/shapebase/isdeleterevision/) { get; } | 如果在启用更改跟踪时在 Microsoft Word 中删除了此对象，则返回 true。 |
| [IsGroup](../../aspose.words.drawing/shapebase/isgroup/) { get; } | 如果这是一个组形状，则返回 true。 |
| [IsHorizontalRule](../../aspose.words.drawing/shapebase/ishorizontalrule/) { get; } | 如果此形状是水平规则，则返回 true。 |
| [IsImage](../../aspose.words.drawing/shapebase/isimage/) { get; } | 如果此形状是图像形状，则返回 true。 |
| [IsInline](../../aspose.words.drawing/shapebase/isinline/) { get; } | 一种快速确定此形状是否与文本内联的方法。 |
| [IsInsertRevision](../../aspose.words.drawing/shapebase/isinsertrevision/) { get; } | 如果在启用更改跟踪时将此对象插入 Microsoft Word，则返回 true。 |
| [IsLayoutInCell](../../aspose.words.drawing/shapebase/islayoutincell/) { get; set; } | 获取或设置一个标志，指示形状是显示在表格内还是表格外。 |
| [IsMoveFromRevision](../../aspose.words.drawing/shapebase/ismovefromrevision/) { get; } | 返回 **真的**如果启用更改跟踪时此对象在 Microsoft Word 中被移动（删除）。 |
| [IsMoveToRevision](../../aspose.words.drawing/shapebase/ismovetorevision/) { get; } | 返回 **真的**如果启用更改跟踪时在 Microsoft Word 中移动（插入）此对象。 |
| [IsSignatureLine](../../aspose.words.drawing/shapebase/issignatureline/) { get; } | 表示形状是 SignatureLine. |
| [IsTopLevel](../../aspose.words.drawing/shapebase/istoplevel/) { get; } | 如果此形状不是组形状的子形状，则返回 true。 |
| [IsWordArt](../../aspose.words.drawing/shapebase/iswordart/) { get; } | 如果此形状是艺术字对象，则返回 true。 |
| [LastChild](../../aspose.words/compositenode/lastchild/) { get; } | 获取节点的最后一个子节点。 |
| [Left](../../aspose.words.drawing/shapebase/left/) { get; set; } | 获取或设置形状包含块的左边缘位置。 |
| [MarkupLanguage](../../aspose.words.drawing/shapebase/markuplanguage/) { get; } | 获取用于此图形对象的 MarkupLanguage。 |
| [Name](../../aspose.words.drawing/shapebase/name/) { get; set; } | 获取或设置可选的形状名称。 |
| [NextSibling](../../aspose.words/node/nextsibling/) { get; } | 获取紧跟此节点的节点。 |
| abstract [NodeType](../../aspose.words/node/nodetype/) { get; } | 获取此节点的类型。 |
| [ParentNode](../../aspose.words/node/parentnode/) { get; } | 获取此节点的直接父节点。 |
| [ParentParagraph](../../aspose.words.drawing/shapebase/parentparagraph/) { get; } | 返回直接父段落。 |
| [PreviousSibling](../../aspose.words/node/previoussibling/) { get; } | 获取紧接在此节点之前的节点。 |
| [Range](../../aspose.words/node/range/) { get; } | 返回一个 **范围**表示此节点中包含的文档部分的对象。 |
| [RelativeHorizontalPosition](../../aspose.words.drawing/shapebase/relativehorizontalposition/) { get; set; } | 指定相对于水平位置的形状。 |
| [RelativeVerticalPosition](../../aspose.words.drawing/shapebase/relativeverticalposition/) { get; set; } | 指定相对于形状垂直定位的位置。 |
| [Right](../../aspose.words.drawing/shapebase/right/) { get; } | 获取形状包含块的右边缘位置。 |
| [Rotation](../../aspose.words.drawing/shapebase/rotation/) { get; set; } | 定义形状旋转的角度（以度为单位）。 正值对应于顺时针旋转角度。 |
| [ScreenTip](../../aspose.words.drawing/shapebase/screentip/) { get; set; } | 定义当鼠标指针移到形状上时显示的文本。 |
| [ShadowFormat](../../aspose.words.drawing/shapebase/shadowformat/) { get; } | 获取形状的阴影格式。 |
| [ShapeType](../../aspose.words.drawing/shapebase/shapetype/) { get; } | 获取形状类型。 |
| [SizeInPoints](../../aspose.words.drawing/shapebase/sizeinpoints/) { get; } | 以点为单位获取形状的大小。 |
| [Target](../../aspose.words.drawing/shapebase/target/) { get; set; } | 获取或设置形状超链接的目标框架。 |
| [Title](../../aspose.words.drawing/shapebase/title/) { get; set; } | 获取或设置当前形状对象的标题（标题）。 |
| [Top](../../aspose.words.drawing/shapebase/top/) { get; set; } | 获取或设置形状包含块的上边缘的位置。 |
| [VerticalAlignment](../../aspose.words.drawing/shapebase/verticalalignment/) { get; set; } | 指定形状如何垂直定位。 |
| [Width](../../aspose.words.drawing/shapebase/width/) { get; set; } | 获取或设置形状包含块的宽度。 |
| [WrapSide](../../aspose.words.drawing/shapebase/wrapside/) { get; set; } | 指定文本如何环绕形状。 |
| [WrapType](../../aspose.words.drawing/shapebase/wraptype/) { get; set; } | 定义形状是内联的还是浮动的。对于浮动形状，定义形状周围文本的环绕模式。 |
| [ZOrder](../../aspose.words.drawing/shapebase/zorder/) { get; set; } | 确定重叠形状的显示顺序。 |

## 方法

| 姓名 | 描述 |
| --- | --- |
| abstract [Accept](../../aspose.words/node/accept/)(DocumentVisitor) | 接受访客。 |
| [AdjustWithEffects](../../aspose.words.drawing/shapebase/adjustwitheffects/)(RectangleF) | 添加到效果范围的源矩形值并返回最终矩形。 |
| [AppendChild](../../aspose.words/compositenode/appendchild/)(Node) | 将指定节点添加到该节点的子节点列表的末尾。 |
| [Clone](../../aspose.words/node/clone/)(bool) | 创建节点的副本。 |
| [CreateNavigator](../../aspose.words/compositenode/createnavigator/)() | 保留供系统使用。 IXPathNavigable. |
| [FetchInheritedShapeAttr](../../aspose.words.drawing/shapebase/fetchinheritedshapeattr/)(int) | 保留供系统使用。 IShapeAttrSource. |
| [FetchShapeAttr](../../aspose.words.drawing/shapebase/fetchshapeattr/)(int) | 保留供系统使用。 IShapeAttrSource. |
| [GetAncestor](../../aspose.words/node/getancestor/)(NodeType) | 获取指定的第一个祖先[`NodeType`](../../aspose.words/nodetype/). |
| [GetAncestor](../../aspose.words/node/getancestor/)(Type) | 获取指定对象类型的第一个祖先。 |
| [GetChild](../../aspose.words/compositenode/getchild/)(NodeType, int, bool) | 返回与指定类型匹配的第 N 个子节点。 |
| [GetChildNodes](../../aspose.words/compositenode/getchildnodes/)(NodeType, bool) | 返回与指定类型匹配的子节点的实时集合。 |
| [GetDirectShapeAttr](../../aspose.words.drawing/shapebase/getdirectshapeattr/)(int) | 保留供系统使用。 IShapeAttrSource. |
| [GetEnumerator](../../aspose.words/compositenode/getenumerator/)() | 为在该节点的子节点上的每个样式迭代提供支持。 |
| [GetShapeRenderer](../../aspose.words.drawing/shapebase/getshaperenderer/)() | 创建并返回一个可用于将此形状渲染为图像的对象。 |
| override [GetText](../../aspose.words/compositenode/gettext/)() | 获取该节点及其所有子节点的文本。 |
| [IndexOf](../../aspose.words/compositenode/indexof/)(Node) | 返回子节点数组中指定子节点的索引。 |
| [InsertAfter](../../aspose.words/compositenode/insertafter/)(Node, Node) | 在指定参考节点之后立即插入指定节点。 |
| [InsertBefore](../../aspose.words/compositenode/insertbefore/)(Node, Node) | 在指定的参考节点之前插入指定的节点。 |
| [LocalToParent](../../aspose.words.drawing/shapebase/localtoparent/)(PointF) | 将一个值从局部坐标空间转换为父图形的坐标空间。 |
| [NextPreOrder](../../aspose.words/node/nextpreorder/)(Node) | 根据前序树遍历算法获取下一个节点。 |
| [PrependChild](../../aspose.words/compositenode/prependchild/)(Node) | 将指定节点添加到此节点的子节点列表的开头。 |
| [PreviousPreOrder](../../aspose.words/node/previouspreorder/)(Node) | 根据前序树遍历算法获取上一个节点。 |
| [Remove](../../aspose.words/node/remove/)() | 从父级中移除自身。 |
| [RemoveAllChildren](../../aspose.words/compositenode/removeallchildren/)() | 移除当前节点的所有子节点。 |
| [RemoveChild](../../aspose.words/compositenode/removechild/)(Node) | 移除指定的子节点。 |
| [RemoveShapeAttr](../../aspose.words.drawing/shapebase/removeshapeattr/)(int) | 保留供系统使用。 IShapeAttrSource. |
| [RemoveSmartTags](../../aspose.words/compositenode/removesmarttags/)() | 删除所有[`SmartTag`](../../aspose.words.markup/smarttag/)当前节点的后代节点。 |
| [SelectNodes](../../aspose.words/compositenode/selectnodes/)(string) | 选择与 XPath 表达式匹配的节点列表。 |
| [SelectSingleNode](../../aspose.words/compositenode/selectsinglenode/)(string) | 选择与 XPath 表达式匹配的第一个节点。 |
| [SetShapeAttr](../../aspose.words.drawing/shapebase/setshapeattr/)(int, object) | 保留供系统使用。 IShapeAttrSource. |
| [ToString](../../aspose.words/node/tostring/)(SaveFormat) | 将节点的内容导出为指定格式的字符串。 |
| [ToString](../../aspose.words/node/tostring/)(SaveOptions) | 使用指定的保存选项将节点的内容导出为字符串。 |

### 评论

这是一个抽象类。您可以实例化 的两个派生类是[`Shape`](../shape/)和[`GroupShape`](../groupshape/).

形状是文档树中的一个节点。

如果形状是 a 的孩子[`Paragraph`](../../aspose.words/paragraph/)对象，则该形状被称为“顶级”。 顶级形状以点为单位进行测量和定位。

形状也可以作为 a 的子级出现[`GroupShape`](../groupshape/)多个shapes 被分组时的对象。组形状的子形状位于坐标空间中，units 由[`CoordSize`](./coordsize/)和[`CoordOrigin`](./coordorigin/)parent 组形状的属性。

形状可以与文本内联或浮动定位。定位方法是使用受控 [`WrapType`](./wraptype/)财产。

当一个形状浮动时，它是相对于某物（例如当前段落、 边距或页面）定位的。使用 指定形状的相对定位[`RelativeHorizontalPosition`](./relativehorizontalposition/)和[`RelativeVerticalPosition`](./relativeverticalposition/)特性。

使用[`Left`](./left/)和[`Top`](./top/) 属性或使用相对于其他对象对齐[`HorizontalAlignment`](./horizontalalignment/) 和[`VerticalAlignment`](./verticalalignment/)特性。

### 例子

演示如何将浮动图像插入页面中心。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// 插入将出现在重叠文本后面的浮动图像，并将其与页面中心对齐。
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### 也可以看看

* class [CompositeNode](../../aspose.words/compositenode/)
* 命名空间 [Aspose.Words.Drawing](../../aspose.words.drawing/)
* 部件 [Aspose.Words](../../)


