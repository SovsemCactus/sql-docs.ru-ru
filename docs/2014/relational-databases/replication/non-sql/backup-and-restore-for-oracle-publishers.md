---
title: Резервное копирование и восстановление для издателей Oracle | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- recovery [SQL Server replication], Oracle publishing
- backups [SQL Server replication], Oracle publishing
- Oracle publishing [SQL Server replication], backup and restore
- restoring [SQL Server replication], Oracle publishing
ms.assetid: e5f181d0-cacf-442b-8b7a-202b3cfc358b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 0fb07772da3bdcf485ca7668fc9a9e34a8e51c5b
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85060572"
---
# <a name="backup-and-restore-for-oracle-publishers"></a>Резервное копирование и восстановление для издателей Oracle
  При резервном копировании и восстановлении соблюдайте следующие рекомендации:  
  
-   Убедитесь в том, что при резервном копировании издателя не запущен агент чтения журнала, а также в отсутствии любой активности в опубликованных таблицах баз данных.  
  
-   Производите резервное копирование издателя и распространителя одновременно.  
  
-   Если издатель или распространитель подлежат восстановлению, то повторно инициализируйте все подписки.  
  
-   Чтобы восстановить подписчика из резервной копии (без необходимости повторной инициализации подписки), должны быть сохранены транзакции, доставленные в базу данных подписки после последнего завершенного резервного копирования этой базы данных. Отрезок времени, в течение которого транзакции все еще доступны, зависит от установок хранения распространения. Сведения об этих настройках см. в статье [Окончание срока действия и отключение подписки](../subscription-expiration-and-deactivation.md).  
  
-   Если издатель или распространитель становятся несинхронизированными в результате восстановления базы данных, агент репликации производит в журнал записи об ошибке. В этом случае следует удалить и повторно создать все соответствующие публикации и подписки:  
  
    1.  Напишите скрипт определений публикаций и подписок. Дополнительные сведения см. в разделе [Scripting Replication](../scripting-replication.md).  
  
         Если определение публикации изменило версию состояния издателя и распространителя, потребуется изменить скрипты.  
  
    2.  Удалите публикации и подписки.  
  
    3.  Выполните скрипты, созданные на шаге 1.  
  
     Если издатель должен быть удален и перенастроен заново, удалите открытый синоним **MSSQLSERVERDISTRIBUTOR** и пользователя настроенной репликации Oracle с помощью параметра **CASCADE** для удаления всех объектов репликации из издателя Oracle.  
  
## <a name="see-also"></a>См. также:  
 [Создание резервной копии и восстановление из копий реплицируемых баз данных](../administration/back-up-and-restore-replicated-databases.md)   
 [Настройка издателя Oracle](configure-an-oracle-publisher.md)   
 [Обзор публикации Oracle](oracle-publishing-overview.md)  
  
  
