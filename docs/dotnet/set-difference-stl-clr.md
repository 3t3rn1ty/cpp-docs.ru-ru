---
title: "set_difference (STL/CLR) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::set_difference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "set_difference - функция [STL/CLR]"
ms.assetid: 47a34d92-53d7-4065-9302-9e2e70e46c4d
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# set_difference (STL/CLR)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Соединяет все элементы, которые принадлежат одному сортируемый диапазон источника, но не на второй отсортированные диапазон источника, в один, упорядоченный диапазон назначения, где критерий упорядочивания может быть указан бинарным предикатом.  
  
## Синтаксис  
  
```  
template<class _InIt1, class _InIt2, class _OutIt> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2,_OutIt _Dest);  
template<class _InIt1, class _InIt2, class _OutIt, class _Pr> inline  
    _OutIt set_difference(_InIt1 _First1, _InIt1 _Last1,  
        _InIt2 _First2, _InIt2 _Last2, _OutIt _Dest, _Pr _Pred);  
```  
  
## Заметки  
 Эта функция работает аналогично функции `set_difference` STL.  Для получения дополнительной информации см. [set\_difference](../Topic/set_difference.md).  
  
## Требования  
 **Заголовок:**\<cliext\/algorithm\>  
  
 **Пространство имен:** cliext  
  
## См. также  
 [algorithm](../Topic/algorithm%20\(STL-CLR\).md)