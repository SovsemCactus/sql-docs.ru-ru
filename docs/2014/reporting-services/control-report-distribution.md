---
title: Управляйте распространением отчетов | Документация Майкрософт
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- subscriptions [Reporting Services], report distribution
- subscriptions [Reporting Services], e-mail
- subscriptions [Reporting Services], file share delivery
- file share delivery [Reporting Services]
- e-mail [Reporting Services]
- subscriptions [Reporting Services], security
- mail [Reporting Services]
ms.assetid: 8f15e2c6-a647-4b05-a519-1743b5d8654c
caps.latest.revision: 32
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: d73a5e483219df7a8b7c06a3c4719850aaf7a3f7
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37160185"
---
# <a name="control-report-distribution"></a>Распространение отчетов управления
  Сервер отчетов можно определенным образом настроить для уменьшения рисков, связанных с электронной почтой и распространением в общей папке.  
  
## <a name="securing-reports"></a>Обеспечение безопасности отчетов  
 Первым шагом в контроле распространения отчетов является обеспечение защиты отчета от несанкционированного доступа. Чтобы отчет попал в подписку, в нем должен применяться хранимый набор учетных данных, одинаковых для разных доставок. Его может запустить и распространить любой пользователь, обладающий доступом к отчету на сервере отчетов. Для предотвращения такой ситуации следует ограничить доступ и предоставить его только тем пользователям, которым он необходим. Дополнительные сведения см. в разделе [защищенные отчеты и ресурсы](security/secure-reports-and-resources.md) и [обеспечение защиты папок](security/secure-folders.md).  
  
 Отчеты повышенной конфиденциальности, использующие для получения доступа безопасность базы данных, не могут распространяться через подписку.  
  
> [!IMPORTANT]  
>  Отчеты переносятся в виде файлов. Риски и защитные меры, которые относятся к файлам, относятся и к отчетам, которые сохраняются на диске или высылаются в виде вложений. Любой пользователь, который имеет доступ к файлам, может распространять или использовать их по собственному усмотрению.  
  
## <a name="controlling-e-mail-delivery"></a>Контроль доставки электронной почты  
 Сервер отчетов можно настроить таким образом, чтобы распространение по электронной почте ограничивалось только определенными доменами. Например, можно запретить серверу отчетов доставку отчета всем доменам, кроме указанных в списке файла конфигурации RSReportServer.  
  
 Кроме того, можно настроить конфигурацию таким образом, чтобы поле **Кому** в подписке было скрыто. В этом случае отчеты будут доставляться только пользователю, который определяет подписку. Однако после отправки отчета пользователю можно явно запретить его пересылку.  
  
 Наиболее эффективный путь управления распространением отчетов — настроить сервер отчетов так, чтобы он отправлял только URL-адрес сервера отчетов. Сервер отчетов управляет доступом к отчетам с помощью проверки подлинности Windows и модели авторизации на основе ролей. Если пользователь случайно получит электронное письмо с отчетом, не предназначенным для этого пользователя, то сервер не отобразит этот отчет.  
  
## <a name="controlling-file-share-delivery"></a>Управление доставкой в общую папку  
 Доставка в общую папку используется для записи отчета в файл на жестком диске. После сохранения файла на диске этот файл перестает быть субъектом модели безопасности на основе ролей, с помощью которой сервер отчетов управляет доступом пользователей. Для защиты отчета, сохраненного на диске, можно поместить списки управления доступом (ACLs) в сам файл или в папку, в которой он находится. Кроме того, в зависимости от операционной системы, могут быть доступны другие параметры безопасности.  
  
## <a name="see-also"></a>См. также  
 [Настройка сервера отчетов для доставки электронной почты &#40;диспетчер конфигурации служб SSRS&#41;](../../2014/sql-server/install/configure-a-report-server-for-e-mail-delivery-ssrs-configuration-manager.md)   
 [Подписки и доставка &#40;службы Reporting Services&#41;](subscriptions/subscriptions-and-delivery-reporting-services.md)   
 [Создание и администрирование подписок для серверов отчетов в собственном режиме](../../2014/reporting-services/create-manage-subscriptions-native-mode-report-servers.md)  
  
  