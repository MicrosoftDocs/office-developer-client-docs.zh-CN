---
title: 发送邮件邮件存储提供程序任务
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: acbfd3ae-bfdc-4103-bed2-6bcf7b9c448c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: de29707c7a257ea0e7ad658622d2a3054487f8b5
ms.sourcegitcommit: adcf409d56b6cb25be6117f09794defa41ad6c0f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2019
ms.locfileid: "37495304"
---
# <a name="sending-messages-message-store-provider-tasks"></a>发送邮件：邮件存储提供程序任务

**适用于**：Outlook 2013 | Outlook 2016 
  
当客户端调用邮件的 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法时，邮件存储提供程序会参与邮件发送过程。 如果要发送多个消息，邮件存储必须按照客户端用于 **其 SubmitMessage** 调用的相同顺序发送它们。 
  
邮件存储提供程序确定是否涉及 MAPI 后台处理程序。 如果邮件存储提供程序未紧密耦合，邮件需要预处理，或者紧密耦合的存储和传输无法处理所有收件人，则必须涉及 MAPI 后台处理程序。 
  
以下过程介绍邮件存储提供程序发送邮件所需的任务。 
  
**在 IMessage：：SubmitMessage 中，邮件存储提供程序：**
  
1. 如果邮件的 PR_MESSAGE_FLAGS ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中设置了 **MSGFLAG_RESEND** 标志，则调用 [IMAPISupport：:P repareSubmit，](imapisupport-preparesubmit.md)并返回客户端的任何错误。 **PrepareSubmit** 检查 **PR_RECIPIENT_TYPE (** 列表中每个收件人的 [PidTagRecipientType](pidtagrecipienttype-canonical-property.md)) 属性。
    
   - 如果设置了 MAPI_SUBMITTED 标志，指示收件人未收到原始邮件， **则 PrepareSubmit** 将清除该标志，将 **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性设置为 TRUE。 
    
   - 如果未设置 MAPI_SUBMITTED 标志，指示收件人确实收到原始邮件， **则 PrepareSubmit** 将 **PR_RECIPIENT_TYPE** 属性更改为 MAPI_P1，将 **PR_RESPONSIBILITY** 属性设置为 TRUE，并返回 **PrepareSubmit** 生成的任何错误到客户端。 
    
2. 在MSGFLAG_SUBMIT属性中 **设置PR_MESSAGE_FLAGS标记** 。 
    
3. 确保收件人表中有一PR_RESPONSIBILITY一列，并设置该列为 FALSE，以指示传输尚未承担传输邮件的责任。 
    
4. 使用[PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md) PR_CLIENT_SUBMIT_TIME (设置原始) 日期和时间。 
    
5. 调用 [IMAPISupport：：ExpandRecips](imapisupport-expandrecips.md) 以： 
    
   - 展开所有个人通讯组列表和自定义收件人，将所有更改的显示名称替换为其原始名称。
   - 删除重复的名称。
   - 检查所需的任何预处理，如果需要预处理，请设置 NEEDS_PREPROCESSING 标志和 **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性，这是为 MAPI 保留的属性。 
   - 如果NEEDS_SPOOLER与传输紧密结合，并且无法处理所有收件人，则设置此标记。 
    
6. 如果设置了邮件NEEDS_PREPROCESSING，则执行以下任务：
    
   - 将邮件放在传出队列中，SUBMITFLAG_PREPROCESS [PidTagSubmitFlags PR_SUBMIT_FLAGS (PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) 位。 
   - 通知 MAPI 后台处理程序队列已更改。
   - 将控制权返回给客户端，消息流将继续在 MAPI 后台处理程序中运行。 
   - MAPI 后台处理程序执行以下任务：
     - 通过调用 IMsgStore：：SetLockState 锁定邮件。 
     - 按注册顺序调用所有预处理函数，执行所需的预处理。 传输提供程序调用 IMAPISupport：：RegisterPreprocessor 以注册预处理函数。 
     - 对打开的邮件调用 IMessage：：SubmitMessage 以向邮件存储指示预处理已完成。

<br/>

如果没有预处理，则以下两个步骤发生在客户端进程中;如果已进行预处理，则 MAPI 后台处理程序调用 **SubmitMessage。** 

**邮件存储提供程序**：

1. 如果邮件存储与传输紧密耦合，并且从 [IMAPISupport：：ExpandRecips](imapisupport-expandrecips.md)返回 NEEDS_SPOOLER，则执行以下任务：
    
   - 处理它可以处理的任何收件人。
   - 将 **PR_RESPONSIBILITY** 处理的任何收件人的属性都为 TRUE。 
   - 如果已知此紧密耦合存储和传输的所有收件人，则执行以下任务：
     - 如果邮件已预处理，或者邮件存储提供程序希望 MAPI 后台处理程序完成建议的消息处理，以便可以调用消息挂钩，则调用 IMAPISupport：：CompleteMsg。 邮件流将继续处理 MAPI 后台处理程序，如以下过程所述。  
     - 如果未预处理邮件或邮件存储提供程序不希望 MAPI 后台处理程序完成邮件处理，则执行以下任务：
       - 将邮件复制到 PidTagSentMailEntryId 属性中的条目标识符PR_SENTMAIL_ENTRYID (PidTagSentMailEntryId) （如果已设置）。
       - 如果 PidTagDeleteAfterSubmit PR_DELETE_AFTER_SUBMIT (设置为 TRUE，) 删除邮件。
       - 如果邮件被锁定，则解锁邮件。
       - 返回到客户端。 邮件流已完成。 
   
2. 如果邮件存储未紧密耦合到传输中，并非所有收件人都已知邮件存储，或已设置 NEEDS_SPOOLER 标志，则执行以下任务：
    
   - 将邮件置于传出队列中，而不在 SUBMITFLAG_PREPROCESS 属性中设置 **PR_SUBMIT_FLAGS** 位。 
   - 通过生成表通知通知 MAPI 后台处理程序，通知传出队列已更改。 
   - 返回到客户端，邮件流将继续由 MAPI 后台处理程序执行一组任务。
    
当 MAPI 后台处理程序处理邮件时，邮件存储提供程序将邮件的 PR_SUBMIT_FLAGS **属性** SUBMITFLAG_LOCKED。 the SUBMITFLAG_LOCKED flag indicates that the MAPI spooler has locked the message for its exclusive use. 当邮件需要由传输PR_SUBMIT_FLAGS注册的一个或多个预处理器函数进行预处理时，将设置邮件的其他值（即 SUBMITFLAG_PREPROCESS）。 
  

