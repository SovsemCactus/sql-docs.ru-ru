---
title: Функция SQLSetConnectOption | Документация Майкрософт
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
apiname:
- SQLSetConnectOption
apilocation:
- sqlsrv32.dll
apitype: dllExport
f1_keywords:
- SQLSetConnectOption
helpviewer_keywords:
- SQLSetConnectOption function [ODBC]
ms.assetid: 8cd2c2a2-25c8-4aff-951c-b593bbfc90ad
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 263b15cb75fb5c0c7c1d7aa630a8da171b9765a7
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "81301599"
---
# <a name="sqlsetconnectoption-function"></a>Функция SQLSetConnectOption
**Соответствия**  
 Введенная версия: соответствие стандартам ODBC 1,0: не рекомендуется  
  
 **Сводка**  
 В ODBC 3 *. x*функция ODBC 2,0 **SQLSetConnectOption** была заменена на **SQLSetConnectAttr**. Дополнительные сведения см. в разделе [SQLSetConnectAttr](../../../odbc/reference/syntax/sqlsetconnectattr-function.md).  
  
> [!NOTE]
>  Дополнительные сведения о том, как диспетчер драйверов сопоставляет эту функцию, когда приложение ODBC 2 *. x* работает с драйвером ODBC 3 *. x* , см. в разделе [сопоставление устаревших функций](../../../odbc/reference/appendixes/mapping-deprecated-functions.md)".  
  
## <a name="remarks"></a>Remarks  
 Если приложение будет работать в 64-разрядной операционной системе, см. [сведения о ODBC 64-bit](../../../odbc/reference/odbc-64-bit-information.md).  
  
> [!NOTE]  
>  Атрибут SQL_ASYNC_DBC_FUNCTION_ENABLE, введенный в ODBC 3,8, не поддерживается **SQLSetConnectOption**. Приложения, использующие асинхронную операцию с маркером соединения, должны использовать **SQLSetConnectAttr**.  
  
## <a name="see-also"></a>См. также:  
 [Справочник по API ODBC](../../../odbc/reference/syntax/odbc-api-reference.md)   
 [Файлы заголовков ODBC](../../../odbc/reference/install/odbc-header-files.md)
