---
title: 处理邮件存储通知
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3e0cc2f9-a88d-4cec-bef5-b60f2ec80f1c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d370603dc7cfc015fe7b2757d1cf0525b3092c5e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428023"
---
# <a name="handling-message-store-notification"></a>处理邮件存储通知
  
**适用于**：Outlook 2013 | Outlook 2016 
  
若要注册邮件存储通知, 请调用[IMAPISession:: advise](imapisession-advise.md)或[IMsgStore:: advise](imsgstore-advise.md)方法, 并在_lpEntryID_参数的内容中指定邮件存储、文件夹或邮件条目标识符。 邮件存储提供程序支持对象通知和表通知。 是否注册特定的邮件存储对象, 以及描述这些对象的文件夹层次结构和内容表, 以及对象和表都取决于您期望看到的通知、您执行操作所需的调用以及如何邮件存储区提供程序支持通知。 
  
由于 MAPI 允许在提供程序支持通知方面有灵活性, 因此请注意, 您不会在响应来自所有邮件存储提供程序的特定事件时始终收到相同类型的通知。 某些邮件存储提供程序根本不支持通知。 若要确定您使用的邮件存储是否支持通知, 请在其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中查找 STORE_NOTIFY_OK 位。
  
支持通知的邮件存储提供程序种类的一端是生成 "富" 通知的提供程序;这些提供程序发送所有已注册的通知源的描述性通知。 另一端是支持有限通知的邮件存储提供程序;这些提供程序发送有关有限数量的通知源的常规通知。 
  
例如, 如果您将邮件复制到已注册为接收对象的已复制和对象移动通知的文件夹, 则可能会收到对象复制的通知。 您是否收到它取决于:
  
- 您调用的用于执行复制的方法。 这可能是[IMAPIFolder:: CopyMessages](imapifolder-copymessages.md)、 [IMAPIProp:: CopyTo](imapiprop-copyto.md)或[IMAPIProp:: CopyProps](imapiprop-copyprops.md)。
    
- 邮件存储区提供程序如何实现 copy 方法。
    
- 邮件存储区提供程序是否支持对文件夹所复制的对象进行通知。
    
由于没有说明如何为邮件存储提供程序实现事件通知的严格准则, 因此客户端无法预期一致的行为。 MAPI 确实提出了有关邮件存储提供程序如何实现事件通知的建议, 下表概述了这些建议。 按如下所示读取表: 在第一列中执行操作后, 如果已为该类型注册了第三列中列出的对象, 则预计会收到第二列中列出的类型的通知。 例如, 创建文件夹后, 只有在使用邮件存储区注册了_fnevObjectCreated_通知时, 才会收到_fnevObjectCreated_通知。 
  
|**操作**|**事件类型**|**建议源**|
|:-----|:-----|:-----|
|创建文件夹  <br/> | _fnevObjectCreated_ <br/> |邮件存储  <br/> |
|删除文件夹  <br/> | _fnevObjectDeleted_ <br/> |邮件存储已删除文件夹  <br/> |
|将文件夹从一个文件夹移动到另一个文件夹  <br/> | _fnevObjectMoved_ <br/> |邮件存储移动文件夹  <br/> |
|将文件夹从一个文件夹复制到另一个文件夹  <br/> | _fnevObjectCopied_ <br/> |邮件存储和复制的文件夹 (没有为文件夹的新副本发送的_fnevObjectCreated_通知)  <br/> |
|计算的文件夹属性中的更改 (**PR_SUBFOLDERS** ([PidTagSubfolders](pidtagsubfolders-canonical-property.md)) **、PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))、 **PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md))  <br/> | _fnevObjectModified_ <br/> |邮件存储已更改文件夹 (无通知给父文件夹)  <br/> |
|创建邮件  <br/> | _fnevObjectCreated_ <br/> |邮件存储  <br/> |
|删除邮件, 导致父文件夹的**PR_CONTENT_COUNT**属性发生更改  <br/> | _fnevObjectDeleted_ <br/> |邮件存储已删除邮件  <br/> |
|将邮件从一个文件夹移动到另一个文件夹  <br/> | _fnevObjectMoved_ <br/> |邮件存储移动邮件  <br/> |
|将邮件从一个文件夹复制到另一个文件夹  <br/> | _fnevObjectCopied_ <br/> |邮件存储复制的邮件 (没有邮件的新副本的_fnevObjectCreated_通知)  <br/> |
|保存一封邮件, 导致父文件夹的**PR_CONTENT_COUNT**属性发生更改  <br/> | _fnevObjectCreated_ <br/> |仅在首次保存时的邮件存储  <br/> |
|保存邮件  <br/> | _fnevObjectModified_ <br/> |在第一次保存已更改的邮件后保存 (未通知给父文件夹) 后的邮件存储  <br/> |
|完成搜索操作  <br/> | _fnevSearchComplete_ <br/> |邮件存储搜索文件夹  <br/> |
|新邮件  <br/> | _fnevNewMail_ <br/> |邮件存储  <br/> |
   
> [!NOTE]
> 当您收到对象修改通知时, 请记住, **OnNotify**调用中_lpNotifications_参数指向的[OBJECT_NOTIFICATION](object_notification.md)结构的属性标记数组部分可能是, 也可能不是 NULL。 邮件存储提供程序不需要在此数组中插入属性信息, 而大多数不需要。 请确保您的**OnNotify**方法可以处理_lpPropTagArray_指针为 NULL 的情况。 
  
大多数情况下, 如果并不是所有对象通知, 请更新受影响的一个或多个文件夹的视图。
  

