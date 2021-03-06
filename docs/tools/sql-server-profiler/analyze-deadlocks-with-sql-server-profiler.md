---
title: Анализ взаимоблокировок
titleSuffix: SQL Server Profiler
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: profiler
ms.topic: conceptual
ms.assetid: 72d6718f-501b-4ea6-b344-c0e653f19561
author: markingmyname
ms.author: maghan
ms.custom: seo-lt-2019
ms.date: 03/03/2017
ms.openlocfilehash: 15d41ae2517a3eadb8305a359f4576fb4407020b
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2020
ms.locfileid: "75307370"
---
# <a name="analyze-deadlocks-with-sql-server-profiler"></a>Анализ взаимоблокировок в приложении SQL Server Profiler

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]

Приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] используется для определения причины взаимоблокировки. Взаимоблокировка возникает, когда имеется циклическая зависимость между несколькими потоками или процессами для некоторого набора ресурсов в сервере SQL Server. При помощи приложения [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)]можно создавать трассировку, которая записывает, воспроизводит и отображает для анализа события взаимоблокировки.  
  
 Для трассировки событий взаимоблокировки добавьте в трассировку класс событий **Deadlock graph** . Этот класс событий заполняет столбец данных **TextData** в трассировке с данными XML о процессе и объектах, которые участвуют во взаимоблокировке. [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] может извлечь XML-документ в XML-файл взаимоблокировки (с расширением XDL), который в дальнейшем становится доступным для просмотра в среде SQL Server Management Studio. Приложение [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] можно настроить на извлечение событий **Deadlock graph** в единый файл, содержащий все события класса **Deadlock graph** , или в отдельные файлы. Это извлечение можно выполнить одним из следующих способов.  
  
-   При настройке трассировки на вкладке **Настройки извлечения событий** . Обратите внимание на то, что эта вкладка не отображается до тех пор, пока не будет выбрано событие **Deadlock graph** на вкладке **Выбор событий** .  
  
-   С помощью параметра **Извлечь события SQL Server** в меню **Файл** .  
  
-   Отдельные события можно также извлекать и сохранять, щелкнув правой кнопкой конкретное событие и выбрав **Извлечь данные события**.  
  
## <a name="deadlock-graphs"></a>Графы взаимоблокировок  
 [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] и среда [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] для описания взаимоблокировки используют граф ожидания взаимоблокировки. Граф ожидания взаимоблокировки содержит узлы процессов, узлы ресурсов и ребра, представляющие связи между процессами и ресурсами. Компоненты графов ожидания взаимоблокировки определяются в следующей таблице:  
  
 Узел процесса  
 Поток, выполняющий задачу, например INSERT, UPDATE или DELETE.  
  
 Узел ресурса  
 Объект базы данных, например таблица, индекс или строка.  
  
 Edge  
 Связь между процессом и ресурсом. Связь **request** возникает, когда процесс ожидает ресурса. Связь **owner** возникает, когда ресурс ожидает процесс. В описание ребра включен режим блокировки. Например, **Режим: X**.  
  
## <a name="deadlock-process-node"></a>Взаимоблокировка узла процесса  
 В графе ожидания узел ожидания содержит информацию о процессе. В следующей таблице поясняются компоненты процесса.  
  
|Компонент|Определение|  
|---------------|----------------|  
|Идентификатор процесса сервера|Идентификатор процесса сервера (SPID), назначенный сервером процессу, владеющему блокировкой.|  
|Идентификатор пакета сервера|Идентификатор пакета сервера (SBID).|  
|Идентификатор контекста выполнения|Идентификатор контекста выполнения (ECID). Идентификатор контекста выполнения данного потока, связанного с определенным идентификатором SPID.<br /><br /> ECID = {0,1,2,3, *...n*}, где 0 всегда представляет основной или родительский поток, а {1,2,3, *...n*} представляет подпроцессы.|  
|Приоритет взаимоблокировки|Приоритет взаимоблокировки для процесса. Дополнительные сведения о возможных значениях см. в статье [SET DEADLOCK_PRIORITY (Transact-SQL)](../../t-sql/statements/set-deadlock-priority-transact-sql.md).|  
|Используемый журнал|Объем пространства журнала, используемого для процесса.|  
|Идентификатор владельца|Идентификатор транзакции для процессов, которые используют транзакции и в настоящее время ожидают окончания блокировки.|  
|Дескриптор транзакции|Указатель на дескриптор транзакции, описывающий состояние транзакции.|  
|Входной буфер|Входной буфер текущего процесса определяет тип события и выполняемую инструкцию. Ниже перечислены возможные значения.<br /><br /> **Язык**<br /><br /> **RPC**<br /><br /> **None**|  
|.|Тип инструкции. Возможны следующие значения:<br /><br /> **NOP**<br /><br /> **SELECT**<br /><br /> **UPDATE**<br /><br /> **INSERT**<br /><br /> **DELETE**<br /><br /> **Unknown**|  
  
## <a name="deadlock-resource-node"></a>Взаимоблокировка узла ресурса  
 Во взаимоблокировке участвуют два процесса, каждый их которых ожидает освобождения ресурса, удерживаемого другим процессом. В графе взаимоблокировки ресурсы отображаются как узлы ресурсов.  
  
  
