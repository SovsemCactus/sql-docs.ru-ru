---
title: Создание и администрирование подписок для серверов отчетов в собственном режиме | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], managing
ms.assetid: 7f46cbdb-5102-4941-bca2-5e0ff9012c6b
caps.latest.revision: 37
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 56fb4e61fe7e442247fb9977afc440f13e5276e6
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37186181"
---
# <a name="create-and-manage-subscriptions-for-native-mode-report-servers"></a>Создание подписок для работающих в основном режиме серверов отчетов и управление этими подписками
  Этот раздел посвящен обработке, контролю и управлению подписками. Управление стандартными подписками и подписками, управляемыми данными, осуществляется по-разному. Стандартные подписки обычно принадлежат пользователю, который отвечает за управление ими. Подписки, управляемые данными, создаются и контролируются администратором сервера отчетов.  
  
 Функции подписок и доставок включены по умолчанию (доставка по электронной почте требует настройки перед использованием). Модули доставки по умолчанию включают доставку на электронный адрес сервера отчетов и в общую папку. Это единственные методы распространения, доступные для подписок на сервере отчетов, работающем в собственном режиме, если только не были созданы или установлены пользовательские модули доставки.  
  
## <a name="permissions-for-subscribing-to-reports-on-a-native-mode-report-server"></a>Разрешения для подписки на отчеты на сервере отчетов, работающем в собственном режиме  
 В зависимости от режима использования ролей можно предоставлять функциональность подписок выбранным группам пользователей, включая или отключая задачи подписок для различных ролей. Функции подписок доступны пользователям посредством двух задач:  
  
-   задача «Управление отдельными подписками» дает возможность пользователям создавать, изменять и удалять подписки для конкретного отчета. Что касается стандартных ролей, эта задача входит в состав ролей «Браузер» и «Построитель отчетов». Назначения ролей, которые включают эту задачу, позволяют управлять только подписками, создаваемыми пользователем;  
  
-   задача «Управление всеми подписками» дает возможность пользователям обращаться ко всем подпискам и изменять их. Эта задача необходима для создания подписок, управляемых данными. Из стандартных ролей эту задачу включает только роль «Диспетчер содержимого».  
  
## <a name="disabling-subscriptions"></a>Отключение подписок  
 Чтобы пользователи не могли создавать подписки, удалите задачу «Управление отдельными подписками» из роли. После этого страницы «Подписка» станут недоступны. В диспетчере отчетов папка «Мои подписки» отображается пустой (ее удалить нельзя), даже если она до этого содержала подписки. Удаление связанных с подписками задач запрещает пользователям создавать и изменять подписки, но не удаляет существующие подписки, которые продолжают действовать до тех пор, пока не удалены. Дополнительные сведения об удалении подписок см. в разделе [создание, изменение и удаление стандартных подписок &#40;служб Reporting Services в собственном режиме&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md).  
  
 Чтобы отключить обработку подписок на сервере отчетов, можно задать `ScheduleEventsAndReportDeliveryEnabled` свойства `False` в **настройки контактной зоны для служб Reporting Services** аспектом [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] управление на основе политик. Это приведет к предотвращению запуска всех запланированных операций. Нельзя отключить только обработку подписок на сервере отчетов.  
  
 Инструкции по отмене подписки, которая обрабатывается на сервере отчетов, см. в разделе [управление запущенным процессом](subscriptions/manage-a-running-process.md).  
  
## <a name="disabling-delivery-extensions"></a>Отключение модулей доставки  
 Все модули доставки, установленные на сервере отчетов, доступны любому пользователю, который имеет разрешение на создание подписки на данный отчет. Следующие модули доставки доступны и настраиваются автоматически:  
  
-   Общая папка Windows  
  
-   библиотека SharePoint (доступна только с сайта SharePoint, который интегрирован с сервером отчетов, работающим в режиме интеграции с SharePoint).  
  
 Доставку по электронной почте перед использованием необходимо настроить. Если настройка не выполнена, эта функция недоступна. Дополнительные сведения см. в разделе [Настройка сервера отчетов для доставки электронной почты &#40;диспетчер конфигурации служб SSRS&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md).  
  
 Если требуется отключить конкретные модули, можно удалить записи, относящиеся к модулю, из файла RSReportServer.config. Дополнительные сведения см. в разделе [файл конфигурации RSReportServer](report-server/rsreportserver-config-configuration-file.md) и [Настройка сервера отчетов для доставки электронной почты &#40;диспетчер конфигурации служб SSRS&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md).  
  
 После удаления модуля доставки он становится недоступным в диспетчере отчетов или на сайте SharePoint. При удалении модуля доставок могут появляться неактивные подписки. Обязательно удаляйте подписки или настраивайте их на использование другого модуля доставки, прежде чем удалить какой-либо модуль.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Использование страницы "Мои подписки"](subscriptions/use-my-subscriptions-native-mode-report-server.md)  
 Объясняет, как пользоваться страницей «Мои подписки» для управления собственными подписками.  
  
 [Приостановка обработки отчета и подписки](subscriptions/disable-or-pause-report-and-subscription-processing.md)  
 Описывает различные способы приостановки обработки отчета, например назначение ролей или отключение ресурсов сервера отчетов.  
  
 [Управление распространением отчета](../../2014/reporting-services/control-report-distribution.md)  
 Содержит описание параметров конфигурации и параметров доставки, при помощи которых можно управлять распространением отчетов.  
  
 [Отслеживание подписок служб Reporting Services](subscriptions/monitor-reporting-services-subscriptions.md)  
 Содержит сведения о том, как определить, успешно или неуспешно выполнена подписка, и каким образом изменение отчета влияет на существующие подписки.  
  
## <a name="see-also"></a>См. также  
 [Создание, изменение и удаление стандартных подписок &#40;Reporting Services в собственном режиме&#41;](subscriptions/create-and-manage-subscriptions-for-native-mode-report-servers.md)  
  
  