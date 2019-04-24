---
title: 查找已发送或已保存的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b6714a5-7f36-4a72-9a2a-0d7fdf0e21b7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 86373fae2753df66d4456cc0fc00f8b289977650
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337126"
---
# <a name="finding-sent-or-saved-messages"></a>查找已发送或已保存的邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **查找已保存或发送的所有待发邮件**
  
1. 调用[IMsgStore:: CompareEntryIDs](imsgstore-compareentryids.md)将包含已发送邮件的文件夹与包含传入邮件的文件夹进行比较。 
    
2. 将_lpEntryID1_参数设置为指向**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)), 并将_lpEntryID2_参数设置为指向**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md))。
    
请注意, 如果在发送邮件后删除邮件或将任何已发送的邮件移到另一个文件夹, 则此策略将不起作用。 
  
如果检查传入邮件, 请注意, 通常由传输提供程序设置的属性丢失, 可以假定传输提供程序从不处理该邮件。 这些属性包括：
  
- **PR_RECEIVED_BY**属性 
    
- **PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))
    
- **PR_TRANSPORT_MESSAGE_HEADERS**([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))
    
- **PR_MESSAGE_TO_ME**([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))
    
- **PR_MESSAGE_CC_ME**([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))
    
- **PR_MESSAGE_RECIP_ME**([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))
    

