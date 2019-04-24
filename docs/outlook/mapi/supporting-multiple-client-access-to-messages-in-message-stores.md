---
title: 支持对邮件存储区中的邮件进行多个客户端访问
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 31885c64-edb2-4a87-8730-09f163dedd40
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 40bed9ccbe8073c8e9ea5176c9d4be8fe642b52d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350601"
---
# <a name="supporting-multiple-client-access-to-messages-in-message-stores"></a><span data-ttu-id="7c9d5-103">支持对邮件存储区中的邮件进行多个客户端访问</span><span class="sxs-lookup"><span data-stu-id="7c9d5-103">Supporting Multiple Client Access to Messages in Message Stores</span></span>

  
  
<span data-ttu-id="7c9d5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7c9d5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7c9d5-105">多个客户端应用程序可以同时打开给定的邮件。</span><span class="sxs-lookup"><span data-stu-id="7c9d5-105">It is possible for multiple client applications to open a given message simultaneously.</span></span> <span data-ttu-id="7c9d5-106">邮件存储提供程序不必遵循用于控制此类访问的任何特定规则。</span><span class="sxs-lookup"><span data-stu-id="7c9d5-106">Message store providers do not have to follow any particular rules for governing such access.</span></span> <span data-ttu-id="7c9d5-107">但是, 如果客户端应用程序修改邮件并保存其更改, 则存储提供程序应遵循以下规则:</span><span class="sxs-lookup"><span data-stu-id="7c9d5-107">However, if the client applications modify the message and save their changes, the store provider should comply with the following rules:</span></span>
  
- <span data-ttu-id="7c9d5-108">允许对[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法进行的第一次调用, 就像它是打开邮件的唯一客户端一样。</span><span class="sxs-lookup"><span data-stu-id="7c9d5-108">Allow the first call to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method to proceed as if it were the only client that has the message open.</span></span> 
    
- <span data-ttu-id="7c9d5-109">在其他客户端的后续**SaveChanges**调用中, 邮件存储提供程序应忽略所做的更改, 然后返回 MAPI_E_OBJECT_CHANGED。</span><span class="sxs-lookup"><span data-stu-id="7c9d5-109">On the subsequent **SaveChanges** calls by other clients, the message store provider should ignore the changes and return MAPI_E_OBJECT_CHANGED.</span></span> 
    
- <span data-ttu-id="7c9d5-110">允许客户端应用程序通过使用 FORCE_SAVE 标志再次调用**SaveChanges**来响应 MAPI_E_OBJECT_CHANGED 返回代码。</span><span class="sxs-lookup"><span data-stu-id="7c9d5-110">Allow client applications to respond to a MAPI_E_OBJECT_CHANGED return code by calling **SaveChanges** again with the FORCE_SAVE flag.</span></span> <span data-ttu-id="7c9d5-111">如果客户端应用程序这样做, 则邮件存储提供程序应将以前的更改替换为新的更改。</span><span class="sxs-lookup"><span data-stu-id="7c9d5-111">If a client application does this, the message store provider should replace the previous changes with the new ones.</span></span> 
    
<span data-ttu-id="7c9d5-112">或者, 邮件存储提供程序可以检测到冲突并提供一个接口, 使用户能够选择是保留原始邮件、使用新更改覆盖原始邮件, 还是将新更改保存到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="7c9d5-112">Alternatively, the message store provider can detect the conflict and present an interface that enables the user to choose whether to keep the original message, overwrite the original message with the new changes, or save the new changes to another location.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7c9d5-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c9d5-113">See also</span></span>



[<span data-ttu-id="7c9d5-114">实现邮件存储中的邮件</span><span class="sxs-lookup"><span data-stu-id="7c9d5-114">Implementing Messages in Message Stores</span></span>](implementing-messages-in-message-stores.md)

