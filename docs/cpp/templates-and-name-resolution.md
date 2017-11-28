---
title: "Шаблоны и разрешение имен | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
ms.assetid: 519ba7b5-cd25-4549-865a-9a7b9dffdc28
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4013b35cf12fdc8b6c586a794df8340472584bc0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="templates-and-name-resolution"></a>Шаблоны и разрешение имен

В определениях шаблонов существует три типа имен:  
  
-   локально объявленные имена, включая имя самого шаблона, и все имена, объявленные в рамках определения шаблона;  
  
-   имена из внешней области видимости вне определения шаблона;  
  
-   имена, зависящие каким-либо образом от аргументов шаблона (называемые зависимыми именами).  
  
 Хотя первые два типа имен также относятся к областям видимости класса и функции, в определениях шаблонов необходимо иметь особые правила разрешения имен для устранения проблем, связанных с дополнительной сложностью зависимых имен. Причина этого в том, что до создания экземпляра шаблона компилятор мало знает об этих именах, поскольку они могут быть совершенно разных типов в зависимости от используемых аргументов шаблона. Поиск независимых имен осуществляется в соответствии с обычными правилами и в точке определения шаблона. Эти имена, не зависящие от аргументов шаблона, ищутся один раз для всех специализаций шаблона. Поиск зависимых имен не выполняется, пока не будет создан экземпляр шаблона, и такие имена ищутся отдельно для каждой специализации.  
  
 Тип является зависимым, если он зависит от аргументов шаблона. В частности, он зависим, если представляет собой:  
  
-   аргумент шаблона:  
  
    ```cpp
    T  
    ```  
  
-   полное имя с квалификацией, включающей зависимый тип:  
  
    ```cpp
    T::myType  
    ```  
  
-   полное имя, если неопределенная часть идентифицирует зависимый тип:  
  
    ```cpp
    N::T  
    ```  
  
-   тип const или volatile, для которого базовый тип является зависимым:  
  
    ```cpp
    const T  
    ```  
  
-   тип указателя, ссылки, массива или указателя функции в зависимости от зависимого типа:  
  
    ```cpp
    T *, T &, T [10], T (*)()  
    ```  
  
-   массив, размер которого зависит от параметра шаблона:  
  
    ```cpp
    template <int arg> class X {  
    int x[arg] ; // dependent type  
    }  
    ```  
  
-   тип шаблона, созданного из параметра шаблона:  
  
    ```cpp
    T<int>, MyTemplate<T>  
    ```  
  
## <a name="type-dependence-and-value-dependence"></a>Зависимость от типа и зависимость от значения

 Имена и выражения, зависящие от параметра шаблона, классифицируются как зависящие от типа или значения в зависимости от того, является ли параметр шаблона параметром типа или параметром значения. Кроме того, все идентификаторы, объявленные в шаблоне с типом, зависящим от аргумента шаблона, считаются зависимыми от значения, так как имеют целочисленный тип или тип перечисления, инициализированный выражением, зависящим от значения.  
  
 Выражения, зависящие от типа, и выражения, зависящие от значения, — это выражения, содержащие переменные, зависящие от типа или значения. Эти выражения могут иметь семантику, зависящую от параметров, используемых для шаблона.  
  
## <a name="see-also"></a>См. также

 [Шаблоны](../cpp/templates-cpp.md)