---
title: 支持多个客户端访问邮件存储区中的邮件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 31885c64-edb2-4a87-8730-09f163dedd40
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b13fbb9f2807c9814fed5ba3bcca8fe73aaa7b01
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22564218"
---
# <a name="supporting-multiple-client-access-to-messages-in-message-stores"></a><span data-ttu-id="20350-103">支持多个客户端访问邮件存储区中的邮件</span><span class="sxs-lookup"><span data-stu-id="20350-103">Supporting Multiple Client Access to Messages in Message Stores</span></span>

  
  
<span data-ttu-id="20350-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="20350-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="20350-105">很可能为多个客户端应用程序同时打开给定的消息。</span><span class="sxs-lookup"><span data-stu-id="20350-105">It is possible for multiple client applications to open a given message simultaneously.</span></span> <span data-ttu-id="20350-106">消息存储提供程序没有关注调控此类访问权限的任何特定规则。</span><span class="sxs-lookup"><span data-stu-id="20350-106">Message store providers do not have to follow any particular rules for governing such access.</span></span> <span data-ttu-id="20350-107">但是，如果客户端应用程序修改邮件，并保存其更改，存储提供程序都应符合以下规则：</span><span class="sxs-lookup"><span data-stu-id="20350-107">However, if the client applications modify the message and save their changes, the store provider should comply with the following rules:</span></span>
  
- <span data-ttu-id="20350-108">允许对[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法的第一个调用，以继续好像它是已打开的消息的唯一客户端。</span><span class="sxs-lookup"><span data-stu-id="20350-108">Allow the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to proceed as if it were the only client that has the message open.</span></span> 
    
- <span data-ttu-id="20350-109">在其他客户端的**SaveChanges**后续呼叫，消息存储提供程序应忽略所做的更改并返回 MAPI_E_OBJECT_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="20350-109">On the subsequent **SaveChanges** calls by other clients, the message store provider should ignore the changes and return MAPI_E_OBJECT_CHANGED.</span></span> 
    
- <span data-ttu-id="20350-110">允许客户端应用程序以应对 MAPI_E_OBJECT_CHANGED 返回代码通过调用**SaveChanges**再次使用 FORCE_SAVE 标志。</span><span class="sxs-lookup"><span data-stu-id="20350-110">Allow client applications to respond to a MAPI_E_OBJECT_CHANGED return code by calling **SaveChanges** again with the FORCE_SAVE flag.</span></span> <span data-ttu-id="20350-111">如果客户端应用程序这，消息存储提供程序应当用新的替换以前的更改。</span><span class="sxs-lookup"><span data-stu-id="20350-111">If a client application does this, the message store provider should replace the previous changes with the new ones.</span></span> 
    
<span data-ttu-id="20350-112">此外，消息存储提供程序可以检测到冲突，并演示使用户可以选择是否保留原始邮件，使用新的更改，覆盖原始邮件或将新的更改保存到另一个位置的接口。</span><span class="sxs-lookup"><span data-stu-id="20350-112">Alternatively, the message store provider can detect the conflict and present an interface that enables the user to choose whether to keep the original message, overwrite the original message with the new changes, or save the new changes to another location.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="20350-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20350-113">See also</span></span>



[<span data-ttu-id="20350-114">实现邮件存储区中的邮件</span><span class="sxs-lookup"><span data-stu-id="20350-114">Implementing Messages in Message Stores</span></span>](implementing-messages-in-message-stores.md)

