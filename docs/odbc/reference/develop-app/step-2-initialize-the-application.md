---
title: Шаг 2. Инициализация приложения | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- initializing applications [ODBC]
- application process [ODBC], initializing applications
ms.assetid: 23a7a230-ae2c-4a5e-9760-d2e17f92c389
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 843155ba6b641ea26717e63af55c8774f963a800
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81288270"
---
# <a name="step-2-initialize-the-application"></a>Шаг 2. Инициализация приложения
Второй шаг — инициализация приложения, как показано на следующем рисунке. Именно то, что здесь делается, зависит от приложения.  
  
 ![Инициализация приложения ODBC](../../../odbc/reference/develop-app/media/pr12.gif "pr12")  
  
 На этом этапе часто используется **SQLGetInfo** для обнаружения возможностей драйвера. Дополнительные сведения см. [в разделе рассмотрение функций базы данных для использования](../../../odbc/reference/develop-app/considering-database-features-to-use.md).  
  
 Все приложения должны выделить маркер инструкции с помощью **функцию SQLAllocHandle**, и многие приложения устанавливают атрибуты инструкций, например тип курсора, с помощью **SQLSetStmtAttr**. Дополнительные сведения см. [в разделе Выделение маркера инструкции](../../../odbc/reference/develop-app/allocating-a-statement-handle-odbc.md) и [атрибутов инструкции](../../../odbc/reference/develop-app/statement-attributes.md).
