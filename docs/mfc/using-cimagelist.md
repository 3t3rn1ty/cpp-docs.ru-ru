---
title: Использование CImageList | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CImageList
dev_langs:
- C++
helpviewer_keywords:
- image list control
- CImageList class [MFC], using
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ebfcb8fbacd3c464fc3697fc15bad385c1547d4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420664"
---
# <a name="using-cimagelist"></a>Использование CImageList

Список изображений, представленный классом [CImageList](../mfc/reference/cimagelist-class.md), — это коллекция изображений одного размера, каждый из которых можно ссылаться по его индексу. Списки изображений используются эффективно управлять большими наборами значков и точечных рисунков. Списки изображений являются сами по себе не элементы управления, так как они не являются windows; Тем не менее, они применяются в несколько различных типов элементов управления, включая список элементов управления ([CListCtrl](../mfc/reference/clistctrl-class.md)), элементы управления дерева ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) и вкладок ([CTabCtrl](../mfc/reference/ctabctrl-class.md)).

Все образы в списке изображений содержатся в единый ширину растрового изображения в формате экрана устройства. Список изображений может также включать монохромную битовую карту, содержащий маски, используемый для рисования изображения прозрачно (стиль значка). `CImageList` предоставляет функции-члены, которые позволяют Рисование изображений, создания и уничтожения списков изображений, добавление и удаление изображений, Замена изображений, объединение изображений и перетащите изображения.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Типы списков изображений](../mfc/types-of-image-lists.md)

- [Использование списка изображений](../mfc/using-an-image-list.md)

- [Управление списками изображений](../mfc/manipulating-image-lists.md)

- [Рисование изображений из списка изображений](../mfc/drawing-images-from-an-image-list.md)

- [Перекрытия изображений в списках изображений](../mfc/image-overlays-in-image-lists.md)

- [Перетаскивание изображений из списка изображений](../mfc/dragging-images-from-an-image-list.md)

- [Сведения об изображениях в списках изображений](../mfc/image-information-in-image-lists.md)

## <a name="see-also"></a>См. также

[Элементы управления](../mfc/controls-mfc.md)

