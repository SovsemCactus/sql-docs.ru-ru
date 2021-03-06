---
title: Задача "Очистка журнала" | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.historycleanuptask.f1
helpviewer_keywords:
- history tables [SQL Server]
- History Cleanup task [Integration Services]
ms.assetid: 5defc5b9-dfd3-4859-a7fe-ac8c2b5480f8
author: janinezhang
ms.author: janinez
ms.openlocfilehash: a5b71480ef7396e935e80f9d94633a5278446700
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84918804"
---
# <a name="history-cleanup-task"></a>Задача «Очистка журнала»
  Задача «Очистка журнала» удаляет записи в следующих таблицах журнала в базе данных msdb [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
-   backupfile;  
  
-   backupfilegroup  
  
-   backupmediafamily;  
  
-   backupmediaset;  
  
-   backupset;  
  
-   restorefile;  
  
-   restorefilegroup;  
  
-   restorehistory.  
  
 Используя задачу «Очистка журнала», пакет может удалить данные журнала, связанные с деятельностью по созданию резервных копий и восстановлению, с заданиями агента [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и планами обслуживания баз данных.  
  
 Эта задача инкапсулирует системную хранимую процедуру sp_delete_backuphistory и передает указанную дату процедуре как аргумент. Дополнительные сведения см. в разделе [sp_delete_backuphistory (Transact-SQL)](/sql/relational-databases/system-stored-procedures/sp-delete-backuphistory-transact-sql).  
  
## <a name="configuration-of-the-history-cleanup-task"></a>Настройка задачи «Очистка журнала»  
 Эта задача включает свойство для указания самой ранней даты для данных, остающихся в таблицах журнала. Дата может задаваться числом дней, недель, месяцев или лет от текущего дня; в этом случае задача автоматически преобразует промежуток времени в дату.  
  
 Свойства задаются с помощью конструктора служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] . Эта задача находится в разделе **Задачи плана обслуживания** **области элементов** в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] .  
  
 Дополнительные сведения о свойствах, которые можно задать в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] , см. в следующем разделе:  
  
-   [Задача "Очистка журнала" (план обслуживания)](../../relational-databases/maintenance-plans/history-cleanup-task-maintenance-plan.md)  
  
 Дополнительные сведения об установке этих свойств в конструкторе служб [!INCLUDE[ssIS](../../../includes/ssis-md.md)] см. в следующем разделе:  
  
-   [Задание свойств задач или контейнеров](../set-the-properties-of-a-task-or-container.md)  
  
## <a name="see-also"></a>См. также:  
 [Задачи служб Integration Services](integration-services-tasks.md)   
 [Поток управления](control-flow.md)  
  
  
