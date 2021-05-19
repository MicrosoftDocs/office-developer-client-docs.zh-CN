---
title: 发送邮件 MAPI 后台处理程序任务
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 81c65f21-03ba-43eb-a6d4-d311e660ac5c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 8a6730cca5c75a888afb5ff0a44f1e2a0a6465e6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420197"
---
# <a name="sending-messages-mapi-spooler-tasks"></a>发送邮件：MAPI 后台处理程序任务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当邮件存储未与传输提供程序紧密耦合、紧密耦合的存储和传输无法处理收件人以及邮件需要预处理时，MAPI 后台处理程序将参与邮件传输过程。
  
 **完成任何必要的预处理后，MAPI 后台处理程序将执行以下步骤：**
  
1. 如果邮件未锁定，则使用 [IMsgStore：：SetLockState](imsgstore-setlockstate.md) 方法锁定邮件。 
    
2. 让传输提供程序将邮件发送给其[PidTagResponsibility PR_RESPONSIBILITY (PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 设置为 FALSE 的所有收件人。  
    
3. 如果 **设置了 PR_PREPROCESS** (PidTagPreprocess) 属性，则调用相应的函数 ([RemovePreprocessInfo](removepreprocessinfo.md)) 以清除已添加到邮件中供预处理期间使用的其他信息 [](pidtagpreprocess-canonical-property.md)。 当传输提供程序注册其预处理器函数时指定此函数。 
    
4. 调用 [IMsgStore：：FinishedMsg](imsgstore-finishedmsg.md) 方法。 在 **FinishedMsg** 中，邮件存储提供程序：
    
  - 解锁邮件。
    
  - 如果邮件挂钩提供程序 [存在，:D IMAPISupport：:D oSentMail](imapisupport-dosentmail.md) 方法执行出站挂钩处理。 然后，它将邮件复制到 **由 PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性中的条目标识符标识的文件夹（如果未被邮件挂钩提供程序发送的邮件处理取代）。 最后，如果[PidTagDeleteAfterSubmit PR_DELETE_AFTER_SUBMIT (PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)属性) 设置为 TRUE，则删除邮件。  
    

