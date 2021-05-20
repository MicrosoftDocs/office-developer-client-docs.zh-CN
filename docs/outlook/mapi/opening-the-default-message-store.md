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
# <a name="opening-the-default-message-store"></a><span data-ttu-id="68152-103">打开默认邮件存储</span><span class="sxs-lookup"><span data-stu-id="68152-103">Opening the default message store</span></span>

<span data-ttu-id="68152-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="68152-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="68152-105">在任何特定会话中，一个邮件存储充当默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="68152-105">In any particular session, one message store acts as the default message store.</span></span> <span data-ttu-id="68152-106">默认邮件存储具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="68152-106">A default message store has the following characteristics:</span></span>
  
- <span data-ttu-id="68152-107">[PidTagDefaultStore PR_DEFAULT_STORE (PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 设置为 TRUE。 </span><span class="sxs-lookup"><span data-stu-id="68152-107">The **PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) property is set to TRUE.</span></span>
    
- <span data-ttu-id="68152-108">The STATUS_DEFAULT_STORE flag is set in the **PR_RESOURCE_FLAGS (** [PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span><span class="sxs-lookup"><span data-stu-id="68152-108">The STATUS_DEFAULT_STORE flag is set in the **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.</span></span>
    
- <span data-ttu-id="68152-109">MAPI 会在打开邮件存储时自动为搜索结果、常见视图和个人视图创建 IPM 子树和根文件夹。</span><span class="sxs-lookup"><span data-stu-id="68152-109">MAPI automatically creates the IPM subtree and the root folders for search-results, common views and personal views when the message store is opened.</span></span> <span data-ttu-id="68152-110">有关这些文件夹详细信息，请参阅 [IPM 子树](ipm-subtree.md) 和 [MAPI 特殊文件夹](mapi-special-folders.md)。</span><span class="sxs-lookup"><span data-stu-id="68152-110">For more information about these folders, see [IPM Subtree](ipm-subtree.md) and [MAPI Special Folders](mapi-special-folders.md).</span></span> 
    
<span data-ttu-id="68152-111">若要检索默认邮件存储的条目标识符，必须调用 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 以打开邮件存储表，在调用 [HrQueryAllRows](hrqueryallrows.md)时应用适当的限制。</span><span class="sxs-lookup"><span data-stu-id="68152-111">To retrieve the entry identifier for the default message store, you must call [IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md) to open the message store table and apply an appropriate restriction in a call to [HrQueryAllRows](hrqueryallrows.md).</span></span> <span data-ttu-id="68152-112">**HrQueryAllRows** 将返回一个行集，该行代表默认邮件存储。</span><span class="sxs-lookup"><span data-stu-id="68152-112">**HrQueryAllRows** will return a row set with the one row that represents the default message store.</span></span> <span data-ttu-id="68152-113">传递给 **HrQueryAllRows 的限制** 可以针对以下表单之一：</span><span class="sxs-lookup"><span data-stu-id="68152-113">The restriction that you pass to **HrQueryAllRows** can take on one of the following forms:</span></span> 
  
1. <span data-ttu-id="68152-114">使用 **SAndRestriction 结构进行组合** 的 **AND** 限制：</span><span class="sxs-lookup"><span data-stu-id="68152-114">An **AND** restriction that uses an **SAndRestriction** structure to combine:</span></span> 
    
   - <span data-ttu-id="68152-115">存在一个使用 **SExistRestriction** 结构来测试是否存在 PR_DEFAULT_STORE **属性的限制** 。</span><span class="sxs-lookup"><span data-stu-id="68152-115">An exists restriction that uses an **SExistRestriction** structure to test for the existence of the **PR_DEFAULT_STORE** property.</span></span> 
    
   - <span data-ttu-id="68152-116">使用 [SPropertyRestriction](spropertyrestriction.md)结构检查属性中的 TRUE 值 **PR_DEFAULT_STORE限制。**</span><span class="sxs-lookup"><span data-stu-id="68152-116">A property restriction that uses an [SPropertyRestriction](spropertyrestriction.md) structure to check for the TRUE value in the **PR_DEFAULT_STORE** property.</span></span> 
    
2. <span data-ttu-id="68152-117">一个位掩码限制，它使用 [SBitMaskRestriction](sbitmaskrestriction.md)结构对 STATUS_DEFAULT_STORE 属性应用该 **PR_RESOURCE_FLAGS掩码。**</span><span class="sxs-lookup"><span data-stu-id="68152-117">A bitmask restriction that uses an [SBitMaskRestriction](sbitmaskrestriction.md) structure for applying STATUS_DEFAULT_STORE as a mask against the **PR_RESOURCE_FLAGS** property.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="68152-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="68152-118">See also</span></span>

- [<span data-ttu-id="68152-119">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="68152-119">SExistRestriction</span></span>](sexistrestriction.md)
- [<span data-ttu-id="68152-120">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="68152-120">SAndRestriction</span></span>](sandrestriction.md)

