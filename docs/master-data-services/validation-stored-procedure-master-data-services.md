---
title: Проверка хранимых процедур
description: Узнайте, как использовать хранимую процедуру MDM. хранимую udpValidateModel для применения бизнес-правил ко всем элементам в версии модели в Master Data Services.
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: mds
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 332d3c86-4440-4f12-a6cb-ffbfbccde52c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: a00666051071791ddb0ab80648680269c66b4cff
ms.sourcegitcommit: 7d6eb09588ff3477cf39a8fd507d537a603bc60d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "84796465"
---
# <a name="validation-stored-procedure-master-data-services"></a>Проверка хранимых процедур (службы Master Data Services)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  В среде [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]проверьте версию на применение бизнес-правил ко всем элементам версии модели.  
  
 В этом разделе объясняется, как использовать хранимую процедуру **mdm.udpValidateModel** для проверки данных. Администратор веб-приложения [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] может проводить проверку в пользовательском интерфейсе. Дополнительные сведения см. в разделе [Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)](../master-data-services/validate-a-version-against-business-rules-master-data-services.md).  
  
> [!NOTE]  
>  При запуске проверки до завершения промежуточного процесса элементы, для которых этот процесс не был завершен, не будут проверены.  
  
## <a name="example"></a>Пример  
  
```  
DECLARE @ModelName nVarchar(50) = 'Customer'   
DECLARE @Model_id int   
DECLARE @UserName nvarchar(50)= 'DOMAIN\user_name'   
DECLARE @User_ID int   
DECLARE @Version_ID int   
  
SET @User_ID = (SELECT ID    
                 FROM mdm.tblUser u   
                 WHERE u.UserName = @UserName)   
SET @Model_ID = (SELECT Top 1 Model_ID   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_Name = @ModelName)   
SET @Version_ID = (SELECT MAX(ID)   
                 FROM mdm.viw_SYSTEM_SCHEMA_VERSION   
                 WHERE Model_ID = @Model_ID)  
  
EXECUTE mdm.udpValidateModel @User_ID, @Model_ID, @Version_ID, 1  
  
```  
  
## <a name="parameters"></a>Параметры  
 Параметры данной процедуры имеют следующие значения:  
  
|Параметр|Описание|  
|---------------|-----------------|  
|UserID|Идентификатор пользователя.|  
|Model_ID|Идентификатор модели.|  
|Version_ID|Идентификатор версии.|  
  
## <a name="see-also"></a>См. также:  
 [Обзор. Импорт данных из таблиц &#40;Master Data Services&#41;](../master-data-services/overview-importing-data-from-tables-master-data-services.md)   
 [Подтверждение исправления проблемы, обнаруженной при проверке на соответствие бизнес-правилам (службы Master Data Services)](../master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
  
