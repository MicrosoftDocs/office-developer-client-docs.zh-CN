---
title: 长期条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a514275e-40c2-48db-8072-1dfc392a7ac6
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e624ab4f39ef5a5385119779b0780ee7173a3ee7
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586919"
---
# <a name="long-term-entry-identifiers"></a><span data-ttu-id="4643b-103">长期条目标识符</span><span class="sxs-lookup"><span data-stu-id="4643b-103">Long-Term Entry Identifiers</span></span>

  
  
<span data-ttu-id="4643b-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4643b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4643b-105">对象需要与长寿命标识符时，将服务提供程序为对象分配的长期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4643b-105">A long-term entry identifier is assigned by a service provider to an object when an object requires an identifier with a prolonged lifespan.</span></span> <span data-ttu-id="4643b-106">长期条目标识符周或月始终是有效，可以在其他工作站，具体取决于提供程序上有效。</span><span class="sxs-lookup"><span data-stu-id="4643b-106">Long-term entry identifiers are always valid for weeks or months and can be valid on other workstations, depending on the provider.</span></span> <span data-ttu-id="4643b-107">创建自定义的收件人的地址簿提供程序的长期标识符是通用有效。</span><span class="sxs-lookup"><span data-stu-id="4643b-107">The long-term identifiers created by address book providers for custom recipients are universally valid.</span></span> 
  
<span data-ttu-id="4643b-108">长期条目标识符已分配给消息存储库、 文件夹、 邮件、 通讯簿容器、 邮件用户和通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="4643b-108">Long-term entry identifiers are assigned to message stores, folders, messages, address book containers, messaging users, and distribution lists.</span></span> <span data-ttu-id="4643b-109">当客户端应用程序调用这些对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法时，始终是返回的长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="4643b-109">When client applications call the [IMAPIProp::GetProps](imapiprop-getprops.md) method of these objects, it is always a long-term entry identifier that is returned.</span></span> 
  
<span data-ttu-id="4643b-110">长期条目标识符必须唯一活动配置文件; 中的所有邮件存储因此，当邮件或文件夹从一个消息存储到另一个复制，必须将它分配新的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4643b-110">Long-term entry identifiers must be unique across all message stores in the active profile; therefore, when a message or folder is copied from one message store to another, it must be assigned a new entry identifier.</span></span> <span data-ttu-id="4643b-111">当移动消息存储对象时，实现移动的消息存储提供程序将确定是否原始条目标识符将一直保持有效。</span><span class="sxs-lookup"><span data-stu-id="4643b-111">When a message store object is moved, the message store provider that implements the move determines whether the original entry identifier will remain valid.</span></span> <span data-ttu-id="4643b-112">某些服务提供商向移动对象; 分配新的项标识符有些则没有。</span><span class="sxs-lookup"><span data-stu-id="4643b-112">Some service providers assign new entry identifiers to moved objects; others do not.</span></span> <span data-ttu-id="4643b-113">如果发生更改时，将得到的移动通知时传递给客户端的信息中包括的新的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4643b-113">If there is a change, the new entry identifier will be included in the information passed to clients when they are notified of the move.</span></span> 
  
<span data-ttu-id="4643b-114">通常情况下，消息存储提供程序时将文件夹移实现以下行为：</span><span class="sxs-lookup"><span data-stu-id="4643b-114">Typically, message store providers implement the following behavior when they move folders:</span></span>
  
- <span data-ttu-id="4643b-115">当文件夹从一个消息存储库移至另一个不同类型的存储时，条目标识符保证更改。</span><span class="sxs-lookup"><span data-stu-id="4643b-115">When a folder is moved from one message store to another store of a different type, the entry identifier is guaranteed to change.</span></span>
    
- <span data-ttu-id="4643b-116">当文件夹从一个消息存储库移至另一个相同类型的存储时，始终更改的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4643b-116">When a folder is moved from one message store to another store of the same type, the entry identifier almost always changes.</span></span>
    
- <span data-ttu-id="4643b-117">当文件夹移至的相同的消息存储中的另一个位置时，条目标识符可能或可能未更改，具体取决于消息存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="4643b-117">When a folder is moved to another location within the same message store, the entry identifier might or might not change, depending on the message store provider.</span></span>
    
<span data-ttu-id="4643b-118">重命名文件夹，而不更改其父文件夹通常不会导致要更改的项标识符。</span><span class="sxs-lookup"><span data-stu-id="4643b-118">Renaming a folder without changing its parent folder usually does not cause the entry identifier to change.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4643b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4643b-119">See also</span></span>



[<span data-ttu-id="4643b-120">MAPI 条目标识符</span><span class="sxs-lookup"><span data-stu-id="4643b-120">MAPI Entry Identifiers</span></span>](mapi-entry-identifiers.md)

