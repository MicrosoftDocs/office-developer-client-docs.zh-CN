---
title: 发送邮件消息存储提供程序任务
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: acbfd3ae-bfdc-4103-bed2-6bcf7b9c448c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8bfa5709dede4a9501d261e0f495acbc0894b470
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778742"
---
# <a name="sending-messages-message-store-provider-tasks"></a>发送邮件：邮件存储区提供程序任务

**适用于**： Outlook 
  
消息存储提供程序获取与消息客户端呼叫消息的[IMessage::SubmitMessage](imessage-submitmessage.md)方法时发送过程涉及。 如果多个邮件发送，消息存储库必须向他们发送与客户端用于其**SubmitMessage**呼叫的顺序相同。 
  
消息存储提供程序确定涉及 MAPI 后台处理程序。 如果未紧密耦合的消息存储提供程序，邮件需要预处理，或紧密耦合的存储和传输无法处理的所有收件人，必须涉及 MAPI 后台处理程序。 
  
以下过程介绍发送消息的消息存储提供程序所需的任务。 
  
**在 IMessage::SubmitMessage 消息存储提供程序**：
  
1. 如果邮件具有其**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置 MSGFLAG_RESEND 标志，并返回到客户端的任何错误，请调用[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md) 。 **PrepareSubmit**检查邮件的收件人列表中的每个收件人的**PR_RECIPIENT_TYPE** ([PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。
    
   - 如果设置了 MAPI_SUBMITTED 标志，指示收件人没有收到原始邮件， **PrepareSubmit**清除标志并将**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。 
    
   - 如果未设置 MAPI_SUBMITTED 标志，指示收件人未收到原始消息， **PrepareSubmit** **PR_RECIPIENT_TYPE**属性更改为 MAPI_P1 和将**PR_RESPONSIBILITY**属性设置为 TRUE 而返回到客户端**PrepareSubmit**生成任何错误。 
    
2. 消息的**PR_MESSAGE_FLAGS**属性中设置 MSGFLAG_SUBMIT 标志。 
    
3. 确保有是**PR_RESPONSIBILITY**收件人表中的列，并将它设置为 FALSE，以指示任何传输具有尚未假定负责传输消息。 
    
4. 设置日期和时间发起的**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性中。
    
5. 调用[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)到： 
    
   - 展开所有个人通讯组列表和自定义收件人并将所有更改的显示名称替换其原始名称。
   - 删除重复的名称。
   - 检查任何所需的预处理，并预处理是必需的如果设置 NEEDS_PREPROCESSING 标志和**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性，供 MAPI 的属性。 
   - 如果与传输紧密耦合的消息存储，它无法处理的所有收件人，则设置 NEEDS_SPOOLER 标志。 
    
6. 如果设置了 NEEDS_PREPROCESSING 邮件标志，请执行以下任务：
    
   - 与**PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) 属性中设置的 SUBMITFLAG_PREPROCESS 位置于传出队列消息。
   - 通知队列已更改 MAPI 后台处理程序。
   - 返回控件添加到客户端，并在 MAPI 后台处理程序的邮件流继续。 
   - MAPI 后台处理程序执行以下任务：
     - 通过调用 IMsgStore::SetLockState 锁定邮件。 
     - 执行所需的预处理通过调用的所有注册的顺序预处理函数。 传输提供程序调用 IMAPISupport::RegisterPreprocessor 注册预处理函数。 
     - 调用 IMessage::SubmitMessage 打开消息以指示消息存储到预处理已完成。

<br/>

如果没有没有预处理，并且当 MAPI 后台处理程序调用**SubmitMessage**是否存在预处理，客户端过程中会发生以下两个步骤。 

**消息存储提供程序**：

1. 如果消息存储紧密耦合到传输和从[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)返回 NEEDS_SPOOLER 标志，请执行以下任务：
    
   - 处理它可以处理任何收件人。
   - 为它处理任何收件人将**PR_RESPONSIBILITY**属性设置为 TRUE。 
   - 如果此紧密耦合的存储和传输到已知所有收件人，请执行以下任务：
     - 如果已预处理邮件或消息存储提供程序希望 MAPI 后台处理程序完成消息处理建议，以便消息可以调用挂接，调用 IMAPISupport::CompleteMsg。 邮件流继续 MAPI 后台处理程序，如下面的过程中所述。  
     - 如果已不预处理邮件或消息存储提供程序不需要 MAPI 后台处理程序完成消息处理，请执行以下任务：
       - 如果由 PR_SENTMAIL_ENTRYID (PidTagSentMailEntryId) 属性中的项标识符标识的文件夹的邮件设置的副本。
       - 如果 PR_DELETE_AFTER_SUBMIT (PidTagDeleteAfterSubmit) 属性已设置为 TRUE，则删除邮件。
       - 如果它已被锁定，解除锁定邮件。
       - 返回到客户端。 邮件流已完成。 
   
2. 如果传输不紧密耦合的消息存储，并非所有收件人已已知的消息存储库，或者 NEEDS_SPOOLER 标志设置，请执行以下任务：
    
   - 邮件未**PR_SUBMIT_FLAGS**属性中设置 SUBMITFLAG_PREPROCESS 位置于传出队列中。 
   - 通知传出队列已更改的生成表通知 MAPI 后台处理程序。 
   - 返回到客户端和邮件流继续执行一组由 MAPI 后台处理程序执行的任务。
    
当一条消息是由 MAPI 后台处理程序时，消息存储提供程序将消息的**PR_SUBMIT_FLAGS**属性设置 SUBMITFLAG_LOCKED。 SUBMITFLAG_LOCKED 标志指示 MAPI 后台处理程序已锁定以供其专用的消息。 当邮件需要预处理由传输提供程序注册的一个或多个预处理器函数设置**PR_SUBMIT_FLAGS，** SUBMITFLAG_PREPROCESS 的其他值。 
  

