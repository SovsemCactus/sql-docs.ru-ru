---
title: Редактор задачи «Отправка почты» (страница «почта») | Документация Майкрософт
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sendmailtask.mail.f1
helpviewer_keywords:
- Send Mail Task Editor
ms.assetid: adb385d5-ef24-4d18-b9ea-b39e00a7075e
author: janinezhang
ms.author: janinez
ms.openlocfilehash: ee2b7992065e31bc6ef57de9b22444cf2da1f963
ms.sourcegitcommit: f71e523da72019de81a8bd5a0394a62f7f76ea20
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84963490"
---
# <a name="send-mail-task-editor-mail-page"></a>Редактор задачи «Отправка почты» (страница «Почта»)
  Страница **Почта** диалогового окна **Редактор задачи «Отправка почты»** служит для определения получателей, типа и приоритета сообщения. К сообщению можно также прикрепить файлы. Текстом сообщения может быть введенная строка, соединение с файлом, содержащим текст, или имя переменной, содержащей текст.  
  
 Дополнительные сведения об этой задаче см. в разделе [Send Mail Task](control-flow/send-mail-task.md).  
  
## <a name="options"></a>Варианты  
 **SMTPConnection**  
 Выберите Диспетчер соединений SMTP в списке или щелкните, **\<New connection...>** чтобы создать новый диспетчер соединений.  
  
> [!IMPORTANT]  
>  Диспетчер SMTP-соединений поддерживает только анонимную проверку подлинности и проверку подлинности Windows. Обычная проверка подлинности не поддерживается.  
  
 **См. также:** [Диспетчер соединений SMTP](connection-manager/smtp-connection-manager.md)  
  
 **От**  
 Задайте адрес электронной почты отправителя.  
  
 **Чтобы**  
 Укажите адреса электронной почты получателей, разделенные точкой с запятой.  
  
 **Кому**  
 Задайте адреса электронной почты получателей, которые также получают копии сообщения. Разделяйте адреса точками с запятой.  
  
 **СК**  
 Задайте адреса электронной почты получателей, которые получают скрытые копии сообщения. Разделяйте адреса точками с запятой.  
  
 **Тема**  
 Укажите тему электронного сообщения.  
  
 **MessageSourceType**  
 Выберите тип источника сообщения. Это свойство имеет параметры, указанные в следующей таблице.  
  
|Применение|Описание|  
|-----------|-----------------|  
|**Прямой ввод**|Задание источника текста сообщения. При выборе этого значения отображается динамический параметр **MessageSource**.|  
|**Соединение с файлом**|Задание в качестве источника файла, содержащего текст сообщения. При выборе этого значения отображается динамический параметр **MessageSource**.|  
|**Переменная**|В качестве источника указывается переменная, содержащая текст сообщения. При выборе этого значения отображается динамический параметр **MessageSource**.|  
  
 **Priority**  
 Задается приоритет сообщения.  
  
 **Вложения**  
 Укажите имена вложений для электронного сообщения, разделенные символом вертикальной черты (|).  
  
> [!NOTE]  
>  Длина строк «Кому», «Копия» и «СК» ограничена 256 символами в соответствии со стандартами Интернета.  
  
## <a name="messagesourcetype-dynamic-options"></a>Динамические параметры MessageSourceType  
  
### <a name="messagesourcetype--direct-input"></a>MessageSourceType = Прямой ввод  
 **MessageSource**  
 Введите текст сообщения или нажмите кнопку обзора (...), а затем введите сообщение в диалоговом окне **Источник сообщения**.  
  
### <a name="messagesourcetype--file-connection"></a>MessageSourceType = Соединение с файлом  
 **MessageSource**  
 Выберите Диспетчер подключения файлов в списке или щелкните \<**New connection...**> , чтобы создать новый диспетчер соединений.  
  
 **См. также:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md)  
  
### <a name="messagesourcetype--variable"></a>MessageSourceType = Переменная  
 **MessageSource**  
 Выберите переменную из списка или щелкните \<**New variable...**> , чтобы создать новую переменную.  
  
 **См. также:** [Integration Services &#40;переменные&#41; SSIS](integration-services-ssis-variables.md), [Добавить переменную](../../2014/integration-services/add-variable.md)  
  
## <a name="see-also"></a>См. также:  
 [Справочник по ошибкам и сообщениям Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md)   
 [Редактор задачи «Отправка почты» &#40;страница «Общие»&#41;](general-page-of-integration-services-designers-options.md)   
 [Страница «Выражения»](expressions/expressions-page.md)  
  
  
