---
title: Ошибка BSCMAKE BK1517 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- BK1517
dev_langs:
- C++
helpviewer_keywords:
- BK1517
ms.assetid: 24391f42-0a3e-40a9-9991-c8b9a6a7b1c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c6f5619a7c2a6ccf671845b27bbedf93d8eb2d69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="bscmake-error-bk1517"></a>Ошибка BSCMAKE BK1517
исходный SBR-файл скомпилирован с параметрами /Yc и /Yu  
  
 SBR-файл ссылается само на себя. Возможно, он был перекомпилирован с параметром /Yu после компиляции с параметром/Yc. Восстановите /Yc параметр компилятора для исходного файла, а затем выберите **Перестроить** , чтобы создать новый SBR-файлы. Не перекомпилируйте исходный файл с /Yu.