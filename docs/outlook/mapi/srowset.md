---
title: SRowSet
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SRowSet
api_type:
- COM
ms.assetid: 7e3761be-afd6-46cb-9a08-25e9016c1241
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5c634fe200dde4bfe6f190f8bfa9e5dfa0868db4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778886"
---
# <a name="srowset"></a><span data-ttu-id="c60ef-103">SRowSet</span><span class="sxs-lookup"><span data-stu-id="c60ef-103">SRowSet</span></span>

  
  
<span data-ttu-id="c60ef-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c60ef-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c60ef-105">包含一个[SRow](srow.md)结构数组。</span><span class="sxs-lookup"><span data-stu-id="c60ef-105">Contains an array of [SRow](srow.md) structures.</span></span> <span data-ttu-id="c60ef-106">每个**SRow**结构介绍表中的行。</span><span class="sxs-lookup"><span data-stu-id="c60ef-106">Each **SRow** structure describes a row from a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c60ef-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="c60ef-107">Header file:</span></span>  <br/> |<span data-ttu-id="c60ef-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c60ef-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="c60ef-109">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="c60ef-109">Related macros:</span></span>  <br/> |<span data-ttu-id="c60ef-110">[CbNewSRowSet](cbnewsrowset.md)， [CbSRowSet](cbsrowset.md)， [SizedSRowSet](sizedsrowset.md)</span><span class="sxs-lookup"><span data-stu-id="c60ef-110">[CbNewSRowSet](cbnewsrowset.md), [CbSRowSet](cbsrowset.md), [SizedSRowSet](sizedsrowset.md)</span></span> <br/> |
   
```cpp
typedef struct _SRowSet
{
  ULONG cRows;
  SRow aRow[MAPI_DIM];
} SRowSet, FAR *LPSRowSet;

```

## <a name="members"></a><span data-ttu-id="c60ef-111">Members</span><span class="sxs-lookup"><span data-stu-id="c60ef-111">Members</span></span>

 <span data-ttu-id="c60ef-112">**cRows**</span><span class="sxs-lookup"><span data-stu-id="c60ef-112">**cRows**</span></span>
  
> <span data-ttu-id="c60ef-113">**SRow**结构**aRow**成员中的计数。</span><span class="sxs-lookup"><span data-stu-id="c60ef-113">Count of **SRow** structures in the **aRow** member.</span></span> 
    
 <span data-ttu-id="c60ef-114">**aRow**</span><span class="sxs-lookup"><span data-stu-id="c60ef-114">**aRow**</span></span>
  
> <span data-ttu-id="c60ef-115">**SRow**结构的数组。</span><span class="sxs-lookup"><span data-stu-id="c60ef-115">Array of **SRow** structures.</span></span> <span data-ttu-id="c60ef-116">没有一个结构表中的各行。</span><span class="sxs-lookup"><span data-stu-id="c60ef-116">There is one structure for each row in the table.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="c60ef-117">说明</span><span class="sxs-lookup"><span data-stu-id="c60ef-117">Remarks</span></span>

<span data-ttu-id="c60ef-118">**SRowSet**结构用于描述多个表中的数据行。</span><span class="sxs-lookup"><span data-stu-id="c60ef-118">An **SRowSet** structure is used to describe multiple rows of data from a table.</span></span> <span data-ttu-id="c60ef-119">**SRowSet**结构[IAddrBook](iaddrbookimapiprop.md)、 [ITableData](itabledataiunknown.md)和[IMAPITable](imapitableiunknown.md)接口方法，除了以下函数中使用：</span><span class="sxs-lookup"><span data-stu-id="c60ef-119">**SRowSet** structures are used in the [IAddrBook](iaddrbookimapiprop.md), [ITableData](itabledataiunknown.md), and [IMAPITable](imapitableiunknown.md) interface methods, in addition to the following functions:</span></span> 
  
- [<span data-ttu-id="c60ef-120">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="c60ef-120">HrQueryAllRows</span></span>](hrqueryallrows.md)
    
- [<span data-ttu-id="c60ef-121">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="c60ef-121">FBadRowSet</span></span>](fbadrowset.md)
    
- [<span data-ttu-id="c60ef-122">FreeProws</span><span class="sxs-lookup"><span data-stu-id="c60ef-122">FreeProws</span></span>](freeprows.md)
    
 <span data-ttu-id="c60ef-123">定义**SRowSet**结构[ADRLIST](adrlist.md)结构，以允许将地址列表中的收件人的表和项的行视为相同的相同。</span><span class="sxs-lookup"><span data-stu-id="c60ef-123">**SRowSet** structures are defined the same as [ADRLIST](adrlist.md) structures to allow the rows of a recipient table and the entries in an address list to be treated the same.</span></span> <span data-ttu-id="c60ef-124">**SRowSet**结构和**ADRLIST**结构可以传递给[IAddrBook::Address](iaddrbook-address.md) [IMessage::ModifyRecipients](imessage-modifyrecipients.md)等的方法。</span><span class="sxs-lookup"><span data-stu-id="c60ef-124">Both **SRowSet** structures and **ADRLIST** structures can be passed to methods such as [IMessage::ModifyRecipients](imessage-modifyrecipients.md) and [IAddrBook::Address](iaddrbook-address.md).</span></span> 
  
<span data-ttu-id="c60ef-125">此外， **SRowSet**结构的内存分配的规则都与**ADRLIST**结构相同。</span><span class="sxs-lookup"><span data-stu-id="c60ef-125">Also, the rules for memory allocation for **SRowSet** structures are the same as for **ADRLIST** structures.</span></span> <span data-ttu-id="c60ef-126">总之，必须单独使用[MAPIAllocateBuffer](mapiallocatebuffer.md)分配指向由**lpProps**成员的每一行的行中设置该数组中每个[SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="c60ef-126">To summarize, each [SPropValue](spropvalue.md) structure in the array pointed to by the **lpProps** member of each row in the row set must be allocated separately using [MAPIAllocateBuffer](mapiallocatebuffer.md).</span></span> <span data-ttu-id="c60ef-127">此外必须使用[MAPIFreeBuffer](mapifreebuffer.md)其**SRowSet**结构的释放之前，以便不会丢失指向分配**SPropValue**结构释放每个属性值结构。</span><span class="sxs-lookup"><span data-stu-id="c60ef-127">Each property value structure must also be deallocated using [MAPIFreeBuffer](mapifreebuffer.md) before the deallocation of its **SRowSet** structure so that pointers to the allocated **SPropValue** structures are not lost.</span></span> <span data-ttu-id="c60ef-128">行的分配内存可以随后可保留并重用**SRowSet**结构的上下文之外。</span><span class="sxs-lookup"><span data-stu-id="c60ef-128">A row's allocated memory can then be preserved and reused outside the context of the **SRowSet** structure.</span></span> 
  
<span data-ttu-id="c60ef-129">有关应分配的内存**SRowSet**结构的方式的详细信息，请参阅[管理内存 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="c60ef-129">For more information about how the memory for **SRowSet** structures should be allocated, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="c60ef-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c60ef-130">See also</span></span>



[<span data-ttu-id="c60ef-131">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="c60ef-131">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="c60ef-132">SPropValue</span><span class="sxs-lookup"><span data-stu-id="c60ef-132">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="c60ef-133">SRow</span><span class="sxs-lookup"><span data-stu-id="c60ef-133">SRow</span></span>](srow.md)
  
[<span data-ttu-id="c60ef-134">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="c60ef-134">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="c60ef-135">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="c60ef-135">MAPIFreeBuffer</span></span>](mapifreebuffer.md)


[<span data-ttu-id="c60ef-136">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="c60ef-136">MAPI Structures</span></span>](mapi-structures.md)

