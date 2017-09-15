---
title: "Функция Callback (библиотека шаблонов C++ среды выполнения Windows) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Callback"
dev_langs: 
  - "C++"
ms.assetid: afb15d25-3230-44f7-b321-e17c54872943
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Функция Callback (библиотека шаблонов C++ среды выполнения Windows)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создает объект, функция\-член которого является методом обратного вызова.  
  
## Синтаксис  
  
```  
template<  
   typename TDelegateInterface,  
   typename TCallback  
>  
ComPtr<TDelegateInterface> Callback(  
   TCallbackcallback  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)()  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5,  
   TArg6)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5,  
   TArg6,  
   TArg7)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5,  
   TArg6,  
   TArg7,  
   TArg8)  
);  
template<  
   typename TDelegateInterface,  
   typename TCallbackObject,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
ComPtr<TDelegateInterface> Callback(  
   _In_ TCallbackObject *object,  
   _In_ HRESULT (TCallbackObject::* method)(TArg1,  
   TArg2,  
   TArg3,  
   TArg4,  
   TArg5,  
   TArg6,  
   TArg7,  
   TArg8,  
   TArg9)  
);  
```  
  
#### Параметры  
 `TDelegateInterface`  
 Параметр шаблона, определяющий интерфейс делегата, который вызывается при возникновении события.  
  
 `TCallback`  
 Параметр шаблона, определяющий тип объекта, который представляет объект и его функцию\-член обратного вызова.  
  
 `TCallbackObject`  
 Параметр шаблона, определяющий объект, функция\-член которого является методом, вызываемым при возникновении события.  
  
 `TArg1`  
 Параметр шаблона, который определяет тип первого аргумента метода обратного вызова.  
  
 `TArg2`  
 Параметр шаблона, который определяет тип второго аргумента метода обратного вызова.  
  
 `TArg3`  
 Параметр шаблона, который определяет тип третьего аргумента метода обратного вызова.  
  
 `TArg4`  
 Параметр шаблона, который определяет тип четвертого аргумента метода обратного вызова.  
  
 `TArg5`  
 Параметр шаблона, который определяет тип пятого аргумента метода обратного вызова.  
  
 `TArg6`  
 Параметр шаблона, который определяет тип шестого аргумента метода обратного вызова.  
  
 `TArg7`  
 Параметр шаблона, который определяет тип седьмого аргумента метода обратного вызова.  
  
 `TArg8`  
 Параметр шаблона, который определяет тип восьмого аргумента метода обратного вызова.  
  
 `TArg9`  
 Параметр шаблона, который определяет тип девятого аргумента метода обратного вызова.  
  
 `callback`  
 Объект, который представляет объект обратного вызова и его функцию\-член.  
  
 `object`  
 Объект, функция\-член которого вызывается при возникновении события.  
  
 `method`  
 Функция\-член, которую необходимо вызвать при возникновении события.  
  
## Возвращаемое значение  
 Объект, функция\-член которого является методом обратного вызова.  
  
## Примечания  
 Базовым классом делегата объекта должен быть IUnknown, а не IInspectable.  
  
## Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)