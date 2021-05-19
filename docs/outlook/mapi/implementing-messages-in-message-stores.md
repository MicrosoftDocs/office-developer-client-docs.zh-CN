---
title: 实现邮件存储中的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: df5003d5-cbfe-40b2-a481-e2e11dce4b3e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 223dfa2ac990875e98e876ab491bf09caf63e874
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416641"
---
# <a name="implementing-messages-in-message-stores"></a><span data-ttu-id="bb525-103">实现邮件存储中的邮件</span><span class="sxs-lookup"><span data-stu-id="bb525-103">Implementing Messages in Message Stores</span></span>

  
  
<span data-ttu-id="bb525-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb525-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb525-105">[IMessage ： IMAPIProp](imessageimapiprop.md)接口类似于[IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)接口，因为两个接口都派生自[IMAPIProp ： IUnknown](imapipropiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="bb525-105">The [IMessage : IMAPIProp](imessageimapiprop.md) interface is similar to the [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) interface in that both interfaces derive from the [IMAPIProp : IUnknown](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="bb525-106">客户端使用 **IMAPIProp** 方法访问邮件的内容。</span><span class="sxs-lookup"><span data-stu-id="bb525-106">Clients use the **IMAPIProp** methods to access the contents of a message.</span></span> <span data-ttu-id="bb525-107">**IMessage** 接口提供用于处理邮件 (其他方法，例如添加附件或修改邮件收件人) 。</span><span class="sxs-lookup"><span data-stu-id="bb525-107">The **IMessage** interface supplies additional methods for manipulating messages (for example, adding attachments or modifying the recipients of a message).</span></span> <span data-ttu-id="bb525-108">**IMessage 接口** 中的方法修改未直接存储在邮件属性中的邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="bb525-108">The methods in the **IMessage** interface modify attributes of messages that are not stored directly in the message's properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bb525-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb525-109">See also</span></span>



[<span data-ttu-id="bb525-110">邮件存储功能</span><span class="sxs-lookup"><span data-stu-id="bb525-110">Message Store Features</span></span>](message-store-features.md)

