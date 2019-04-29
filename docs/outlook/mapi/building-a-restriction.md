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
# <a name="building-a-restriction"></a><span data-ttu-id="9b571-103">生成限制</span><span class="sxs-lookup"><span data-stu-id="9b571-103">Building a restriction</span></span>

<span data-ttu-id="9b571-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9b571-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9b571-105">若要生成限制, 客户端应用程序将创建各种类型的一个或多个限制结构的层次结构, 并将指向该层次结构的指针传递给[IMAPITable:: Restrict](imapitable-restrict.md)或[imapitable:: FindRow](imapitable-findrow.md)方法。</span><span class="sxs-lookup"><span data-stu-id="9b571-105">To build a restriction, a client application creates a hierarchy of one or more restriction structures of various types and passes a pointer to the hierarchy to the [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md) method.</span></span> <span data-ttu-id="9b571-106">下面的插图和[示例限制代码](sample-restriction-code.md)中的代码示例演示了如何使用不同类型的链接限制结构来实现典型限制。</span><span class="sxs-lookup"><span data-stu-id="9b571-106">The illustration that follows and the code sample in [Sample Restriction Code](sample-restriction-code.md) demonstrate how a typical restriction is implemented with linked restriction structures of different types.</span></span> 

<span data-ttu-id="9b571-107">在此示例中, 客户端应用程序的用户尝试查找主题行中包含单词 "volleyball" 的所有邮件, 并将其从 Sam 发送给 Sue。</span><span class="sxs-lookup"><span data-stu-id="9b571-107">In this example, a user of a client application is trying to find all messages that contain the word "volleyball" in the subject line and were sent to Sue from Sam.</span></span> <span data-ttu-id="9b571-108">首先, 分配一个通用的[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="9b571-108">First, a generic [SRestriction](srestriction.md) structure is allocated.</span></span> <span data-ttu-id="9b571-109">此结构成为对[MAPIAllocateMore](mapiallocatemore.md)函数的其他调用的基础, 以创建可通过对[MAPIFreeBuffer](mapifreebuffer.md)的单个调用释放的链接的[SRestriction](srestriction.md)和[SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="9b571-109">This structure becomes the basis for other calls to the [MAPIAllocateMore](mapiallocatemore.md) function to create linked [SRestriction](srestriction.md) and [SPropValue](spropvalue.md) structures that can be freed with a single call to [MAPIFreeBuffer](mapifreebuffer.md).</span></span> <span data-ttu-id="9b571-110">由于要应用于邮件集的条件分为三个部分, 因此顶级限制结构是**和**限制。</span><span class="sxs-lookup"><span data-stu-id="9b571-110">Because the criteria to apply to the set of messages is in three parts, the top level restriction structure is an **AND** restriction.</span></span> <span data-ttu-id="9b571-111">[SAndRestriction](sandrestriction.md)结构的**cRes**成员设置为 3, 以指示要评估的三个限制, 并将其**lpRes**成员设置为**SRestriction**结构的三个成员数组。</span><span class="sxs-lookup"><span data-stu-id="9b571-111">The [SAndRestriction](sandrestriction.md) structure's **cRes** member is set to 3 to indicate the three restrictions to evaluate and its **lpRes** member is set to a three member array of **SRestriction** structures.</span></span> 
  
<span data-ttu-id="9b571-112">若要搜索发送到特定收件人的邮件, 必须在 "收件人" 表中搜索每封邮件, 而不是邮件本身。</span><span class="sxs-lookup"><span data-stu-id="9b571-112">To search for messages that are sent to a particular recipient, it is necessary to search the recipient table for each message rather than the message itself.</span></span> <span data-ttu-id="9b571-113">子范围限制用于执行收件人表搜索。</span><span class="sxs-lookup"><span data-stu-id="9b571-113">A subobject restriction is used to perform the recipient table search.</span></span> <span data-ttu-id="9b571-114">因此, 数组的第一个成员指向其**ulSubObject**成员设置为**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 的[SSubRestriction](ssubrestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="9b571-114">Therefore, the first member of the array points to an [SSubRestriction](ssubrestriction.md) structure with its **ulSubObject** member set to **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)).</span></span> <span data-ttu-id="9b571-115">然后, 若要指定要在收件人表中查找的内容, 请使用内容限制。</span><span class="sxs-lookup"><span data-stu-id="9b571-115">Then, to specify what to look for in the recipient table, a content restriction is used.</span></span> 
  
<span data-ttu-id="9b571-116">数组的第二个和第三个成员更简单。</span><span class="sxs-lookup"><span data-stu-id="9b571-116">The second and third members of the array are more straightforward.</span></span> <span data-ttu-id="9b571-117">它们都指向内容限制结构, 一个用于搜索**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 属性设置为 "Sam" 的邮件, 另一个设置为**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性设置为 "volleyball "。</span><span class="sxs-lookup"><span data-stu-id="9b571-117">They both point to content restriction structures, one to search for messages that have a **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) property set to "Sam" and another that has a **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property set to "volleyball."</span></span>
  
<span data-ttu-id="9b571-118">**限制实现**</span><span class="sxs-lookup"><span data-stu-id="9b571-118">**Restriction implementation**</span></span>
  
<span data-ttu-id="9b571-119">![限制实现](media/amapi_61.gif "限制实现")</span><span class="sxs-lookup"><span data-stu-id="9b571-119">![Restriction implementation](media/amapi_61.gif "Restriction implementation")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9b571-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b571-120">See also</span></span>

- [<span data-ttu-id="9b571-121">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="9b571-121">MAPI Tables</span></span>](mapi-tables.md)

