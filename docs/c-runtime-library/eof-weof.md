---
title: "EOF, WEOF | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- EOF
dev_langs:
- C++
helpviewer_keywords:
- EOF function
- WEOF function
- end of file
ms.assetid: a7150563-cdae-4cdf-9798-ad509990e505
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 193998c6a20388d8fd066b00c0eb9bdeea069624
ms.contentlocale: ru-ru
ms.lasthandoff: 05/18/2017

---
# <a name="eof-weof"></a>EOF, WEOF
## <a name="syntax"></a>Синтаксис  
  
```  
  
#include <stdio.h>  
```  
  
## <a name="remarks"></a>Примечания  
 Символ EOF возвращается подпрограммой ввода-вывода, если достигнут конец файла (или, в некоторых случаях, если возникла ошибка).  
  
 Символ WEOF формирует возвращаемое значение типа **wint_t**, которое используется для сообщения о конце потока расширенных символов или об ошибке.  
  
## <a name="see-also"></a>См. также  
 [putc, putwc](../c-runtime-library/reference/putc-putwc.md)   
 [ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [fflush](../c-runtime-library/reference/fflush.md)   
 [fclose, _fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)   
 [_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock](../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)   
 [_putch, _putwch](../c-runtime-library/reference/putch-putwch.md)   
 [isascii, __isascii, iswascii](../c-runtime-library/reference/isascii-isascii-iswascii.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)