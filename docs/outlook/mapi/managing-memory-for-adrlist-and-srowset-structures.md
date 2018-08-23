---
title: 管理 ADRLIST 和 SRowSet 结构的内存
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: d009f6b6-d151-4d52-b7cc-a15127142354
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ef20cf8460aa7d3d160208109e42b2de66658d54
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589726"
---
# <a name="managing-memory-for-adrlist-and-srowset-structures"></a><span data-ttu-id="b1667-103">管理内存 ADRLIST 和 SRowSet 结构"</span><span class="sxs-lookup"><span data-stu-id="b1667-103">Managing memory for ADRLIST and SRowSet structures"</span></span>

<span data-ttu-id="b1667-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b1667-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b1667-105">为尽可能使用单个**MAPIAllocateBuffer**呼叫缓冲区分配所有内存要求不适用于时使用的地址列表中或**ADRLIST**，和行集或**SRowSet**，结构。</span><span class="sxs-lookup"><span data-stu-id="b1667-105">The requirement to allocate all memory for a buffer whenever possible with a single **MAPIAllocateBuffer** call does not apply when using the address list, or **ADRLIST**, and row set, or **SRowSet**, structures.</span></span> 
  
<span data-ttu-id="b1667-106">以下两个结构是分配和释放内存的标准规则例外。</span><span class="sxs-lookup"><span data-stu-id="b1667-106">These two structures are exceptions to the standard rules for allocating and releasing memory.</span></span> <span data-ttu-id="b1667-107">它们包含多个层次结构的旨在使单个成员都能添加或删除。</span><span class="sxs-lookup"><span data-stu-id="b1667-107">They contain multiple levels of structures and are designed to enable individual members to be added or removed.</span></span> <span data-ttu-id="b1667-108">因此，每个属性必须单独分配。</span><span class="sxs-lookup"><span data-stu-id="b1667-108">Therefore, each property must be a separate allocation.</span></span> 

<span data-ttu-id="b1667-109">其中大多数结构释放调用一次**MAPIFreeBuffer**，每个**ADRLIST**或**SRowSet**结构中的各个条目，必须释放自己调用**MAPIFreeBuffer**或单个调用**FreeProws**或**FreePadrlist**。</span><span class="sxs-lookup"><span data-stu-id="b1667-109">Where most structures are freed with one call to **MAPIFreeBuffer**, each individual entry in an **ADRLIST** or **SRowSet** structure must be freed with its own call to **MAPIFreeBuffer** or a single call to either **FreeProws** or **FreePadrlist**.</span></span> <span data-ttu-id="b1667-110">有关详细信息，请参阅[MAPIFreeBuffer](mapifreebuffer.md)、 [ADRLIST](adrlist.md)和[SRowSet](srowset.md)。</span><span class="sxs-lookup"><span data-stu-id="b1667-110">For more information, see [MAPIFreeBuffer](mapifreebuffer.md), [ADRLIST](adrlist.md), and [SRowSet](srowset.md).</span></span> 

<span data-ttu-id="b1667-111">**FreeProws**和**FreePadrlist**是由 MAPI 提供的用于简化这些数据结构释放的功能。</span><span class="sxs-lookup"><span data-stu-id="b1667-111">**FreeProws** and **FreePadrlist** are functions provided by MAPI for simplifying the freeing of these data structures.</span></span> <span data-ttu-id="b1667-112">有关详细信息，请参阅[FreeProws](freeprows.md)和[FreePadrlist](freepadrlist.md)。</span><span class="sxs-lookup"><span data-stu-id="b1667-112">For more information, see [FreeProws](freeprows.md) and [FreePadrlist](freepadrlist.md).</span></span> <span data-ttu-id="b1667-113">**FreePadrlist**释放**ADRLIST**结构内存以及所有关联的结构成员; 内存**FreeProws**执行相同的**SRowSet**结构。</span><span class="sxs-lookup"><span data-stu-id="b1667-113">**FreePadrlist** frees the memory for the **ADRLIST** structure plus all associated memory for the structure members; **FreeProws** does the same for the **SRowSet** structure.</span></span> 
  
<span data-ttu-id="b1667-114">下图显示了指示所需的单独的内存分配**ADRLIST**数据结构的布局。</span><span class="sxs-lookup"><span data-stu-id="b1667-114">The following diagram shows the layout of an **ADRLIST** data structure, indicating the separate memory allocations required.</span></span> <span data-ttu-id="b1667-115">灰色框中显示可以分配和释放调用一次使用的内存。</span><span class="sxs-lookup"><span data-stu-id="b1667-115">The gray boxes show memory that can be allocated and released with one call.</span></span> 
  
<span data-ttu-id="b1667-116">**ADRLIST 内存分配**</span><span class="sxs-lookup"><span data-stu-id="b1667-116">**ADRLIST memory allocation**</span></span>
  
<span data-ttu-id="b1667-117">![ADRLIST 内存分配](media/amapi_52.gif "ADRLIST 内存分配")</span><span class="sxs-lookup"><span data-stu-id="b1667-117">![ADRLIST memory allocation](media/amapi_52.gif "ADRLIST memory allocation")</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b1667-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1667-118">See also</span></span>

- [<span data-ttu-id="b1667-119">管理 MAPI 中的内存</span><span class="sxs-lookup"><span data-stu-id="b1667-119">Managing Memory in MAPI</span></span>](managing-memory-in-mapi.md)

