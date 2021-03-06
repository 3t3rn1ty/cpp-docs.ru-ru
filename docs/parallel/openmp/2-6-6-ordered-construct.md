---
title: 2.6.6 конструкция ordered | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b83c3dfc13b231a1314343a1dff496acf7a99b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412201"
---
# <a name="266-ordered-construct"></a>2.6.6 Конструкция ordered

Следующие структурированный блок **упорядоченные** директива выполняется в том порядке, в котором выполняются итерации с помощью последовательного цикла. Синтаксис **упорядоченные** директива выглядит следующим образом:

```
#pragma omp ordered new-linestructured-block
```

**Упорядоченные** директива должна быть в пределах динамический объем **для** или **параллельных для** построения. **Для** или **параллельных для** директивы, к которому **упорядоченные** конструкция привязки должен иметь **упорядоченные** условие, указанное как описано в разделе [Разделе 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) на стр. 11. При выполнении **для** или **параллельных для** построения с **упорядоченные** предложение, **упорядоченные** конструкции выполняются в строго порядок, в котором они будут выполняться в последовательного выполнения цикла.

Ограничения для **упорядоченные** директива таковы:

- Итерация цикла с **для** конструкция не может выполняться же директивы ordered более одного раза, и он не может выполняться несколько **упорядоченные** директива.