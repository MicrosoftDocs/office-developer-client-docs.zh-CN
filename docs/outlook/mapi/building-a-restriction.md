---
title: 构建限制
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 12abbd8c-f825-493e-af42-344371d9658e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 3b40c8433f93237db2ae4fd5449fe8a0da486539
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774614"
---
# <a name="building-a-restriction"></a><span data-ttu-id="0931c-103">构建限制</span><span class="sxs-lookup"><span data-stu-id="0931c-103">Building a restriction</span></span>

<span data-ttu-id="0931c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0931c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0931c-105">若要构建限制，客户端应用程序创建的各种类型的一个或多个限制结构层次结构，并将指针传递给[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)方法的层次结构。</span><span class="sxs-lookup"><span data-stu-id="0931c-105">To build a restriction, a client application creates a hierarchy of one or more restriction structures of various types and passes a pointer to the hierarchy to the [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md) method.</span></span> <span data-ttu-id="0931c-106">下面的图和[限制的示例代码](sample-restriction-code.md)中的代码示例演示如何与不同类型的链接的限制结构实施的典型的限制。</span><span class="sxs-lookup"><span data-stu-id="0931c-106">The illustration that follows and the code sample in [Sample Restriction Code](sample-restriction-code.md) demonstrate how a typical restriction is implemented with linked restriction structures of different types.</span></span> 

<span data-ttu-id="0931c-107">本示例中，客户端应用程序的用户正尝试查找包含单词"排球"的主题行中和从 Sam 发送到 Sue 所有邮件。</span><span class="sxs-lookup"><span data-stu-id="0931c-107">In this example, a user of a client application is trying to find all messages that contain the word "volleyball" in the subject line and were sent to Sue from Sam.</span></span> <span data-ttu-id="0931c-108">首先，分配泛型[SRestriction](srestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="0931c-108">First, a generic [SRestriction](srestriction.md) structure is allocated.</span></span> <span data-ttu-id="0931c-109">此结构将成为对[MAPIAllocateMore](mapiallocatemore.md)函数的其他调用一次对[MAPIFreeBuffer](mapifreebuffer.md)创建链接的[SRestriction](srestriction.md)和[SPropValue](spropvalue.md)结构可释放的基础。</span><span class="sxs-lookup"><span data-stu-id="0931c-109">This structure becomes the basis for other calls to the [MAPIAllocateMore](mapiallocatemore.md) function to create linked [SRestriction](srestriction.md) and [SPropValue](spropvalue.md) structures that can be freed with a single call to [MAPIFreeBuffer](mapifreebuffer.md).</span></span> <span data-ttu-id="0931c-110">要应用于的消息集条件分为三个部分，因为顶部级别限制结构是**和**限制。</span><span class="sxs-lookup"><span data-stu-id="0931c-110">Because the criteria to apply to the set of messages is in three parts, the top level restriction structure is an **AND** restriction.</span></span> <span data-ttu-id="0931c-111">[SAndRestriction](sandrestriction.md)结构的**cRes**成员设置为 3，以指示用于计算的三个限制和其**lpRes**成员设置为**SRestriction**结构的三个成员数组。</span><span class="sxs-lookup"><span data-stu-id="0931c-111">The [SAndRestriction](sandrestriction.md) structure's **cRes** member is set to 3 to indicate the three restrictions to evaluate and its **lpRes** member is set to a three member array of **SRestriction** structures.</span></span> 
  
<span data-ttu-id="0931c-112">若要搜索发送到特定收件人的邮件，必要时搜索每条消息，而不是邮件本身的收件人表。</span><span class="sxs-lookup"><span data-stu-id="0931c-112">To search for messages that are sent to a particular recipient, it is necessary to search the recipient table for each message rather than the message itself.</span></span> <span data-ttu-id="0931c-113">子对象限制用于执行收件人表搜索。</span><span class="sxs-lookup"><span data-stu-id="0931c-113">A subobject restriction is used to perform the recipient table search.</span></span> <span data-ttu-id="0931c-114">因此，该数组指向[SSubRestriction](ssubrestriction.md)结构具有其**ulSubObject**成员的第一个成员设置为**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="0931c-114">Therefore, the first member of the array points to an [SSubRestriction](ssubrestriction.md) structure with its **ulSubObject** member set to **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)).</span></span> <span data-ttu-id="0931c-115">然后，若要指定要在收件人的表中查找的内容，请使用内容的限制。</span><span class="sxs-lookup"><span data-stu-id="0931c-115">Then, to specify what to look for in the recipient table, a content restriction is used.</span></span> 
  
<span data-ttu-id="0931c-116">数组的第二个和第三个成员是更简单。</span><span class="sxs-lookup"><span data-stu-id="0931c-116">The second and third members of the array are more straightforward.</span></span> <span data-ttu-id="0931c-117">都指向内容限制结构，之一来搜索邮件已具有**PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) 属性设置为**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) 属性设置为"Sam"，另一个"排球。"</span><span class="sxs-lookup"><span data-stu-id="0931c-117">They both point to content restriction structures, one to search for messages that have a **PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md)) property set to "Sam" and another that has a **PR_SUBJECT** ([PidTagSubject](pidtagsubject-canonical-property.md)) property set to "volleyball."</span></span>
  
<span data-ttu-id="0931c-118">**限制实现**</span><span class="sxs-lookup"><span data-stu-id="0931c-118">**Restriction implementation**</span></span>
  
<span data-ttu-id="0931c-119">![限制实现](media/amapi_61.gif "限制实现")</span><span class="sxs-lookup"><span data-stu-id="0931c-119">![Restriction implementation](media/amapi_61.gif "Restriction implementation")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0931c-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0931c-120">See also</span></span>

- [<span data-ttu-id="0931c-121">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="0931c-121">MAPI Tables</span></span>](mapi-tables.md)

