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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339674"
---
# <a name="sending-messages-mapi-spooler-tasks"></a>发送邮件: MAPI 后台处理程序任务

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当邮件存储区与传输提供程序不紧密结合时, 如果紧耦合存储和传输无法处理收件人, 以及当邮件需要预处理时, MAPI 后台处理程序将包含在邮件传输过程中。
  
 **在进行任何必要的预处理后, MAPI 后台处理程序将执行以下步骤:**
  
1. 如果邮件未锁定, 则使用[IMsgStore:: SetLockState](imsgstore-setlockstate.md)方法锁定邮件。 
    
2. 使传输提供程序将邮件发送给将其**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 FALSE 的所有收件人。 
    
3. 调用适当的函数 ([RemovePreprocessInfo](removepreprocessinfo.md)) 来清除添加到邮件中以供在预处理过程中使用的任何其他信息 (如果已设置**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性)。 此函数在传输提供程序注册其预处理器函数时指定。 
    
4. 调用[IMsgStore:: FinishedMsg](imsgstore-finishedmsg.md)方法。 在**FinishedMsg**中, 邮件存储区提供程序:
    
  - 解除对邮件的锁定。
    
  - 调用[IMAPISupport::D osentmail](imapisupport-dosentmail.md)方法来执行出站挂钩处理 (如果存在消息传递挂钩提供程序)。 然后, 它将邮件复制到由**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性中的条目标识符标识的文件夹中 (如果不是由邮件传递挂钩提供程序的已发送邮件处理取代的)。 最后, 如果**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性设置为 TRUE, 则删除该邮件。 
    

