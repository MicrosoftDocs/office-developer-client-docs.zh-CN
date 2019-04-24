---
title: 发送邮件邮件存储区提供程序任务
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: acbfd3ae-bfdc-4103-bed2-6bcf7b9c448c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b65113e59b236b1f13596627a8669ae458f76369
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32338428"
---
# <a name="sending-messages-message-store-provider-tasks"></a>发送邮件: 邮件存储提供程序任务

**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端调用邮件的[IMessage:: SubmitMessage](imessage-submitmessage.md)方法时, 邮件存储提供程序将涉及邮件发送过程。 如果要发送多封邮件, 邮件存储必须按照客户端用于其**SubmitMessage**呼叫的相同顺序发送它们。 
  
邮件存储区提供程序确定是否涉及 MAPI 后台处理程序。 如果邮件存储区提供程序未紧密结合, 则邮件需要进行预处理, 或者紧耦合的存储和传输无法处理所有收件人, 必须参与 MAPI 后台处理程序。 
  
下面的过程介绍了邮件存储提供程序发送邮件所需的任务。 
  
**在 IMessage:: SubmitMessage 中, 邮件存储区提供程序**:
  
1. 调用[IMAPISupport::P reparesubmit](imapisupport-preparesubmit.md)如果邮件在其**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置了 MSGFLAG_RESEND 标志, 并将任何错误返回到客户端。 **PrepareSubmit**检查邮件的收件人列表中每个收件人的**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。
    
   - 如果设置了 MAPI_SUBMITTED 标志, 指示收件人未收到原始邮件, 则**PrepareSubmit**将清除该标志并将**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。 
    
   - 如果未设置 MAPI_SUBMITTED 标志, 则指示收件人确实收到原始的 " **PrepareSubmit** ", 则会将**PR_RECIPIENT_TYPE**属性更改为 MAPI_P1, 并将**PR_RESPONSIBILITY**属性设置为 TRUE, 并返回由**PrepareSubmit**生成的任何错误到客户端。 
    
2. 在邮件的**PR_MESSAGE_FLAGS**属性中设置 MSGFLAG_SUBMIT 标志。 
    
3. 确保在 "收件人" 表中有一个**PR_RESPONSIBILITY**列, 并将其设置为 FALSE, 以指示没有传输具有用于传输邮件的假定责任。 
    
4. 设置**PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性中的源的日期和时间。
    
5. 调用[IMAPISupport:: ExpandRecips](imapisupport-expandrecips.md) to: 
    
   - 展开所有个人通讯组列表和自定义收件人, 并将所有更改的显示名称替换为其原始名称。
   - 删除重复的名称。
   - 检查是否有任何必需的预处理, 如果需要进行预处理, 请设置 NEEDS_PREPROCESSING 标志和**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性 (为 MAPI 保留的属性)。 
   - 如果邮件存储区与传输紧密结合, 并且无法处理所有收件人, 请设置 NEEDS_SPOOLER 标志。 
    
6. 如果设置了 NEEDS_PREPROCESSING 消息标志, 则执行以下任务:
    
   - 将邮件放入传出队列中, 并在**PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) 属性中设置 SUBMITFLAG_PREPROCESS 位。
   - 通知 MAPI 后台处理程序队列已更改。
   - 将控制返回给客户端, 并在 MAPI 后台处理程序中继续进行邮件流。 
   - MAPI 后台处理程序执行以下任务:
     - 通过调用 IMsgStore:: SetLockState 锁定邮件。 
     - 通过以注册顺序调用所有预处理函数来执行所需的预处理。 传输提供程序调用 IMAPISupport:: RegisterPreprocessor 以注册预处理函数。 
     - 对打开的邮件调用 IMessage:: SubmitMessage, 以指示已完成预处理的邮件存储区。

<br/>

如果没有任何预处理, 则在客户端进程中执行以下两个步骤, 当 MAPI 后台处理程序调用**SubmitMessage**时, 如果有预处理。 

**邮件存储区提供程序**:

1. 如果邮件存储区与传输紧密耦合且从 IMAPISupport 返回了 NEEDS_SPOOLER 标志, 则执行以下任务[:: ExpandRecips](imapisupport-expandrecips.md):
    
   - 处理它可以处理的任何收件人。
   - 将其处理的所有收件人的**PR_RESPONSIBILITY**属性设置为 TRUE。 
   - 如果所有收件人都已知此紧密结合的存储和传输, 则执行以下任务:
     - 调用 IMAPISupport:: CompleteMsg 如果邮件是经过预处理的, 或者邮件存储区提供程序希望 MAPI 后台处理程序完成邮件处理, 以便可以调用邮件传递挂钩。 邮件流按照以下过程中所述继续使用 MAPI 后台处理程序。  
     - 如果邮件未经过预处理或者邮件存储区提供程序不希望 MAPI 后台处理程序完成邮件处理, 则执行以下任务:
       - 将邮件复制到由 PR_SENTMAIL_ENTRYID (PidTagSentMailEntryId) 属性中的条目标识符标识的文件夹 (如果已设置)。
       - 如果 PR_DELETE_AFTER_SUBMIT (PidTagDeleteAfterSubmit) 属性已设置为 TRUE, 则删除该邮件。
       - 如果邮件被锁定, 则解除锁定。
       - 返回到客户端。 邮件流已完成。 
   
2. 如果邮件存储不与传输紧密相连, 并且不是所有收件人都知道邮件存储, 或者设置了 NEEDS_SPOOLER 标志, 则执行以下任务:
    
   - 将邮件放入传出队列, 而不在**PR_SUBMIT_FLAGS**属性中设置 SUBMITFLAG_PREPROCESS 位。 
   - 通知 MAPI 后台处理程序传出队列已通过生成表通知进行了更改。 
   - 返回到客户端, 邮件流将继续处理由 MAPI 后台处理程序执行的一组任务。
    
当 MAPI 后台处理程序处理邮件时, 邮件存储提供程序会将邮件的**PR_SUBMIT_FLAGS**属性设置为 SUBMITFLAG_LOCKED。 SUBMITFLAG_LOCKED 标志指示 MAPI 后台处理程序已锁定邮件以供独占使用。 当邮件需要由传输提供程序注册的一个或多个预处理器函数需要进行预处理时, 将设置**PR_SUBMIT_FLAGS、** SUBMITFLAG_PREPROCESS 的其他值。 
  

