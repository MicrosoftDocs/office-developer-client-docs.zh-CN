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
  
若要注册邮件存储通知，请调用 [IMAPISession：：Advise](imapisession-advise.md) 或 [IMsgStore：：Advise](imsgstore-advise.md) 方法，在  _lpEntryID_ 参数的内容中指定邮件存储、文件夹或邮件条目标识符。 邮件存储提供程序支持对象和表通知。 注册特定邮件存储对象、使用描述这些对象的文件夹层次结构和内容表，还是同时使用对象和表取决于预期看到的通知、您为执行的操作而进行调用以及邮件存储提供程序如何支持通知。 
  
由于 MAPI 允许提供程序支持通知的方式的灵活性，因此请注意，您不会始终收到同一类型的通知，以响应来自所有邮件存储提供程序的特定事件。 某些邮件存储提供程序完全不支持通知。 若要确定你使用的邮件存储是否支持通知，请在其 PR_STORE_SUPPORT_MASK ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 查找 STORE_NOTIFY_OK 位。 
  
支持通知的邮件存储提供程序的一端是生成"丰富"通知的提供程序;这些提供程序会发送所有已注册的建议源的描述性通知。 另一端是支持有限通知的邮件存储提供程序;这些提供程序发送有限数量的通知源的常规通知。 
  
例如，如果将邮件复制到已注册接收对象复制通知和对象移动通知的文件夹，则您可以接收对象复制的通知，也可以不接收。 是否收到它取决于：
  
- 您为执行复制而调用的方法。 这可以是 [IMAPIFolder：：CopyMessages](imapifolder-copymessages.md) [、IMAPIProp：：CopyTo](imapiprop-copyto.md)或 [IMAPIProp：：CopyProps](imapiprop-copyprops.md)。
    
- 邮件存储提供程序如何实现 copy 方法。
    
- 邮件存储提供程序是否支持文件夹上的对象复制通知。
    
因为没有严格的准则可描述如何为邮件存储提供程序实现事件通知，客户端无法期望一致的行为。 MAPI 对邮件存储提供程序如何实施事件通知提供了建议，下表概述了这些建议。 按如下方式阅读该表：在您执行第一列中的操作后，如果已使用第三列中列出的对象为类型注册，则预期会收到第二列中列出的类型的通知。 例如，创建文件夹后，只有在邮件存储中注册  _了 fnevObjectCreated_ 通知时，你才能收到  _fnevObjectCreated_ 通知。 
  
|**操作**|**事件类型**|**建议源**|
|:-----|:-----|:-----|
|创建文件夹  <br/> | _fnevObjectCreated_ <br/> |邮件存储  <br/> |
|删除文件夹  <br/> | _fnevObjectDeleted_ <br/> |邮件存储 已删除文件夹  <br/> |
|将文件夹从一个文件夹移动到另一个文件夹  <br/> | _fnevObjectMoved_ <br/> |邮件存储已移动文件夹  <br/> |
|将文件夹从一个文件夹复制到另一个文件夹  <br/> | _fnevObjectCopied_ <br/> |邮件存储和复制的文件夹 (没有为文件夹的新副本发送  _的 fnevObjectCreated_)   <br/> |
| ( PR_SUBFOLDERS ([PidTagSubfolders](pidtagsubfolders-canonical-property.md) **) 、PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md) **) 、PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md)) 中的计算文件夹属性更改  <br/> | _fnevObjectModified_ <br/> |邮件存储 更改 (没有通知到父文件夹)   <br/> |
|创建邮件  <br/> | _fnevObjectCreated_ <br/> |邮件存储  <br/> |
|删除邮件，导致父文件夹的 PR_CONTENT_COUNT **属性更改**  <br/> | _fnevObjectDeleted_ <br/> |邮件存储 已删除邮件  <br/> |
|将邮件从一个文件夹移动到另一个文件夹  <br/> | _fnevObjectMoved_ <br/> |邮件存储 已移动邮件  <br/> |
|将邮件从一个文件夹复制到另一个文件夹  <br/> | _fnevObjectCopied_ <br/> |邮件存储 已复制 (没有  _fnevObjectCreated_ 新邮件副本的通知)   <br/> |
|保存邮件，导致父文件夹的 PR_CONTENT_COUNT **属性更改**  <br/> | _fnevObjectCreated_ <br/> |仅在首次保存时存储邮件  <br/> |
|保存邮件  <br/> | _fnevObjectModified_ <br/> |第一次保存更改的邮件后保存的邮件存储 (没有通知到父文件夹)   <br/> |
|完成搜索操作  <br/> | _fnevSearchComplete_ <br/> |邮件存储搜索文件夹  <br/> |
|新邮件  <br/> | _fnevNewMail_ <br/> |邮件存储  <br/> |
   
> [!NOTE]
> 当您收到对象修改通知时，请记住 **OnNotify** 调用中的 _lpNotifications_ 参数指向 [的 OBJECT_NOTIFICATION](object_notification.md)结构的属性标记数组部分可能为 NULL，也可能不为 NULL。 邮件存储提供程序不需要在此数组中插入属性信息，大多数提供程序不需要。 确保 **OnNotify** 方法可以处理  _lpPropTagArray_ 指针为 NULL 的情况。 
  
对于大多数对象通知（如果不是所有对象通知）更新受影响文件夹的视图。
  

