---
title: Экспорт домена в файл .dqs
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: data-quality-services
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: eba10d3d-b5c4-447b-8a30-fa07996cb28e
author: swinarko
ms.author: sawinark
ms.openlocfilehash: 518b393b296425c1aaf54229a8a843576c6a628a
ms.sourcegitcommit: e042272a38fb646df05152c676e5cbeae3f9cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "75251616"
---
# <a name="export-a-domain-to-a-dqs-file"></a>Экспорт домена в файл .dqs

[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md-winonly](../includes/appliesto-ss-xxxx-xxxx-xxx-md-winonly.md)]

  В этом разделе описывается экспорт домена в файл .dqs в службах [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS). Экспортировать в файл данных можно домен или всю базу знаний. Сведения об экспорте базы знаний см. в разделе [Экспорт базы знаний в файл DQS](../data-quality-services/export-a-knowledge-base-to-a-dqs-file.md).  
  
 Экспорт домена из одной базы знаний в файл данных DQS и последующий импорт в другую базу знаний упрощает процесс создания знаний и экономит время. Благодаря этому можно использовать домен и его набор знаний совместно с другими пользователями.  
  
 Можно экспортировать один одиночный домен или один составной домен. Файл DQS содержащий один домен, включает все сведения о домене, включая свойства домена, значения и сведения о правилах, кроме сведений о добавленных ссылочных данных. Файл DQS, содержащий составной домен, содержит все данные составного домена, в том числе все данные для доменов, которые входят в составной домен, а также свойства, связи и правила составного домена, кроме сведений о ссылочных данных. После импорта файла DQS следует повторно добавить домен или составной домен в соответствующие службы ссылочных данных. Экспортируются как опубликованные, так и неопубликованные данные.  
  
 Файл данных DQS, созданный в процессе экспорта, зашифровывается, его просмотр становится невозможным.  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> Перед началом  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> Предварительные требования  
 Чтобы экспортировать домен в файл данных .dqs, необходимо предварительно создать и выбрать одиночный домен или составной домен, содержащий несколько одиночных доменов. Файл DQS не требуется, он будет создан в процессе экспорта.  
  
###  <a name="security"></a><a name="Security"></a> безопасность  
  
####  <a name="permissions"></a><a name="Permissions"></a> Permissions  
 Для экспорта домена в файл данных .dqs необходимы роли dqs_kb_editor или dqs_administrator в базе данных DQS_MAIN.  
  
##  <a name="export-a-domain-to-a-dqs-file"></a><a name="Export"></a>Экспорт домена в файл DQS  
 Можно выполнить экспорт с любой страницы «Управление доменами». Команда экспорта доступна как в виде элемента управления в пользовательском интерфейсе, так и в виде команды контекстного меню на панели «Список доменов».  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)][Запустите приложение Data Quality Client](../data-quality-services/run-the-data-quality-client-application.md).  
  
2.  На главном экране клиента [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] откройте базу знаний в разделе управления доменами.  
  
3.  На странице **Управление доменами** (с любой выбранной вкладкой) выберите одиночный или составной домен в списке **Домен** .  
  
4.  Щелкните значок **Экспортировать данные базы знаний** над списком доменов, затем щелкните **Экспортировать домен**. Также можно щелкнуть правой кнопкой мыши домен в списке **Домен** , указать пункт **Экспорт**, а затем выбрать команду **Экспортировать домен**.  
  
5.  В диалоговом окне **Экспорт в файл данных** перейдите в папку, где нужно сохранить файл, присвойте файлу имя или оставьте имя по умолчанию, оставьте **Файлы данных DQS (\*.dqs)** в качестве **Типа файла** и нажмите кнопку **Сохранить**.  
  
6.  В диалоговом окне **Экспортировать домен** убедитесь, что в строке состояния диалогового окна отобразилось сообщение о завершении экспорта. Нажмите кнопку **ОК**.  
  
##  <a name="follow-up-after-exporting-a-domain-to-a-dqs-file"></a><a name="FollowUp"></a>Дальнейшие действия. После экспорта домена в файл DQS  
 После экспорта домена в файл DQS можно импортировать домен в другую базу знаний.  
  
  
