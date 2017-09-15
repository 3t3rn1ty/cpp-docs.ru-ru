---
title: "Относительные указатели в C | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 26bc7760c0cb498004ad1dc185d11d1d6ebfeaea
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="based-pointers-c"></a>Основанные указатели (C)
**Блок, относящийся только к системам Майкрософт**  
  
 [__based (Справочник по C ++)](../cpp/based-pointers-cpp.md)  
  
 В 32- и 64-разрядных компиляторах Microsoft базовый указатель является 32- или 64-разрядным смещением от 32- или 64-разрядной базы указателя. Базовая адресация полезна для управления разделами, в которых размещены объекты, поскольку уменьшается размер исполняемого файла и увеличивается скорость выполнения. Как правило, используется следующая форма определения относительного указателя.  
  
```  
  
type  
__based(  
base  
)  
declarator  
  
```  
  
 Вариант базовой адресации, основанный на указателе, позволяет использовать спецификацию указателя в качестве базы. В свою очередь, относительный указатель является смещением в раздел памяти, который начинается в начале указателя, на котором он основан. Указатели, основанные на адресах указателей, являются единственной формой ключевого слова `__based`, допустимой в 32- и 64-разрядных компиляциях. В таких компиляциях они представляют собой 32- или 64-разрядные смещения от 32- или 64-разрядной базы.  
  
 Указатели на основе указателей, в частности, используются для постоянных идентификаторов, которые содержат указатели. Связанный список, состоящий из указателей на основе указателей, можно сохранить на диск, а затем перезагрузить в другое место в памяти. При этом все указатели останутся действительными.  
  
 В следующем примере показан указатель на основе указателя.  
  
```  
void *vpBuffer;  
  
struct llist_t  
{  
    void __based( vpBuffer ) *vpData;  
    struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Указателю `vpBuffer` назначается адрес в памяти, который выделяется на более позднем этапе программы. Связанный список перемещается относительно значения `vpBuffer`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Деклараторы и объявления переменных](../c-language/declarators-and-variable-declarations.md)