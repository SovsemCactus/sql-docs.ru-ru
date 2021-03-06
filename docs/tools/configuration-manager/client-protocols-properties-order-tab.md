---
title: Свойства клиентских протоколов (вкладка «Порядок»)
ms.custom: seo-lt-2019
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: sql-tools
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- client protocols [SQL Server]
ms.assetid: 64fd7135-1756-4885-bed9-9ab8997ecc6c
author: markingmyname
ms.author: maghan
monikerRange: '>=sql-server-2016||=sqlallproducts-allversions'
ms.openlocfilehash: 59ffc1332b52d95221541a45ba90fe3e22a89caa
ms.sourcegitcommit: ff82f3260ff79ed860a7a58f54ff7f0594851e6b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/29/2020
ms.locfileid: "75306519"
---
# <a name="client-protocols-properties-order-tab"></a>Свойства клиентских протоколов (вкладка «Порядок»)
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]
  Используйте страницу **Порядок** диалогового окна **Свойства протокола клиента** для просмотра и включения клиентских протоколов.  
  
 Щелкните протокол, а затем выберите команду **Включить** или **Выключить** для перемещения выбранного протокола в список **Отключенные протоколы** или **Включенные протоколы** .  
  
 Попытки использования протоколов происходят в перечисленной в списке последовательности: сначала осуществляется попытка соединения при помощи самого верхнего протокола, затем при помощи протокола, второго в списке, и так далее. Передвигать протоколы вверх и вниз по списку **Включенные протоколы** можно, нажимая кнопки со стрелкой вверх и со стрелкой вниз. При подключении к [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] из клиента на том же компьютере в первую очередь происходит попытка подключения через протокол **Shared Memory** (Общая память), если он включен.  
  
> [!NOTE]  
>  Эти настройки не используются клиентом [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET SqlClient. В порядке протоколов для клиента .NET SqlClient первым идет протокол TCP, а затем именованные каналы. Этот порядок нельзя изменить.  
  
## <a name="options"></a>Параметры  
 **Отключенные протоколы**  
 Содержит список установленных, но не используемых в этот момент протоколов.  
  
 **Включенные протоколы**  
 Содержит список протоколов, доступных для клиентов [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] на этом компьютере.  
  
 **>**  
 Включает выделенный протокол в окне **Отключенные протоколы** и переносит его в окно **Включенные протоколы** .  
  
 **\<**  
 Отключает выделенный протокол в окне **Включенные протоколы** и переносит его в окно **Отключенные протоколы** .  
  
 Стрелка вверх  
 Перемещает выделенный протокол вверх по списку. Это позволяет повысить приоритет использования сетевой библиотекой выбранного протокола для соединений.  
  
 Стрелка вниз  
 Перемещает выделенный протокол вниз по списку. Это позволяет понизить приоритет использования сетевой библиотекой выбранного протокола для соединений.  
  
 **Включить протокол общей памяти**  
 Включает протокол общей памяти, который всегда используется первым (в том случае, если он включен) при подключении к [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] с клиента на том же компьютере.  
  
> [!NOTE]  
>  Если протокол определен через префикс или как часть строки соединения, то попытка подключения будет происходить только через определенный протокол.  
  
## <a name="see-also"></a>См. также:  
 [Выбор сетевого протокола](https://msdn.microsoft.com/library/6565fb7d-b076-4447-be90-e10d0dec359a)  
  
  
