---
title: OLFI
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 44bfaadf-36f9-bd8e-6158-646533f6849e
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: ff23472254df2bd9d2195c7cf2c4258b856ec430
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776548"
---
# <a name="olfi"></a><span data-ttu-id="31245-103">OLFI</span><span class="sxs-lookup"><span data-stu-id="31245-103">OLFI</span></span>

  
  
<span data-ttu-id="31245-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="31245-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="31245-105">个人文件夹文件 (PST) 存储提供程序用于分配新的邮件或文件夹在脱机模式下的条目 ID 的长期 ID 结构的队列。</span><span class="sxs-lookup"><span data-stu-id="31245-105">Queue of long-term ID structures used by the Personal Folders file (PST) store provider to assign an Entry ID for a new message or folder in offline mode.</span></span>
  
## <a name="quick-info"></a><span data-ttu-id="31245-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="31245-106">Quick info</span></span>

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

## <a name="members"></a><span data-ttu-id="31245-107">成员</span><span class="sxs-lookup"><span data-stu-id="31245-107">Members</span></span>

 <span data-ttu-id="31245-108">_ulVersion_</span><span class="sxs-lookup"><span data-stu-id="31245-108">_ulVersion_</span></span>
  
- <span data-ttu-id="31245-109">结构的版本号。</span><span class="sxs-lookup"><span data-stu-id="31245-109">Version number for the structure.</span></span> 
    
 <span data-ttu-id="31245-110">_muidReserved_</span><span class="sxs-lookup"><span data-stu-id="31245-110">_muidReserved_</span></span>
  
- <span data-ttu-id="31245-111">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="31245-111">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="31245-112">_ulReserved_</span><span class="sxs-lookup"><span data-stu-id="31245-112">_ulReserved_</span></span>
  
- <span data-ttu-id="31245-113">此成员仅供内部使用的 Outlook，不支持。</span><span class="sxs-lookup"><span data-stu-id="31245-113">This member is reserved for the internal use of Outlook and is not supported.</span></span>
    
 <span data-ttu-id="31245-114">_dwAlloc_</span><span class="sxs-lookup"><span data-stu-id="31245-114">_dwAlloc_</span></span>
  
- <span data-ttu-id="31245-115">供分配的条目数。</span><span class="sxs-lookup"><span data-stu-id="31245-115">The number of entries that are available for allocation.</span></span> <span data-ttu-id="31245-116">这些条目共享相同的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="31245-116">These entries share the same globally unique identifier (GUID).</span></span>
    
 <span data-ttu-id="31245-117">_dwNextAlloc_</span><span class="sxs-lookup"><span data-stu-id="31245-117">_dwNextAlloc_</span></span>
  
- <span data-ttu-id="31245-118">分配下一步是可用的条目数。</span><span class="sxs-lookup"><span data-stu-id="31245-118">The number of entries that are available next for allocation.</span></span> <span data-ttu-id="31245-119">这些条目共享相同的 GUID。</span><span class="sxs-lookup"><span data-stu-id="31245-119">These entries share the same GUID.</span></span>
    
 <span data-ttu-id="31245-120">_ltidAlloc_</span><span class="sxs-lookup"><span data-stu-id="31245-120">_ltidAlloc_</span></span>
  
- <span data-ttu-id="31245-121">长期 ID 结构， **[LTID](ltid.md)**，标识当前可用于分配条目。</span><span class="sxs-lookup"><span data-stu-id="31245-121">The long-term ID structure, **[LTID](ltid.md)**, identifying the entry currently available for allocation.</span></span> <span data-ttu-id="31245-122">长期 ID 结构包含一个 GUID 和识别存储区中的对象的索引。</span><span class="sxs-lookup"><span data-stu-id="31245-122">The long-term ID structure contains a GUID and an index identifying an object in the store.</span></span> <span data-ttu-id="31245-123">在一起，GUID 和索引形成对象的唯一的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="31245-123">Together, the GUID and the index can form a unique Entry ID for an object.</span></span> 
    
 <span data-ttu-id="31245-124">_ltidNextAlloc_</span><span class="sxs-lookup"><span data-stu-id="31245-124">_ltidNextAlloc_</span></span>
  
- <span data-ttu-id="31245-125">标识的下一个可用的条目的长期 ID 结构。</span><span class="sxs-lookup"><span data-stu-id="31245-125">Long-term ID structure identifying the next available entry.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="31245-126">备注</span><span class="sxs-lookup"><span data-stu-id="31245-126">Remarks</span></span>

<span data-ttu-id="31245-127">条目 ID 是 4 字节 MAPI 项标识符的文件夹或一条消息。</span><span class="sxs-lookup"><span data-stu-id="31245-127">An Entry ID is a 4-byte MAPI entry identifier for a folder or a message.</span></span> <span data-ttu-id="31245-128">有关详细信息，请参阅[ENTRYID](http://msdn.microsoft.com/en-us/library/ms836424)。</span><span class="sxs-lookup"><span data-stu-id="31245-128">For more information, see [ENTRYID](http://msdn.microsoft.com/en-us/library/ms836424).</span></span>
  
<span data-ttu-id="31245-129">当 PST 存储提供程序将条目 ID 分配给一个新的对象时，首先需要标识服务器的 GUID 和标识存储区中的对象的索引。</span><span class="sxs-lookup"><span data-stu-id="31245-129">When a PST store provider assigns an Entry ID to a new object, it first needs a GUID that identifies the server, and an index that identifies the object in the store.</span></span> <span data-ttu-id="31245-130">即使跨所有条目 Id GUID 不唯一，GUID 和索引组合将提供一个唯一的项。</span><span class="sxs-lookup"><span data-stu-id="31245-130">Even though the GUID is not unique across all Entry IDs, the GUID and the index combined provide a unique entry.</span></span> <span data-ttu-id="31245-131">此 GUID 和索引对跟踪通过长期的 ID 结构**LTID**，这是**OLFI**结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="31245-131">This GUID and index pair is tracked by a long-term ID structure, **LTID**, which is part of the **OLFI** structure.</span></span> 
  
<span data-ttu-id="31245-132">PST 存储提供程序不会从物理上隔离保留**OLFI**中的每个 GUID 索引对**LTID**结构。</span><span class="sxs-lookup"><span data-stu-id="31245-132">The PST store provider does not physically keep in **OLFI** an **LTID** structure for each GUID-index pair.</span></span> <span data-ttu-id="31245-133">它会保留一个**LTID**结构， *ltidAlloc* ，当前第一个可用的 GUID 索引对;count， *dwAlloc* ，可用共享此相同的 GUID; 的项的数目和第二个**LTID**结构*ltidNextAlloc*下, 一步的可用 GUID 索引对具有不同的 GUID。</span><span class="sxs-lookup"><span data-stu-id="31245-133">It keeps one **LTID** structure,  *ltidAlloc*  , for the currently first available GUID-index pair; a count,  *dwAlloc*  , of the number of available entries that share this same GUID; and a second **LTID** structure,  *ltidNextAlloc*  , for the next available GUID-index pair that has a different GUID.</span></span> <span data-ttu-id="31245-134">PST 存储提供程序使用**OLFI**结构，以跟踪 Guid 和它具有分发的索引。在虚拟级别，提供程序维护储备数**LTID**结构已准备好进行分配。</span><span class="sxs-lookup"><span data-stu-id="31245-134">The PST store provider uses the **OLFI** structure to track the GUIDs and indexes that it has handed out. At a virtual level, the provider maintains a reserve of a number of **LTID** structures that are ready to be allocated.</span></span>  <span data-ttu-id="31245-135">*dwAlloc*维护可用**LTID**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="31245-135">*dwAlloc*  maintains a count of the available **LTID** structures.</span></span> 
  
<span data-ttu-id="31245-136">请求条目 Id 前置块中。</span><span class="sxs-lookup"><span data-stu-id="31245-136">Requests for Entry IDs come in blocks.</span></span> <span data-ttu-id="31245-137">存在块的请求时，请 PST 存储提供程序将检查是否存在足够保留现有通过比较*dwAlloc*与请求的大小。</span><span class="sxs-lookup"><span data-stu-id="31245-137">When there is a request for a block, the PST store provider checks if there is sufficient reserve on hand by comparing the requested size with  *dwAlloc*  .</span></span> <span data-ttu-id="31245-138">如果没有足够的保留，它返回 GUID 和索引中的分配*ltidAlloc* 。</span><span class="sxs-lookup"><span data-stu-id="31245-138">If there is sufficient reserve, it returns the GUID and index in  *ltidAlloc*  for allocation.</span></span> <span data-ttu-id="31245-139">然后*dwAlloc*减少请求的大小，并在*ltidAlloc*索引递增请求的大小。</span><span class="sxs-lookup"><span data-stu-id="31245-139">It then decreases  *dwAlloc*  by the requested size, and increments the index in  *ltidAlloc*  by the requested size.</span></span> <span data-ttu-id="31245-140">此准备的条目 Id 的另一个块分配下一个请求*ltidAlloc* PST 存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="31245-140">This prepares the PST store provider to allocate  *ltidAlloc*  on the next request for another block of Entry IDs.</span></span> <span data-ttu-id="31245-141">请注意 GUID 保持不变的下一个请求。</span><span class="sxs-lookup"><span data-stu-id="31245-141">Note that the GUID remains the same for the next request.</span></span> 
  
<span data-ttu-id="31245-142">如果请求的大小大于*dwAlloc* ，PST 存储提供程序尝试使用它在下一步具有的作预备，由*dwNextAlloc*和*ltidNextAlloc*指定。</span><span class="sxs-lookup"><span data-stu-id="31245-142">If the size of a request is larger than  *dwAlloc*  , the PST store provider tries to use what it has next in reserve, as specified by  *dwNextAlloc*  and  *ltidNextAlloc*  .</span></span> <span data-ttu-id="31245-143">它分别将*dwNextAlloc*和*ltidNextAlloc*复制到*dwAlloc*和*ltidAlloc* ，并将*dwNextAlloc*和*ltidNextAlloc*设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="31245-143">It copies  *dwNextAlloc*  and  *ltidNextAlloc*  to  *dwAlloc*  and  *ltidAlloc*  respectively, and sets  *dwNextAlloc*  and  *ltidNextAlloc*  to NULL.</span></span> 
  
<span data-ttu-id="31245-144">换行的 PST 存储提供程序的提供程序应定期检查*ltidNextAlloc*为 NULL。</span><span class="sxs-lookup"><span data-stu-id="31245-144">A provider that wraps the PST store provider should periodically check  *ltidNextAlloc*  to see if it is NULL.</span></span> <span data-ttu-id="31245-145">如果是，提供程序应填充使用新的 GUID，并重置*dwNextAlloc* ，以便可以分配多个条目 Id。</span><span class="sxs-lookup"><span data-stu-id="31245-145">If it is, the provider should populate it with a new GUID and reset  *dwNextAlloc*  so that more entry IDs can be allocated.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="31245-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31245-146">See also</span></span>



[<span data-ttu-id="31245-147">有关复制 API</span><span class="sxs-lookup"><span data-stu-id="31245-147">About the Replication API</span></span>](about-the-replication-api.md)
  
[<span data-ttu-id="31245-148">有关的复制状态机</span><span class="sxs-lookup"><span data-stu-id="31245-148">About the Replication State Machine</span></span>](about-the-replication-state-machine.md)
  
[<span data-ttu-id="31245-149">LTID</span><span class="sxs-lookup"><span data-stu-id="31245-149">LTID</span></span>](ltid.md)

