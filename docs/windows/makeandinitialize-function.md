---
title: "Функция MakeAndInitialize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::MakeAndInitialize"
dev_langs: 
  - "C++"
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# Функция MakeAndInitialize
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Инициализирует заданный класс [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Используйте эту функцию, чтобы создать экземпляр компонента, который определен в том же модуле.  
  
## Синтаксис  
  
```cpp  
template <typename T, typename I,   
typename TArg1,   
typename TArg2,   
typename TArg3,   
typename TArg4,   
typename TArg5,   
typename TArg6,   
typename TArg7,   
typename TArg8,   
typename TArg9> HRESULT MakeAndInitialize(_Outptr_result_nullonfailure_ I** ppvObject, TArg1 &&arg1, TArg2 &&arg2, TArg3 &&arg3, TArg4 &&arg4, TArg5 &&arg5, TArg6 &&arg6, TArg7 &&arg7, TArg8 &&arg8, TArg9 &&arg9) throw()  
  
```  
  
#### Параметры  
 `T`  
 Определяемый пользователем класс, наследуемый от `WRL::RuntimeClass`.  
  
 `TArg1`  
 Тип аргумента 1, который передается указанному классу среды выполнения.  
  
 `TArg2`  
 Тип аргумента 2, который передается указанному классу среды выполнения.  
  
 `TArg3`  
 Тип аргумента 3, который передается указанному классу среды выполнения.  
  
 `TArg4`  
 Тип аргумента 4, который передается указанному классу среды выполнения.  
  
 `TArg5`  
 Тип аргумента 5, который передается указанному классу среды выполнения.  
  
 `TArg6`  
 Тип аргумента 6, который передается указанному классу среды выполнения.  
  
 `TArg7`  
 Тип аргумента 7, который передается указанному классу среды выполнения.  
  
 `TArg8`  
 Тип аргумента 8, который передается указанному классу среды выполнения.  
  
 `TArg9`  
 Тип аргумента 9, который передается указанному классу среды выполнения.  
  
 `arg1`  
 Аргумент 1, который передается указанному классу среды выполнения.  
  
 `arg2`  
 Аргумент 2, который передается указанному классу среды выполнения.  
  
 `arg3`  
 Аргумент 3, который передается указанному классу среды выполнения.  
  
 `arg4`  
 Аргумент 4, который передается указанному классу среды выполнения.  
  
 `arg5`  
 Аргумент 5, который передается указанному классу среды выполнения.  
  
 `arg6`  
 Аргумент 6, который передается указанному классу среды выполнения.  
  
 `arg7`  
 Аргумент 7, который передается указанному классу среды выполнения.  
  
 `arg8`  
 Аргумент 8, который передается указанному классу среды выполнения.  
  
 `arg9`  
 Аргумент 9, который передается указанному классу среды выполнения.  
  
## Возвращаемое значение  
 Значение `HRESULT`.  
  
## Примечания  
 См. раздел [Практическое руководство. Непосредственное создание экземпляра компонентов WRL](../windows/how-to-instantiate-wrl-components-directly.md), чтобы понять различия между этой функцией и [Microsoft::WRL::Make](../windows/make-function.md), а также получить пример.  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)