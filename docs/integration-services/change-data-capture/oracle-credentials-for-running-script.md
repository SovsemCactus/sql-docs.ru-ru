---
title: Учетные данные Oracle для выполнения скрипта | Документы Майкрософт
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4a301cb0-2f5b-41ba-81bf-46b41d07f137
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 9aa748fff6c0986290267815b90b43fd8fecb6b1
ms.sourcegitcommit: 58158eda0aa0d7f87f9d958ae349a14c0ba8a209
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "71294653"
---
# <a name="oracle-credentials-for-running-script"></a>Учетные данные Oracle для выполнения скрипта

[!INCLUDE[ssis-appliesto](../../includes/ssis-appliesto-ssvrpluslinux-asdb-asdw-xxx.md)]


  Чтобы запустить скрипт дополнительного журналирования Oracle из консоли конструктора CDC Oracle, программа запрашивает учетные данные пользователя Oracle, запускающего скрипт. Чтобы запустить этот скрипт, пользователь Oracle должен иметь разрешение ALTER TABLE для всех таблиц, которые будут отслеживаться, а также разрешение SELECT на представление DBA_LOG_GROUPS.  
  
## <a name="task-list"></a>Список задач  
 Введите в этом диалоговом окне следующие данные:  
  
 **Аутентификация**  
  
 Выберите один из следующих вариантов:  
  
-   **Проверка подлинности Windows**. Выберите этот параметр, чтобы использовать учетные данные текущего пользователя Windows. Этот параметр можно использовать только в том случае, если в базе данных Oracle настроено использование проверки подлинности Windows.  
  
-   **Проверка подлинности Oracle**. Если выбран этот вариант, то нужно будет ввести **Имя пользователя** и **Пароль** пользователя в исходной базе данных Oracle, с которой устанавливается соединение.  
  
## <a name="see-also"></a>См. также:  
 [How to Manage a CDC Instance](../../integration-services/change-data-capture/how-to-manage-a-cdc-instance.md)   
 [Обзор и создание скриптов дополнительного журналирования](../../integration-services/change-data-capture/review-and-generate-supplemental-logging-scripts.md)  
  
  
