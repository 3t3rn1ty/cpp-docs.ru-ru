---
title: "Escape-последовательности | Документы Майкрософт"
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
- "\r escape sequence"
- double backslash
- horizontal-tab 	 escape sequence
- (') single quotation mark
- "bell character \a escape sequence"
- escape sequences
- hexadecimal escape sequence
- carriage returns
- tab 	 escape sequence
- "\f escape sequence"
- quotation marks, single
- "formfeed \f escape sequence"
- "\v escape sequence"
- control character escape sequences
- " symbol in escape sequences"
- octal escape sequence
- escape characters
- "newline character \n escape sequence"
- nongraphic control characters
- question mark, literal
- "\nescape sequence"
- "vertical tab \v escape sequence"
- "\a escape sequence"
- '? symbol'
- '? symbol, escape sequence character'
- "	 escape sequence"
- backspace escape sequence
ms.assetid: 5aef377f-a76c-4d5c-aa04-8308758ad6a8
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
ms.translationtype: HT
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: f8c15c7419f440626f590488a3e7bf52a2282041
ms.contentlocale: ru-ru
ms.lasthandoff: 07/14/2017

---
# <a name="escape-sequences"></a>Escape-последовательность
Сочетания символов, состоящих из обратной косой черты (**\\**), за которой следует буква или набор цифр, называются escape-последовательностями. Для представления знака новой строки, одиночной кавычки или некоторых других символов в символьной константе, необходимо использовать escape-последовательности. Escape-последовательность рассматривается как один символ и, следовательно, является допустимой символьной константой.  
  
 Escape-последовательности обычно используются для указания действий, например возврата каретки или табуляции, на терминалах и принтерах. Они также используются для обозначения буквенных представлений непечатаемых символов, а также символов, которые обычно имеют специальное значение, например двойных кавычек (**"**). В следующей таблице перечислены escape-последовательности ANSI и представляемые ими значения.  
  
 Обратите внимание, что вопросительный знак, перед которым стоит обратная косая черта (**\\?**), обозначает литерал вопросительного знака в случаях, когда данная последовательность символов может быть ошибочно интерпретирована как триграф. Дополнительные сведения см. в разделе [Триграфы](../c-language/trigraphs.md).  
  
### <a name="escape-sequences"></a>Escape-последовательность  
  
|Escape-последовательность|Представляет|  
|---------------------|----------------|  
|**\a**|Звонок (предупреждение)|  
|**\b**|Backspace|  
|**\f**|Перевод страницы|  
|**\n**|Новая строка|  
|**\r**|Возврат каретки|  
|**\t**|Горизонтальная табуляция|  
|**\v**|Вертикальная табуляция|  
|**\\'**|Одиночная кавычка|  
|**\\"**|Двойная кавычка|  
|**\\\\**|Обратная косая черта|  
|**\\?**|Литерал вопросительного знака|  
|**\\** *ooo*|Символ ASCII в восьмеричной нотации|  
|**\x** *hh*|Символ ASCII в шестнадцатеричной нотации|  
|**\x** *hhhh*|Символ юникода в шестнадцатеричном формате, если эта escape-последовательность используется в многобайтовой знаковой константе или строковом литерале юникода.<br /><br /> Например, `WCHAR f = L'\x4e00'` или `WCHAR b[] = L"The Chinese character for one is \x4e00"`.|  
  
 **Блок, относящийся только к системам Майкрософт**  
  
 Если обратная косая черта предшествует символу, которого нет в таблице, компилятор не обрабатывает неопределенный символ сам как символ. Например, escape-последовательность `\c` обрабатывается как символ `c`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
 Escape-последовательности позволяют отправлять неграфические управляющие символы на устройство отображения. Например, символ ESC (**\033**) часто используется в качестве первого символа команды управления для терминала или принтера. Некоторые escape-последовательности используются только на конкретных устройствах. Например, escape-последовательности вертикальной табуляции и перевода страницы (**\v** и **\f**) не влияют на вывод данных на экране, но отвечают за определенные операции на принтере.  
  
 Кроме того, обратную косую черту (**\\**) можно использовать как символ продолжения. Если сразу за обратной косой чертой следует символ новой строки (эквивалентен нажатию клавиши ВОЗВРАТ), компилятор игнорирует эту последовательность и обрабатывает следующую строку как продолжение предыдущей. Эта возможность используется в основном для определений препроцессора, длина которых превышает одну строку. Пример:  
  
```  
#define assert(exp) \  
( (exp) ? (void) 0:_assert( #exp, __FILE__, __LINE__ ) )  
```  
  
## <a name="see-also"></a>См. также  
 [Константы символов в C](../c-language/c-character-constants.md)