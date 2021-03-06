---
title: Свойства сервера (страница "Соединения") | Документы Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.serverproperties.connections.f1
ms.assetid: 33be8ac5-12dd-4b8a-99e0-68261c219dd2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: b894d7b554dffcb0941ddf38182519cf85a84c2f
ms.sourcegitcommit: 9ee72c507ab447ac69014a7eea4e43523a0a3ec4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84934965"
---
# <a name="server-properties-connections-page"></a>Свойства сервера (страница «Соединения»)
  Данная страница предназначена для просмотра или изменения параметров соединения.  
  
## <a name="connections"></a>Соединения  
 **Максимальное число одновременных соединений (0 = неограниченно)**  
 При установке значения, отличающегося от нуля, ограничивает количество соединений, допускаемое [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
> [!CAUTION]  
>  Установка этого параметра на малое значение, например 1 или 2, может не дать возможности администраторам соединиться с целью администрирования сервера, однако выделенное соединение с сервером может быть осуществлено всегда.  
  
## <a name="default-connection-options"></a>Параметры соединения по умолчанию  
 **Default connection options**  
 Задает параметры соединения по умолчанию, описанные в следующей таблице.  
  
|Параметр конфигурации|Описание|  
|--------------------------|-----------------|  
|**отключить отложенную проверку ограничений**|Управляет промежуточной или отложенной проверкой ограничений.|  
|**неявные транзакции**|Управляет неявным началом транзакции при выполнении инструкции.|  
|**закрытие курсора при фиксации**|Управляет поведением курсора после выполнения операции фиксации.|  
|**предупреждения в формате ANSI**|Управляет усечением и значениями NULL в предупреждениях статистических вычислений.|  
|**заполнение символами ANSI**|Управляет заполнением переменных фиксированной длины.|  
|**значения NULL по стандарту ANSI**|Управляет обработкой значений `NULL` при использовании операторов равенства.|  
|**прерывание арифметических действий**|Завершает запрос, если во время выполнения запроса возникает ошибка переполнения или деления на нуль.|  
|**пропуск арифметических действий**|Возвращает значение NULL, если во время выполнения запроса возникла ошибка переполнения или деления на ноль.|  
|**заключенный в кавычки идентификатор**|При вычислении выражения различает двойные и одинарные кавычки.|  
|**отсутствует счетчик**|Выключает сообщение, которое возвращается в конце каждой инструкции и указывает количество затронутых строк.|  
|**ANSI NULL по умолчанию включен**|Изменяет поведение сеанса по использованию ANSI-совместимости для поддержки значений NULL. Новые столбцы, которые определялись без явного указания поддержки значений NULL, допускают значения NULL.|  
|**ANSI NULL по умолчанию выключен**|Изменяет поведение сеанса, чтобы не допустить использования ANSI-совместимости для поддержки значений NULL. Новые столбцы, которые определялись без явной поддержки значений NULL, определяются с недопущением этих значений.|  
|**сцепление значений NULL дает значение NULL**|При сцеплении значения NULL со строкой возвращается значение NULL.|  
|**прерывание округления**|Формируется ошибка при потере точности в выражении.|  
|**прерывание транзакции**|Если при выполнении инструкции Transact-SQL возникла ошибка, то выполняется откат транзакции.|  
  
 Для получения дополнительных сведений о параметрах соединения выполните поиск конкретного параметра см. в электронной документации.  
  
## <a name="remote-server-connections"></a>Удаленные серверные соединения  
 **Разрешить удаленные соединения с этим сервером**  
 Управляет выполнением хранимых процедур с удаленных серверов, на которых запущены экземпляры [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. Установка этого флажка приводит к таким же результатам, что и задание для параметра **удаленного доступа sp_configure** значения 1. Снятие этого флажка предотвращает выполнение хранимых процедур с удаленного сервера.  
  
 **Время ожидания удаленного запроса (в секундах, 0 = неограниченно)**  
 Задает время (в секундах), в течение которого может выполняться удаленная операция перед истечением времени ожидания [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] . Значение по умолчанию составляет 600 секунд, то есть 10 минут ожидания.  
  
 **Требовать применения распределенных транзакций для соединения «сервер-сервер»**  
 Защищает действия процедуры между серверами посредством транзакции координатора распределенных транзакций (MS DTC) ( [!INCLUDE[msCoName](../../includes/msconame-md.md)] ). Дополнительные сведения см. в статье [Настройка параметра конфигурации сервера remote proc trans](configure-the-remote-proc-trans-server-configuration-option.md).  
  
## <a name="property-page-display-options"></a>Параметры отображения страницы свойств  
 **Настроенные значения**  
 Отображает настроенные значения для параметров на этой панели. В случае изменения этих значений выберите пункт **Текущие значения** и посмотрите, вступили ли в силу внесенные изменения. В противном случае первым должен быть перезапущен экземпляр [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .  
  
 **Текущие значения**  
 Просмотр текущих значений для параметров на этой панели. Эти значения доступны только для чтения.  
  
## <a name="see-also"></a>См. также:  
 [Параметры &#40;выполнения запроса: SQL Server: страница "Дополнительно"&#41;](../options-query-execution-sql-server-advanced-page.md)   
 [Параметры конфигурации сервера (SQL Server)](server-configuration-options-sql-server.md)  
  
  
