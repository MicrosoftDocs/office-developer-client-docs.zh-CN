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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339681"
---
# <a name="sending-messages-by-using-message-store-providers"></a>使用邮件存储提供程序发送邮件

**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序不需要支持传出邮件提交 (即, 客户端应用程序使用邮件存储提供程序发送邮件的功能)。 客户端应用程序需要在发送邮件时使用邮件存储, 因为邮件的数据必须存储在用户完成组合的时间与 MAPI 后台处理程序将邮件提供给的传输提供程序的时间之间的位置。提交到基础邮件系统。 如果您的邮件存储提供程序不支持传出邮件提交, 则不能将其用作默认邮件存储。
  
若要支持发送邮件, 您的邮件存储提供程序必须执行以下操作:
  
- 实现传出邮件队列。
    
- 支持在邮件存储区中创建的邮件对象上的[IMessage:: SubmitMessage](imessage-submitmessage.md)方法。 
    
- 支持特定于 MAPI 后台处理程序的**IMsgStore**方法: [IMsgStore:: FinishedMsg](imsgstore-finishedmsg.md)、 [IMsgStore:: GetOutgoingQueue](imsgstore-getoutgoingqueue.md)、 [IMsgStore:: NotifyNewMail](imsgstore-notifynewmail.md)和[IMsgStore:: SetLockState](imsgstore-setlockstate.md)。
    
在 MAPI 后台处理程序和客户端之间进行正确的互操作时, **SetLockState**方法是非常重要的。 当 MAPI 后台处理程序在传出邮件上调用**SetLockState**时, 邮件存储提供程序必须不允许客户端打开邮件。 如果客户端尝试打开 MAPI 后台处理程序锁定的邮件, 则邮件存储提供程序应返回 MAPI_E_NO_ACCESS。 如果 MAPI 后台处理程序锁定邮件, 则邮件的锁定状态不必是持久的, 以防存储关闭。 
  
无论 MAPI 后台处理程序是否已锁定传出邮件, 邮件存储提供程序都不应允许打开传出邮件队列中的邮件进行写入。 如果客户端使用 MAPI_MODIFY 标记对传出邮件调用[IMSgStore:: OpenEntry](imsgstore-openentry.md)方法, 则该调用应失败并返回 MAPI_E_SUBMITTED。 如果客户端应用程序在带有 MAPI_BEST_ACCESS 标志的传出邮件上调用**OpenEntry** , 则邮件存储提供程序应允许对邮件进行只读访问。 
  
当 MAPI 后台处理程序处理邮件时, 邮件存储提供程序会将邮件的**PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) 属性设置为 SUBMITFLAG_LOCKED。 SUBMITFLAG_LOCKED 值指示 MAPI 后台处理程序已锁定邮件的独占使用。 当邮件需要由传输提供程序注册的一个或多个预处理器函数需要进行预处理时, 将设置**PR_SUBMIT_FLAGS**、SUBMITFLAG_PREPROCESS 的其他值。
  
以下过程介绍邮件存储、传输和 MAPI 后台处理程序如何交互, 以便将邮件从客户端发送给一个或多个收件人。 
  
客户端应用程序调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法。 在**SubmitMessage**中, 邮件存储提供程序执行以下操作:
  
1. 调用[IMAPISupport::P reparesubmit](imapisupport-preparesubmit.md)。 如果 MAPI 返回错误, 则邮件存储提供程序会将该错误返回给客户端。
    
2. 设置邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的 MSGFLAG_SUBMIT 位。
    
3. 确保在 "收件人" 表中有一个**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性的列, 并将其设置为 FALSE, 以指示没有传输尚未承担发送邮件的责任。
    
4. 设置**PR_CLIENT_SUBMIT_TIME** ([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性中的源的日期和时间。
    
5. 调用[IMAPISupport:: ExpandRecips](imapisupport-expandrecips.md)执行以下操作: 
    
    1. 展开所有个人通讯组列表和自定义收件人, 并将所有更改的显示名称替换为其原始名称。
        
    2. 删除重复的名称。
        
    3. 检查是否有任何必需的预处理, 如果需要预处理, 请设置 NEEDS_PREPROCESSING 标志和**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性, 该属性是为 MAPI 保留的。 
        
    4. 如果邮件存储区与传输紧密结合, 并且无法处理所有收件人, 请设置 NEEDS_SPOOLER 标志。 
    
6. 如果设置了 NEEDS_PREPROCESSING 消息标志, 则执行以下任务:
    
    1. 将邮件放入传出队列中, 并在**PR_SUBMIT_FLAGS**属性中设置 SUBMITFLAG_PREPROCESS 位。 
        
    2. 通知 MAPI 后台处理程序队列已更改。
        
    3. 将控制返回给客户端, 并在 MAPI 后台处理程序中继续进行邮件流。 MAPI 后台处理程序执行以下任务: 
    
       1. 通过调用[IMsgStore:: SetLockState](imsgstore-setlockstate.md)锁定邮件。
            
       2. 通过以注册顺序调用所有预处理函数来执行所需的预处理。 传输提供程序调用[IMAPISupport:: RegisterPreprocessor](imapisupport-registerpreprocessor.md)以注册预处理函数。 
            
       3. 对打开的邮件调用[IMessage:: SubmitMessage](imessage-submitmessage.md) , 以指示已完成预处理的邮件存储区。 
    
如果没有任何预处理, 或者存在预处理和 MAPI 假脱机程序 (称为**SubmitMessage**), 则邮件存储提供程序将在客户端进程中执行以下操作: 
  
- 如果邮件存储区与传输紧密耦合且从 IMAPISupport 返回了 NEEDS_SPOOLER 标志, 则执行以下任务[:: ExpandRecips](imapisupport-expandrecips.md):
    
   - 处理它可以处理的任何收件人。
    
   - 将其处理的所有收件人的**PR_RESPONSIBILITY**属性设置为 TRUE。 
    
   - 如果所有收件人都已知此紧密结合的存储和传输, 则执行以下任务: 
    
     - 调用[IMAPISupport:: CompleteMsg](imapisupport-completemsg.md)如果邮件是经过预处理的或邮件存储区提供程序希望 MAPI 后台处理程序完成邮件处理。 邮件流继续使用 MAPI 后台处理程序。 
    
     - 如果邮件未经过预处理或者邮件存储区提供程序不希望 MAPI 后台处理程序完成邮件处理, 则执行以下任务:
    
       1. 将邮件复制到由**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性中的条目标识符标识的文件夹 (如果已设置)。
            
       2. 如果**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性已设置为 TRUE, 则删除该邮件。
            
       3. 如果邮件被锁定, 则解除锁定。
            
       4. 返回到客户端。 邮件流已完成。
    
  - 如果邮件经过预处理或提供程序希望 MAPI 后台处理程序完成邮件处理, 则执行以下任务:
    
    1. 调用[IMAPISupport:: CompleteMsg](imapisupport-completemsg.md)。 
          
    2. 继续使用 MAPI 后台处理程序的邮件流。 有关详细信息, 请参阅[发送邮件: MAPI 后台处理程序任务](sending-messages-mapi-spooler-tasks.md)。
    
  - 如果邮件未经过预处理或者提供程序不希望后台打印程序完成邮件处理, 则执行以下任务:
    
    1. 将邮件复制到由**PR_SENTMAIL_ENTRYID**属性中的条目标识符标识的文件夹 (如果已设置)。 
        
    2. 如果**PR_DELETE_AFTER_SUBMIT**属性已设置为 TRUE, 则删除该邮件。 
        
    3. 如果邮件被锁定, 则解除锁定。 
        
    4. 返回到调用方。 邮件流已完成。
    
- 如果邮件存储不与传输紧密相连, 并且不是所有收件人都知道邮件存储, 或者设置了 NEEDS_SPOOLER 标志, 则执行以下任务:
    
  1. 将邮件放入传出队列, 而不在**PR_SUBMIT_FLAGS**属性中设置 SUBMITFLAG_PREPROCESS 位。 
    
  2. 通知 MAPI 后台处理程序传出队列已通过生成表通知进行了更改。 
    
  3. 返回到客户端, 邮件流将继续处理由 MAPI 后台处理程序执行的一组任务。
    
## <a name="see-also"></a>另请参阅

- [邮件存储区功能](message-store-features.md)

