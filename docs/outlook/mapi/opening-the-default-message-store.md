---
title: 打开默认的邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 670fb896-9aaf-4a96-83f7-76237409e956
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 1eb4e150be68ea01060c7afaed489c8759b576db
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776540"
---
# <a name="opening-the-default-message-store"></a><span data-ttu-id="e5e58-103">打开默认的邮件存储</span><span class="sxs-lookup"><span data-stu-id="e5e58-103">Opening the default message store</span></span>

<span data-ttu-id="e5e58-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e5e58-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e5e58-105">在任何特定的会话中一个消息存储用作默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="e5e58-105">In any particular session, one message store acts as the default message store.</span></span> <span data-ttu-id="e5e58-106">默认邮件存储区具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="e5e58-106">A default message store has the following characteristics:</span></span>
  
- <span data-ttu-id="e5e58-107">**PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="e5e58-107">The **PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) property is set to TRUE.</span></span>
    
- <span data-ttu-id="e5e58-108">**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置了 STATUS_DEFAULT_STORE 标志。</span><span class="sxs-lookup"><span data-stu-id="e5e58-108">The STATUS_DEFAULT_STORE flag is set in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="e5e58-109">打开消息存储库时，MAPI 自动创建 IPM 子树和搜索结果、 公共视图和个人视图的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="e5e58-109">MAPI automatically creates the IPM subtree and the root folders for search-results, common views and personal views when the message store is opened.</span></span> <span data-ttu-id="e5e58-110">有关这些文件夹的详细信息，请参阅[IPM 子树](ipm-subtree.md)和[MAPI 特殊文件夹](mapi-special-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="e5e58-110">For more information about these folders, see [IPM Subtree](ipm-subtree.md) and [MAPI Special Folders](mapi-special-folders.md).</span></span> 
    
<span data-ttu-id="e5e58-111">若要检索默认的邮件存储的项标识符，必须调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)打开的消息存储表格并应用[HrQueryAllRows](hrqueryallrows.md)将调用适当的限制。</span><span class="sxs-lookup"><span data-stu-id="e5e58-111">To retrieve the entry identifier for the default message store, you must call [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) to open the message store table and apply an appropriate restriction in a call to [HrQueryAllRows](hrqueryallrows.md).</span></span> <span data-ttu-id="e5e58-112">**HrQueryAllRows**将返回的行集与表示默认的邮件存储的一个行。</span><span class="sxs-lookup"><span data-stu-id="e5e58-112">**HrQueryAllRows** will return a row set with the one row that represents the default message store.</span></span> <span data-ttu-id="e5e58-113">传递给**HrQueryAllRows**限制可以采用以下形式之一：</span><span class="sxs-lookup"><span data-stu-id="e5e58-113">The restriction that you pass to **HrQueryAllRows** can take on one of the following forms:</span></span> 
  
1. <span data-ttu-id="e5e58-114">使用**SAndRestriction**结构组合**和**限制：</span><span class="sxs-lookup"><span data-stu-id="e5e58-114">An **AND** restriction that uses an **SAndRestriction** structure to combine:</span></span> 
    
   - <span data-ttu-id="e5e58-115">存在使用**SExistRestriction**结构**PR_DEFAULT_STORE**属性是否存在测试的限制。</span><span class="sxs-lookup"><span data-stu-id="e5e58-115">An exists restriction that uses an **SExistRestriction** structure to test for the existence of the **PR_DEFAULT_STORE** property.</span></span> 
    
   - <span data-ttu-id="e5e58-116">使用[SPropertyRestriction](spropertyrestriction.md)结构**PR_DEFAULT_STORE**属性中的则返回 TRUE 值来检查属性限制。</span><span class="sxs-lookup"><span data-stu-id="e5e58-116">A property restriction that uses an [SPropertyRestriction](spropertyrestriction.md) structure to check for the TRUE value in the **PR_DEFAULT_STORE** property.</span></span> 
    
2. <span data-ttu-id="e5e58-117">位掩码限制为针对**PR_RESOURCE_FLAGS**属性掩码应用 STATUS_DEFAULT_STORE 使用[SBitMaskRestriction](sbitmaskrestriction.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e5e58-117">A bitmask restriction that uses an [SBitMaskRestriction](sbitmaskrestriction.md) structure for applying STATUS_DEFAULT_STORE as a mask against the **PR_RESOURCE_FLAGS** property.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="e5e58-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5e58-118">See also</span></span>

- [<span data-ttu-id="e5e58-119">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="e5e58-119">SExistRestriction</span></span>](sexistrestriction.md)
- [<span data-ttu-id="e5e58-120">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="e5e58-120">SAndRestriction</span></span>](sandrestriction.md)

