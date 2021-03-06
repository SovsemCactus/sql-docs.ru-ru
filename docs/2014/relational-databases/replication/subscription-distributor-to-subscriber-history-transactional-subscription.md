---
title: Подписка, вкладка "Журнал операций от распространителя к подписчику" (транзакционная подписка) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.monitor.subscription.disttosub.f1
ms.assetid: 1aad5b82-592e-4907-92f7-b90794175be5
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 7c4c97e61191da4d51830b1bc8d44bfc98f698a9
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84997961"
---
# <a name="subscription-distributor-to-subscriber-history-transactional-subscription"></a>Подписка, журнал от распространителя к подписчику (подписка на публикацию транзакций)
   Вкладка **Журнал операций от распространителя к подписчику** содержит подробные сведения об агенте распространителя, включая состояние, журнал, информационные сообщения и любые сообщения об ошибках.  
  
## <a name="options"></a>Варианты  
 В меню **Вид** выберите сеансы, какого агента распространителя необходимо просмотреть, а затем в сетке **Сеансы агента распространителя**выберите определенный сеанс. Подробные сведения об этом сеансе отображаются в сетке, помеченной как **Действия в выбранном сеансе**. Если выбранный сеанс закончен с ошибкой, также выводится на экран текстовое поле, помеченное как **Описание ошибки или сообщение выбранного сеанса** .  
  
 **Вид**  
 Выберите агента распространителя, сеансы которого необходимо просмотреть. Как правило, агент распространителя работает постоянно, поэтому просмотреть можно только один сеанс.  
  
 **Состояние**  
 Состояние агента распространителя. Возможные значения состояния показаны в следующем списке:  
  
-   Error  
  
-   Завершено  
  
-   Повтор  
  
-   Запущен  
  
 **Время начала**  
 Время начала сеанса.  
  
 **Время окончания**  
 Время окончания сеанса. Если агент не остановлен, это поле остается пустым.  
  
 **Длительность**  
 Длительность работы агента распространителя в этом сеансе. Если в данный момент агент работает, отображается время его работы, после завершения сеанса агента отображается общая длительность сеанса.  
  
 **Сообщение об ошибке**  
 Если сеанс завершился ошибкой, в данном поле отображается последнее сообщение об ошибке, зарегистрированное агентом распространителя. Если сеанс завершился без ошибки, это поле остается пустым.  
  
 **Сообщение действия**  
 Все информационные сообщения и сообщения об ошибках, зарегистрированные агентом распространителя в течение выбранного сеанса.  
  
 **Время действия**  
 Время, когда было выполнено действие, описанное в столбце **Сообщение действия** .  
  
 **Описание ошибки или сообщение выбранного сеанса**  
 Выводится, только если выбранный сеанс отображает значение **Ошибка** в столбце **Состояние** . Это текстовое поле отображает подробные данные об ошибке и о выполняемой во время возникновения ошибки команде. Также содержит ссылки на дополнительные данные, имеющие отношение к ошибке.  
  
## <a name="see-also"></a>См. также:  
 [Запуск монитора репликации](monitor/start-the-replication-monitor.md)   
 [Просмотр сведений и выполнение задач с помощью монитора репликации](monitor/view-information-and-perform-tasks-replication-monitor.md)   
 [Мониторинг репликации](monitoring-replication.md)   
 [Replication Agents Overview](agents/replication-agents-overview.md)  
  
  
