---
title: Неподдерживаемые возможности в SQL Server Reporting Services в SQL Server 2014 | Документация Майкрософт
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
- discontinued functionality [Reporting Services]
- Reporting Services, backward compatibility
- Rsactivate.exe
- unsupported features [Reporting Services]
ms.assetid: d529cc96-3483-480b-9bfc-bd28b1d0ef52
caps.latest.revision: 47
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 971662bbb0b1c8b08507574d569418d065f6204a
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37201034"
---
# <a name="discontinued-functionality-to-sql-server-reporting-services-in-sql-server-2014"></a>Неподдерживаемые возможности в службах SQL Server Reporting Services в версии SQL Server "2014"
  В этом разделе описаны функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] , которые больше недоступны в [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)]. Сюда не входят объявления о прекращении поддержки определенных версий операционных систем или служб [!INCLUDE[msCoName](../includes/msconame-md.md)] IIS. Дополнительные сведения об этих системных требованиях см. в разделе [оборудованию и программному обеспечению для установки SQL Server 2014](../sql-server/install/hardware-and-software-requirements-for-installing-sql-server.md).  
  
 В этом разделе:  
  
-   [SQL Server 2014 Reporting Services неподдерживаемые функции](#bkmk_sql14)  
  
-   [SQL Server 2012 Reporting Services неподдерживаемые функции](#bkmk_rc0)  
  
-   [SQL Server 2008 R2 Reporting Services неподдерживаемые возможности](#bkmk_kj)  
  
##  <a name="bkmk_sql14"></a> [!INCLUDE[ssSQL14](../includes/sssql14-md.md)] Неподдерживаемые возможности в службах Reporting Services  
 В [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] отсутствуют неподдерживаемые функции служб [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].  
  
##  <a name="bkmk_rc0"></a> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] Неподдерживаемые возможности в службах Reporting Services  
 В этом разделе описаны неподдерживаемые функции служб [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] в [!INCLUDE[ssSQL11](../includes/sssql11-md.md)].  
  
 В [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] отсутствуют неподдерживаемые функции служб [!INCLUDE[ssSQL14](../includes/sssql14-md.md)].  
  
##  <a name="bkmk_kj"></a> SQL Server 2008 R2 Reporting Services неподдерживаемые возможности  
 В этом разделе описаны неподдерживаемые изменения в службах [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].  
  
> [!NOTE]  
>  Поскольку SQL Server 2008 R2 содержит изменения дополнительного номера версии по сравнению с SQL Server 2008, рекомендуется также просмотреть содержимое раздела по SQL Server 2008.  
  
### <a name="64-bit-platform-support"></a>Поддержка 64-разрядной платформы  
 Начиная с версии [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)], [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] больше не поддерживают серверы на основе Itanium под управлением Windows Server 2003 или Windows Server 2003 R2. [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] продолжает поддерживать другие 64-разрядных операционных систем, включая Windows Server 2008 для систем на основе процессоров Itanium и Windows Server 2008 R2 для систем на платформе Itanium. Чтобы обновить установленный экземпляр [!INCLUDE[ssKilimanjaro](../includes/sskilimanjaro-md.md)] со службами [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], работающий под управлением Windows Server 2003 или Windows Server 2003 R2 для систем на основе процессоров Itanium, до выпуска [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)], необходимо предварительно обновить операционную систему.  
  
### <a name="data-source-credentials-in-url-access"></a>Учетные данные источника данных при доступе через URL-адрес  
 Строки параметров доступа URL-адрес *dsu:datasourcename = value* и *dsp:datasourcename = value* теперь не поддерживается. В предыдущих версиях эти строки параметров хранились в виде открытого текста в кэше браузера, что небезопасно.  
  
## <a name="see-also"></a>См. также  
 [Новые возможности &#40;службы Reporting Services&#41;](what-s-new-reporting-services.md)   
 [Изменения в работе в SQL Server Reporting Services в SQL Server 2014](behavior-changes-to-sql-server-reporting-services-in-sql-server-2016.md)   
 [Нерекомендуемые функции служб SQL Server Reporting Services в SQL Server 2014](deprecated-features-in-sql-server-reporting-services-ssrs.md)  
  
  