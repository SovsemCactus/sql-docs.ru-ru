---
title: URL-адрес диспетчер отчетов (собственный режим служб SSRS) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.rsconfigtool.reportmanagervirtualdirectory.f1
ms.assetid: 45768952-23a6-45a5-b541-e7bf192b4a78
author: maggiesMSFT
ms.author: maggies
ms.openlocfilehash: 53eaf828dd3fe6f5fa4056bda9dbc428dfa5d385
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85054634"
---
# <a name="report-manager-url-ssrs-native-mode"></a>URL-адрес диспетчера отчетов (службы Reporting Services в собственном режиме)
  Настроить или изменить URL-адрес для доступа к диспетчеру отчетов можно на странице «URL-адрес диспетчера отчетов». По умолчанию на этой странице наследуется префикс, IP-адрес и порт, соответствующие URL-адресу веб-службы сервера отчетов. Это связано с тем, что диспетчер отчетов предоставляет клиентский доступ к веб-службе, которая запускается под управлением той же службы сервера отчетов. Если нужно изолировать приложения друг от друга и пользоваться диспетчером отчетов для доступа к веб-службе сервера отчетов на другом компьютере, то в файле RSReportServer.config укажите для диспетчера отчетов другой экземпляр. Дополнительные сведения о настройке подключения диспетчер отчетов к удаленному серверу отчетов см. в разделе [диспетчер конфигурации служб Reporting Services &#40;в основном режиме&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).  
  
 [!INCLUDE[applies](../../includes/applies-md.md)][!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]Собственный режим.  
  
 Если настройка сервера отчетов выполняется для работы в режиме интеграции с SharePoint, то создавать URL-адрес диспетчера отчетов не нужно. Диспетчер отчетов не поддерживается на сервере отчетов, работающем в режиме интеграции с SharePoint. Если для диспетчера отчетов URL-адрес уже существует, то после настройки конфигурации сервера отчетов для работы в режиме интеграции с SharePoint он становится недоступен.  
  
 Чтобы открыть эту страницу, запустите диспетчер конфигурации служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] и выберите на панели навигации пункт **URL-адрес диспетчера отчетов** . Дополнительные сведения о запуске Configuration Manager см. в разделе [диспетчер конфигурации служб Reporting Services &#40;основном режиме&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).  
  
> [!NOTE]  
>  Если диспетчер отчетов не включен, настройка параметров на этой странице будет невозможна. Дополнительные сведения о включении диспетчер отчетов см. в разделе [диспетчер конфигурации служб Reporting Services &#40;основном режиме&#41;](../../../2014/sql-server/install/reporting-services-configuration-manager-native-mode.md).  
  
## <a name="options"></a>Варианты  
 **Виртуальный каталог**  
 Указывает имя виртуального каталога диспетчера отчетов. Каждый экземпляр диспетчера отчетов на одном компьютере может иметь только одно имя виртуального каталога.  
  
 **URL-адреса**  
 Отображает URL-адрес, определенный для текущего экземпляра диспетчера отчетов.  
  
 **Дополнительно**  
 Введите дополнительный URL-адрес для текущего экземпляра диспетчера отчетов.  
  
## <a name="see-also"></a>См. также:  
 [Настройка URL-адреса &#40;SSRS Configuration Manager&#41;](../../reporting-services/install-windows/configure-a-url-ssrs-configuration-manager.md)   
 [URL-адреса в файлах конфигурации &#40;Configuration Manager SSRS&#41;](../../reporting-services/install-windows/urls-in-configuration-files-ssrs-configuration-manager.md)   
 [Настройка URL-адресов сервера отчетов (диспетчер конфигурации служб SSRS)](../../reporting-services/install-windows/configure-report-server-urls-ssrs-configuration-manager.md)  
  
  
