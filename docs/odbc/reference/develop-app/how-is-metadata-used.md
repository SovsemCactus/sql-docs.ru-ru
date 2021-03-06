---
title: Как используются метаданные? | Документы Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- result sets [ODBC], metadata
- metadata [ODBC]
ms.assetid: 70fb976c-9342-4edd-b066-1140696fd0fa
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: fbbba96fa2e99a2ccc0618f31e3b29e7d479f703
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81300174"
---
# <a name="how-is-metadata-used"></a>Как используются метаданные?
Метаданные требуются приложениям для большинства операций с результирующими наборами. Например, приложение использует тип данных столбца, чтобы определить, какую переменную привязывать к этому столбцу. Он использует длину в байтах символьного столбца, чтобы определить, сколько пространства требуется для отображения данных из этого столбца. Способ определения метаданных для столбца зависит от типа приложения.  
  
 Вертикальные приложения работают с предопределенными таблицами и выполняют предопределенные операции с этими таблицами. Так как метаданные результирующего набора для таких приложений определяются до того, как приложение записывается и контролируется разработчиком приложения, его можно жестко закодировать в приложение. Например, если столбец идентификатора заказа определен в источник данных как 4-байтовое целое число, приложение может всегда привязывать 4-байтовые целые числа к этому столбцу. Если метаданные жестко запрограммированы в приложении, изменения в используемых приложением таблицах обычно подразумевают изменения в коде приложения. Это редко бывает проблемой, так как подобные изменения обычно вносятся как часть нового выпуска приложения.  
  
 Как и в вертикальных приложениях, пользовательские приложения обычно работают с предопределенными таблицами и выполняют предопределенные операции с этими таблицами. Например, приложение может быть написано для перемещения данных между тремя разными источниками данных. данные, предназначенные для передачи, обычно называются при написании приложения. Поэтому в пользовательских приложениях также обычно задаются жестко запрограммированные метаданные.  
  
 Универсальные приложения, особенно те, которые поддерживают нерегламентированные запросы, практически никогда не узнают метаданные создаваемых результирующих наборов. Поэтому они должны обнаруживать метаданные во время выполнения с помощью функций **SQLNumResultCols**, **SQLDescribeCol**и **SQLColAttribute**, описанных в следующем разделе, [SQLDescribeCol и SQLColAttribute](../../../odbc/reference/develop-app/sqldescribecol-and-sqlcolattribute.md).  
  
 Все приложения, независимо от их типа, могут жестко кодировать метаданные для результирующих наборов, возвращаемых функциями каталога. Эти результирующие наборы определены в разделе справки данного руководства.
