---
title: Aspose.Words.Layout
second_title: Référence de l'API Aspose.Words pour .NET
description: La Aspose.Words.Layoutnamespace fournit des classes qui permettent daccéder à des informations telles que sur quelle page et où sur une page des éléments de document particuliers sont positionnés lorsque le document est formaté en pages.
type: docs
weight: 110
url: /fr/net/aspose.words.layout/
---
La **Aspose.Words.Layout**namespace fournit des classes qui permettent d'accéder à des informations telles que sur quelle page et où sur une page des éléments de document particuliers sont positionnés, lorsque le document est formaté en pages.

## Des classes

| Classer | La description |
| --- | --- |
| [LayoutCollector](./layoutcollector/) | Cette classe permet de calculer les numéros de page des nœuds de document. |
| [LayoutEnumerator](./layoutenumerator/) | Énumère les entités de mise en page d'un document. Vous pouvez utiliser cette classe pour parcourir le modèle de mise en page. Les propriétés disponibles sont le type, la géométrie, le texte et l'index de page où l'entité est rendue, ainsi que la structure globale et les relations. Utilisez une combinaison de[`GetEntity`](../aspose.words.layout/layoutcollector/getentity/) et[`Current`](../aspose.words.layout/layoutenumerator/current/) déplacer vers l'entité qui correspond à un nœud de document. |
| [LayoutOptions](./layoutoptions/) | Contient les options qui permettent de contrôler le processus de mise en page du document. |
| [PageLayoutCallbackArgs](./pagelayoutcallbackargs/) | Un argument passé dans[`Notify`](../aspose.words.layout/ipagelayoutcallback/notify/) |
| [RevisionOptions](./revisionoptions/) | Permet de contrôler la façon dont les révisions de document sont gérées pendant le processus de mise en page. |
## Interfaces

| Interface | La description |
| --- | --- |
| [IPageLayoutCallback](./ipagelayoutcallback/) | Implémentez cette interface si vous souhaitez que votre propre méthode personnalisée soit appelée lors de la construction et du rendu du modèle de mise en page. |
## Énumération

| Énumération | La description |
| --- | --- |
| [CommentDisplayMode](./commentdisplaymode/) | Spécifie le mode de rendu des commentaires de document. |
| [ContinuousSectionRestart](./continuoussectionrestart/) | Représente différents comportements lors du calcul des numéros de page dans une section continue qui redémarre la numérotation des pages. |
| [LayoutEntityType](./layoutentitytype/) | Types des entités de mise en page. |
| [PageLayoutEvent](./pagelayoutevent/) | Un code d'événement déclenché lors de la création et du rendu du modèle de mise en page. |
| [RevisionColor](./revisioncolor/) | Permet de spécifier la couleur des révisions du document. |
| [RevisionTextEffect](./revisiontexteffect/) | Permet de spécifier l'effet de décoration pour les révisions du texte du document. |
| [ShowInBalloons](./showinballoons/) | Spécifie quelles révisions sont rendues dans des ballons. |


