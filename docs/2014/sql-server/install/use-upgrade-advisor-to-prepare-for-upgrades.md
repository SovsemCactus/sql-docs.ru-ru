---
title: Использование помощника по обновлению для подготовки к обновлениям | Документация Майкрософт
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- database-engine
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor [SQL Server]
- upgrading SQL Server, Upgrade Advisor
- upgrading SQL Server, preparing to upgrade
- SQL Server Upgrade Advisor
- analyzing installations for upgrading [SQL Server]
ms.assetid: d85b0833-ddeb-42e3-9397-97ea60d521b7
caps.latest.revision: 51
author: mashamsft
ms.author: mathoma
manager: craigg
ms.openlocfilehash: 4e669b214e73d462f141022aa84d41224e88ac0c
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37234424"
---
# <a name="use-upgrade-advisor-to-prepare-for-upgrades"></a>Использование помощника по обновлению для подготовки к обновлениям
  Помощник по обновлению [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] помогает произвести подготовку к обновлениям [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]. Помощник по обновлению анализирует установленные компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и создает отчет, содержащий список проблем, которые должны быть решены перед началом обновления.  
  
## <a name="how-upgrade-advisor-works"></a>Как работает помощник по обновлению  
 После запуска помощника по обновлению появляется его домашняя страница. С домашней страницы можно запустить следующие средства:  
  
-   мастер анализа помощника по обновлению;  
  
-   Средство просмотра отчетов помощника по обновлению  
  
-   справка помощника по обновлению.  
  
 При первом запуске помощника по обновлению следует запустить мастер анализа помощника по обновлению, чтобы проанализировать компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]. После того как мастер закончит анализ, итоговый отчет можно просмотреть с помощью средства просмотра отчетов помощника по обновлению. Каждый отчет предоставляет ссылки на сведения из справки помощника по обновлению, которые помогут исправить или обойти возникшие проблемы.  
  
## <a name="upgrade-advisor-analysis"></a>Анализ помощника по обновлению  
 Помощник по обновлению анализирует следующие компоненты [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:  
  
-   [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
-   [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]  
  
-   [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]  
  
-   [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]  
  
 В ходе анализа проверяются все доступные объекты: скрипты, хранимые процедуры, триггеры и файлы трассировки. Помощник по обновлению не производит анализ настольных приложений и зашифрованных хранимых процедур.  
  
 Результат формируется в виде XML-отчета. Просмотреть отчет в формате XML можно с помощью средства просмотра отчетов помощника по обновлению.  
  
> [!NOTE]  
>  Отчеты могут содержать элемент «другие проблемы обновления». Этот элемент содержит ссылку на список проблем, которые не были обнаружены помощником по обновлению, но могут присутствовать на сервере или в приложениях. Необходимо просмотреть этот список и определиться с изменениями, которые необходимо произвести на сервере или в приложениях для исправления этих ошибок.  
  
## <a name="how-to-install-and-run-upgrade-advisor"></a>Установка и запуск помощника по обновлению  
 Место установки помощника по обновлению [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] зависит от того, что именно необходимо проанализировать. Помощник по обновлению поддерживает удаленный анализ всех поддерживаемых компонентов, за исключением служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]. Если просмотр экземпляров служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] не производится, помощник по обновлению может быть установлен на любой компьютер, который способен подключаться к экземпляру [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] и удовлетворяет требованиям к установке помощника по обновлению. Дополнительные сведения см. в статье [Supported Version and Edition Upgrades](../../database-engine/install-windows/supported-version-and-edition-upgrades.md). Для просмотра экземпляров служб [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)]следует установить помощник по обновлению на сервер отчетов.  
  
 Советник по переходу доступен в пакете дополнительных компонентов.  
  
 Ниже перечислены предварительные условия для установки и запуска помощника по обновлению.  
  
-   [!INCLUDE[firstref_longhorn](../../includes/firstref-longhorn-md.md)] с пакетом обновления 2 (SP2), Windows 7 с пакетом обновления 1 (SP1) и [!INCLUDE[winserver2008r2](../../includes/winserver2008r2-md.md)] с пакетом обновления 1 (SP1).  
  
-   Установщик Windows Installer, начиная с версии 4.5. Вы можете установить установщик Windows из [веб-установщик Windows сайт](http://go.microsoft.com/fwlink/?LinkId=49112).  
  
-   Microsoft .NET Framework 4. .NET framework 4 доступна на [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] носителе продукта и из [странице загрузки .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=209895).  
  
    -   Чтобы установить платформу .NET Framework 4 с установочного диска [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], перейдите в корневой каталог диска. Откройте папку «\redist», а затем папку «DotNetFrameworks», после чего запустите файл dotNetFx40_Full_x86_x64.exe (для 32- и 64-разрядных версий операционных систем).  
  
 Чтобы установить помощник по обновлению из веб-узла, нажмите кнопку загрузки на странице загрузки. Затем можно либо сразу начать установку, либо сохранить файл SQLUA.msi для последующего запуска. При установке с диска продукта запустите SQLUA.msi непосредственно с диска.  
  
 После установки помощник по обновлению, его можно открыть из **запустить** меню:  
  
-   Нажмите кнопку **запустить**, пункты **все программы**, пункты [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], а затем нажмите кнопку  **[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] помощник по обновлению**.  
  
 Дополнительные сведения см. в документации помощника по обновлению, включенной в пакет загрузки, и в заметках о выпуске [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)].  
  
## <a name="see-also"></a>См. также  
 [Работать с несколькими версиями и экземплярами SQL Server](../../../2014/sql-server/install/work-with-multiple-versions-and-instances-of-sql-server.md)   
 [Поддерживаемые обновления версий и выпусков](../../database-engine/install-windows/supported-version-and-edition-upgrades.md)   
 [Обратная совместимость](../../../2014/getting-started/backward-compatibility.md)  
  
  