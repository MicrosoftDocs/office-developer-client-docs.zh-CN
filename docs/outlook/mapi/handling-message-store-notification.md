---
title: 处理消息存储通知
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3e0cc2f9-a88d-4cec-bef5-b60f2ec80f1c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 898f8b6ff3d0b0dd42a670596b54171f18b4a5e3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775056"
---
# <a name="handling-message-store-notification"></a>处理消息存储通知
  
**适用于**： Outlook 
  
若要注册的消息存储通知，调用[IMAPISession::Advise](imapisession-advise.md)或[IMsgStore::Advise](imsgstore-advise.md)方法，并指定_lpEntryID_参数的内容中的消息存储库、 文件夹或消息条目标识符。 消息存储提供程序支持对象和表格的通知。 是否注册与特定的消息存储对象、 介绍这些对象的文件夹层次结构和内容表个或两个对象和表取决于您希望查看，请执行操作，您发出的呼叫通知以及如何升级消息存储提供程序支持通知。 
  
因为 MAPI 允许灵活的提供程序如何支持通知，请注意，不会始终收到通知的相同类型在特定事件响应来自所有消息存储提供程序。 某些消息存储提供程序根本不支持通知。 确定要使用的消息存储是否支持通知，其**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中的 STORE_NOTIFY_OK 位的外观。
  
一端在多种消息存储提供程序支持通知是生成"丰富"的通知; 的提供程序这些提供程序发送的所有注册的描述性通知告知源。 在另一端是邮件支持有限的通知; 的存储提供程序这些提供商发送常规通知受限 advise 源数。 
  
例如，如果将邮件复制到文件夹与注册接收的这两个对象复制和移动通知对象，可能也可能不会收到复制对象通知。 收到它依赖：
  
- 调用要进行复制的方法。 这可能是[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)、 [IMAPIProp::CopyTo](imapiprop-copyto.md)或[IMAPIProp::CopyProps](imapiprop-copyprops.md)。
    
- 如何消息存储提供程序实现 copy 方法。
    
- 是否消息存储提供程序支持的文件夹对象复制通知。
    
由于有介绍了如何实现事件通知的消息不严格准则存储提供程序，客户端无法预想一致的行为。 MAPI 使建议如何消息存储提供程序实现事件通知和下表概括了这些建议。 读取表，如下所示： 中的第一列执行该操作后，希望接收通知的类型列出的第二列中，如果已注册第三列中列出的对象的类型。 例如，创建一个文件夹后，您将收到_fnevObjectCreated_通知，仅当您注册消息存储与_fnevObjectCreated_通知。 
  
|**Operation**|**事件类型**|**建议源**|
|:-----|:-----|:-----|
|创建一个文件夹  <br/> | _fnevObjectCreated_ <br/> |消息存储库  <br/> |
|删除文件夹  <br/> | _fnevObjectDeleted_ <br/> |消息存储已删除文件夹  <br/> |
|将文件夹从一个文件夹移到另一个  <br/> | _fnevObjectMoved_ <br/> |消息存储移动文件夹  <br/> |
|将文件夹从一个文件夹复制到另一个  <br/> | _fnevObjectCopied_ <br/> |消息存储和复制文件夹 （没有新的文件夹的副本发送_fnevObjectCreated_通知）  <br/> |
|在计算的文件夹属性 （**PR_SUBFOLDERS** ([PidTagSubfolders](pidtagsubfolders-canonical-property.md))、 **PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))、 **PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md)) 中更改  <br/> | _fnevObjectModified_ <br/> |消息存储 Changed 文件夹 （没有父文件夹的通知）  <br/> |
|创建邮件  <br/> | _fnevObjectCreated_ <br/> |消息存储库  <br/> |
|删除一条消息，更改导致父文件夹的**PR_CONTENT_COUNT**属性  <br/> | _fnevObjectDeleted_ <br/> |消息存储已删除邮件  <br/> |
|将一条消息从一个文件夹移至另一个  <br/> | _fnevObjectMoved_ <br/> |消息存储移动消息  <br/> |
|将一条消息从一个文件夹复制到另一个  <br/> | _fnevObjectCopied_ <br/> |消息存储库复制邮件 （没有_fnevObjectCreated_新副本的通知邮件）  <br/> |
|保存一条消息，更改导致父文件夹的**PR_CONTENT_COUNT**属性  <br/> | _fnevObjectCreated_ <br/> |保存唯一的第一个邮件存储  <br/> |
|保存一条消息  <br/> | _fnevObjectModified_ <br/> |保存后保存 Changed 邮件 （发送给父文件夹没有通知） 的第一个邮件存储  <br/> |
|完成搜索操作  <br/> | _fnevSearchComplete_ <br/> |消息存储搜索文件夹  <br/> |
|新的邮件  <br/> | _fnevNewMail_ <br/> |消息存储库  <br/> |
   
> [!NOTE]
> 当您收到对象修改通知时，请记住所指的**OnNotify**调用中_lpNotifications_参数[OBJECT_NOTIFICATION](object_notification.md)结构的属性标记数组部分可能，也可能不是 NULL。 消息存储提供程序不需要在此数组中插入属性信息和最不。 请确保您**OnNotify**方法可以处理_lpPropTagArray_指针为 NULL 的情况。 
  
对于大多数，如果不是所有对象通知，更新受影响的文件夹或文件夹的视图。
  

