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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32318256"
---
# <a name="building-a-restriction"></a>生成限制

**适用于**：Outlook 2013 | Outlook 2016 
  
若要生成限制, 客户端应用程序将创建各种类型的一个或多个限制结构的层次结构, 并将指向该层次结构的指针传递给[IMAPITable:: Restrict](imapitable-restrict.md)或[imapitable:: FindRow](imapitable-findrow.md)方法。 下面的插图和[示例限制代码](sample-restriction-code.md)中的代码示例演示了如何使用不同类型的链接限制结构来实现典型限制。 

在此示例中, 客户端应用程序的用户尝试查找主题行中包含单词 "volleyball" 的所有邮件, 并将其从 Sam 发送给 Sue。 首先, 分配一个通用的[SRestriction](srestriction.md)结构。 此结构成为对[MAPIAllocateMore](mapiallocatemore.md)函数的其他调用的基础, 以创建可通过对[MAPIFreeBuffer](mapifreebuffer.md)的单个调用释放的链接的[SRestriction](srestriction.md)和[SPropValue](spropvalue.md)结构。 由于要应用于邮件集的条件分为三个部分, 因此顶级限制结构是**和**限制。 [SAndRestriction](sandrestriction.md)结构的**cRes**成员设置为 3, 以指示要评估的三个限制, 并将其**lpRes**成员设置为**SRestriction**结构的三个成员数组。 
  
若要搜索发送到特定收件人的邮件, 必须在 "收件人" 表中搜索每封邮件, 而不是邮件本身。 子范围限制用于执行收件人表搜索。 因此, 数组的第一个成员指向其**ulSubObject**成员设置为**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 的[SSubRestriction](ssubrestriction.md)结构。 然后, 若要指定要在收件人表中查找的内容, 请使用内容限制。 
  
数组的第二个和第三个成员更简单。 它们都指向内容限制结构, 一个用于搜索**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 属性设置为 "Sam" 的邮件, 另一个设置为**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性设置为 "volleyball "。
  
**限制实现**
  
![限制实现](media/amapi_61.gif "限制实现")
  
## <a name="see-also"></a>另请参阅

- [MAPI 表](mapi-tables.md)

