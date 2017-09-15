---
title: "Операторы &lt;hash_set&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: []
ms.assetid: 403d8e4e-0b3f-43fb-bc5a-8100c4f331c5
caps.latest.revision: 13
manager: ghogen
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 5434d1dc44724cf876a42323140877ba38cb2b45
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="lthashsetgt-operators"></a>Операторы &lt;hash_set&gt;
||||  
|-|-|-|  
|[оператор!=](#op_neq)|[operator!= (hash_multiset)](#op_neq_hash_multiset)|[оператор==](#op_eq_eq)|  
|[operator== (hash_multiset)](#op_eq_eq_hash_multiset)|  
  
##  <a name="op_neq"></a>  оператор!=  
  
> [!NOTE]
>  Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).  
  
 Проверяет неравенство объекта hash_set слева от оператора и объекта hash_set справа от оператора.  
  
```  
bool operator!=(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `hash_set`.  
  
 `right`  
 Объект типа `hash_set`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объекты hash_set не равны; **false**, если объекты hash_set равны.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами hash_set основывается на попарном сравнении их элементов. Два объекта hash_set равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 Члены [< hash_map >](../standard-library/hash-map.md) и [< hash_set >](../standard-library/hash-set.md) файлы заголовка, [пространство имен stdext](../standard-library/stdext-namespace.md).
  
### <a name="example"></a>Пример  
  
```cpp  
// hash_set_op_ne.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_set <int> hs1, hs2, hs3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hs1.insert ( i );  
      hs2.insert ( i * i );  
      hs3.insert ( i );  
   }  
  
   if ( hs1 != hs2 )  
      cout << "The hash_sets hs1 and hs2 are not equal." << endl;  
   else  
      cout << "The hash_sets hs1 and hs2 are equal." << endl;  
  
   if ( hs1 != hs3 )  
      cout << "The hash_sets hs1 and hs3 are not equal." << endl;  
   else  
      cout << "The hash_sets hs1 and hs3 are equal." << endl;  
}  
```  
  
```Output  
The hash_sets hs1 and hs2 are not equal.  
The hash_sets hs1 and hs3 are equal.  
```  
  
##  <a name="op_eq_eq"></a>  оператор==  
  
> [!NOTE]
>  Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).  
  
 Проверяет равенство объекта hash_set слева от оператора и объекта hash_set справа от оператора.  
  
```  
bool operator!==(const hash_set <Key, Traits, Allocator>& left, const hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `hash_set`.  
  
 `right`  
 Объект типа `hash_set`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект hash_set слева от оператора равен объекту hash_set справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами hash_set основывается на попарном сравнении их элементов. Два объекта hash_set равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 В Visual C++ .NET 2003 члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Более подробные сведения см. в разделе [Пространство имен stdext](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Пример  
  
```cpp  
// hash_set_op_eq.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_set <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The hash_sets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_sets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The hash_sets s1 and s3 are equal." << endl;  
   else  
      cout << "The hash_sets s1 and s3 are not equal." << endl;  
}  
```  
  
```Output  
The hash_sets s1 and s2 are not equal.  
The hash_sets s1 and s3 are equal.  
```  
  
##  <a name="neq_hash_multiset"></a>  operator!= (hash_multiset)  
  
> [!NOTE]
>  Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).  
  
 Проверяет неравенство объекта hash_multiset слева от оператора и объекта hash_multiset справа от оператора.  
  
```  
bool operator!=(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `hash_multiset`.  
  
 `right`  
 Объект типа `hash_multiset`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объекты hash_multiset не равны; **false**, если они равны.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами hash_multiset основывается на попарном сравнении их элементов. Два объекта hash_multiset равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 В Visual C++ .NET 2003 члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они перемещены в пространство имен stdext. Более подробные сведения см. в разделе [Пространство имен stdext](../standard-library/stdext-namespace.md).  
  
### <a name="example"></a>Пример  
  
```cpp  
// hashset_op_ne.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )   
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> hs1, hs2, hs3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      hs1.insert ( i );  
      hs2.insert ( i * i );  
      hs3.insert ( i );  
   }  
  
   if ( hs1 != hs2 )  
      cout << "The hash_multisets hs1 and hs2 are not equal." << endl;  
   else  
      cout << "The hash_multisets hs1 and hs2 are equal." << endl;  
  
   if ( hs1 != hs3 )  
      cout << "The hash_multisets hs1 and hs3 are not equal." << endl;  
   else  
      cout << "The hash_multisets hs1 and hs3 are equal." << endl;  
}  
```  
  
```Output  
The hash_multisets hs1 and hs2 are not equal.  
The hash_multisets hs1 and hs3 are equal.  
```  
  
##  <a name="eq_eq_hash_multiset"></a>  operator== (hash_multiset)  
  
> [!NOTE]
>  Этот API устарел. Вместо него следует использовать [класс unordered_set](../standard-library/unordered-set-class.md).  
  
 Проверяет равенство объекта hash_multiset слева от оператора и объекта hash_multiset справа от оператора.  
  
```  
bool operator!==(const hash_multiset <Key, Traits, Allocator>& left, const hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Параметры  
 `left`  
 Объект типа `hash_multiset`.  
  
 `right`  
 Объект типа `hash_multiset`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 **true**, если объект hash_multiset слева от оператора равен объекту hash_multiset справа от оператора; в противном случае **false**.  
  
### <a name="remarks"></a>Примечания  
 Сравнение между объектами hash_multiset основывается на попарном сравнении их элементов. Два объекта hash_multiset равны, если они содержат одинаковое количество элементов, а их соответствующие элементы имеют одинаковые значения. В противном случае они не равны.  
  
 В Visual C++ .NET 2003 члены файлов заголовков [<hash_map>](../standard-library/hash-map.md) и [<hash_set>](../standard-library/hash-set.md) больше не находятся в пространстве имен std. Они были перенесены в пространство имен stdext. В разделе [пространство имен stdext](../standard-library/stdext-namespace.md) для получения дополнительной информации.  
  
### <a name="example"></a>Пример  
  
```cpp  
// hash_multiset_op_eq.cpp  
// compile with: /EHsc  
#include <hash_set>  
#include <iostream>  
  
int main( )  
{  
   using namespace std;  
   using namespace stdext;  
   hash_multiset <int> s1, s2, s3;  
   int i;  
  
   for ( i = 0 ; i < 3 ; i++ )  
   {  
      s1.insert ( i );  
      s2.insert ( i * i );  
      s3.insert ( i );  
   }  
  
   if ( s1 == s2 )  
      cout << "The hash_multisets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_multisets s1 and s2 are not equal." << endl;  
  
   if ( s1 == s3 )  
      cout << "The hash_multisets s1 and s2 are equal." << endl;  
   else  
      cout << "The hash_multisets s1 and s2 are not equal." << endl;  
}  
```  
  
```Output  
The hash_multisets s1 and s2 are not equal.  
The hash_multisets s1 and s2 are equal.  
```  
  
## <a name="see-also"></a>См. также  
 [<hash_set>](../standard-library/hash-set.md)

