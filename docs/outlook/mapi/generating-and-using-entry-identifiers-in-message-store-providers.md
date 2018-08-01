---
title: 生成并在消息中使用项标识符存储提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 0c43546a-4788-4852-bc89-d6baa4f33c94
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3bfda4a1dbe464c744917c2e9b3ca66eaf88fd20
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775038"
---
# <a name="generating-and-using-entry-identifiers-in-message-store-providers"></a><span data-ttu-id="3df43-103">生成并在消息中使用项标识符存储提供程序</span><span class="sxs-lookup"><span data-stu-id="3df43-103">Generating and using entry identifiers in message store providers</span></span>

<span data-ttu-id="3df43-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3df43-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3df43-105">消息存储区中创建新的文件夹或邮件时，消息存储提供程序必须将该对象分配条目标识符，以便客户端应用程序可以引用它。</span><span class="sxs-lookup"><span data-stu-id="3df43-105">When a new folder or message is created in a message store, the message store provider has to assign that object an entry identifier so that client applications can refer to it.</span></span> <span data-ttu-id="3df43-106">消息存储提供程序可重用的已删除对象已失效的长期条目标识符或创建新的标识符。</span><span class="sxs-lookup"><span data-stu-id="3df43-106">Message store providers can either reuse the defunct long-term entry identifiers of deleted objects or create new identifiers.</span></span> <span data-ttu-id="3df43-107">没有不要求使用一种方法或另一个用于消息存储提供程序;但是，如果可行，消息存储提供程序应总是会生成新的新对象，而不是重新使用旧的长期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3df43-107">There is no requirement one way or the other for message store providers; however, if it is feasible, a message store provider should always generate new long-term entry identifiers for new objects rather than reusing old ones.</span></span> <span data-ttu-id="3df43-108">在删除它们引用的对象时重用短期条目标识符没关系。</span><span class="sxs-lookup"><span data-stu-id="3df43-108">It is fine to reuse short-term entry identifiers when the objects they refer to are deleted.</span></span>
  
<span data-ttu-id="3df43-109">此删除操作的原因是，客户端可以缓存条目标识符，有时长时间。</span><span class="sxs-lookup"><span data-stu-id="3df43-109">The reason for this deletion is that clients can cache entry identifiers, sometimes for long periods of time.</span></span> <span data-ttu-id="3df43-110">如果发生这种情况和消息存储提供程序执行重用条目标识符，则可能要引用的不同对象，当客户端打开比其第一次获得的项标识符的项标识符的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3df43-110">If that happens and the message store provider does reuse entry identifiers, it is possible for the entry identifier to refer to a different object when the client opens the entry identifier than when it first obtained the entry identifier.</span></span> <span data-ttu-id="3df43-111">如果消息存储提供程序不会再条目标识符 — 或至少使用不重复很长时间的项标识符生成方案 — 不能出现此问题。</span><span class="sxs-lookup"><span data-stu-id="3df43-111">If the message store provider does not reuse entry identifiers — or at least uses an entry identifier generation scheme that does not repeat for a very long time — this problem cannot occur.</span></span>
  
<span data-ttu-id="3df43-112">同样，消息存储提供程序应尝试在他们会移动消息存储库中时保留文件夹和邮件的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3df43-112">Similarly, message store providers should attempt to preserve entry identifiers for folders and messages when they are moved in the message store.</span></span> <span data-ttu-id="3df43-113">消息存储提供程序可以执行的操作，如果存储区中的对象的引用，不能无效时对象移动到其他位置存储中。</span><span class="sxs-lookup"><span data-stu-id="3df43-113">If the message store provider can do that, references to objects in the store will not become invalid when the object is moved to a different location in the store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3df43-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3df43-114">See also</span></span>

- [<span data-ttu-id="3df43-115">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="3df43-115">Message Store Features</span></span>](message-store-features.md)

