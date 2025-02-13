---
title: Class ShapeBase
second_title: Referencia de API de Aspose.Words para .NET
description: Aspose.Words.Drawing.ShapeBase clase. Clase base para objetos en la capa de dibujo como autoforma forma libre objeto OLE control ActiveX o imagen.
type: docs
weight: 1110
url: /es/net/aspose.words.drawing/shapebase/
---
## ShapeBase class

Clase base para objetos en la capa de dibujo, como autoforma, forma libre, objeto OLE, control ActiveX o imagen.

```csharp
public abstract class ShapeBase : CompositeNode
```

## Propiedades

| Nombre | Descripción |
| --- | --- |
| [AllowOverlap](../../aspose.words.drawing/shapebase/allowoverlap/) { get; set; } | Obtiene o establece un valor que especifica si esta forma puede superponerse a otras formas. |
| [AlternativeText](../../aspose.words.drawing/shapebase/alternativetext/) { get; set; } | Define el texto alternativo que se mostrará en lugar de un gráfico. |
| [AnchorLocked](../../aspose.words.drawing/shapebase/anchorlocked/) { get; set; } | Especifica si el ancla de la forma está bloqueada. |
| [AspectRatioLocked](../../aspose.words.drawing/shapebase/aspectratiolocked/) { get; set; } | Especifica si la relación de aspecto de la forma está bloqueada. |
| [BehindText](../../aspose.words.drawing/shapebase/behindtext/) { get; set; } | Especifica si la forma está debajo o encima del texto. |
| [Bottom](../../aspose.words.drawing/shapebase/bottom/) { get; } | Obtiene la posición del borde inferior del bloque contenedor de la forma. |
| [Bounds](../../aspose.words.drawing/shapebase/bounds/) { get; set; } | Obtiene o establece la ubicación y el tamaño del bloque contenedor de la forma. |
| [BoundsInPoints](../../aspose.words.drawing/shapebase/boundsinpoints/) { get; } | Obtiene la ubicación y el tamaño del bloque contenedor de la forma en puntos, en relación con el ancla de la forma superior. |
| [BoundsWithEffects](../../aspose.words.drawing/shapebase/boundswitheffects/) { get; } | Obtiene la extensión final que tiene este objeto de forma después de aplicar los efectos de dibujo. El valor se mide en puntos. |
| [CanHaveImage](../../aspose.words.drawing/shapebase/canhaveimage/) { get; } | Devuelve verdadero si el tipo de forma permite que la forma tenga una imagen. |
| [ChildNodes](../../aspose.words/compositenode/childnodes/) { get; } | Obtiene todos los nodos secundarios inmediatos de este nodo. |
| [CoordOrigin](../../aspose.words.drawing/shapebase/coordorigin/) { get; set; } | Las coordenadas en la esquina superior izquierda del bloque contenedor de esta forma. |
| [CoordSize](../../aspose.words.drawing/shapebase/coordsize/) { get; set; } | El ancho y alto del espacio de coordenadas dentro del bloque contenedor de esta forma. |
| [Count](../../aspose.words/compositenode/count/) { get; } | Obtiene el número de hijos inmediatos de este nodo. |
| [CustomNodeId](../../aspose.words/node/customnodeid/) { get; set; } | Especifica el identificador de nodo personalizado. |
| [DistanceBottom](../../aspose.words.drawing/shapebase/distancebottom/) { get; set; } | Devuelve o establece la distancia (en puntos) entre el texto del documento y el borde inferior de la forma. |
| [DistanceLeft](../../aspose.words.drawing/shapebase/distanceleft/) { get; set; } | Devuelve o establece la distancia (en puntos) entre el texto del documento y el borde izquierdo de la forma. |
| [DistanceRight](../../aspose.words.drawing/shapebase/distanceright/) { get; set; } | Devuelve o establece la distancia (en puntos) entre el texto del documento y el borde derecho de la forma. |
| [DistanceTop](../../aspose.words.drawing/shapebase/distancetop/) { get; set; } | Devuelve o establece la distancia (en puntos) entre el texto del documento y el borde superior de la forma. |
| virtual [Document](../../aspose.words/node/document/) { get; } | Obtiene el documento al que pertenece este nodo. |
| [Fill](../../aspose.words.drawing/shapebase/fill/) { get; } | Obtiene el formato de relleno para la forma. |
| [FirstChild](../../aspose.words/compositenode/firstchild/) { get; } | Obtiene el primer hijo del nodo. |
| [FlipOrientation](../../aspose.words.drawing/shapebase/fliporientation/) { get; set; } | Cambia la orientación de una forma. |
| [Font](../../aspose.words.drawing/shapebase/font/) { get; } | Proporciona acceso al formato de fuente de este objeto. |
| [HasChildNodes](../../aspose.words/compositenode/haschildnodes/) { get; } | Devuelve verdadero si este nodo tiene nodos secundarios. |
| [Height](../../aspose.words.drawing/shapebase/height/) { get; set; } | Obtiene o establece la altura del bloque contenedor de la forma. |
| [HorizontalAlignment](../../aspose.words.drawing/shapebase/horizontalalignment/) { get; set; } | Especifica cómo se coloca la forma horizontalmente. |
| [HRef](../../aspose.words.drawing/shapebase/href/) { get; set; } | Obtiene o establece la dirección de hipervínculo completa para una forma. |
| override [IsComposite](../../aspose.words/compositenode/iscomposite/) { get; } | Devuelve verdadero ya que este nodo puede tener nodos secundarios. |
| [IsDecorative](../../aspose.words.drawing/shapebase/isdecorative/) { get; set; } | Obtiene o establece el indicador que especifica si la forma es decorativa en el documento. |
| [IsDeleteRevision](../../aspose.words.drawing/shapebase/isdeleterevision/) { get; } | Devuelve verdadero si este objeto se eliminó en Microsoft Word mientras el seguimiento de cambios estaba habilitado. |
| [IsGroup](../../aspose.words.drawing/shapebase/isgroup/) { get; } | Devuelve verdadero si se trata de una forma de grupo. |
| [IsHorizontalRule](../../aspose.words.drawing/shapebase/ishorizontalrule/) { get; } | Devuelve verdadero si esta forma es una regla horizontal. |
| [IsImage](../../aspose.words.drawing/shapebase/isimage/) { get; } | Devuelve verdadero si esta forma es una forma de imagen. |
| [IsInline](../../aspose.words.drawing/shapebase/isinline/) { get; } | Una forma rápida de determinar si esta forma se coloca en línea con el texto. |
| [IsInsertRevision](../../aspose.words.drawing/shapebase/isinsertrevision/) { get; } | Devuelve verdadero si este objeto se insertó en Microsoft Word mientras el seguimiento de cambios estaba habilitado. |
| [IsLayoutInCell](../../aspose.words.drawing/shapebase/islayoutincell/) { get; set; } | Obtiene o establece un indicador que indica si la figura se muestra dentro o fuera de una tabla. |
| [IsMoveFromRevision](../../aspose.words.drawing/shapebase/ismovefromrevision/) { get; } | Devoluciones **verdadero** si este objeto se movió (eliminó) en Microsoft Word mientras el seguimiento de cambios estaba habilitado. |
| [IsMoveToRevision](../../aspose.words.drawing/shapebase/ismovetorevision/) { get; } | Devoluciones **verdadero** si este objeto se movió (insertó) en Microsoft Word mientras el seguimiento de cambios estaba habilitado. |
| [IsSignatureLine](../../aspose.words.drawing/shapebase/issignatureline/) { get; } | Indica que la forma es una SignatureLine. |
| [IsTopLevel](../../aspose.words.drawing/shapebase/istoplevel/) { get; } | Devuelve verdadero si esta forma no es hija de una forma de grupo. |
| [IsWordArt](../../aspose.words.drawing/shapebase/iswordart/) { get; } | Devuelve verdadero si esta forma es un objeto de WordArt. |
| [LastChild](../../aspose.words/compositenode/lastchild/) { get; } | Obtiene el último hijo del nodo. |
| [Left](../../aspose.words.drawing/shapebase/left/) { get; set; } | Obtiene o establece la posición del borde izquierdo del bloque contenedor de la forma. |
| [MarkupLanguage](../../aspose.words.drawing/shapebase/markuplanguage/) { get; } | Obtiene MarkupLanguage utilizado para este objeto gráfico. |
| [Name](../../aspose.words.drawing/shapebase/name/) { get; set; } | Obtiene o establece el nombre de forma opcional. |
| [NextSibling](../../aspose.words/node/nextsibling/) { get; } | Obtiene el nodo que sigue inmediatamente a este nodo. |
| abstract [NodeType](../../aspose.words/node/nodetype/) { get; } | Obtiene el tipo de este nodo. |
| [ParentNode](../../aspose.words/node/parentnode/) { get; } | Obtiene el padre inmediato de este nodo. |
| [ParentParagraph](../../aspose.words.drawing/shapebase/parentparagraph/) { get; } | Devuelve el párrafo padre inmediato. |
| [PreviousSibling](../../aspose.words/node/previoussibling/) { get; } | Obtiene el nodo inmediatamente anterior a este nodo. |
| [Range](../../aspose.words/node/range/) { get; } | Devuelve un **Rango** objeto que representa la parte de un documento que está contenido en este nodo. |
| [RelativeHorizontalPosition](../../aspose.words.drawing/shapebase/relativehorizontalposition/) { get; set; } | Especifica en relación con la posición horizontal de la forma. |
| [RelativeVerticalPosition](../../aspose.words.drawing/shapebase/relativeverticalposition/) { get; set; } | Especifica en relación a qué forma se coloca verticalmente. |
| [Right](../../aspose.words.drawing/shapebase/right/) { get; } | Obtiene la posición del borde derecho del bloque contenedor de la forma. |
| [Rotation](../../aspose.words.drawing/shapebase/rotation/) { get; set; } | Define el ángulo (en grados) con el que se rota una forma. El valor positivo corresponde al ángulo de rotación en el sentido de las agujas del reloj. |
| [ScreenTip](../../aspose.words.drawing/shapebase/screentip/) { get; set; } | Define el texto que se muestra cuando el puntero del mouse se mueve sobre la forma. |
| [ShadowFormat](../../aspose.words.drawing/shapebase/shadowformat/) { get; } | Obtiene el formato de sombra para la forma. |
| [ShapeType](../../aspose.words.drawing/shapebase/shapetype/) { get; } | Obtiene el tipo de forma. |
| [SizeInPoints](../../aspose.words.drawing/shapebase/sizeinpoints/) { get; } | Obtiene el tamaño de la forma en puntos. |
| [Target](../../aspose.words.drawing/shapebase/target/) { get; set; } | Obtiene o establece el marco de destino para el hipervínculo de forma. |
| [Title](../../aspose.words.drawing/shapebase/title/) { get; set; } | Obtiene o establece el título (título) del objeto de forma actual. |
| [Top](../../aspose.words.drawing/shapebase/top/) { get; set; } | Obtiene o establece la posición del borde superior del bloque contenedor de la forma. |
| [VerticalAlignment](../../aspose.words.drawing/shapebase/verticalalignment/) { get; set; } | Especifica cómo se coloca la forma verticalmente. |
| [Width](../../aspose.words.drawing/shapebase/width/) { get; set; } | Obtiene o establece el ancho del bloque contenedor de la forma. |
| [WrapSide](../../aspose.words.drawing/shapebase/wrapside/) { get; set; } | Especifica cómo se envuelve el texto alrededor de la forma. |
| [WrapType](../../aspose.words.drawing/shapebase/wraptype/) { get; set; } | Define si la forma es en línea o flotante. Para formas flotantes define el modo de ajuste para el texto alrededor de la forma. |
| [ZOrder](../../aspose.words.drawing/shapebase/zorder/) { get; set; } | Determina el orden de visualización de las formas superpuestas. |

## Métodos

| Nombre | Descripción |
| --- | --- |
| abstract [Accept](../../aspose.words/node/accept/)(DocumentVisitor) | Acepta un visitante. |
| [AdjustWithEffects](../../aspose.words.drawing/shapebase/adjustwitheffects/)(RectangleF) | Agrega al rectángulo de origen los valores de la extensión del efecto y devuelve el rectángulo final. |
| [AppendChild](../../aspose.words/compositenode/appendchild/)(Node) | Agrega el nodo especificado al final de la lista de nodos secundarios para este nodo. |
| [Clone](../../aspose.words/node/clone/)(bool) | Crea un duplicado del nodo. |
| [CreateNavigator](../../aspose.words/compositenode/createnavigator/)() | Reservado para uso del sistema. IXPathNavigable. |
| [FetchInheritedShapeAttr](../../aspose.words.drawing/shapebase/fetchinheritedshapeattr/)(int) | Reservado para uso del sistema. IShapeAttrSource. |
| [FetchShapeAttr](../../aspose.words.drawing/shapebase/fetchshapeattr/)(int) | Reservado para uso del sistema. IShapeAttrSource. |
| [GetAncestor](../../aspose.words/node/getancestor/)(NodeType) | Obtiene el primer ancestro del especificado[`NodeType`](../../aspose.words/nodetype/) . |
| [GetAncestor](../../aspose.words/node/getancestor/)(Type) | Obtiene el primer ancestro del tipo de objeto especificado. |
| [GetChild](../../aspose.words/compositenode/getchild/)(NodeType, int, bool) | Devuelve un enésimo nodo secundario que coincide con el tipo especificado. |
| [GetChildNodes](../../aspose.words/compositenode/getchildnodes/)(NodeType, bool) | Devuelve una colección activa de nodos secundarios que coinciden con el tipo especificado. |
| [GetDirectShapeAttr](../../aspose.words.drawing/shapebase/getdirectshapeattr/)(int) | Reservado para uso del sistema. IShapeAttrSource. |
| [GetEnumerator](../../aspose.words/compositenode/getenumerator/)() | Proporciona soporte para la iteración de cada estilo sobre los nodos secundarios de este nodo. |
| [GetShapeRenderer](../../aspose.words.drawing/shapebase/getshaperenderer/)() | Crea y devuelve un objeto que se puede usar para convertir esta forma en una imagen. |
| override [GetText](../../aspose.words/compositenode/gettext/)() | Obtiene el texto de este nodo y de todos sus hijos. |
| [IndexOf](../../aspose.words/compositenode/indexof/)(Node) | Devuelve el índice del nodo secundario especificado en la matriz de nodos secundarios. |
| [InsertAfter](../../aspose.words/compositenode/insertafter/)(Node, Node) | Inserta el nodo especificado inmediatamente después del nodo de referencia especificado. |
| [InsertBefore](../../aspose.words/compositenode/insertbefore/)(Node, Node) | Inserta el nodo especificado inmediatamente antes del nodo de referencia especificado. |
| [LocalToParent](../../aspose.words.drawing/shapebase/localtoparent/)(PointF) | Convierte un valor del espacio de coordenadas local en el espacio de coordenadas de la forma principal. |
| [NextPreOrder](../../aspose.words/node/nextpreorder/)(Node) | Obtiene el siguiente nodo de acuerdo con el algoritmo de recorrido del árbol de pedido previo. |
| [PrependChild](../../aspose.words/compositenode/prependchild/)(Node) | Agrega el nodo especificado al principio de la lista de nodos secundarios para este nodo. |
| [PreviousPreOrder](../../aspose.words/node/previouspreorder/)(Node) | Obtiene el nodo anterior de acuerdo con el algoritmo de recorrido del árbol de pedido previo. |
| [Remove](../../aspose.words/node/remove/)() | Se elimina a sí mismo del padre. |
| [RemoveAllChildren](../../aspose.words/compositenode/removeallchildren/)() | Elimina todos los nodos secundarios del nodo actual. |
| [RemoveChild](../../aspose.words/compositenode/removechild/)(Node) | Elimina el nodo secundario especificado. |
| [RemoveShapeAttr](../../aspose.words.drawing/shapebase/removeshapeattr/)(int) | Reservado para uso del sistema. IShapeAttrSource. |
| [RemoveSmartTags](../../aspose.words/compositenode/removesmarttags/)() | Elimina todo[`SmartTag`](../../aspose.words.markup/smarttag/) nodos descendientes del nodo actual. |
| [SelectNodes](../../aspose.words/compositenode/selectnodes/)(string) | Selecciona una lista de nodos que coinciden con la expresión XPath. |
| [SelectSingleNode](../../aspose.words/compositenode/selectsinglenode/)(string) | Selecciona el primer nodo que coincide con la expresión XPath. |
| [SetShapeAttr](../../aspose.words.drawing/shapebase/setshapeattr/)(int, object) | Reservado para uso del sistema. IShapeAttrSource. |
| [ToString](../../aspose.words/node/tostring/)(SaveFormat) | Exporta el contenido del nodo a una cadena en el formato especificado. |
| [ToString](../../aspose.words/node/tostring/)(SaveOptions) | Exporta el contenido del nodo a una cadena utilizando las opciones de guardado especificadas. |

### Observaciones

Esto es una clase abstracta. Las dos clases derivadas que puede instanciar son[`Shape`](../shape/) y[`GroupShape`](../groupshape/).

Una forma es un nodo en el árbol del documento.

Si la forma es hija de un[`Paragraph`](../../aspose.words/paragraph/) objeto, entonces se dice que la forma es de "nivel superior". Las formas de nivel superior se miden y colocan en puntos.

Una forma también puede ocurrir como un hijo de un[`GroupShape`](../groupshape/) objeto cuando se agrupan varias formas . Las formas secundarias de una forma de grupo se colocan en el espacio de coordenadas y las unidades definidas por el[`CoordSize`](./coordsize/) y[`CoordOrigin`](./coordorigin/)propiedades de la forma del grupo parent .

Una forma se puede colocar en línea con el texto o flotar. El método de posicionamiento se controla usando el[`WrapType`](./wraptype/) propiedad.

Cuando una forma está flotando, se posiciona en relación con algo (por ejemplo, el párrafo actual, el margen o la página). El posicionamiento relativo de la forma se especifica usando the [`RelativeHorizontalPosition`](./relativehorizontalposition/) y[`RelativeVerticalPosition`](./relativeverticalposition/) propiedades.

Una forma flotante puede posicionarse explícitamente usando el[`Left`](./left/) y[`Top`](./top/) propiedades o alineado en relación con algún otro objeto usando el[`HorizontalAlignment`](./horizontalalignment/) y[`VerticalAlignment`](./verticalalignment/) propiedades.

### Ejemplos

Muestra cómo insertar una imagen flotante en el centro de una página.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Inserta una imagen flotante que aparecerá detrás del texto superpuesto y alinéala con el centro de la página.
Shape shape = builder.InsertImage(ImageDir + "Logo.jpg");
shape.WrapType = WrapType.None;
shape.BehindText = true;
shape.RelativeHorizontalPosition = RelativeHorizontalPosition.Page;
shape.RelativeVerticalPosition = RelativeVerticalPosition.Page;
shape.HorizontalAlignment = HorizontalAlignment.Center;
shape.VerticalAlignment = VerticalAlignment.Center;

doc.Save(ArtifactsDir + "Image.CreateFloatingPageCenter.docx");
```

### Ver también

* class [CompositeNode](../../aspose.words/compositenode/)
* espacio de nombres [Aspose.Words.Drawing](../../aspose.words.drawing/)
* asamblea [Aspose.Words](../../)


