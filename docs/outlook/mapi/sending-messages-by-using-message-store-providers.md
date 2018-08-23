---
title: 使用邮件的发送消息存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7632d784-00d8-48fd-a73b-73778efbef7f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e29b909e90d2767bcf1bb9382a46e6f2c1cd9f2a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569797"
---
# <a name="sending-messages-by-using-message-store-providers"></a>使用邮件的发送消息存储提供程序

**适用于**： Outlook 2013 |Outlook 2016 
  
消息存储提供程序不需要支持传出邮件提交 （即，客户端应用程序使用的消息存储提供程序来发送邮件的功能）。 客户端应用程序需要使用的消息存储时发送邮件，因为必须消息的数据存储这二者之间用户已完成的时间撰写及其 MAPI 后台处理程序提供邮件到传输提供程序的时间提交到基础邮件系统。 如果您的消息存储提供程序不支持传出邮件提交，它不能用作默认邮件存储区。
  
若要支持发送消息，消息存储提供程序必须执行以下操作：
  
- 实现传出消息队列。
    
- 消息存储中创建的消息对象支持[IMessage::SubmitMessage](imessage-submitmessage.md)方法。 
    
- 支持特定于 MAPI 后台处理程序的**IMsgStore**方法： [IMsgStore::FinishedMsg](imsgstore-finishedmsg.md)、 [IMsgStore::GetOutgoingQueue](imsgstore-getoutgoingqueue.md)、 [IMsgStore::NotifyNewMail](imsgstore-notifynewmail.md)和[IMsgStore::SetLockState](imsgstore-setlockstate.md)。
    
**SetLockState**方法很重要的 MAPI 后台处理程序和客户端之间的正确进行互操作。 当 MAPI 后台处理程序调用**SetLockState**传出邮件时，消息存储提供程序必须不允许客户端打开该邮件。 如果客户端执行尝试打开一条消息，MAPI 后台处理程序被锁定，消息存储提供程序应返回 MAPI_E_NO_ACCESS。 不必是永久性的邮件锁定 MAPI 后台打印程序时存储已关闭的情况下一条消息的锁定的状态。 
  
无论是否 MAPI 后台处理程序已锁定的传出邮件，消息存储提供程序不应在传出的消息队列，要打开以进行编写允许一条消息。 如果客户端在带 MAPI_MODIFY 标志的传出邮件上调用[IMSgStore::OpenEntry](imsgstore-openentry.md)方法，呼叫应失败并返回 MAPI_E_SUBMITTED。 如果客户端应用程序调用带 MAPI_BEST_ACCESS 标志的传出邮件上**OpenEntry** ，消息存储提供程序应允许到邮件的只读访问权限。 
  
当一条消息是由 MAPI 后台处理程序时，消息存储提供程序将消息的**PR_SUBMIT_FLAGS** ([PidTagSubmitFlags](pidtagsubmitflags-canonical-property.md)) 属性设置 SUBMITFLAG_LOCKED。 SUBMITFLAG_LOCKED 值指示 MAPI 后台处理程序已锁定以供其专用的消息。 当邮件需要预处理由传输提供程序注册的一个或多个预处理器函数设置**PR_SUBMIT_FLAGS**，SUBMITFLAG_PREPROCESS 的其他值。
  
下面的过程介绍如何消息存储、 传输和 MAPI 后台处理程序交互作用以便从客户端向一个或多个收件人发送一条消息。 
  
客户端应用程序调用[IMessage::SubmitMessage](imessage-submitmessage.md)方法。 在**SubmitMessage**，消息存储提供程序执行以下操作：
  
1. 调用[IMAPISupport::PrepareSubmit](imapisupport-preparesubmit.md)。 如果 MAPI 返回一个错误，消息存储提供程序将返回到客户端的错误。
    
2. 设置消息的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中位 MSGFLAG_SUBMIT。
    
3. 确保有是**PR_RESPONSIBILITY** ([PidTagResponsibility](pidtagresponsibility-canonical-property.md)) 属性收件人表中的列，并将其设置为 FALSE 以指示的任何传输尚未假定负责传输消息。
    
4. 设置日期和时间发起的**期限**([PidTagClientSubmitTime](pidtagclientsubmittime-canonical-property.md)) 属性中。
    
5. 调用[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)执行下列操作： 
    
    1. 展开所有个人通讯组列表和自定义收件人并将所有更改的显示名称替换其原始名称。
        
    2. 删除重复的名称。
        
    3. 检查任何所需预处理，然后，如果预处理是必需的设置 NEEDS_PREPROCESSING 标志和供 MAPI 的**PR_PREPROCESS** ([PidTagPreprocess](pidtagpreprocess-canonical-property.md)) 属性。 
        
    4. 如果与传输紧密耦合的消息存储，它无法处理的所有收件人，则设置 NEEDS_SPOOLER 标志。 
    
6. 如果设置了 NEEDS_PREPROCESSING 邮件标志，请执行以下任务：
    
    1. 与**PR_SUBMIT_FLAGS**属性中设置的 SUBMITFLAG_PREPROCESS 位置于传出队列消息。 
        
    2. 通知队列已更改 MAPI 后台处理程序。
        
    3. 返回控件添加到客户端，并在 MAPI 后台处理程序的邮件流继续。 MAPI 后台处理程序执行以下任务： 
    
       1. 通过调用[IMsgStore::SetLockState](imsgstore-setlockstate.md)锁定邮件。
            
       2. 执行所需的预处理通过调用的所有注册的顺序预处理函数。 传输提供程序调用[IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md)注册预处理函数。 
            
       3. 在打开的邮件，以指示邮件[IMessage::SubmitMessage](imessage-submitmessage.md)存储该预处理的呼叫即告完成。 
    
如果没有任何预处理，或出现预处理和 MAPI 后台处理程序调用**SubmitMessage**，消息存储提供程序执行以下客户端过程中： 
  
- 如果消息存储紧密耦合到传输和从[IMAPISupport::ExpandRecips](imapisupport-expandrecips.md)返回 NEEDS_SPOOLER 标志，请执行以下任务：
    
   - 处理它可以处理任何收件人。
    
   - 为它处理任何收件人将**PR_RESPONSIBILITY**属性设置为 TRUE。 
    
   - 如果此紧密耦合的存储和传输到已知所有收件人，请执行以下任务： 
    
     - 如果已预处理邮件或消息存储提供程序希望进行完整的消息处理 MAPI 后台处理程序，调用[IMAPISupport::CompleteMsg](imapisupport-completemsg.md) 。 邮件流继续 MAPI 后台处理程序。 
    
     - 如果已不预处理邮件或消息存储提供程序不需要 MAPI 后台处理程序完成消息处理，请执行以下任务：
    
       1. 如果**PR_SENTMAIL_ENTRYID** ([PidTagSentMailEntryId](pidtagsentmailentryid-canonical-property.md)) 属性中的项标识符标识的文件夹的邮件的副本设置。
            
       2. 如果**PR_DELETE_AFTER_SUBMIT** ([PidTagDeleteAfterSubmit](pidtagdeleteaftersubmit-canonical-property.md)) 属性已设置为 TRUE，则删除邮件。
            
       3. 如果它已被锁定，解除锁定邮件。
            
       4. 返回到客户端。 邮件流已完成。
    
  - 如果邮件已预处理或提供程序希望 MAPI 后台处理程序完成消息处理，请执行以下任务：
    
    1. 调用[IMAPISupport::CompleteMsg](imapisupport-completemsg.md)。 
          
    2. 继续使用 MAPI 后台处理程序的邮件流。 有关详细信息，请参阅[发送的邮件： MAPI 后台处理程序任务](sending-messages-mapi-spooler-tasks.md)。
    
  - 如果邮件已不预处理或提供程序不需要完成消息处理后台处理程序，请执行以下任务：
    
    1. 如果由**PR_SENTMAIL_ENTRYID**属性中的项标识符标识的文件夹的邮件设置的副本。 
        
    2. 如果**PR_DELETE_AFTER_SUBMIT**属性已设置为 TRUE，则删除邮件。 
        
    3. 如果它已被锁定，解除锁定邮件。 
        
    4. 返回到呼叫者。 邮件流已完成。
    
- 如果传输不紧密耦合的消息存储，并非所有收件人已已知的消息存储库，或者 NEEDS_SPOOLER 标志设置，请执行以下任务：
    
  1. 邮件未**PR_SUBMIT_FLAGS**属性中设置 SUBMITFLAG_PREPROCESS 位置于传出队列中。 
    
  2. 通知传出队列已更改的生成表通知 MAPI 后台处理程序。 
    
  3. 返回到客户端和邮件流继续执行一组由 MAPI 后台处理程序执行的任务。
    
## <a name="see-also"></a>另请参阅

- [邮件存储区功能](message-store-features.md)

