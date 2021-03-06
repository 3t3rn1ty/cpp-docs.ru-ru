---
title: регион, endregion | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs:
- C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dac2df26f393b7491d94abdb6d987a8e424723e1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45715563"
---
# <a name="region-endregion"></a>region, endregion
`#pragma region` позволяет указать блок кода, который можно разворачивать и сворачивать с помощью [возможности структурирования](/visualstudio/ide/outlining) редактор кода Visual Studio.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
### <a name="parameters"></a>Параметры  
*comment*  
(Необязательно) Комментарий, который будет отображаться в редакторе кода.  
  
*name*  
(Необязательно) Имя области.  Имя, отображаемое в редакторе кода.  
  
## <a name="remarks"></a>Примечания  
 
`#pragma endregion` Помечает конец `#pragma region` блока.  
  
Объект `#region` блок должен заканчиваться `#pragma endregion`.  
  
## <a name="example"></a>Пример  
  
```cpp  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)