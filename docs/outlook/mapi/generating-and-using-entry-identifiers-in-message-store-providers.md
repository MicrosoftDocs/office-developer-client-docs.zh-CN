---
title: 生成和使用邮件存储提供程序中的条目标识符
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0c43546a-4788-4852-bc89-d6baa4f33c94
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 005742eaaba81600be249d52e5d8098e9f286f17
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437677"
---
# <a name="generating-and-using-entry-identifiers-in-message-store-providers"></a><span data-ttu-id="0d329-103">生成和使用邮件存储提供程序中的条目标识符</span><span class="sxs-lookup"><span data-stu-id="0d329-103">Generating and using entry identifiers in message store providers</span></span>

<span data-ttu-id="0d329-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0d329-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0d329-105">在邮件存储中新建文件夹或邮件时，邮件存储提供程序必须向该对象分配条目标识符，以便客户端应用程序可以引用该对象。</span><span class="sxs-lookup"><span data-stu-id="0d329-105">When a new folder or message is created in a message store, the message store provider has to assign that object an entry identifier so that client applications can refer to it.</span></span> <span data-ttu-id="0d329-106">邮件存储提供程序可以重用已删除对象的已失效长期条目标识符，也可以创建新的标识符。</span><span class="sxs-lookup"><span data-stu-id="0d329-106">Message store providers can either reuse the defunct long-term entry identifiers of deleted objects or create new identifiers.</span></span> <span data-ttu-id="0d329-107">对邮件存储提供程序没有一种或另一种要求;但是，如果可行，邮件存储提供程序应始终为新对象生成新的长期条目标识符，而不是重新使用旧对象。</span><span class="sxs-lookup"><span data-stu-id="0d329-107">There is no requirement one way or the other for message store providers; however, if it is feasible, a message store provider should always generate new long-term entry identifiers for new objects rather than reusing old ones.</span></span> <span data-ttu-id="0d329-108">在删除其引用的对象时，可以重用短期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="0d329-108">It is fine to reuse short-term entry identifiers when the objects they refer to are deleted.</span></span>
  
<span data-ttu-id="0d329-109">此删除的原因是客户端可以缓存条目标识符，有时可以缓存很长时间。</span><span class="sxs-lookup"><span data-stu-id="0d329-109">The reason for this deletion is that clients can cache entry identifiers, sometimes for long periods of time.</span></span> <span data-ttu-id="0d329-110">如果发生这种情况并且邮件存储提供程序确实重复使用条目标识符，则当客户端打开条目标识符时，条目标识符可以引用与客户端首次获取条目标识符时不同的对象。</span><span class="sxs-lookup"><span data-stu-id="0d329-110">If that happens and the message store provider does reuse entry identifiers, it is possible for the entry identifier to refer to a different object when the client opens the entry identifier than when it first obtained the entry identifier.</span></span> <span data-ttu-id="0d329-111">如果邮件存储提供程序不重用条目标识符（或者至少使用不会长时间重复的条目标识符生成方案）则不会发生此问题。</span><span class="sxs-lookup"><span data-stu-id="0d329-111">If the message store provider does not reuse entry identifiers — or at least uses an entry identifier generation scheme that does not repeat for a very long time — this problem cannot occur.</span></span>
  
<span data-ttu-id="0d329-112">同样，当文件夹和邮件在邮件存储中移动时，邮件存储提供程序应尝试保留这些文件夹和邮件的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="0d329-112">Similarly, message store providers should attempt to preserve entry identifiers for folders and messages when they are moved in the message store.</span></span> <span data-ttu-id="0d329-113">如果邮件存储提供程序可以这样做，当对象移动到存储区中的不同位置时，对存储中的对象的引用不会变为无效。</span><span class="sxs-lookup"><span data-stu-id="0d329-113">If the message store provider can do that, references to objects in the store will not become invalid when the object is moved to a different location in the store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0d329-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d329-114">See also</span></span>

- [<span data-ttu-id="0d329-115">邮件存储功能</span><span class="sxs-lookup"><span data-stu-id="0d329-115">Message Store Features</span></span>](message-store-features.md)

