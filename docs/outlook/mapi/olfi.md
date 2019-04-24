---
title: OLFI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 44bfaadf-36f9-bd8e-6158-646533f6849e
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 027905721b5730b4c3d78f496022b88a8e6b84d6
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279751"
---
# <a name="olfi"></a><span data-ttu-id="65fbf-103">OLFI</span><span class="sxs-lookup"><span data-stu-id="65fbf-103">OLFI</span></span>

  
  
<span data-ttu-id="65fbf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="65fbf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="65fbf-105">个人文件夹文件 (PST) 存储提供程序用于为脱机模式中的新邮件或文件夹分配条目 id 的长期 ID 结构队列。</span><span class="sxs-lookup"><span data-stu-id="65fbf-105">Queue of long-term ID structures used by the Personal Folders file (PST) store provider to assign an Entry ID for a new message or folder in offline mode.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="65fbf-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="65fbf-106">Quick info</span></span>

```cpp
typedef struct { 
    ULONG    ulVersion; 
    MAPIUID  muidReserved; 
    ULONG    ulReserved; 
    DWORD    dwAlloc; 
    DWORD    dwNextAlloc; 
    LTID     ltidAlloc; 
    LTID     ltidNextAlloc; 
} OLFI, *POLFI;
```

## <a name="members"></a><span data-ttu-id="65fbf-107">成员</span><span class="sxs-lookup"><span data-stu-id="65fbf-107">Members</span></span>

 <span data-ttu-id="65fbf-108">_ulVersion_</span><span class="sxs-lookup"><span data-stu-id="65fbf-108">_ulVersion_</span></span>
  
- <span data-ttu-id="65fbf-109">结构的版本号。</span><span class="sxs-lookup"><span data-stu-id="65fbf-109">Version number for the structure.</span></span> 
    
 <span data-ttu-id="65fbf-110">_muidReserved_</span><span class="sxs-lookup"><span data-stu-id="65fbf-110">_muidReserved_</span></span>
  
- <span data-ttu-id="65fbf-111">此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="65fbf-111">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="65fbf-112">_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="65fbf-112">_ulReserved_</span></span>
  
- <span data-ttu-id="65fbf-113">此成员是为内部使用 Outlook 而保留的, 不受支持。</span><span class="sxs-lookup"><span data-stu-id="65fbf-113">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="65fbf-114">_dwAlloc_</span><span class="sxs-lookup"><span data-stu-id="65fbf-114">_dwAlloc_</span></span>
  
- <span data-ttu-id="65fbf-115">可分配的条目数。</span><span class="sxs-lookup"><span data-stu-id="65fbf-115">The number of entries that are available for allocation.</span></span> <span data-ttu-id="65fbf-116">这些条目共享相同的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="65fbf-116">These entries share the same globally unique identifier (GUID).</span></span>
    
 <span data-ttu-id="65fbf-117">_dwNextAlloc_</span><span class="sxs-lookup"><span data-stu-id="65fbf-117">_dwNextAlloc_</span></span>
  
- <span data-ttu-id="65fbf-118">用于分配的下一个条目的数量。</span><span class="sxs-lookup"><span data-stu-id="65fbf-118">The number of entries that are available next for allocation.</span></span> <span data-ttu-id="65fbf-119">这些条目共享相同的 GUID。</span><span class="sxs-lookup"><span data-stu-id="65fbf-119">These entries share the same GUID.</span></span>
    
 <span data-ttu-id="65fbf-120">_ltidAlloc_</span><span class="sxs-lookup"><span data-stu-id="65fbf-120">_ltidAlloc_</span></span>
  
- <span data-ttu-id="65fbf-121">长期 ID 结构, **[LTID](ltid.md)**, 用于标识当前可供分配的条目。</span><span class="sxs-lookup"><span data-stu-id="65fbf-121">The long-term ID structure, **[LTID](ltid.md)**, identifying the entry currently available for allocation.</span></span> <span data-ttu-id="65fbf-122">长期 ID 结构包含一个 GUID 和一个索引, 用于标识存储区中的对象。</span><span class="sxs-lookup"><span data-stu-id="65fbf-122">The long-term ID structure contains a GUID and an index identifying an object in the store.</span></span> <span data-ttu-id="65fbf-123">GUID 和索引可以构成对象的唯一条目 ID。</span><span class="sxs-lookup"><span data-stu-id="65fbf-123">Together, the GUID and the index can form a unique Entry ID for an object.</span></span> 
    
 <span data-ttu-id="65fbf-124">_ltidNextAlloc_</span><span class="sxs-lookup"><span data-stu-id="65fbf-124">_ltidNextAlloc_</span></span>
  
- <span data-ttu-id="65fbf-125">长期 ID 结构, 用于标识下一个可用的条目。</span><span class="sxs-lookup"><span data-stu-id="65fbf-125">Long-term ID structure identifying the next available entry.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="65fbf-126">注解</span><span class="sxs-lookup"><span data-stu-id="65fbf-126">Remarks</span></span>

<span data-ttu-id="65fbf-127">条目 ID 是文件夹或邮件的4字节 MAPI 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="65fbf-127">An Entry ID is a 4-byte MAPI entry identifier for a folder or a message.</span></span> <span data-ttu-id="65fbf-128">有关详细信息, 请参阅[ENTRYID](https://msdn.microsoft.com/library/ms836424)。</span><span class="sxs-lookup"><span data-stu-id="65fbf-128">For more information, see [ENTRYID](https://msdn.microsoft.com/library/ms836424).</span></span>
  
<span data-ttu-id="65fbf-129">当 PST 存储提供程序将条目 ID 分配给新对象时, 它首先需要一个标识服务器的 GUID 以及一个标识存储中的对象的索引。</span><span class="sxs-lookup"><span data-stu-id="65fbf-129">When a PST store provider assigns an Entry ID to a new object, it first needs a GUID that identifies the server, and an index that identifies the object in the store.</span></span> <span data-ttu-id="65fbf-130">尽管 guid 在所有条目 id 中不是唯一的, 但 guid 和索引组合提供了唯一的条目。</span><span class="sxs-lookup"><span data-stu-id="65fbf-130">Even though the GUID is not unique across all Entry IDs, the GUID and the index combined provide a unique entry.</span></span> <span data-ttu-id="65fbf-131">此 GUID 和索引对由长期 ID 结构 ( **LTID**) 跟踪, 后者是**OLFI**结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="65fbf-131">This GUID and index pair is tracked by a long-term ID structure, **LTID**, which is part of the **OLFI** structure.</span></span> 
  
<span data-ttu-id="65fbf-132">PST 存储提供程序不会在物理上保留每个 GUID 索引对的**LTID**结构**OLFI** 。</span><span class="sxs-lookup"><span data-stu-id="65fbf-132">The PST store provider does not physically keep in **OLFI** an **LTID** structure for each GUID-index pair.</span></span> <span data-ttu-id="65fbf-133">它保留一个**LTID**结构*ltidAlloc* , 用于当前的第一个可用的 GUID 索引对;共享此同一 GUID 的可用条目数的计数、 *dwAlloc* 、第二个**LTID**结构, *ltidNextAlloc* , 用于具有不同 guid 的下一个可用的 guid 索引对。</span><span class="sxs-lookup"><span data-stu-id="65fbf-133">It keeps one **LTID** structure,  *ltidAlloc*  , for the currently first available GUID-index pair; a count,  *dwAlloc*  , of the number of available entries that share this same GUID; and a second **LTID** structure,  *ltidNextAlloc*  , for the next available GUID-index pair that has a different GUID.</span></span> <span data-ttu-id="65fbf-134">PST 存储提供程序使用**OLFI**结构跟踪已提交的 guid 和索引。在虚拟级别, 提供程序保留准备分配的大量**LTID**结构的保留。</span><span class="sxs-lookup"><span data-stu-id="65fbf-134">The PST store provider uses the **OLFI** structure to track the GUIDs and indexes that it has handed out. At a virtual level, the provider maintains a reserve of a number of **LTID** structures that are ready to be allocated.</span></span>  <span data-ttu-id="65fbf-135">*dwAlloc*维护可用的**LTID**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="65fbf-135">*dwAlloc*  maintains a count of the available **LTID** structures.</span></span> 
  
<span data-ttu-id="65fbf-136">条目 id 请求进入块。</span><span class="sxs-lookup"><span data-stu-id="65fbf-136">Requests for Entry IDs come in blocks.</span></span> <span data-ttu-id="65fbf-137">当对块发出请求时, PST 存储提供程序将通过将请求的大小与*dwAlloc*进行比较来检查是否有足够的预留。</span><span class="sxs-lookup"><span data-stu-id="65fbf-137">When there is a request for a block, the PST store provider checks if there is sufficient reserve on hand by comparing the requested size with  *dwAlloc*  .</span></span> <span data-ttu-id="65fbf-138">如果有足够的准备金, 它将在*ltidAlloc*中返回 GUID 和索引以进行分配。</span><span class="sxs-lookup"><span data-stu-id="65fbf-138">If there is sufficient reserve, it returns the GUID and index in  *ltidAlloc*  for allocation.</span></span> <span data-ttu-id="65fbf-139">然后, 它将*dwAlloc*减小请求的大小, 并根据请求的大小增加*ltidAlloc*中的索引。</span><span class="sxs-lookup"><span data-stu-id="65fbf-139">It then decreases  *dwAlloc*  by the requested size, and increments the index in  *ltidAlloc*  by the requested size.</span></span> <span data-ttu-id="65fbf-140">这将为 PST 存储提供程序准备在下一个条目 id 块的下一个请求上分配*ltidAlloc* 。</span><span class="sxs-lookup"><span data-stu-id="65fbf-140">This prepares the PST store provider to allocate  *ltidAlloc*  on the next request for another block of Entry IDs.</span></span> <span data-ttu-id="65fbf-141">请注意, 对于下一个请求, GUID 保持不变。</span><span class="sxs-lookup"><span data-stu-id="65fbf-141">Note that the GUID remains the same for the next request.</span></span> 
  
<span data-ttu-id="65fbf-142">如果请求的大小大于*dwAlloc* , PST 存储提供程序将尝试使用*dwNextAlloc*和*ltidNextAlloc*指定的下一个保留内容。</span><span class="sxs-lookup"><span data-stu-id="65fbf-142">If the size of a request is larger than  *dwAlloc*  , the PST store provider tries to use what it has next in reserve, as specified by  *dwNextAlloc*  and  *ltidNextAlloc*  .</span></span> <span data-ttu-id="65fbf-143">它分别将*dwNextAlloc*和*ltidNextAlloc*复制到*dwAlloc*和*ltidAlloc* , 并将*dwNextAlloc*和*ltidNextAlloc*设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="65fbf-143">It copies  *dwNextAlloc*  and  *ltidNextAlloc*  to  *dwAlloc*  and  *ltidAlloc*  respectively, and sets  *dwNextAlloc*  and  *ltidNextAlloc*  to NULL.</span></span> 
  
<span data-ttu-id="65fbf-144">包装 PST 存储提供程序的提供程序应定期检查*ltidNextAlloc* , 以查看它是否为 NULL。</span><span class="sxs-lookup"><span data-stu-id="65fbf-144">A provider that wraps the PST store provider should periodically check  *ltidNextAlloc*  to see if it is NULL.</span></span> <span data-ttu-id="65fbf-145">如果是, 则提供程序应使用新的 GUID 填充它并重置*dwNextAlloc* , 以便可以分配更多的条目 id。</span><span class="sxs-lookup"><span data-stu-id="65fbf-145">If it is, the provider should populate it with a new GUID and reset  *dwNextAlloc*  so that more entry IDs can be allocated.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="65fbf-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65fbf-146">See also</span></span>



[<span data-ttu-id="65fbf-147">关于复制 API</span><span class="sxs-lookup"><span data-stu-id="65fbf-147">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="65fbf-148">关于复制状态机</span><span class="sxs-lookup"><span data-stu-id="65fbf-148">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="65fbf-149">LTID</span><span class="sxs-lookup"><span data-stu-id="65fbf-149">LTID</span></span>](ltid.md)

