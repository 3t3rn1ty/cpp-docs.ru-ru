---
title: Структура DispatchState | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- DispatchState
- CONCRTRM/concurrency::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::DispatchState
- CONCRTRM/concurrency::DispatchState::DispatchState::m_dispatchStateSize
- CONCRTRM/concurrency::DispatchState::DispatchState::m_fIsPreviousContextAsynchronouslyBlocked
- CONCRTRM/concurrency::DispatchState::DispatchState::m_reserved
dev_langs:
- C++
helpviewer_keywords:
- DispatchState structure
ms.assetid: 8c52546e-1650-48a0-985f-7e4a0fc26a90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cb60a183497942d7a8bea6a333d2dea62d8e2b4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448081"
---
# <a name="dispatchstate-structure"></a>Структура DispatchState

Структура `DispatchState` используется для передачи состояния в метод `IExecutionContext::Dispatch`. Она описывает обстоятельства, при которых метод `Dispatch` вызывается для интерфейса `IExecutionContext`.

## <a name="syntax"></a>Синтаксис

```
struct DispatchState;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[DispatchState::DispatchState](#ctor)|Создает новый `DispatchState` объекта.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[DispatchState::m_dispatchStateSize](#m_dispatchstatesize)|Размер этой структуры, которая используется для управления версиями.|
|[DispatchState::m_fIsPreviousContextAsynchronouslyBlocked](#m_fispreviouscontextasynchronouslyblocked)|Сообщает, вошел ли этот контекст `Dispatch` метод из-за предыдущего контекста асинхронно блокировки. Это используется только в контексте планирования UMS и присваивается значение `0` для всех остальных контекстов выполнения.|
|[DispatchState::m_reserved](#m_reserved)|Бит, зарезервированных для передачи сведения на будущее.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`DispatchState`

## <a name="requirements"></a>Требования

**Заголовок:** concrtrm.h

**Пространство имен:** concurrency

##  <a name="ctor"></a>  Конструктор DispatchState::DispatchState

Создает новый `DispatchState` объекта.

```
DispatchState();
```

##  <a name="m_dispatchstatesize"></a>  Член данных DispatchState::m_dispatchStateSize

Размер этой структуры, которая используется для управления версиями.

```
unsigned long m_dispatchStateSize;
```

##  <a name="m_fispreviouscontextasynchronouslyblocked"></a>  Член данных DispatchState::m_fIsPreviousContextAsynchronouslyBlocked

Сообщает, вошел ли этот контекст `Dispatch` метод из-за предыдущего контекста асинхронно блокировки. Это используется только в контексте планирования UMS и присваивается значение `0` для всех остальных контекстов выполнения.

```
unsigned int m_fIsPreviousContextAsynchronouslyBlocked : 1;
```

##  <a name="m_reserved"></a>  Член данных DispatchState::m_reserved

Бит, зарезервированных для передачи сведения на будущее.

```
unsigned int m_reserved : 31;
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
