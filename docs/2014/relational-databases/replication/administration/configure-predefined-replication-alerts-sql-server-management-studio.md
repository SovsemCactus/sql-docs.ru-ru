---
title: Настройка стандартных предупреждений репликации (среда SQL Server Management Studio) | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- alerts [SQL Server replication]
- predefined replication alerts [SQL Server replication]
ms.assetid: c0414147-7ffe-4f9a-908c-71c1b5201584
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 191ffcfe0fb5ac041956a42500da650f6d8cc453
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85066027"
---
# <a name="configure-predefined-replication-alerts-sql-server-management-studio"></a>Настройка стандартных предупреждений репликации (среда SQL Server Management Studio)
  Репликация предоставляет следующие предварительно установленные предупреждения, которые могут быть настроены для реакции на события репликации:  
  
-   **Репликация: успех агента**    
-   **Репликация: неудача агента**    
-   **Репликация: повторная попытка агента**    
-   **Репликация: истекшая подписка удалена**    
-   **Репликация. Подписка повторно инициализирована после неудачной проверки допустимости**    
-   **Репликация. Подписчик не прошел проверку допустимости данных**    
-   **Репликация. Подписчик прошел проверку допустимости данных**    
-   **Репликация: нестандартное завершение работы агента**  
  
 Настройте эти предупреждения в папке **Предупреждения** среды [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../../includes/ssmanstudiofull-md.md)] или на вкладке **Предупреждения** монитора репликации. Дополнительные сведения о доступе к этой вкладке см. в разделе [Просмотр сведений и выполнение задач с помощью монитора репликации](../monitor/view-information-and-perform-tasks-replication-monitor.md).  
  
 Наряду с этими предупреждениями монитор репликации предоставляет набор предупреждений и оповещений, относящихся к состоянию и производительности. Дополнительные сведения см. [в разделе Установка пороговых значений и предупреждений в](../monitor/set-thresholds-and-warnings-in-replication-monitor.md) инфраструктуре предупреждений монитора репликации. Дополнительные сведения см. в статье [Создание пользовательского события](../../../ssms/agent/create-a-user-defined-event.md).  
  
### <a name="to-configure-a-predefined-replication-alert-in-management-studio"></a>Настройка предварительно определенного предупреждения репликации в Management Studio  
  
1.  Подключитесь к распространителю в [!INCLUDE[ssManStudio](../../../includes/ssmanstudio-md.md)]и разверните узел сервера.    
2.  Раскройте папку **Агент SQL Server** , затем раскройте папку **Предупреждения** .    
3.  Щелкните правой кнопкой мыши предупреждение репликации, затем щелкните **Свойства**.    
4.  Задайте параметры в диалоговом окне « ** \<AlertName> Свойства предупреждения** ».    
    -   На странице **Общие** щелкните **Включить**, укажите базу данных, к которой нужно применить данное предупреждение.    
    -   На странице **Ответ** укажите, надо ли отправить оповещение по электронной почте и/или запустить задание.  
  
         Если оповещение является **репликацией: ошибка проверки данных подписчиком**, можно указать задание ответа, которое будет предоставлено репликацией для этого оповещения: выберите **выполнить задание**и нажмите кнопку обзора (**...**). В диалоговом окне **Найти задание** нажмите кнопку **Обзор**. В диалоговом окне **Поиск объектов** установите флажок **Повторная инициализация подписок, имеющих сбои при выполнении проверки данных**. В обоих окнах нажмите **ОК** . Во время выполнения задание осуществляет удаленный вызов хранимой процедуры, которая повторно инициализирует подписку. Если издатель использует удаленный распространитель, необходимо указать на издателе имя входа удаленного сервера, чтобы сделать возможным удаленный вызов процедур с распространителя на издатель.   
    -   На странице **Параметры** измените текст ответа.    
5.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-configure-an-alert-for-a-threshold-in-replication-monitor"></a>Настройка предупреждения для порогового значения в мониторе репликации  
  
1.  На вкладке **Предупреждения** щелкните **Настройка предупреждений**.    
2.  В диалоговом окне **Настройка предупреждений репликации** выберите необходимое предупреждение, а затем щелкните **Настроить**.    
3.  Задайте параметры в диалоговом окне « ** \<AlertName> Свойства предупреждения** ».    
    -   На странице **Общие** щелкните **Включить**, укажите базу данных, к которой нужно применить данное предупреждение.    
    -   На странице **Ответ** укажите, надо ли отправить оповещение по электронной почте и/или запустить задание.    
         Если оповещение является **репликацией: ошибка проверки данных подписчиком**, можно указать задание ответа, которое будет предоставлено репликацией для этого оповещения: выберите **выполнить задание**и нажмите кнопку обзора (**...**). В диалоговом окне **Найти задание** нажмите кнопку **Обзор**. В диалоговом окне **Поиск объектов** установите флажок **Повторная инициализация подписок, имеющих сбои при выполнении проверки данных**. В обоих окнах нажмите **ОК** . Во время выполнения задание осуществляет удаленный вызов хранимой процедуры, которая повторно инициализирует подписку. Если издатель использует удаленный распространитель, необходимо указать на издателе имя входа удаленного сервера, чтобы сделать возможным удаленный вызов процедур с распространителя на издатель.   
    -   На странице **Параметры** измените текст ответа.    
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]    
5.  Щелкните **Закрыть**.  
  
## <a name="see-also"></a>См. также:  
 [Использование предупреждений для событий агента репликации](../agents/use-alerts-for-replication-agent-events.md)  
  
  
