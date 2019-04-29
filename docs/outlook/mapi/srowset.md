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
ms.openlocfilehash: 63cef6ef2bb26e8b723c60fe01dd6771aa070ae8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407254"
---
# <a name="srowset"></a><span data-ttu-id="d696f-103">SRowSet</span><span class="sxs-lookup"><span data-stu-id="d696f-103">SRowSet</span></span>

  
  
<span data-ttu-id="d696f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d696f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d696f-105">包含[SRow](srow.md)结构的数组。</span><span class="sxs-lookup"><span data-stu-id="d696f-105">Contains an array of [SRow](srow.md) structures.</span></span> <span data-ttu-id="d696f-106">每个**SRow**结构描述表中的行。</span><span class="sxs-lookup"><span data-stu-id="d696f-106">Each **SRow** structure describes a row from a table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d696f-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d696f-107">Header file:</span></span>  <br/> |<span data-ttu-id="d696f-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d696f-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d696f-109">相关宏:</span><span class="sxs-lookup"><span data-stu-id="d696f-109">Related macros:</span></span>  <br/> |<span data-ttu-id="d696f-110">[CbNewSRowSet](cbnewsrowset.md)、 [CbSRowSet](cbsrowset.md)、 [SizedSRowSet](sizedsrowset.md)</span><span class="sxs-lookup"><span data-stu-id="d696f-110">[CbNewSRowSet](cbnewsrowset.md), [CbSRowSet](cbsrowset.md), [SizedSRowSet](sizedsrowset.md)</span></span> <br/> |
   
```cpp
typedef struct _SRowSet
{
  ULONG cRows;
  SRow aRow[MAPI_DIM];
} SRowSet, FAR *LPSRowSet;

```

## <a name="members"></a><span data-ttu-id="d696f-111">Members</span><span class="sxs-lookup"><span data-stu-id="d696f-111">Members</span></span>

 <span data-ttu-id="d696f-112">**cRows**</span><span class="sxs-lookup"><span data-stu-id="d696f-112">**cRows**</span></span>
  
> <span data-ttu-id="d696f-113">**aRow**成员中的**SRow**结构的计数。</span><span class="sxs-lookup"><span data-stu-id="d696f-113">Count of **SRow** structures in the **aRow** member.</span></span> 
    
 <span data-ttu-id="d696f-114">**aRow**</span><span class="sxs-lookup"><span data-stu-id="d696f-114">**aRow**</span></span>
  
> <span data-ttu-id="d696f-115">**SRow**结构的数组。</span><span class="sxs-lookup"><span data-stu-id="d696f-115">Array of **SRow** structures.</span></span> <span data-ttu-id="d696f-116">表中的每一行都有一个结构。</span><span class="sxs-lookup"><span data-stu-id="d696f-116">There is one structure for each row in the table.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d696f-117">说明</span><span class="sxs-lookup"><span data-stu-id="d696f-117">Remarks</span></span>

<span data-ttu-id="d696f-118">**SRowSet**结构用于描述表中的多行数据。</span><span class="sxs-lookup"><span data-stu-id="d696f-118">An **SRowSet** structure is used to describe multiple rows of data from a table.</span></span> <span data-ttu-id="d696f-119">除了以下函数之外, 还可以在[IAddrBook](iaddrbookimapiprop.md)、 [ITableData](itabledataiunknown.md)和[IMAPITable](imapitableiunknown.md)接口方法中使用**SRowSet**结构:</span><span class="sxs-lookup"><span data-stu-id="d696f-119">**SRowSet** structures are used in the [IAddrBook](iaddrbookimapiprop.md), [ITableData](itabledataiunknown.md), and [IMAPITable](imapitableiunknown.md) interface methods, in addition to the following functions:</span></span> 
  
- [<span data-ttu-id="d696f-120">HrQueryAllRows</span><span class="sxs-lookup"><span data-stu-id="d696f-120">HrQueryAllRows</span></span>](hrqueryallrows.md)
    
- [<span data-ttu-id="d696f-121">FBadRowSet</span><span class="sxs-lookup"><span data-stu-id="d696f-121">FBadRowSet</span></span>](fbadrowset.md)
    
- [<span data-ttu-id="d696f-122">FreeProws</span><span class="sxs-lookup"><span data-stu-id="d696f-122">FreeProws</span></span>](freeprows.md)
    
 <span data-ttu-id="d696f-123">**SRowSet**结构的定义与[ADRLIST](adrlist.md)结构相同, 以允许收件人表的行和地址列表中的条目被视为相同。</span><span class="sxs-lookup"><span data-stu-id="d696f-123">**SRowSet** structures are defined the same as [ADRLIST](adrlist.md) structures to allow the rows of a recipient table and the entries in an address list to be treated the same.</span></span> <span data-ttu-id="d696f-124">**SRowSet**结构和**ADRLIST**结构都可以传递给方法, 如[IMessage:: ModifyRecipients](imessage-modifyrecipients.md)和[IAddrBook:: Address](iaddrbook-address.md)。</span><span class="sxs-lookup"><span data-stu-id="d696f-124">Both **SRowSet** structures and **ADRLIST** structures can be passed to methods such as [IMessage::ModifyRecipients](imessage-modifyrecipients.md) and [IAddrBook::Address](iaddrbook-address.md).</span></span> 
  
<span data-ttu-id="d696f-125">此外, 为**SRowSet**结构分配的内存规则与**ADRLIST**结构的规则相同。</span><span class="sxs-lookup"><span data-stu-id="d696f-125">Also, the rules for memory allocation for **SRowSet** structures are the same as for **ADRLIST** structures.</span></span> <span data-ttu-id="d696f-126">总而言之, 必须使用[MAPIAllocateBuffer](mapiallocatebuffer.md)分别分配行集中每行的**lpProps**成员所指向的数组中的每个[SPropValue](spropvalue.md)结构。</span><span class="sxs-lookup"><span data-stu-id="d696f-126">To summarize, each [SPropValue](spropvalue.md) structure in the array pointed to by the **lpProps** member of each row in the row set must be allocated separately using [MAPIAllocateBuffer](mapiallocatebuffer.md).</span></span> <span data-ttu-id="d696f-127">在取消分配其**SRowSet**结构之前, 还必须使用[MAPIFreeBuffer](mapifreebuffer.md)释放每个属性值结构, 这样, 指向分配的**SPropValue**结构的指针不会丢失。</span><span class="sxs-lookup"><span data-stu-id="d696f-127">Each property value structure must also be deallocated using [MAPIFreeBuffer](mapifreebuffer.md) before the deallocation of its **SRowSet** structure so that pointers to the allocated **SPropValue** structures are not lost.</span></span> <span data-ttu-id="d696f-128">然后, 可以保留行的已分配内存, 并在**SRowSet**结构的上下文外部重用它。</span><span class="sxs-lookup"><span data-stu-id="d696f-128">A row's allocated memory can then be preserved and reused outside the context of the **SRowSet** structure.</span></span> 
  
<span data-ttu-id="d696f-129">有关应如何分配**SRowSet**结构的内存的详细信息, 请参阅[管理内存用于 ADRLIST 和 SRowSet 结构](managing-memory-for-adrlist-and-srowset-structures.md)。</span><span class="sxs-lookup"><span data-stu-id="d696f-129">For more information about how the memory for **SRowSet** structures should be allocated, see [Managing Memory for ADRLIST and SRowSet Structures](managing-memory-for-adrlist-and-srowset-structures.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d696f-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d696f-130">See also</span></span>



[<span data-ttu-id="d696f-131">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="d696f-131">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="d696f-132">SPropValue</span><span class="sxs-lookup"><span data-stu-id="d696f-132">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="d696f-133">SRow</span><span class="sxs-lookup"><span data-stu-id="d696f-133">SRow</span></span>](srow.md)
  
[<span data-ttu-id="d696f-134">MAPIAllocateBuffer</span><span class="sxs-lookup"><span data-stu-id="d696f-134">MAPIAllocateBuffer</span></span>](mapiallocatebuffer.md)
  
[<span data-ttu-id="d696f-135">MAPIFreeBuffer</span><span class="sxs-lookup"><span data-stu-id="d696f-135">MAPIFreeBuffer</span></span>](mapifreebuffer.md)


[<span data-ttu-id="d696f-136">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="d696f-136">MAPI Structures</span></span>](mapi-structures.md)

