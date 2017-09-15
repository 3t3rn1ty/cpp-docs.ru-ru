---
title: "Класс random_device | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random_device
- random/std::random_device
- random/std::random_device::min
- random/std::random_device::max
- random/std::random_device::entropy
- random/std::random_device::operator()
- random/std::random_device::entropy
- random/std::random_device::operator()
dev_langs:
- C++
helpviewer_keywords:
- random_device class
ms.assetid: 4393d515-0cb6-4e0d-a2ba-c780f05dc1bf
caps.latest.revision: 27
author: corob-msft
ms.author: corob
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 842e4f9b53a06373df8e00f64b1ab24a48a5c6b9
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="randomdevice-class"></a>Класс random_device
Формирует случайную последовательность с помощью внешнего устройства.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class random_device {  
public:  
   typedef unsigned int result_type;  
   
   // constructor 
   explicit random_device(const std::string& token = "");
   
   // properties 
   static result_type min();
   static result_type max();
   double entropy() const;
   
   // generate 
   result_type operator()();

   // no-copy functions 
   random_device(const random_device&) = delete;  
   void operator=(const random_device&) = delete;  
   };  
```  

## <a name="members"></a>Члены  
  
|||  
|-|-|  
|[random_device](#random_device)|[энтропия](#entropy)|  
|[random_device::operator()](#op_call)||  
  
## <a name="remarks"></a>Примечания  
Этот класс описывает источник случайных чисел и, согласно стандарту ISO C++, может быть недетерминистическим или криптостойким (но это необязательно). В реализации в Visual Studio полученные значения являются недетерминистическими и криптостойкими, но производительность ниже, чем у генераторов, созданных на основе механизмов и адаптеров механизмов (таких как [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md), быстрого и качественного механизма для большинства приложений).  
  
Результаты `random_device` равномерно распределены в замкнутом диапазоне [`0, 2`<sup>32</sup>).  
  
Не гарантируется, что `random_device` приведет к неблокирующему вызову.  
  
В целом, `random_device` используется для получения начальных значений для других генераторов, созданных с помощью механизмов или адаптеров механизмов. Дополнительные сведения см. в разделе [\<random>](../standard-library/random.md).  
  
## <a name="example"></a>Пример  
В следующем коде показаны основные функции класса и результаты его применения. Из-за недетерминистической природы `random_device` случайные значения, показанные в разделе **Выходные данные**, не будут совпадать с вашими результатами. Подобный результат является нормальным и ожидаемым.  
  
```cpp  
// random_device_engine.cpp   
// cl.exe /W4 /nologo /EHsc /MTd   
#include <random>   
#include <iostream>   
using namespace std;  
  
int main()   
{   
    random_device gen;   
  
    cout << "entropy == " << gen.entropy() << endl;   
    cout << "min == " << gen.min() << endl;   
    cout << "max == " << gen.max() << endl;   
  
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
}  
```  
  
```Output  
entropy == 32
min == 0
max == 4294967295
a random value == 2378414971
a random value == 3633694716
a random value == 213725214
```  
  
Этот пример упрощен и не представляет собой общего примера применения этого генератора. Более полный пример приведен в разделе [\<random>](../standard-library/random.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** \<random>  
  
 **Пространство имен:** std  
  
##  <a name="random_device"></a>  random_device::random_device  
Формирует генератор.  
  
```  
random_device(const std::string& = "");
```  
  
### <a name="remarks"></a>Примечания  
Конструктор инициализирует генератор, как требуется, игнорируя строковый параметр. Возвращает значение определенного в реализации типа, производного из [exception](../standard-library/exception-class.md), если не удалось инициализировать `random_device`.  
  
##  <a name="entropy"></a>  random_device::entropy  
Оценивает стохастичность источника.  
  
```  
double entropy() const noexcept;  
```  
  
### <a name="remarks"></a>Примечания  
Эта функция-член возвращает оценку стохастичности источника в битах.  
  
##  <a name="op_call"></a>  random_device::operator()  
Возвращает случайное значение.  
  
```  
result_type operator()();
```  
  
### <a name="remarks"></a>Примечания  
Возвращает значения с равномерным распределением в замкнутом интервале [`min, max`] в соответствии с функциями-членами `min()` и `max()`. Если случайное число не удалось получить, возвращается значение определенного в реализации типа, производного от [exception](../standard-library/exception-class.md).  
  
## <a name="see-also"></a>См. также  
[\<random>](../standard-library/random.md)

