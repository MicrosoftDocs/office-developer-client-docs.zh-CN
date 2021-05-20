---
title: 使用邮件存储提供程序发送邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7632d784-00d8-48fd-a73b-73778efbef7f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b34714a230adb44417624d149d34ed6a14a2dfa5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437607"
---
# <a name="sending-messages-by-using-message-store-providers"></a>使用邮件存储提供程序发送邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序不需要支持传出邮件 (，即客户端应用程序能够使用邮件存储提供程序将邮件) 。 客户端应用程序在发送邮件时必须使用邮件存储，因为邮件数据必须存储在用户完成撰写邮件到 MAPI 后台处理程序将邮件提交给传输提供程序以提交到基础邮件系统之间的某位置。 如果邮件存储提供程序不支持传出邮件提交，则不能用作默认邮件存储。
  
若要支持发送邮件，邮件存储提供程序必须执行以下操作：
  
- 实现传出邮件队列。
    
- 对在 [邮件存储中创建的邮件对象支持 IMessage：：SubmitMessage](imessage-submitmessage.md) 方法。 
    
- 支持特定于 MAPI 后台处理程序的 **IMsgStore** 方法：IMsgStore：：FinishedMsg、IMsgStore：：GetOutgoingQueue、IMsgStore：：NotifyNewMail 和 [IMsgStore：：SetLockState](imsgstore-setlockstate.md)。 [](imsgstore-finishedmsg.md) [](imsgstore-getoutgoingqueue.md) [](imsgstore-notifynewmail.md)
    
**SetLockState** 方法对于 MAPI 后台处理程序和客户端之间的正确互操作非常重要。 当 MAPI 后台处理程序对传出邮件调用 **SetLockState** 时，邮件存储提供程序不得允许客户端打开该邮件。 如果客户端确实尝试打开 MAPI 后台处理程序锁定的邮件，则邮件存储提供程序应返回MAPI_E_NO_ACCESS。 当 MAPI 后台处理程序锁定邮件时，如果存储关闭，则邮件的锁定状态无需是永久性的。 
  
无论 MAPI 后台处理程序是否已锁定传出邮件，邮件存储提供程序都不应允许打开传出邮件队列中的邮件进行写入。 如果客户端对具有 MAPI_MODIFY 标志的传出邮件调用 [IMSgStore：：OpenEntry](imsgstore-openentry.md) 方法，则调用应失败并返回MAPI_E_SUBMITTED。 如果客户端应用程序对具有 MAPI_BEST_ACCESS 标志的传出邮件调用 **OpenEntry，** 则邮件存储提供程序应允许对邮件进行只读访问。 
  
当 MAPI 后台处理程序处理邮件时，邮件存储提供程序将邮件的 **PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) 属性SUBMITFLAG_LOCKED。 the SUBMITFLAG_LOCKED value indicates that the MAPI spooler has locked the message for its exclusive use. 当邮件需要由 **传输** PR_SUBMIT_FLAGS注册的一个或多个预处理器函数进行预处理时，将设置 PR_SUBMIT_FLAGS 的另一个值（即 SUBMITFLAG_PREPROCESS）。
  
以下过程介绍邮件存储、传输和 MAPI 后台处理程序如何交互以将邮件从客户端发送到一个或多个收件人。 
  
客户端应用程序调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法。 在 **SubmitMessage** 中，邮件存储提供程序执行以下操作：
  
1. 调用 [IMAPISupport：:P repareSubmit](imapisupport-preparesubmit.md)。 如果 MAPI 返回错误，邮件存储提供程序会向客户端返回该错误。
    
2. 设置MSGFLAG_SUBMIT [PidTagMessageFlags PR_MESSAGE_FLAGS (PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 中的位。 
    
3. 确保收件人表中存在 **PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性的列，并设置此属性为 FALSE 以指示尚未对传输邮件承担任何传输责任。
    
4. 使用[PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md) PR_CLIENT_SUBMIT_TIME (设置原始) 日期和时间。 
    
5. 调用 [IMAPISupport：：ExpandRecips](imapisupport-expandrecips.md) 以执行以下操作： 
    
    1. 展开所有个人通讯组列表和自定义收件人，将所有更改的显示名称替换为其原始名称。
        
    2. 删除重复的名称。
        
    3. 检查所需的任何预处理，如果需要预处理，请设置 NEEDS_PREPROCESSING 标志和 **PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性（为 MAPI 保留）。 
        
    4. 如果NEEDS_SPOOLER与传输紧密结合，并且无法处理所有收件人，则设置此标记。 
    
6. 如果设置了邮件NEEDS_PREPROCESSING，则执行以下任务：
    
    1. 将邮件放在传出队列中，SUBMITFLAG_PREPROCESS设置 PR_SUBMIT_FLAGS **位。** 
        
    2. 通知 MAPI 后台处理程序队列已更改。
        
    3. 将控制权返回给客户端，消息流将继续在 MAPI 后台处理程序中运行。 MAPI 后台处理程序执行以下任务： 
    
       1. 通过调用 [IMsgStore：：SetLockState 锁定邮件](imsgstore-setlockstate.md)。
            
       2. 按注册顺序调用所有预处理函数，执行所需的预处理。 传输提供程序调用 [IMAPISupport：：RegisterPreprocessor](imapisupport-registerpreprocessor.md) 以注册预处理函数。 
            
       3. 对 [打开的邮件调用 IMessage：：SubmitMessage](imessage-submitmessage.md) 以向邮件存储指示预处理已完成。 
    
如果没有预处理，或者存在预处理和名为 **SubmitMessage** 的 MAPI 后台处理程序，邮件存储提供程序将在客户端进程中执行以下操作： 
  
- 如果邮件存储与传输紧密耦合，并且从 [IMAPISupport：：ExpandRecips](imapisupport-expandrecips.md)返回 NEEDS_SPOOLER，则执行以下任务：
    
   - 处理它可以处理的任何收件人。
    
   - 将 **PR_RESPONSIBILITY** 处理的任何收件人的属性都为 TRUE。 
    
   - 如果已知此紧密耦合存储和传输的所有收件人，则执行以下任务： 
    
     - 如果邮件已预处理或邮件存储提供程序希望 MAPI 后台处理程序完成消息处理，则调用[IMAPISupport：：CompleteMsg。](imapisupport-completemsg.md) 邮件流将继续使用 MAPI 后台处理程序。 
    
     - 如果未预处理邮件或邮件存储提供程序不希望 MAPI 后台处理程序完成邮件处理，则执行以下任务：
    
       1. 将邮件复制到[PidTagSentMailEntryId PR_SENTMAIL_ENTRYID (PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 标识的文件夹（如果已设置）。 
            
       2. 如果[PidTagDeleteAfterSubmit PR_DELETE_AFTER_SUBMIT (PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)属性) 设置为 TRUE，则删除邮件。 
            
       3. 如果邮件被锁定，则解锁邮件。
            
       4. 返回到客户端。 邮件流已完成。
    
  - 如果邮件已预处理或提供程序希望 MAPI 后台处理程序完成邮件处理，则执行以下任务：
    
    1. 调用 [IMAPISupport：：CompleteMsg](imapisupport-completemsg.md)。 
          
    2. 使用 MAPI 后台处理程序继续消息流。 有关详细信息，请参阅发送邮件 [：MAPI 后台处理程序任务](sending-messages-mapi-spooler-tasks.md)。
    
  - 如果未预处理邮件或提供程序不希望后台处理程序完成邮件处理，则执行以下任务：
    
    1. 将邮件复制到由 PR_SENTMAIL_ENTRYID 属性中的条目 **标识符标识** 的文件夹（如果已设置）。 
        
    2. 如果邮件的 PR_DELETE_AFTER_SUBMIT **属性已** 设置为 TRUE，则删除该邮件。 
        
    3. 如果邮件被锁定，则解锁邮件。 
        
    4. 返回给调用方。 邮件流已完成。
    
- 如果邮件存储未紧密耦合到传输中，并非所有收件人都已知邮件存储，或已设置 NEEDS_SPOOLER 标志，则执行以下任务：
    
  1. 将邮件置于传出队列中，而不在 SUBMITFLAG_PREPROCESS 属性中设置 **PR_SUBMIT_FLAGS** 位。 
    
  2. 通过生成表通知通知 MAPI 后台处理程序，通知传出队列已更改。 
    
  3. 返回到客户端，邮件流将继续由 MAPI 后台处理程序执行一组任务。
    
## <a name="see-also"></a>另请参阅

- [邮件存储功能](message-store-features.md)

