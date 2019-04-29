---
title: 打开默认邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 670fb896-9aaf-4a96-83f7-76237409e956
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d8e620516e2b3e61cd07f3a08af989cc4ed5b61e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436025"
---
# <a name="opening-the-default-message-store"></a><span data-ttu-id="73f95-103">打开默认邮件存储</span><span class="sxs-lookup"><span data-stu-id="73f95-103">Opening the default message store</span></span>

<span data-ttu-id="73f95-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="73f95-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="73f95-105">在任何特定的会话中, 一个邮件存储将充当默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="73f95-105">In any particular session, one message store acts as the default message store.</span></span> <span data-ttu-id="73f95-106">默认邮件存储区具有以下特征:</span><span class="sxs-lookup"><span data-stu-id="73f95-106">A default message store has the following characteristics:</span></span>
  
- <span data-ttu-id="73f95-107">**PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="73f95-107">The **PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) property is set to TRUE.</span></span>
    
- <span data-ttu-id="73f95-108">在**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 STATUS_DEFAULT_STORE 标志。</span><span class="sxs-lookup"><span data-stu-id="73f95-108">The STATUS_DEFAULT_STORE flag is set in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="73f95-109">MAPI 在打开邮件库时, 会自动为搜索结果、常见视图和个人视图创建 IPM 子树和根文件夹。</span><span class="sxs-lookup"><span data-stu-id="73f95-109">MAPI automatically creates the IPM subtree and the root folders for search-results, common views and personal views when the message store is opened.</span></span> <span data-ttu-id="73f95-110">有关这些文件夹的详细信息, 请参阅[IPM 子树](ipm-subtree.md)和[MAPI 特殊文件夹](mapi-special-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="73f95-110">For more information about these folders, see [IPM Subtree](ipm-subtree.md) and [MAPI Special Folders](mapi-special-folders.md).</span></span> 
    
<span data-ttu-id="73f95-111">若要检索默认邮件存储的条目标识符, 必须调用[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)打开邮件存储表, 并在对[HrQueryAllRows](hrqueryallrows.md)的调用中应用适当的限制。</span><span class="sxs-lookup"><span data-stu-id="73f95-111">To retrieve the entry identifier for the default message store, you must call [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) to open the message store table and apply an appropriate restriction in a call to [HrQueryAllRows](hrqueryallrows.md).</span></span> <span data-ttu-id="73f95-112">**HrQueryAllRows**将返回行集, 其中的一行表示默认邮件存储区。</span><span class="sxs-lookup"><span data-stu-id="73f95-112">**HrQueryAllRows** will return a row set with the one row that represents the default message store.</span></span> <span data-ttu-id="73f95-113">传递给**HrQueryAllRows**的限制可采用以下形式之一:</span><span class="sxs-lookup"><span data-stu-id="73f95-113">The restriction that you pass to **HrQueryAllRows** can take on one of the following forms:</span></span> 
  
1. <span data-ttu-id="73f95-114">一个**和**限制, 它使用**SAndRestriction**结构来进行组合:</span><span class="sxs-lookup"><span data-stu-id="73f95-114">An **AND** restriction that uses an **SAndRestriction** structure to combine:</span></span> 
    
   - <span data-ttu-id="73f95-115">存在一个限制, 它使用**SExistRestriction**结构来测试**PR_DEFAULT_STORE**属性是否存在。</span><span class="sxs-lookup"><span data-stu-id="73f95-115">An exists restriction that uses an **SExistRestriction** structure to test for the existence of the **PR_DEFAULT_STORE** property.</span></span> 
    
   - <span data-ttu-id="73f95-116">使用[SPropertyRestriction](spropertyrestriction.md)结构检查**PR_DEFAULT_STORE**属性中的 TRUE 值的属性限制。</span><span class="sxs-lookup"><span data-stu-id="73f95-116">A property restriction that uses an [SPropertyRestriction](spropertyrestriction.md) structure to check for the TRUE value in the **PR_DEFAULT_STORE** property.</span></span> 
    
2. <span data-ttu-id="73f95-117">一个位掩码限制, 它使用[SBitMaskRestriction](sbitmaskrestriction.md)结构将 STATUS_DEFAULT_STORE 应用于**PR_RESOURCE_FLAGS**属性的掩码。</span><span class="sxs-lookup"><span data-stu-id="73f95-117">A bitmask restriction that uses an [SBitMaskRestriction](sbitmaskrestriction.md) structure for applying STATUS_DEFAULT_STORE as a mask against the **PR_RESOURCE_FLAGS** property.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="73f95-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="73f95-118">See also</span></span>

- [<span data-ttu-id="73f95-119">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="73f95-119">SExistRestriction</span></span>](sexistrestriction.md)
- [<span data-ttu-id="73f95-120">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="73f95-120">SAndRestriction</span></span>](sandrestriction.md)

