---
title: 传出队列表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 070377ca-ba9e-42ef-ac6b-ff7548b5ccf5
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 10890c1fe430ddbc45c16908df3ac340284c9f18
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776567"
---
# <a name="outgoing-queue-tables"></a>传出队列表

  
  
**适用于**： Outlook 
  
传出的队列表包含有关邮件存储区的所有传出邮件的信息。 消息存储提供程序实现 MAPI 后台处理程序使用的传出队列的表。 存储区不支持发送或接收的消息不需要实现此表。 
  
若要访问传出队列表，MAPI 后台处理程序调用[IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)方法。 
  
没有邮件预处理，如它们发送的客户端应用程序提交到传输提供程序的顺序的要求。 MAPI 后台处理程序旨在接受来自提交时间的升序顺序的消息存储的邮件。 由于此要求，可能会有一些延迟之前传出队列表中显示的某些消息。 
  
消息存储也应允许传出队列表进行排序，以便 MAPI 后台处理程序可以由提交时间排序邮件或默认的排序顺序应为按升序排序提交时间。 
  
队列的内容更改时，必须将传出队列表发送通知。
  
以下属性构成传出队列表中所需的列：
  
|||
|:-----|:-----|
|**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))  <br/> |**PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))  <br/> |
|**PR_DISPLAY_CC**([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))  <br/> |**仅包含显示名称**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |
|**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))  <br/> |**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))  <br/> |
|**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |
|**PR_SUBMIT_FLAGS**([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md))  <br/> | <br/> |
   
有关如何使用传出队列表的详细信息，请参阅[通过使用消息存储提供程序发送的邮件](sending-messages-by-using-message-store-providers.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

