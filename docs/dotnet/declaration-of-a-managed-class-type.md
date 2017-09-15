---
title: "Объявление управляемых типов классов | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__gc - типы"
  - "__value - ключевое слово"
  - "class - ключевое слово [C++], среда CLR"
  - "классы [C++], управляемая"
  - "класс интерфейса - ключевое слово"
  - "управляемые классы"
  - "ref - ключевое слово [C++]"
  - "value - ключевое слово [C++]"
  - "типы значений, объявление"
ms.assetid: 16de9c94-91d7-492f-8ac7-f0729cc627e9
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Объявление управляемых типов классов
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Способ объявления ссылочного типа классов изменился в [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] по сравнению с управляемыми расширениями для C\+\+.  
  
 В управляемых расширениях ссылочному типу классов предшествовало ключевое слово `__gc`.  В новом синтаксисе ключевое слово `__gc` заменено на одно из двух составных ключевых слов: `ref class` или `ref struct`.  Выбор ключевого слова `struct` или `class` означает уровень доступа по умолчанию для элементов, объявленных в начальном неразмеченном разделе тела типа: public \(для `struct`\) или private \(для `class`\).  
  
 В управляемых расширениях типу значения классов предшествовало ключевое слово `__value`.  В новом синтаксисе ключевое слово `__value` заменено на одно из двух составных ключевых слов: `value class` или `value struct`.  
  
 Тип интерфейсов в управляемых расширениях обозначался с помощью ключевого слова `__interface`.  В новом синтаксисе оно заменено на ключевое слово `interface class`.  
  
 В качестве примера рассмотрим следующие объявления класса в управляемых расширениях:  
  
```  
public __gc class Block {};     // reference class  
public __value class Vector {}; // value class  
public __interface IFooBar {};  // interface class  
```  
  
 В новом синтаксисе те же объявления выглядят следующим образом:  
  
```  
public ref class Block {};         // reference class  
public value class Vector {};      // value class  
public interface class IFooBar {}; // interface class  
```  
  
## Определение класса как абстрактного  
 В управляемых расширениях ключевое слово `__abstract` указывается перед ключевым словом `class` \(либо до, либо после ключевого слова `__gc`\), чтобы указать, что класс является неполным и объекты данного класса не могут создаваться в программе.  
  
```  
public __gc __abstract class Shape {};  
public __gc __abstract class Shape2D: public Shape {};  
```  
  
 В новом синтаксисе используется контекстно\-зависимое ключевое слово `abstract`, расположенное после имени класса и перед телом класса, списком классов, производных от базового класса, или точкой с запятой.  
  
```  
public ref class Shape abstract {};  
public ref class Shape2D abstract : public Shape{};  
```  
  
 При этом семантическое значение остается неизменным.  
  
## Определение класса как запечатанного  
 В управляемых расширениях ключевое слово `__sealed` указывается перед ключевым словом `class` \(либо до, либо после ключевого слова `__gc`\), чтобы указать, что от объектов данного класса не может выполняться наследование.  
  
```  
public __gc __sealed class String {};  
```  
  
 В новом синтаксисе используется контекстно\-зависимое ключевое слово `sealed`, расположенное после имени класса и перед телом класса, списком классов, производных от базового класса, или точкой с запятой.  
  
 При этом можно как получать производные классы, так и запечатывать их.  Например, класс `String` неявно является производным от `Object`.  Преимуществом запечатывания класса является то, что такой класс поддерживает статическое разрешение вызовов всех виртуальных функций \(во время компиляции\) с помощью запечатанного объекта ссылочного класса.  Это происходит благодаря тому, что описатель `sealed` не позволяет дескриптору отслеживания `String` ссылаться на производный класс, который предоставляет экземпляр, переопределяющий вызываемый виртуальный метод.  Пример запечатанного класса в новом синтаксисе:  
  
```  
public ref class String sealed {};  
```  
  
 Также можно определить класс одновременно как абстрактный и запечатанный. Это является особым условием для определения класса как статического.  В документации среды CLR это описывается следующим образом:  
  
 "Тип, который одновременно является `abstract` и `sealed`, должен содержать только статические члены и являться тем, что в некоторых языках называется пространством имен".  
  
 В качестве примера ниже приводится объявление абстрактного запечатанного класса с помощью синтаксиса управляемых расширений.  
  
```  
public __gc __sealed __abstract class State {  
public:  
   static State() {}  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
 Далее приводится это же объявление, но с использованием нового синтаксиса.  
  
```  
public ref class State abstract sealed {  
public:  
   static State();  
   static bool inParamList();  
  
private:  
   static bool ms_inParam;  
};  
```  
  
## Наследование в среде CLR. Указание базового класса  
 В объектной модели CLR поддерживается только открытое единичное наследование.  Управляемые расширения сохранили используемую в ISO\-C\+\+ по умолчанию интерпретацию базового класса без использования ключевого слова доступа, определявшую наследование как закрытое.  Это означало, что для каждого объявления наследования в CLR необходимо было использовать ключевое слово `public`, чтобы переопределить интерпретацию по умолчанию.  
  
```  
// Managed Extensions: error: defaults to private derivation  
__gc class Derived : Base {};  
```  
  
 В новом синтаксисе отсутствие в определении наследования ключевого слова доступа обозначает, что наследование в CLR является открытым.  Таким образом, использование ключевого слова `public` теперь не является обязательным.  Поскольку это не приводит к необходимости вносить какие\-либо изменения в код управляемых расширений для C\+\+, данная информация приводится только в ознакомительных целях.  
  
```  
// New syntax: ok: defaults to public derivation  
ref class Derived : Base{};  
```  
  
## См. также  
 [Управляемые типы \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)   
 [abstract](../windows/abstract-cpp-component-extensions.md)   
 [запечатанные](../windows/sealed-cpp-component-extensions.md)