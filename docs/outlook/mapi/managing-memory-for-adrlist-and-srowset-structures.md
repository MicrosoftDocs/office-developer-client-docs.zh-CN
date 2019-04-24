---
title: 管理 ADRLIST 和 SRowSet 结构的内存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d009f6b6-d151-4d52-b7cc-a15127142354
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a5636cad7cad23bb5114bdbd34aff48c3639773b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32298124"
---
# <a name="managing-memory-for-adrlist-and-srowset-structures"></a><span data-ttu-id="bb867-103">管理 ADRLIST 和 SRowSet 结构的内存</span><span class="sxs-lookup"><span data-stu-id="bb867-103">Managing memory for ADRLIST and SRowSet structures"</span></span>

<span data-ttu-id="bb867-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb867-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb867-105">如果使用单个**MAPIAllocateBuffer**调用时, 需要为缓冲区分配所有内存, 如果使用地址列表、 **ADRLIST**、行集或**SRowSet**, 则不适用。</span><span class="sxs-lookup"><span data-stu-id="bb867-105">The requirement to allocate all memory for a buffer whenever possible with a single **MAPIAllocateBuffer** call does not apply when using the address list, or **ADRLIST**, and row set, or **SRowSet**, structures.</span></span> 
  
<span data-ttu-id="bb867-106">这两个结构是用于分配和释放内存的标准规则的例外。</span><span class="sxs-lookup"><span data-stu-id="bb867-106">These two structures are exceptions to the standard rules for allocating and releasing memory.</span></span> <span data-ttu-id="bb867-107">它们包含多个级别的结构, 旨在允许添加或删除单个成员。</span><span class="sxs-lookup"><span data-stu-id="bb867-107">They contain multiple levels of structures and are designed to enable individual members to be added or removed.</span></span> <span data-ttu-id="bb867-108">因此, 每个属性都必须是单独的分配。</span><span class="sxs-lookup"><span data-stu-id="bb867-108">Therefore, each property must be a separate allocation.</span></span> 

<span data-ttu-id="bb867-109">在使用一次调用**MAPIFreeBuffer**释放大部分结构后, **ADRLIST**或**SRowSet**结构中的每个单独条目都必须使用自己的**MAPIFreeBuffer**调用或对**FreeProws** **的单个调用进行释放, 或者FreePadrlist**。</span><span class="sxs-lookup"><span data-stu-id="bb867-109">Where most structures are freed with one call to **MAPIFreeBuffer**, each individual entry in an **ADRLIST** or **SRowSet** structure must be freed with its own call to **MAPIFreeBuffer** or a single call to either **FreeProws** or **FreePadrlist**.</span></span> <span data-ttu-id="bb867-110">有关详细信息, 请参阅[MAPIFreeBuffer](mapifreebuffer.md)、 [ADRLIST](adrlist.md)和[SRowSet](srowset.md)。</span><span class="sxs-lookup"><span data-stu-id="bb867-110">For more information, see [MAPIFreeBuffer](mapifreebuffer.md), [ADRLIST](adrlist.md), and [SRowSet](srowset.md).</span></span> 

<span data-ttu-id="bb867-111">**FreeProws**和**FreePadrlist**是 MAPI 提供的用于简化这些数据结构的释放的函数。</span><span class="sxs-lookup"><span data-stu-id="bb867-111">**FreeProws** and **FreePadrlist** are functions provided by MAPI for simplifying the freeing of these data structures.</span></span> <span data-ttu-id="bb867-112">有关详细信息, 请参阅[FreeProws](freeprows.md)和[FreePadrlist](freepadrlist.md)。</span><span class="sxs-lookup"><span data-stu-id="bb867-112">For more information, see [FreeProws](freeprows.md) and [FreePadrlist](freepadrlist.md).</span></span> <span data-ttu-id="bb867-113">**FreePadrlist**释放**ADRLIST**结构的内存以及结构成员的所有关联内存;**FreeProws**对**SRowSet**结构进行相同的工作。</span><span class="sxs-lookup"><span data-stu-id="bb867-113">**FreePadrlist** frees the memory for the **ADRLIST** structure plus all associated memory for the structure members; **FreeProws** does the same for the **SRowSet** structure.</span></span> 
  
<span data-ttu-id="bb867-114">下图显示了**ADRLIST**数据结构的布局, 指示需要单独的内存分配。</span><span class="sxs-lookup"><span data-stu-id="bb867-114">The following diagram shows the layout of an **ADRLIST** data structure, indicating the separate memory allocations required.</span></span> <span data-ttu-id="bb867-115">灰色框显示可通过一次调用分配和释放的内存。</span><span class="sxs-lookup"><span data-stu-id="bb867-115">The gray boxes show memory that can be allocated and released with one call.</span></span> 
  
<span data-ttu-id="bb867-116">**ADRLIST 内存分配**</span><span class="sxs-lookup"><span data-stu-id="bb867-116">**ADRLIST memory allocation**</span></span>
  
<span data-ttu-id="bb867-117">![ADRLIST 内存分配](media/amapi_52.gif "ADRLIST 内存分配")</span><span class="sxs-lookup"><span data-stu-id="bb867-117">![ADRLIST memory allocation](media/amapi_52.gif "ADRLIST memory allocation")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb867-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb867-118">See also</span></span>

- [<span data-ttu-id="bb867-119">管理 MAPI 中的内存</span><span class="sxs-lookup"><span data-stu-id="bb867-119">Managing Memory in MAPI</span></span>](managing-memory-in-mapi.md)

