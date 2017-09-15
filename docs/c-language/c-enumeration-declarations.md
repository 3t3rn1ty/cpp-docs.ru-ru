---
title: "Объявления перечислений C | Документация Майкрософт"
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
- declarations, enumerations
- define directive (#define), alternative to
- enumerators, declaring
- '#define directive, alternative to'
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: bd18f673-4dda-4bc1-92fd-d1ce10074910
caps.latest.revision: 11
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
ms.openlocfilehash: 90d3b0837adb2bd646ef39f4898377c41a030a81
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="c-enumeration-declarations"></a>Объявления перечислений C
Перечисление состоит из набора именованных целочисленных констант. Объявление типа перечисления предоставляет имя тега перечисления (необязательно) и определяет набор именованных целочисленных идентификаторов (называемых "набор перечисления", "константы перечислителя", "перечислители" или "члены"). Переменная с типом перечисления хранит одно из значений набора перечисления, определенных этим типом.  
  
 Переменные типа `enum` можно использовать в выражениях индексации и в качестве операндов всех арифметических операторов и операторов отношения. Перечисления являются альтернативой директиве препроцессора `#define` с тем преимуществом, что можно создать значения, подчиняющиеся обычным правилам области.  
  
 В ANSI C выражения, определяющие значение константы перечислителя, всегда имеют тип `int`. Таким образом, хранилище, связанное с переменной перечисления, является хранилищем, необходимым для одного значения `int`. Константу перечисления или значение перечисляемого типа можно использовать как целочисленное выражение в любом месте, допустимом в языке C.  
  
## <a name="syntax"></a>Синтаксис  
 *enum-specifier*:  
 **enum**  *identifier* opt**{** *enumerator-list* **}**  
  
 **enum**  *identifier*  
  
 Необязательный параметр *identifier* именует тип перечисления, определенный параметром *enumerator-list*. Этот идентификатор часто называется тегом перечисления, определенным списком. Описатель типа  
  
```  
  
enum  
identifier  
{  
enumerator-list  
}  
  
```  
  
 объявляет, что *identifier* является тегом для перечисления, определенного нетерминальным параметром *enumerator-list*. *enumerator-list* определяет содержимое перечислителя. Подробное описание параметра *enumerator-list* представлено ниже.  
  
 Если объявление тега является видимым, все последующие объявления, в которых используется этот тег, но отсутствует *enumerator-list*, обозначают ранее объявленный перечисляемый тип. Тег должен ссылаться на определенный тип перечисления, и этот тип перечисления должен находиться в текущей области. Поскольку тип перечисления определен в другом месте, *enumerator-list* не отображается в этом объявлении. В объявлениях типов, производных от перечислений, и объявлениях `typedef` для типов перечислений тег перечисления может использоваться до определения типа перечисления.  
  
## <a name="syntax"></a>Синтаксис  
 *enumerator-list*:  
 *enumerator*  
  
 *enumerator-list* **,**  `enumerator`  
  
 `enumerator`:  
 *enumeration-constant*  
  
 *enumeration-constant*  **=**  *constant-expression*  
  
 *enumeration-constant*:  
 *identifier*  
  
 Каждое значение *enumeration-constant* в списке *enumerator-list* именует значение набора перечисления. По умолчанию первый параметр *enumeration-constant* связан со значением 0. Следующий параметр *enumeration-constant* в списке связывается со значением (*enumeration-constant* + 1), если явно не указано другое значение. Имя параметра *enumeration-constant* эквивалентно его значению.  
  
 Можно использовать выражение *enumeration-constant = constant-expression* для переопределения используемой по умолчанию последовательности значений. Таким образом, если в списке *enumerator-list* встречается выражение *enumeration-constant = constant-expression*, параметр *enumeration-constant* связывается со значением соответствующего выражения *constant-expression*. Выражение *constant-expression* должно иметь тип `int` и может быть отрицательным.  
  
 К членам набора перечисления применяются следующие правила.  
  
-   Набор перечисления может содержать повторяющиеся постоянные значения. Например, значение 0 можно связать с двумя разными идентификаторами, такими как `null` и `zero`, в одном и том же наборе.  
  
-   Идентификаторы в списке перечисления должны отличаться от других идентификаторов в той же области с той же видимостью, включая обычные имена переменных и идентификаторы в других списках перечисления.  
  
-   К тегам перечисления применяются обычные правила области. Они должны отличаться от всех тегов перечислений, структур или объединений с такой же видимостью.  
  
## <a name="examples"></a>Примеры  
 В следующих примерах показаны объявления перечисления.  
  
```  
enum DAY            /* Defines an enumeration type    */  
{  
    saturday,       /* Names day and declares a       */  
    sunday = 0,     /* variable named workday with    */   
    monday,         /* that type                      */  
    tuesday,  
    wednesday,      /* wednesday is associated with 3 */  
    thursday,  
    friday  
} workday;  
```  
  
 Значение 0 связано с `saturday` по умолчанию. Для идентификатора `sunday` явно задано значение 0. Оставшимся идентификаторам по умолчанию присваиваются значения от 1 до 5.  
  
 В этом примере значение из набора `DAY` присваивается переменной `today`.  
  
```  
enum DAY today = wednesday;  
```  
  
 Обратите внимание, что имя константы перечисления используется для присвоения значения. Поскольку тип перечисления `DAY` был объявлен ранее, необходим только тег перечисления `DAY`.  
  
 Чтобы явно присвоить целочисленное значение переменной перечисляемого типа данных, используйте следующее приведение типа.  
  
```  
workday = ( enum DAY ) ( day_value - 1 );  
```  
  
 Это приведение рекомендовано к использованию в С, но не является обязательным.  
  
```  
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */  
{  
    false,     /* false = 0, true = 1 */  
    true   
};   
  
enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */  
```  
  
 Это объявление также можно указать как  
  
```  
enum BOOLEAN { false, true } end_flag, match_flag;\  
```  
  
 или как  
  
```  
enum BOOLEAN { false, true } end_flag;  
enum BOOLEAN match_flag;  
```  
  
 Пример, в котором используются эти переменные, может выглядеть следующим образом.  
  
```  
if ( match_flag == false )  
    {  
     .  
     .   /* statement */   
     .  
    }  
    end_flag = true;  
```  
  
 Также можно объявить неименованные типы данных перечислителя. Имя типа данных опускается, но можно объявлять переменные. Переменная `response` является переменной определенного типа.  
  
```  
enum { yes, no } response;  
```  
  
## <a name="see-also"></a>См. также  
 [Перечисления](../cpp/enumerations-cpp.md)