---
title: 传出队列表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 070377ca-ba9e-42ef-ac6b-ff7548b5ccf5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4bf935f58fb20460bbf6baf4b1434be1f3ab8156
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348501"
---
# <a name="outgoing-queue-tables"></a>传出队列表

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
传出队列表包含有关邮件存储区的所有传出邮件的信息。 邮件存储提供程序实现要使用的 MAPI 后台处理程序的传出队列表。 不支持发送或接收邮件的存储无需实现此表。 
  
若要访问传出队列表, MAPI 后台处理程序将调用[IMsgStore:: GetOutgoingQueue](imsgstore-getoutgoingqueue.md)方法。 
  
要求按照客户端应用程序发送的顺序, 对邮件进行预处理并将其提交到传输提供程序。 MAPI 后台处理程序旨在按提交时间的升序顺序接受邮件存储区中的邮件。 由于此要求, 在传出队列表中出现一些邮件之前可能会有一些延迟。 
  
邮件存储区应允许对传出的队列表进行排序, 以便 MAPI 后台处理程序可以按提交时间对邮件进行排序, 或者默认的排序顺序应为 "按升序提交时间"。 
  
当队列的内容发生更改时, 传出队列表必须发送通知。
  
以下属性组成出站队列表中所需的列集:
  
|||
|:-----|:-----|
|**PR_CLIENT_SUBMIT_TIME**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md))  <br/> |**PR_DISPLAY_BCC**([PidTagDisplayBcc](pidtagdisplaybcc-canonical-property.md))  <br/> |
|**PR_DISPLAY_CC**([PidTagDisplayCc](pidtagdisplaycc-canonical-property.md))  <br/> |**PR_DISPLAY_TO**([PidTagDisplayTo](pidtagdisplayto-canonical-property.md))  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |**PR_MESSAGE_FLAGS**([PidTagMessageFlags](pidtagmessageflags-canonical-property.md))  <br/> |
|**PR_MESSAGE_SIZE**([PidTagMessageSize](pidtagmessagesize-canonical-property.md))  <br/> |**PR_PRIORITY**([PidTagPriority](pidtagpriority-canonical-property.md))  <br/> |
|**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))  <br/> |**PR_SUBJECT**([PidTagSubject](pidtagsubject-canonical-property.md))  <br/> |
|**PR_SUBMIT_FLAGS**([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md))  <br/> | <br/> |
   
有关如何使用传出队列表的详细信息, 请参阅[使用邮件存储提供程序发送邮件](sending-messages-by-using-message-store-providers.md)。
  
## <a name="see-also"></a>另请参阅



[MAPI 表](mapi-tables.md)

