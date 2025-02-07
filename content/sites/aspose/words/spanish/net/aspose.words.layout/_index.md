---
title: Aspose.Words.Layout
second_title: Referencia de API de Aspose.Words para .NET
description: los Aspose.Words.LayoutEl espacio de nombres proporciona clases que permiten acceder a información  como en qué página y en qué parte de una página se colocan los elementos de un documento en particular cuando el documento está formateado en páginas.
type: docs
weight: 110
url: /es/net/aspose.words.layout/
---
los **Aspose.Words.Layout**El espacio de nombres proporciona clases que permiten acceder a información , como en qué página y en qué parte de una página se colocan los elementos de un documento en particular, cuando el documento está formateado en páginas.

## Clases

| Clase | Descripción |
| --- | --- |
| [LayoutCollector](./layoutcollector/) | Esta clase permite calcular los números de página de los nodos del documento. |
| [LayoutEnumerator](./layoutenumerator/) | Enumera entidades de diseño de página de un documento. Puede utilizar esta clase para recorrer el modelo de diseño de página. Las propiedades disponibles son el tipo, la geometría, el texto y el índice de página donde se representa la entidad, , así como la estructura general y las relaciones. Usar una combinación de[`GetEntity`](../aspose.words.layout/layoutcollector/getentity/) y[`Current`](../aspose.words.layout/layoutenumerator/current/) mover a la entidad que corresponde a un documento node. |
| [LayoutOptions](./layoutoptions/) | Contiene las opciones que permiten controlar el proceso de maquetación del documento. |
| [PageLayoutCallbackArgs](./pagelayoutcallbackargs/) | Un argumento pasado a[`Notify`](../aspose.words.layout/ipagelayoutcallback/notify/) |
| [RevisionOptions](./revisionoptions/) | Permite controlar cómo se manejan las revisiones de documentos durante el proceso de diseño. |
## Interfaces

| Interfaz | Descripción |
| --- | --- |
| [IPageLayoutCallback](./ipagelayoutcallback/) | Implemente esta interfaz si desea que se llame a su propio método personalizado durante la creación y representación del modelo de diseño de página. |
## Enumeración

| Enumeración | Descripción |
| --- | --- |
| [CommentDisplayMode](./commentdisplaymode/) | Especifica el modo de representación de los comentarios del documento. |
| [ContinuousSectionRestart](./continuoussectionrestart/) | Representa diferentes comportamientos al calcular números de página en una sección continua que reinicia la numeración de páginas. |
| [LayoutEntityType](./layoutentitytype/) | Tipos de las entidades de diseño. |
| [PageLayoutEvent](./pagelayoutevent/) | Un código de evento generado durante la generación y representación del modelo de diseño de página. |
| [RevisionColor](./revisioncolor/) | Permite especificar el color de las revisiones del documento. |
| [RevisionTextEffect](./revisiontexteffect/) | Permite especificar el efecto de decoración para las revisiones del texto del documento. |
| [ShowInBalloons](./showinballoons/) | Especifica qué revisiones se representan en globos. |


