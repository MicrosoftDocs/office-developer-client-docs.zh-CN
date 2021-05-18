---
title: 生成限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 12abbd8c-f825-493e-af42-344371d9658e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 38182abd922cd5806a14b6541c22ce675b997387
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422508"
---
# <a name="building-a-restriction"></a>生成限制

**适用于**：Outlook 2013 | Outlook 2016 
  
为了构建限制，客户端应用程序会创建一个包含各种类型的一个或多个限制结构的层次结构，将指向该层次结构的指针传递给 [IMAPITable：：Restrict](imapitable-restrict.md) 或 [IMAPITable：：FindRow](imapitable-findrow.md) 方法。 下图和示例限制代码中的代码示例演示了[](sample-restriction-code.md)如何使用不同类型的链接限制结构实现典型限制。 

本示例中，客户端应用程序的用户尝试在主题行中查找包含单词"开发程序"的所有邮件，并发送给 Sam 的一位用户。 首先，分配泛型 [SRestriction](srestriction.md) 结构。 此结构成为 [对 MAPIAllocateMore](mapiallocatemore.md) 函数的其他调用的基础，以创建链接 [的 SRestriction](srestriction.md) 和 [SPropValue](spropvalue.md) 结构，这些结构可通过对 [MAPIFreeBuffer](mapifreebuffer.md)的单个调用释放。 由于应用于邮件集的条件由三部分组成，因此顶级限制结构是 **AND** 限制。 [SAndRestriction](sandrestriction.md)结构的 **cRes** 成员设置为 3，以指示要评估的三个限制，并且其 **lpRes** 成员设置为 **SRestriction** 结构的三个成员数组。 
  
若要搜索发送给特定收件人的邮件，必须搜索每封邮件的收件人表，而不是邮件本身。 子对象限制用于执行收件人表搜索。 因此，数组的第一个成员指向其 **ulSubObject** 成员集 为 **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 的 [SSubRestriction](ssubrestriction.md)结构。 然后，若要指定在收件人表中查找的内容，则使用内容限制。 
  
数组的第二个成员和第三个成员更为简单。 它们均指向内容限制结构，一种用于搜索 PR_SENDER_NAME **(** [PidTagSenderName](pidtagsendername-canonical-property.md)) 属性设置为"Sam"的邮件，另一个属性将 **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性设置为"用户"的邮件。
  
**限制实现**
  
![限制实现](media/amapi_61.gif "限制实现")
  
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

