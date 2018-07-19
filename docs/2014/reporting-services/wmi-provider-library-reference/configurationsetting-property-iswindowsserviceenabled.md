---
title: Свойство IsWindowsServiceEnabled (WMI MSReportServer_ConfigurationSetting) | Документы Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.suite: ''
ms.technology:
- reporting-services-native
ms.tgt_pltfrm: ''
ms.topic: conceptual
api_name:
- IsWindowsServiceEnabled
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- IsWindowsServiceEnabled property
ms.assetid: b1b75d72-6220-43fe-abfb-f967f3972d00
caps.latest.revision: 18
author: markingmyname
ms.author: maghan
manager: craigg
ms.openlocfilehash: 8fb3667bea39842d8a3e1acad4da8d25c6fe4bc9
ms.sourcegitcommit: c18fadce27f330e1d4f36549414e5c84ba2f46c2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2018
ms.locfileid: "37222684"
---
# <a name="iswindowsserviceenabled-property-wmi-msreportserverconfigurationsetting"></a>Свойство IsWindowsServiceEnabled (WMI MSReportServer_ConfigurationSetting)
  Указывает, включена ли служба Windows сервера отчетов. Только для чтения.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Public Dim IsWindowsServiceEnabled As Boolean  
```  
  
```csharp  
public boolean IsWindowsServiceEnabled;  
```  
  
## <a name="property-values"></a>Значения свойств  
 **Логическое** значение только для чтения. Значение `true` показывает, что служба Windows сервера отчетов включена.  
  
## <a name="example-code"></a>Пример кода  
 [Класс MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a>Требования  
 **Пространство имен:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Элементы MSReportServer_ConfigurationSetting](msreportserver-configurationsetting-members.md)  
  
  