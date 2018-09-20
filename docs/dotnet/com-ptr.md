---
title: COM::PTR | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- ptr
dev_langs:
- C++
helpviewer_keywords:
- com::ptr
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f5e6a3f7936e21d22282fe37a29b5d91f2e50caa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434496"
---
# <a name="comptr"></a>com::ptr

Оболочка для COM-объекта, который может использоваться как член класса CLR. Оболочки также позволяет автоматизировать управление жизненным циклом COM-объекта, освобождая собственные ссылки объекта, когда его деструктора. Аналогично [класс CComPtr](../atl/reference/ccomptr-class.md).

## <a name="syntax"></a>Синтаксис

```
#include <msclr\com\ptr.h>
```

## <a name="remarks"></a>Примечания

[Класс COM::PTR](../dotnet/com-ptr-class.md) определяется в \<msclr\com\ptr.h > файла.

## <a name="see-also"></a>См. также

[Библиотека поддержки C++](../dotnet/cpp-support-library.md)