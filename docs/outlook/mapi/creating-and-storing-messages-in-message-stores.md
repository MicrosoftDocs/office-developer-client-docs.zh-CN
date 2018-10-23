---
title: 在邮件存储中创建和存储邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cc74b31c-d7ed-4fcf-9535-a2f9222901b7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: be718ea3ef4da91d2f85a0229f5a506198a2527f
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589173"
---
# <a name="creating-and-storing-messages-in-message-stores"></a>在邮件存储中创建和存储邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
邮件存储提供程序如何在基础存储机制中创建和存储邮件很大程度上取决于基础存储机制本身。 一般情况下，仅需要编写代码来保存邮件的属性及其值。
  
当邮件存储提供程序创建新邮件时，提供程序需要使用邮件的必需属性创建邮件。 可以在 [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md) 界面的文档中找到这些属性的列表。 之后，客户端应用程序可使用 [IMAPIProp](imapipropiunknown.md) 方法添加任何其他属性。 
  
当邮件存储提供程序将邮件保存到基础存储机制时，提供程序需要循环访问该邮件的属性，并将其保存到基础存储机制，以便在稍后打开邮件时可以完全恢复它们。
  
MAPI 需要对 [IMessage](imessageimapiprop.md) 界面上的属性进行事务处理，这意味着在邮件对象上调用  [IMAPIProp::SaveChanges](imapiprop-savechanges.md) 方法之前，对其所作的更改不会永久。 邮件存储提供程序负责实现这一行为。 通常这并不困难；这只是意味着在修改属性时将其保留在内存中并在调用 **SaveChanges** 时将它们提交给基础存储机制。 
  
就 **SaveChanges** 方法而言，邮件对象上的某些属性对客户端应用程序有着特殊的语义，如下： 
  
- 某些属性在调用 **SaveChanges** 之前为读/写，但之后为只读。 例如，**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 最初由创建邮件的客户端应用程序设置（因此是读/写），但首次调用 **SaveChanges** 之后无法更改。
    
- 某些属性与它们所在文件夹上的属性或 **IMAPIFolder** 方法有特殊关系。 例如，**PR_MESSAGE_FLAGS** 属性与 [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) 调用使用的标签相关。 
    
- 某些属性在首次调用 **SaveChanges** 前不可用。 例如，**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性在调用 **SaveChanges** 前不可用。 
    
- 某些属性可能与邮件对象上的其他属性有特殊关系。 例如，**PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 属性通常派生自支持 RTF 格式邮件的邮件存储提供程序中的 **PR_RTF_COMPRESSED** ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 属性。
    
- 某些属性用于与邮件存储相关的多个对象类型。 例如，**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性在文件夹和邮件对象以及以及邮件存储对象上都是必需的。
    
邮件存储提供程序有责任实现这些属性的正确语义。
  
## <a name="see-also"></a>另请参阅



[实现邮件存储中的邮件](implementing-messages-in-message-stores.md)

