---
title: Просмотр состояния зеркального отображения базы данных (среда SQL Server Management Studio) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- states [SQL Server], database mirroring
- database mirroring [SQL Server], states
ms.assetid: 544f4194-253e-4c57-96ca-31c16301434f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7a6d664a838e82a10df4ab16f4f6c097ffacf8b2
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84933812"
---
# <a name="view-the-state-of-a-mirrored-database-sql-server-management-studio"></a>Просмотр состояния зеркального отображения базы данных (среда SQL Server Management Studio)
  Во время сеанса зеркального отображения базы данных можно просмотреть его состояние на странице **Зеркальное отображение** диалогового окна **Свойства базы данных** .  
  
### <a name="to-view-the-status-of-a-database-mirroring-session"></a>Просмотр состояния сеанса зеркального отображения базы данных  
  
1.  После подключения к экземпляру основного сервера в обозревателе объектов щелкните имя сервера, чтобы развернуть дерево сервера.  
  
2.  Раскройте узел **Базы данных**и выберите базу данных для зеркального отображения.  
  
3.  Щелкните базу данных правой кнопкой мыши, выберите **Задачи**, а затем **Зеркальное отображение**. Откроется страница **Зеркальное отображение** диалогового окна **Свойства базы данных** .  
  
4.  После начала зеркального отображения на панели **Состояние** отражается та же информация о состоянии сеанса зеркального отображения, что и при выборе страницы **Зеркальное отображение** или нажатии кнопки **Обновить** . Возможны следующие состояния.  
  
    |Состояния|Объяснение|  
    |------------|-----------------|  
    |\<blank>|Не существует ни одного сеанса зеркального отображения, а сведения об активности не представлены на странице **Зеркальное отображение** .|  
    |Приостановлено|Основная база данных запущена, но не посылает никаких записей журнала на зеркальный сервер. Зеркальное отображение базы данных недоступно.|  
    |Нет соединения|Экземпляр основного сервера не может подключиться к другому участнику или следящему серверу (если он есть).|  
    |Синхронизация|Содержимое зеркальной базы данных отстает от содержимого основной базы данных. Экземпляр основного сервера отправляет записи журнала на экземпляр зеркального сервера, который применяет эти изменения к зеркальной базе данных для выполнения наката.<br /><br /> В начале сеанса зеркального отображения базы данных основная и зеркальная базы данных синхронизированы.|  
    |Отработка отказа|Процесс отработки отказа вручную (смена ролей) начался на экземпляре основного сервера, но еще не был принят зеркальным сервером.|  
    |синхронизировано;|Зеркальная база данных содержит те же данные, что и основная база данных. Ручная и автоматическая отработка отказа возможна *только* в этом состоянии.|  
  
## <a name="see-also"></a>См. также:  
 [Состояния зеркального отображения (SQL Server)](mirroring-states-sql-server.md)  
  
  
