---
title: Class ShapeBase
second_title: Aspose.Words för .NET API Referens
description: Aspose.Words.Drawing.ShapeBase klass. Basklass för objekt i ritskiktet såsom en AutoShape freeform OLEobjekt ActiveXkontroll eller bild.
type: docs
weight: 1110
url: /sv/net/aspose.words.drawing/shapebase/
---
## ShapeBase class

Basklass för objekt i ritskiktet, såsom en AutoShape, freeform, OLE-objekt, ActiveX-kontroll eller bild.

```csharp
public abstract class ShapeBase : CompositeNode
```

## Egenskaper

| namn | Beskrivning |
| --- | --- |
| [AllowOverlap](../../aspose.words.drawing/shapebase/allowoverlap/) { get; set; } | Hämtar eller ställer in ett värde som anger om denna form kan överlappa andra former. |
| [AlternativeText](../../aspose.words.drawing/shapebase/alternativetext/) { get; set; } | Definierar alternativ text som ska visas istället för en grafik. |
| [AnchorLocked](../../aspose.words.drawing/shapebase/anchorlocked/) { get; set; } | Anger om formens ankare är låst. |
| [AspectRatioLocked](../../aspose.words.drawing/shapebase/aspectratiolocked/) { get; set; } | Anger om formens bildförhållande är låst. |
| [BehindText](../../aspose.words.drawing/shapebase/behindtext/) { get; set; } | Anger om formen är under eller över text. |
| [Bottom](../../aspose.words.drawing/shapebase/bottom/) { get; } | Hämtar positionen för den nedre kanten av det innehållande blocket av formen. |
| [Bounds](../../aspose.words.drawing/shapebase/bounds/) { get; set; } | Hämtar eller ställer in platsen och storleken på formens innehållsblock. |
| [BoundsInPoints](../../aspose.words.drawing/shapebase/boundsinpoints/) { get; } | Hämtar platsen och storleken på formens innehållande block i punkter, i förhållande till ankaret för den översta formen. |
| [BoundsWithEffects](../../aspose.words.drawing/shapebase/boundswitheffects/) { get; } | Får den slutliga omfattningen som detta formobjekt har efter applicering av ritningseffekter. Värdet mäts i punkter. |
| [CanHaveImage](../../aspose.words.drawing/shapebase/canhaveimage/) { get; } | Returnerar sant om formtypen tillåter att formen har en bild. |
| [ChildNodes](../../aspose.words/compositenode/childnodes/) { get; } | Hämtar alla omedelbara underordnade noder för denna nod. |
| [CoordOrigin](../../aspose.words.drawing/shapebase/coordorigin/) { get; set; } | Koordinaterna i det övre vänstra hörnet av det innehållande blocket med denna form. |
| [CoordSize](../../aspose.words.drawing/shapebase/coordsize/) { get; set; } | Bredden och höjden på koordinatutrymmet inuti det innehållande blocket med denna form. |
| [Count](../../aspose.words/compositenode/count/) { get; } | Hämtar antalet omedelbara barn till denna nod. |
| [CustomNodeId](../../aspose.words/node/customnodeid/) { get; set; } | Anger anpassad nodidentifierare. |
| [DistanceBottom](../../aspose.words.drawing/shapebase/distancebottom/) { get; set; } | Returnerar eller ställer in avståndet (i punkter) mellan dokumenttexten och den nedre kanten av formen. |
| [DistanceLeft](../../aspose.words.drawing/shapebase/distanceleft/) { get; set; } | Returnerar eller ställer in avståndet (i punkter) mellan dokumenttexten och den vänstra kanten av formen. |
| [DistanceRight](../../aspose.words.drawing/shapebase/distanceright/) { get; set; } | Returnerar eller ställer in avståndet (i punkter) mellan dokumenttexten och den högra kanten av formen. |
| [DistanceTop](../../aspose.words.drawing/shapebase/distancetop/) { get; set; } | Returnerar eller ställer in avståndet (i punkter) mellan dokumenttexten och formens övre kant. |
| virtual [Document](../../aspose.words/node/document/) { get; } | Hämtar dokumentet som denna nod tillhör. |
| [Fill](../../aspose.words.drawing/shapebase/fill/) { get; } | Får fyllningsformatering för formen. |
| [FirstChild](../../aspose.words/compositenode/firstchild/) { get; } | Får det första barnet i noden. |
| [FlipOrientation](../../aspose.words.drawing/shapebase/fliporientation/) { get; set; } | Ändrar orienteringen för en form. |
| [Font](../../aspose.words.drawing/shapebase/font/) { get; } | Ger tillgång till teckensnittsformateringen för detta objekt. |
| [HasChildNodes](../../aspose.words/compositenode/haschildnodes/) { get; } | Returnerar sant om denna nod har några underordnade noder. |
| [Height](../../aspose.words.drawing/shapebase/height/) { get; set; } | Hämtar eller ställer in höjden på formens innehållsblock. |
| [HorizontalAlignment](../../aspose.words.drawing/shapebase/horizontalalignment/) { get; set; } | Anger hur formen placeras horisontellt. |
| [HRef](../../aspose.words.drawing/shapebase/href/) { get; set; } | Hämtar eller ställer in den fullständiga hyperlänkadressen för en form. |
| override [IsComposite](../../aspose.words/compositenode/iscomposite/) { get; } | Returnerar sant eftersom denna nod kan ha underordnade noder. |
| [IsDecorative](../../aspose.words.drawing/shapebase/isdecorative/) { get; set; } | Hämtar eller ställer in flaggan som anger om formen är dekorativ i dokumentet. |
| [IsDeleteRevision](../../aspose.words.drawing/shapebase/isdeleterevision/) { get; } | Returnerar sant om detta objekt raderades i Microsoft Word medan ändringsspårning var aktiverad. |
| [IsGroup](../../aspose.words.drawing/shapebase/isgroup/) { get; } | Returnerar sant om detta är en gruppform. |
| [IsHorizontalRule](../../aspose.words.drawing/shapebase/ishorizontalrule/) { get; } | Returnerar sant om denna form är en horisontell regel. |
| [IsImage](../../aspose.words.drawing/shapebase/isimage/) { get; } | Returnerar sant om denna form är en bildform. |
| [IsInline](../../aspose.words.drawing/shapebase/isinline/) { get; } | Ett snabbt sätt att avgöra om denna form är placerad i linje med text. |
| [IsInsertRevision](../../aspose.words.drawing/shapebase/isinsertrevision/) { get; } | Returnerar sant om det här objektet infogades i Microsoft Word medan ändringsspårning var aktiverad. |
| [IsLayoutInCell](../../aspose.words.drawing/shapebase/islayoutincell/) { get; set; } | Hämtar eller sätter en flagga som indikerar om formen visas inuti en tabell eller utanför den. |
| [IsMoveFromRevision](../../aspose.words.drawing/shapebase/ismovefromrevision/) { get; } | Returnerar **Sann** om det här objektet flyttades (borttogs) i Microsoft Word medan ändringsspårning var aktiverad. |
| [IsMoveToRevision](../../aspose.words.drawing/shapebase/ismovetorevision/) { get; } | Returnerar **Sann** om detta objekt flyttades (infogades) i Microsoft Word medan ändringsspårning var aktiverad. |
| [IsSignatureLine](../../aspose.words.drawing/shapebase/issignatureline/) { get; } | Indikerar att formen är en SignatureLine. |
| [IsTopLevel](../../aspose.words.drawing/shapebase/istoplevel/) { get; } | Returnerar sant om denna form inte är ett underordnat till en gruppform. |
| [IsWordArt](../../aspose.words.drawing/shapebase/iswordart/) { get; } | Returnerar sant om den här formen är ett WordArt-objekt. |
| [LastChild](../../aspose.words/compositenode/lastchild/) { get; } | Hämtar nodens sista underordnade. |
| [Left](../../aspose.words.drawing/shapebase/left/) { get; set; } | Hämtar eller ställer in positionen för den vänstra kanten av formens innehållsblock. |
| [MarkupLanguage](../../aspose.words.drawing/shapebase/markuplanguage/) { get; } | Får MarkupLanguage som används för detta grafiska objekt. |
| [Name](../../aspose.words.drawing/shapebase/name/) { get; set; } | Hämtar eller ställer in det valfria formnamnet. |
| [NextSibling](../../aspose.words/node/nextsibling/) { get; } | Hämtar noden omedelbart efter denna nod. |
| abstract [NodeType](../../aspose.words/node/nodetype/) { get; } | Hämtar typen av denna nod. |
| [ParentNode](../../aspose.words/node/parentnode/) { get; } | Hämtar den omedelbara föräldern till denna nod. |
| [ParentParagraph](../../aspose.words.drawing/shapebase/parentparagraph/) { get; } | Returnerar det omedelbara överordnade stycket. |
| [PreviousSibling](../../aspose.words/node/previoussibling/) { get; } | Hämtar noden omedelbart före denna nod. |
| [Range](../../aspose.words/node/range/) { get; } | Returnerar en **Räckvidd** objekt som representerar den del av ett dokument som finns i denna nod. |
| [RelativeHorizontalPosition](../../aspose.words.drawing/shapebase/relativehorizontalposition/) { get; set; } | Anger i förhållande till vad formen är placerad horisontellt. |
| [RelativeVerticalPosition](../../aspose.words.drawing/shapebase/relativeverticalposition/) { get; set; } | Anger i förhållande till vad formen är placerad vertikalt. |
| [Right](../../aspose.words.drawing/shapebase/right/) { get; } | Får positionen för den högra kanten av det innehållande blocket av formen. |
| [Rotation](../../aspose.words.drawing/shapebase/rotation/) { get; set; } | Definierar vinkeln (i grader) som en form roteras. Positivt värde motsvarar medurs rotationsvinkel. |
| [ScreenTip](../../aspose.words.drawing/shapebase/screentip/) { get; set; } | Definierar texten som visas när muspekaren rör sig över formen. |
| [ShadowFormat](../../aspose.words.drawing/shapebase/shadowformat/) { get; } | Får skuggformatering för formen. |
| [ShapeType](../../aspose.words.drawing/shapebase/shapetype/) { get; } | Hämtar formtypen. |
| [SizeInPoints](../../aspose.words.drawing/shapebase/sizeinpoints/) { get; } | Får formens storlek i poäng. |
| [Target](../../aspose.words.drawing/shapebase/target/) { get; set; } | Hämtar eller ställer in målramen för formhyperlänken. |
| [Title](../../aspose.words.drawing/shapebase/title/) { get; set; } | Hämtar eller ställer in titeln (bildtexten) för det aktuella formobjektet. |
| [Top](../../aspose.words.drawing/shapebase/top/) { get; set; } | Hämtar eller ställer in positionen för den övre kanten av formens innehållsblock. |
| [VerticalAlignment](../../aspose.words.drawing/shapebase/verticalalignment/) { get; set; } | Anger hur formen är placerad vertikalt. |
| [Width](../../aspose.words.drawing/shapebase/width/) { get; set; } | Hämtar eller ställer in bredden på formens innehållsblock. |
| [WrapSide](../../aspose.words.drawing/shapebase/wrapside/) { get; set; } | Anger hur texten lindas runt formen. |
| [WrapType](../../aspose.words.drawing/shapebase/wraptype/) { get; set; } | Definierar om formen är inline eller flytande. För flytande former definierar lindningsläget för text runt formen. |
| [ZOrder](../../aspose.words.drawing/shapebase/zorder/) { get; set; } | Bestämmer visningsordningen för överlappande former. |

## Metoder

| namn | Beskrivning |
| --- | --- |
| abstract [Accept](../../aspose.words/node/accept/)(DocumentVisitor) | Accepterar en besökare. |
| [AdjustWithEffects](../../aspose.words.drawing/shapebase/adjustwitheffects/)(RectangleF) | Lägger till källrektangelvärdena för effektomfattningen och returnerar den sista rektangeln. |
| [AppendChild](../../aspose.words/compositenode/appendchild/)(Node) | Lägger till den angivna noden i slutet av listan över underordnade noder för denna nod. |
| [Clone](../../aspose.words/node/clone/)(bool) | Skapar en dubblett av noden. |
| [CreateNavigator](../../aspose.words/compositenode/createnavigator/)() | Reserverad för systemanvändning. IXPathNavigable. |
| [FetchInheritedShapeAttr](../../aspose.words.drawing/shapebase/fetchinheritedshapeattr/)(int) | Reserverad för systemanvändning. IShapeAttrSource. |
| [FetchShapeAttr](../../aspose.words.drawing/shapebase/fetchshapeattr/)(int) | Reserverad för systemanvändning. IShapeAttrSource. |
| [GetAncestor](../../aspose.words/node/getancestor/)(NodeType) | Hämtar den första förfadern till den angivna[`NodeType`](../../aspose.words/nodetype/) . |
| [GetAncestor](../../aspose.words/node/getancestor/)(Type) | Hämtar den första förfadern till den angivna objekttypen. |
| [GetChild](../../aspose.words/compositenode/getchild/)(NodeType, int, bool) | Returnerar en N:te underordnad nod som matchar den angivna typen. |
| [GetChildNodes](../../aspose.words/compositenode/getchildnodes/)(NodeType, bool) | Returnerar en aktiv samling av underordnade noder som matchar den angivna typen. |
| [GetDirectShapeAttr](../../aspose.words.drawing/shapebase/getdirectshapeattr/)(int) | Reserverad för systemanvändning. IShapeAttrSource. |
| [GetEnumerator](../../aspose.words/compositenode/getenumerator/)() | Tillhandahåller stöd för varje stiliteration över undernoderna för denna nod. |
| [GetShapeRenderer](../../aspose.words.drawing/shapebase/getshaperenderer/)() | Skapar och returnerar ett objekt som kan användas för att återge denna form till en bild. |
| override [GetText](../../aspose.words/compositenode/gettext/)() | Hämtar texten för denna nod och alla dess underordnade. |
| [IndexOf](../../aspose.words/compositenode/indexof/)(Node) | Returnerar indexet för den angivna undernoden i den underordnade nodmatrisen. |
| [InsertAfter](../../aspose.words/compositenode/insertafter/)(Node, Node) | Infogar den angivna noden omedelbart efter den angivna referensnoden. |
| [InsertBefore](../../aspose.words/compositenode/insertbefore/)(Node, Node) | Infogar den angivna noden omedelbart före den angivna referensnoden. |
| [LocalToParent](../../aspose.words.drawing/shapebase/localtoparent/)(PointF) | Konverterar ett värde från det lokala koordinatutrymmet till koordinatutrymmet för den överordnade formen. |
| [NextPreOrder](../../aspose.words/node/nextpreorder/)(Node) | Hämtar nästa nod enligt algoritmen för förbeställningsträdet. |
| [PrependChild](../../aspose.words/compositenode/prependchild/)(Node) | Lägger till den angivna noden i början av listan över underordnade noder för denna nod. |
| [PreviousPreOrder](../../aspose.words/node/previouspreorder/)(Node) | Hämtar föregående nod enligt algoritmen för förbeställningsträdet. |
| [Remove](../../aspose.words/node/remove/)() | Tar bort sig själv från föräldern. |
| [RemoveAllChildren](../../aspose.words/compositenode/removeallchildren/)() | Tar bort alla undernoder för den aktuella noden. |
| [RemoveChild](../../aspose.words/compositenode/removechild/)(Node) | Tar bort den angivna underordnade noden. |
| [RemoveShapeAttr](../../aspose.words.drawing/shapebase/removeshapeattr/)(int) | Reserverad för systemanvändning. IShapeAttrSource. |
| [RemoveSmartTags](../../aspose.words/compositenode/removesmarttags/)() | Tar bort alla[`SmartTag`](../../aspose.words.markup/smarttag/) underliggande noder till den aktuella noden. |
| [SelectNodes](../../aspose.words/compositenode/selectnodes/)(string) | Väljer en lista med noder som matchar XPath-uttrycket. |
| [SelectSingleNode](../../aspose.words/compositenode/selectsinglenode/)(string) | Väljer den första noden som matchar XPath-uttrycket. |
| [SetShapeAttr](../../aspose.words.drawing/shapebase/setshapeattr/)(int, object) | Reserverad för systemanvändning. IShapeAttrSource. |
| [ToString](../../aspose.words/node/tostring/)(SaveFormat) | Exporterar innehållet i noden till en sträng i angivet format. |
| [ToString](../../aspose.words/node/tostring/)(SaveOptions) | Exporterar innehållet i noden till en sträng med de angivna sparalternativen. |

### Anmärkningar

Detta är en abstrakt klass. De två härledda klasserna som du kan instansiera är[`Shape`](../shape/) och[`GroupShape`](../groupshape/).

En form är en nod i dokumentträdet.

Om formen är ett barn till en[`Paragraph`](../../aspose.words/paragraph/) objekt, då sägs formen vara "top-level". Toppnivå-former mäts och placeras i punkter.

En form kan också förekomma som barn till en[`GroupShape`](../groupshape/) objekt när flera former är grupperade. Underordnade former av en gruppform är placerade i koordinatutrymmet och units som definieras av[`CoordSize`](./coordsize/) och[`CoordOrigin`](./coordorigin/)egenskaper för gruppformen parent .

En form kan placeras inline med text eller flytande. Positioneringsmetoden kontrolleras med hjälp av[`WrapType`](./wraptype/) fast egendom.

När en form är flytande placeras den i förhållande till något (t.ex. det aktuella stycket, marginalen eller sidan). Formens relativa placering anges med hjälp av [`RelativeHorizontalPosition`](./relativehorizontalposition/) och[`RelativeVerticalPosition`](./relativeverticalposition/) egenskaper.

En flytande form placeras explicit med hjälp av[`Left`](./left/) och[`Top`](./top/) egenskaper eller justerad i förhållande till något annat objekt med hjälp av[`HorizontalAlignment`](./horizontalalignment/) och[`VerticalAlignment`](./verticalalignment/) egenskaper.

### Exempel

Visar hur man infogar en flytande bild i mitten av en sida.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Infoga en flytande bild som kommer att visas bakom den överlappande texten och justera den mot sidans mitt.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Se även

* class [CompositeNode](../../aspose.words/compositenode/)
* namnutrymme [Aspose.Words.Drawing](../../aspose.words.drawing/)
* hopsättning [Aspose.Words](../../)


