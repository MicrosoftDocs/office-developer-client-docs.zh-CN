---
title: 查找已发送或保存的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 6b6714a5-7f36-4a72-9a2a-0d7fdf0e21b7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5a2e4f4b248cb8eefd5ee37c0c90d5ef9c0d0cac
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565016"
---
# <a name="finding-sent-or-saved-messages"></a>查找已发送或保存的邮件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
 **若要找到已保存或发送的所有传出邮件**
  
1. 调用[IMsgStore::CompareEntryIDs](imsgstore-compareentryids.md)进行比较的文件夹，包含与包含您的传入邮件的文件夹已发送的邮件。 
    
2. 设置以指向**PR_IPM_SENTMAIL_ENTRYID** ([PidTagIpmSentMailEntryId](pidtagipmsentmailentryid-canonical-property.md)) _lpEntryID1_参数和_lpEntryID2_参数以指向**PR_PARENT_ENTRYID** ([PidTagParentEntryId](pidtagparententryid-canonical-property.md))。
    
请注意，如果它们发送或已移动已发送任何的邮件到另一个文件夹中后，也可以删除邮件，此策略将无法工作。 
  
如果在检查传入消息您注意到丢失了通常设置由传输提供程序的属性，可以假定该消息已从不处理由传输提供程序。 这些属性包括：
  
- **PR_RECEIVED_BY**属性 
    
- **PR_MESSAGE_DOWNLOAD_TIME**([PidTagMessageDownloadTime](pidtagmessagedownloadtime-canonical-property.md))
    
- **PR_TRANSPORT_MESSAGE_HEADERS**([PidTagTransportMessageHeaders](pidtagtransportmessageheaders-canonical-property.md))
    
- **PR_MESSAGE_TO_ME**([PidTagMessageToMe](pidtagmessagetome-canonical-property.md))
    
- **PR_MESSAGE_CC_ME**([PidTagMessageCcMe](pidtagmessageccme-canonical-property.md))
    
- **PR_MESSAGE_RECIP_ME**([PidTagMessageRecipientMe](pidtagmessagerecipientme-canonical-property.md))
    

