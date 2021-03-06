---
title: Подсистема расширенных событий SQL Server | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xevents
ms.topic: conceptual
helpviewer_keywords:
- extended events [SQL Server], engine
ms.assetid: d74642a5-42b9-4a15-aa3d-f98bfe695050
author: rothja
ms.author: jroth
ms.openlocfilehash: 43ccc0f4b72b8ddd6f1fed66ead95d19247dc5c9
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85027273"
---
# <a name="sql-server-extended-events-engine"></a>Подсистема расширенных событий SQL Server
  Подсистема расширенных событий [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] представляет собой набор служб и объектов, которые выполняют следующие действия.  
  
-   Включает определения событий.  
  
-   Включает обработку данных событий.  
  
-   Управляет службами и объектами расширенных событий в системе.  
  
-   Поддерживает список сеансов расширенных событий и управляет доступом к этому списку.  
  
 Сама подсистема расширенных событий не предоставляет никаких событий или действий при запуске события. Взаимодействие с подсистемой расширенных событий определяют процессы, использующие ее. Процессы добавляют точки событий и предоставляют действия, которые необходимо предпринять при возникновении события.  
  
 На следующем рисунке показан упрощенный вид сеанса расширенных событий. Дополнительные сведения см. в разделе [SQL Server Extended Events Sessions](sql-server-extended-events-sessions.md).  
  
 ![Подробная архитектура расширенных событий](../../database-engine/media/xearchitecturedetailed.gif "Подробная архитектура расширенных событий")  
  
 Следует отметить следующее.  
  
-   Каждому процессу Windows соответствует один или несколько модулей (**процесс Win32**, **модуль Win32**). Они называются *двоичными* или *исполняемыми модулями*.  
  
-   Каждый модуль процесса Windows содержит один или несколько пакетов расширенных событий (**пакет**), который содержит один или несколько объектов расширенных событий (**тип**, **цель**, **действие**, **сопоставление**, **предикат**и **событие**).  
  
-   Процесс может содержать только один экземпляр подсистемы расширенных событий (**подсистема расширенных событий**), который выполняет указанные ниже действия.  
  
    -   Управляет некоторыми аспектами сеанса (например перечислением сеансов).  
  
    -   Обрабатывает доставку (**диспетчер**). (подобно пулу потоков).  
  
    -   Управляет буферами памяти (**буфер**) событий. Когда буфер заполняется, он отправляется цели.  
  
-   После создания сеанса к нему можно привязать события (**контекст сеанса**):  
  
    -   Экземпляры целей (**целевой экземпляр**) также можно создавать и добавлять к сеансу.  
  
    -   Когда буферы заполняются, они отправляются целям.  
  
## <a name="see-also"></a>См. также:  
 [Расширенные события](extended-events.md)  
  
  
