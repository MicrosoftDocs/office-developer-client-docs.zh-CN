---
title: 在邮件存储区中创建和存储邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc74b31c-d7ed-4fcf-9535-a2f9222901b7
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: be718ea3ef4da91d2f85a0229f5a506198a2527f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589173"
---
# <a name="creating-and-storing-messages-in-message-stores"></a>在邮件存储区中创建和存储邮件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
消息存储提供程序如何创建和基础存储机制中存储的消息取决于主要基础存储机制本身。 一般情况下，则只需编写代码以保留的一条消息，及其值的属性。
  
当邮件存储提供程序创建一个新的邮件，提供程序需要创建具有所需属性的邮件的邮件。 有关的文档中找不到这些属性的列表[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)接口。 之后，客户端应用程序使用[IMAPIProp](imapipropiunknown.md)方法添加的任何其他属性。 
  
当邮件存储提供程序保存到基础存储机制一条消息时，提供程序需要循环访问该消息的属性，并将其保存到基础存储机制，以便他们可以完全恢复如果以后打开邮件。
  
MAPI 需要的[IMessage](imessageimapiprop.md)接口上的属性进行事务处理，这意味着，对它们进行更改之前，不会永久消息对象上调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法。 消息存储提供程序负责为实现此行为。 通常是不变得比较困难;它就意味着修改它们时，在内存中按住属性并将它们提交给基础存储机制，调用**SaveChanges**时。 
  
消息对象的某些属性具有特殊的语义相对于**SaveChanges**方法中，客户端应用程序，如下所示： 
  
- **SaveChanges**调用之前，但只读此后，某些属性应为读/写。 例如， **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 的客户端应用程序创建邮件 （并因此是可读写） 最初设置但不能更改后**SaveChanges**为第一个呼叫。
    
- 有些属性具有特殊关系与属性，它们是在或给**IMAPIFolder**方法的文件夹。 例如， **PR_MESSAGE_FLAGS**属性与[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)呼叫使用的标志。 
    
- 一些属性可能不可用，直到**SaveChanges**称为第一次。 例如， **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性可能不可用调用**SaveChanges**之前。 
    
- 有些属性可以 message 对象上具有特殊关系的其他属性。 例如， **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性通常源自消息存储提供程序支持富文本格式的邮件中的**PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。
    
- 某些属性使用多个与邮件存储相关的对象类型。 例如上的文件夹和对象以及消息存储对象的邮件需要**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性。
    
它是要实现此类属性的正确语义消息存储提供程序的责任。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储区中的邮件](implementing-messages-in-message-stores.md)

