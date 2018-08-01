---
title: 实现邮件存储区中的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: df5003d5-cbfe-40b2-a481-e2e11dce4b3e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: c21fea9b0c8de96f427c4bcdfabfde3a0032f0c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775811"
---
# <a name="implementing-messages-in-message-stores"></a><span data-ttu-id="a6604-103">实现邮件存储区中的邮件</span><span class="sxs-lookup"><span data-stu-id="a6604-103">Implementing Messages in Message Stores</span></span>

  
  
<span data-ttu-id="a6604-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="a6604-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="a6604-105">[IMessage: IMAPIProp](imessageimapiprop.md)接口是类似于[IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)接口中的两个接口派生[IMAPIProp: IUnknown](imapipropiunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="a6604-105">The [IMessage : IMAPIProp](imessageimapiprop.md) interface is similar to the [IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md) interface in that both interfaces derive from the [IMAPIProp : IUnknown](imapipropiunknown.md) interface.</span></span> <span data-ttu-id="a6604-106">客户端使用**IMAPIProp**方法访问一条消息的内容。</span><span class="sxs-lookup"><span data-stu-id="a6604-106">Clients use the **IMAPIProp** methods to access the contents of a message.</span></span> <span data-ttu-id="a6604-107">**IMessage**接口提供用于处理邮件 （例如，将附件添加或修改邮件的收件人） 的其他方法。</span><span class="sxs-lookup"><span data-stu-id="a6604-107">The **IMessage** interface supplies additional methods for manipulating messages (for example, adding attachments or modifying the recipients of a message).</span></span> <span data-ttu-id="a6604-108">**IMessage**接口中的方法修改的消息不直接在该消息属性中存储的属性。</span><span class="sxs-lookup"><span data-stu-id="a6604-108">The methods in the **IMessage** interface modify attributes of messages that are not stored directly in the message's properties.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a6604-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6604-109">See also</span></span>



[<span data-ttu-id="a6604-110">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="a6604-110">Message Store Features</span></span>](message-store-features.md)

