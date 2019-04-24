---
title: 长期条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a514275e-40c2-48db-8072-1dfc392a7ac6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b65656992681618aa8a1c53217bdd7101bc2502b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307782"
---
# <a name="long-term-entry-identifiers"></a><span data-ttu-id="3b68e-103">长期条目标识符</span><span class="sxs-lookup"><span data-stu-id="3b68e-103">Long-Term Entry Identifiers</span></span>

  
  
<span data-ttu-id="3b68e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3b68e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3b68e-105">当对象需要具有长时间寿命的标识符时, 服务提供商会将长期条目标识符分配给对象。</span><span class="sxs-lookup"><span data-stu-id="3b68e-105">A long-term entry identifier is assigned by a service provider to an object when an object requires an identifier with a prolonged lifespan.</span></span> <span data-ttu-id="3b68e-106">长期条目标识符对星期或月始终有效, 并且可以在其他工作站上有效, 具体取决于提供程序。</span><span class="sxs-lookup"><span data-stu-id="3b68e-106">Long-term entry identifiers are always valid for weeks or months and can be valid on other workstations, depending on the provider.</span></span> <span data-ttu-id="3b68e-107">由通讯簿提供程序为自定义收件人创建的长期标识符是普遍有效的。</span><span class="sxs-lookup"><span data-stu-id="3b68e-107">The long-term identifiers created by address book providers for custom recipients are universally valid.</span></span> 
  
<span data-ttu-id="3b68e-108">长期条目标识符分配给邮件存储、文件夹、邮件、通讯簿容器、邮件用户和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3b68e-108">Long-term entry identifiers are assigned to message stores, folders, messages, address book containers, messaging users, and distribution lists.</span></span> <span data-ttu-id="3b68e-109">当客户端应用程序调用这些对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法时, 它始终是返回的长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3b68e-109">When client applications call the [IMAPIProp::GetProps](imapiprop-getprops.md) method of these objects, it is always a long-term entry identifier that is returned.</span></span> 
  
<span data-ttu-id="3b68e-110">长期条目标识符必须在活动配置文件中的所有邮件存储区中都是唯一的;因此, 将邮件或文件夹从一个邮件存储复制到另一个邮件库时, 必须为其分配一个新的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="3b68e-110">Long-term entry identifiers must be unique across all message stores in the active profile; therefore, when a message or folder is copied from one message store to another, it must be assigned a new entry identifier.</span></span> <span data-ttu-id="3b68e-111">移动邮件存储对象时, 实现移动的邮件存储提供程序将确定原始条目标识符是否仍然有效。</span><span class="sxs-lookup"><span data-stu-id="3b68e-111">When a message store object is moved, the message store provider that implements the move determines whether the original entry identifier will remain valid.</span></span> <span data-ttu-id="3b68e-112">某些服务提供程序将新的条目标识符分配给移动的对象;而不是其他人。</span><span class="sxs-lookup"><span data-stu-id="3b68e-112">Some service providers assign new entry identifiers to moved objects; others do not.</span></span> <span data-ttu-id="3b68e-113">如果发生更改, 则新条目标识符将包含在发送给客户端的信息在移动时传递给客户端。</span><span class="sxs-lookup"><span data-stu-id="3b68e-113">If there is a change, the new entry identifier will be included in the information passed to clients when they are notified of the move.</span></span> 
  
<span data-ttu-id="3b68e-114">通常情况下, 邮件存储提供程序会在移动文件夹时实现以下行为:</span><span class="sxs-lookup"><span data-stu-id="3b68e-114">Typically, message store providers implement the following behavior when they move folders:</span></span>
  
- <span data-ttu-id="3b68e-115">将文件夹从一个邮件存储移动到其他类型的另一个存储区时, 会保证条目标识符的变化。</span><span class="sxs-lookup"><span data-stu-id="3b68e-115">When a folder is moved from one message store to another store of a different type, the entry identifier is guaranteed to change.</span></span>
    
- <span data-ttu-id="3b68e-116">将文件夹从一个邮件存储移动到同一类型的另一个存储区时, 该条目标识符几乎总是发生变化。</span><span class="sxs-lookup"><span data-stu-id="3b68e-116">When a folder is moved from one message store to another store of the same type, the entry identifier almost always changes.</span></span>
    
- <span data-ttu-id="3b68e-117">将文件夹移动到同一邮件存储区中的其他位置时, 条目标识符可能会更改, 也可能不会更改, 具体取决于邮件存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="3b68e-117">When a folder is moved to another location within the same message store, the entry identifier might or might not change, depending on the message store provider.</span></span>
    
<span data-ttu-id="3b68e-118">重命名文件夹而不更改其父文件夹通常不会导致项目标识符发生变化。</span><span class="sxs-lookup"><span data-stu-id="3b68e-118">Renaming a folder without changing its parent folder usually does not cause the entry identifier to change.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3b68e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b68e-119">See also</span></span>



[<span data-ttu-id="3b68e-120">MAPI 条目标识符</span><span class="sxs-lookup"><span data-stu-id="3b68e-120">MAPI Entry Identifiers</span></span>](mapi-entry-identifiers.md)

