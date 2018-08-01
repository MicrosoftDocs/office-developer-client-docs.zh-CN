---
title: 构建限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 12abbd8c-f825-493e-af42-344371d9658e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3b40c8433f93237db2ae4fd5449fe8a0da486539
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774614"
---
# <a name="building-a-restriction"></a>构建限制

**适用于**： Outlook 
  
若要构建限制，客户端应用程序创建的各种类型的一个或多个限制结构层次结构，并将指针传递给[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)方法的层次结构。 下面的图和[限制的示例代码](sample-restriction-code.md)中的代码示例演示如何与不同类型的链接的限制结构实施的典型的限制。 

本示例中，客户端应用程序的用户正尝试查找包含单词"排球"的主题行中和从 Sam 发送到 Sue 所有邮件。 首先，分配泛型[SRestriction](srestriction.md)结构。 此结构将成为对[MAPIAllocateMore](mapiallocatemore.md)函数的其他调用一次对[MAPIFreeBuffer](mapifreebuffer.md)创建链接的[SRestriction](srestriction.md)和[SPropValue](spropvalue.md)结构可释放的基础。 要应用于的消息集条件分为三个部分，因为顶部级别限制结构是**和**限制。 [SAndRestriction](sandrestriction.md)结构的**cRes**成员设置为 3，以指示用于计算的三个限制和其**lpRes**成员设置为**SRestriction**结构的三个成员数组。 
  
若要搜索发送到特定收件人的邮件，必要时搜索每条消息，而不是邮件本身的收件人表。 子对象限制用于执行收件人表搜索。 因此，该数组指向[SSubRestriction](ssubrestriction.md)结构具有其**ulSubObject**成员的第一个成员设置为**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))。 然后，若要指定要在收件人的表中查找的内容，请使用内容的限制。 
  
数组的第二个和第三个成员是更简单。 都指向内容限制结构，之一来搜索邮件已具有**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性设置为**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 属性设置为"Sam"，另一个"排球。"
  
**限制实现**
  
![限制实现](media/amapi_61.gif "限制实现")
  
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

