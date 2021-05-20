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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437418"
---
# <a name="finding-sent-or-saved-messages"></a>查找已发送或已保存的邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
 **查找已保存或发送的所有传出邮件**
  
1. 调用 [IMsgStore：：CompareEntryIDs](imsgstore-compareentryids.md) 将包含已发送邮件的文件夹与包含传入邮件的文件夹进行比较。 
    
2. 将  _lpEntryID1_ 参数设置为指向 **PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) ，将  _lpEntryID2_ 参数设置为指向 **PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md)) 。
    
请注意，如果在邮件发送后删除邮件或将任何已发送的邮件移动到另一个文件夹，此策略将不起作用。 
  
如果在检查传入邮件时注意到传输提供程序通常设置的属性缺失，您可以假定该邮件从未由传输提供程序处理过。 这些属性包括：
  
- **PR_RECEIVED_BY** 属性 
    
- **PR_MESSAGE_DOWNLOAD_TIME (** [PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md)) 
    
- **PR_TRANSPORT_MESSAGE_HEADERS (** [PidTagTransportMessageHeaders)](pidtagtransportmessageheaders-canonical-property.md)
    
- **PR_MESSAGE_TO_ME (** [PidTagMessageToMe)](pidtagmessagetome-canonical-property.md)
    
- **PR_MESSAGE_CC_ME (** [PidTagMessageCcMe)](pidtagmessageccme-canonical-property.md)
    
- **PR_MESSAGE_RECIP_ME (** [PidTagMessageRecipientMe)](pidtagmessagerecipientme-canonical-property.md)
    

