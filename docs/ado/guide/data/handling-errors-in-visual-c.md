---
title: Обработка ошибок в Visual C++ | Документация Майкрософт
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- errors [ADO], Visual C++
- Visual C++ error handling [ADO]
ms.assetid: b7576f07-020a-45f7-9e79-b5756f33f7ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 1628522a6ef1c9498ea26e987070ee9f3a873d19
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2020
ms.locfileid: "82758850"
---
# <a name="handling-errors-in-visual-c"></a>Обработка ошибок в Visual C++
В COM большинство операций возвращают код возврата HRESULT, указывающий, успешно ли завершилась функция. Директива #import создает код-оболочку вокруг каждого "необработанного" метода или свойства и проверяет возвращенное значение HRESULT. Если HRESULT указывает на сбой, код программы-оболочки вызывает ошибку COM путем вызова _com_issue_errorex () с кодом возврата HRESULT в качестве аргумента. Объекты ошибок COM могут быть перехвачены в блок **try-catch** . (Для повышения эффективности перехватите ссылку на объект _com_error.)  
  
 Помните, что это ошибки ADO: они вызваны сбоем операции ADO. Ошибки, возвращенные базовым поставщиком, отображаются как объекты **ошибок** в коллекции **ошибок** объекта **Connection** .  
  
 Директива #import создает только подпрограммы обработки ошибок для методов и свойств, объявленных в ADO. dll. Тем не менее можно воспользоваться тем же механизмом обработки ошибок, создав собственный макрос проверки ошибок или встроенную функцию. Примеры см. в разделе Visual C++ расширений®.
