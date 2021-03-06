---
title: Открытие, разблокировка, переименование и удаление проекта качества данных
description: Узнайте, как открыть, разблокировать, переименовать и удалить проект служб DQS с помощью SQL Server Data Quality Services.
ms.custom: seo-lt-2019
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: data-quality-services
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql13.dqs.dqproject.opendqproject.f1
helpviewer_keywords:
- data quality project,delete
- data quality project,rename
- data quality project,unlock
- data quality project,open
ms.assetid: de8a2b04-4673-4beb-b4cf-96a28cdf3a93
author: swinarko
ms.author: sawinark
ms.openlocfilehash: 666e7fdbc080af3ed259dae978bd782e437eae2e
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "75557811"
---
# <a name="open-unlock-rename-and-delete-a-data-quality-project---data-quality-services-dqs"></a>Открытие, разблокировка, переименование и удаление проекта качества данных — службы Data Quality Services (DQS)

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  В этом разделе описывается управление проектом служб DQS с помощью [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] : такие действия, как открытие, разблокирование, переименование и удаление проекта.  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> Ограничения  
  
-   Нельзя открыть заблокированный проект, созданный другим пользователем.  
  
-   Невозможно разблокировать, переименовать или удалить проект служб DQS, созданный другим пользователем.  
  
-   Нельзя удалить заблокированный проект служб DQS. Чтобы проект можно было удалить, его необходимо сначала разблокировать.  
  
-   Вы можете разблокировать только тот проект служб DQS, который сами создали.  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> Предварительные требования  
 Для управления должен быть в наличии хотя бы один проект служб DQS.  
  
###  <a name="security"></a><a name="Security"></a> безопасность  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 Для управления проектом служб DQS необходимо иметь роль dqs_kb_editor или dqs_kb_operator в базе данных DQS_MAIN.  
  
##  <a name="open-a-data-quality-project"></a><a name="Open"></a> Открытие проекта служб DQS  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)][Запустите приложение Data Quality Client](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  На [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] главном экране щелкните **Open Data Quality Project (открыть проект**служб DQS). Появится экран **Открытие проекта** .  
  
     Также вы можете напрямую открыть проект служб DQS, щелкнув его в области **Последние проекты служб DQS** .  
  
3.  На экране **Открытие проекта** щелчком выберите нужный проект служб DQS и нажмите кнопку **Далее**.  
  
4.  Проект служб DQS откроется в том же состоянии, в каком он был закрыт в последний раз. Проект служб DQS имеет следующие состояния:  
  
    -   Для действия **Очистка** проект качества данных может иметь следующие состояния: **Очистка-Map**, **Очистка — Очистка**, **Очистка — управление и просмотр результатов**, а также **Очистка и экспорт**.  
  
    -   Для действия **сопоставления** проект качества данных может иметь следующие состояния: **Match-Map**, **Match-Match**, **Match-выживания**и **Match-Export**.  
  
##  <a name="unlock-a-data-quality-project"></a><a name="Unlock"></a> Разблокирование проекта служб DQS  
 При создании проекта служб DQS он находится в заблокированном состоянии для предотвращения использования или изменения другими пользователями. Необходимо разблокировать проект служб DQS после завершения работы, если требуется, чтобы с этим проектом могли работать другие пользователи. Для заблокированных проектов отображается символ блокировки.  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)][Запустите приложение Data Quality Client](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  На [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] главном экране щелкните **Open Data Quality Project (открыть проект**служб DQS). Появится экран **Открытие проекта** .  
  
3.  На экране **Открытие проекта** щелкните правой кнопкой мыши созданный вами заблокированный проект служб DQS, затем выберите **Разблокировать** в контекстном меню. Рядом с именем проекта отобразится зеленый флажок, означающий, что проект разблокирован.  
  
##  <a name="rename-a-data-quality-project"></a><a name="Rename"></a> Переименование проекта служб DQS  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)][Запустите приложение Data Quality Client](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  На [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] главном экране щелкните **Open Data Quality Project (открыть проект**служб DQS). Появится экран **Открытие проекта** .  
  
3.  На экране **Открытие проекта** щелкните правой кнопкой мыши созданный вами проект служб DQS, затем выберите **Переименовать** в контекстном меню.  
  
4.  Имя проекта служб DQS станет доступным для редактирования в столбце **Имя** . Введите новое имя и нажмите клавишу «Ввод».  
  
##  <a name="delete-a-data-quality-project"></a><a name="Delete"></a> Удаление проекта служб DQS  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)][Запустите приложение Data Quality Client](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  На [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] главном экране щелкните **Open Data Quality Project (открыть проект**служб DQS). Появится экран **Открытие проекта** .  
  
3.  На экране **Открытие проекта** щелкните правой кнопкой мыши созданный вами разблокированный проект служб DQS, затем выберите **Удалить** в контекстном меню.  
  
4.  Появится окно подтверждения. Нажмите кнопку **Да**.  
  
  
