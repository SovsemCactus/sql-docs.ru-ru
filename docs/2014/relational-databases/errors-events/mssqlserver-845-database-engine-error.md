---
title: MSSQLSERVER_845 | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 845 (Database Engine error)
ms.assetid: 8fff6ad4-234c-44be-b123-e25d5e1cd63e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: ff19f2b2e57d1b7c29b2aefe69e8ba4cae5c58dd
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85053597"
---
# <a name="mssqlserver_845"></a>MSSQLSERVER_845
    
## <a name="details"></a>Сведения  
  
|||  
|-|-|  
|Название продукта|SQL Server|  
|Идентификатор события|845|  
|Источник события|MSSQLSERVER|  
|Компонент|SQLEngine|  
|Символическое имя|BUFLATCH_TIMEOUT|  
|Текст сообщения|Истекло время ожидания кратковременной блокировки буфера — тип %d, страница %S_PGID, идентификатор базы данных %d.|  
  
## <a name="explanation"></a>Объяснение  
 Процесс ожидал получения кратковременной блокировки, но время ожидания истекло, и блокировку не удалось получить. Это может произойти, если операциях ввода-вывода выполняется слишком долго. Обычно это происходит в результате блокировки системных процессов другими задачами. В некоторых случаях эта ошибка может возникать в результате сбоя оборудования.  
  
## <a name="user-action"></a>Действие пользователя  
 Для того чтобы предотвратить эту ошибку, выполните следующие задачи:  
  
-   Уменьшите рабочую нагрузку.  
  
-   Убедитесь, что в журнале событий или журнале ошибок присутствуют взаимосвязанные сбои операций ввода-вывода. Сбои операций ввода-вывода обычно вызваны неправильной работой диска.  
  
-   Проверьте наличие невыполненных задач и других критических ошибок в журнале ошибок.  
  
-   Если критические ошибки встречаются часто, устраните их причину.  
  
 Если ошибка продолжает возникать, обратитесь в службу поддержки пользователей корпорации Майкрософт.  
  
  
