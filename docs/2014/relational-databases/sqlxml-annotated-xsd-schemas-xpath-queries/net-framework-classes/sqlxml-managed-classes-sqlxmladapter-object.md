---
title: Объект Склксмладаптер (управляемые классы SQLXML) | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- void Update(DataSet ds) method
- SqlXmlAdapter object
- void Fill(DataSet ds) method
- SQLXML Managed Classes, SqlXmlAdapter object
- Managed Classes [SQLXML], SqlXmlAdapter object
ms.assetid: 0a16eddf-fc26-4d92-82d4-359b5fb905d5
author: rothja
ms.author: jroth
ms.openlocfilehash: f950ad2bd22fa84b5f62711ee4fd290ebab136bb
ms.sourcegitcommit: 57f1d15c67113bbadd40861b886d6929aacd3467
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "85015297"
---
# <a name="sqlxmladapter-object-sqlxml-managed-classes"></a>Объект SqlXmlAdapter (управляемые классы SQLXML)
  В этом объекте реализованы методы, облегчающие взаимодействие с набором данных в [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework. Рабочий пример см. в разделе [доступ к функциям SQLXML в среде .NET](accessing-sqlxml-functionality-in-the-net-environment.md).  
  
 Объект Склксмладаптер поддерживает следующие методы:  
  
 void Fill (набор данных DS)  
 Заполняет набор данных в .NET Framework XML-данными, полученными от [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].  
  
 пустое обновление (набор данных DS)  
 Применяет обновления к записям в [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] из данных, содержащихся в наборе данных.  
  
 Объект Склксмладаптер поддерживает следующие конструкторы:  
  
```  
public SqlXmlAdapter(SqlXmlCommand  cmd)   
  
public SqlXmlAdapter(  
                     string commandText,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                      )   
  
public SqlXmlAdapter(  
                     Stream commandStream,   
                     SqlXmlCommandType cmdType,   
                     string connectionString  
                     )   
```  
  
## <a name="see-also"></a>См. также:  
 [Объект SqlXmlCommand &#40;управляемые классы SQLXML&#41;](sqlxml-4-0-net-framework-support-managed-classes.md)   
 [Объект SqlXmlParameter &#40;управляемые классы SQLXML&#41;](sqlxml-managed-classes-sqlxmlparameter-object.md)  
  
  
