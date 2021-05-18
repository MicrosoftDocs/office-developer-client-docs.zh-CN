---
title: FLATENTRYLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLATENTRYLIST
api_type:
- COM
ms.assetid: b465d015-9b62-4986-b0df-118121f60602
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bc511ea4b3ec4eea9e38f744bcb8f277108085cc
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413855"
---
# <a name="flatentrylist"></a><span data-ttu-id="1b5a3-103">FLATENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="1b5a3-103">FLATENTRYLIST</span></span>

<span data-ttu-id="1b5a3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b5a3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b5a3-105">包含 [FLATENTRY 结构](flatentry.md) 数组。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-105">Contains an array of [FLATENTRY](flatentry.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1b5a3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1b5a3-106">Header file:</span></span>  <br/> |<span data-ttu-id="1b5a3-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1b5a3-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="1b5a3-108">相关宏：</span><span class="sxs-lookup"><span data-stu-id="1b5a3-108">Related macros:</span></span>  <br/> |<span data-ttu-id="1b5a3-109">[CbFLATENTRYLIST](cbflatentrylist.md) [、CbNewFLATENTRYLIST](cbnewflatentrylist.md)</span><span class="sxs-lookup"><span data-stu-id="1b5a3-109">[CbFLATENTRYLIST](cbflatentrylist.md), [CbNewFLATENTRYLIST](cbnewflatentrylist.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cEntries;
  ULONG cbEntries;
  BYTE abEntries[MAPI_DIM];
} FLATENTRYLIST, FAR *LPFLATENTRYLIST;

```

## <a name="members"></a><span data-ttu-id="1b5a3-110">Members</span><span class="sxs-lookup"><span data-stu-id="1b5a3-110">Members</span></span>

<span data-ttu-id="1b5a3-111">**cEntries**</span><span class="sxs-lookup"><span data-stu-id="1b5a3-111">**cEntries**</span></span>
  
> <span data-ttu-id="1b5a3-112">**abEntries** 成员描述的数组中的 **FLATENTRY** 结构计数。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-112">Count of **FLATENTRY** structures in the array described by the **abEntries** member.</span></span> 
    
<span data-ttu-id="1b5a3-113">**cbEntries**</span><span class="sxs-lookup"><span data-stu-id="1b5a3-113">**cbEntries**</span></span>
  
> <span data-ttu-id="1b5a3-114">abEntries 描述的数组中的 **字节数**。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-114">Count of bytes in the array described by **abEntries**.</span></span> 
    
<span data-ttu-id="1b5a3-115">**abEntries**</span><span class="sxs-lookup"><span data-stu-id="1b5a3-115">**abEntries**</span></span>
  
> <span data-ttu-id="1b5a3-116">包含一个或多个 **FLATENTRY** 结构的字节数组，端到端排列。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-116">Byte array that contains one or more **FLATENTRY** structures, arranged end to end.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="1b5a3-117">备注</span><span class="sxs-lookup"><span data-stu-id="1b5a3-117">Remarks</span></span>

<span data-ttu-id="1b5a3-118">在 **abEntries** 数组中，每个 **FLATENTRY** 结构在自然对齐的边界上对齐。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-118">In the **abEntries** array, each **FLATENTRY** structure is aligned on a naturally aligned boundary.</span></span> <span data-ttu-id="1b5a3-119">额外字节作为填充包括在内，以确保任何两个 **FLATENTRY** 结构之间的自然对齐。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-119">Extra bytes are included as padding to make sure natural alignment between any two **FLATENTRY** structures.</span></span> <span data-ttu-id="1b5a3-120">数组中的第一个 **FLATENTRY** 结构始终正确对齐，因为 **abEntries** 成员偏移量为 8。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-120">The first **FLATENTRY** structure in the array is always aligned correctly because the offset of the **abEntries** member is 8.</span></span> <span data-ttu-id="1b5a3-121">若要计算下一结构的偏移量，请使用向上舍入到下一个 4 倍数的第一个条目的大小。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-121">To compute the offset of the next structure, use the size of the first entry rounded up to the next multiple of 4.</span></span> <span data-ttu-id="1b5a3-122">使用 [CbFLATENTRY](cbflatentry.md) 宏计算 **FLATENTRY** 结构的大小。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-122">Use the [CbFLATENTRY](cbflatentry.md) macro to compute the size of a **FLATENTRY** structure.</span></span> 
  
<span data-ttu-id="1b5a3-123">例如，第二 **个 FLATENTRY** 结构从偏移开始，该偏移由第一个条目的偏移量加上舍入到后四个字节的第一个条目的长度组成。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-123">For example, the second **FLATENTRY** structure starts at an offset that consists of the offset of the first entry plus the length of the first entry rounded to the next four bytes.</span></span> <span data-ttu-id="1b5a3-124">第一个条目的长度是 **cb** 成员的长度及其 **abEntry 成员** 的长度。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-124">The length of the first entry is the length of its **cb** member plus the length of its **abEntry** member.</span></span> 
  
<span data-ttu-id="1b5a3-125">下面的代码示例指示如何在 **FLATENTRYLIST** 结构中计算偏移。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-125">The following code sample indicates how to compute offsets in a **FLATENTRYLIST** structure.</span></span> <span data-ttu-id="1b5a3-126">假定  _lpFlatEntry_ 是指向列表中第一个结构的指针。</span><span class="sxs-lookup"><span data-stu-id="1b5a3-126">Assume that  _lpFlatEntry_ is a pointer to the first structure in the list.</span></span> 
  
```cpp
(offsetof(lpFlatEntry->ab) // for example, 4
+ lpFlatEntry->cb // size of lpFlatEntry->ab 
+ 4) & ~3 // round to next 4 byte boundary
```

## <a name="see-also"></a><span data-ttu-id="1b5a3-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b5a3-127">See also</span></span>

- [<span data-ttu-id="1b5a3-128">FLATENTRY</span><span class="sxs-lookup"><span data-stu-id="1b5a3-128">FLATENTRY</span></span>](flatentry.md)
- [<span data-ttu-id="1b5a3-129">PidTagReplyRecipientEntries 规范属性</span><span class="sxs-lookup"><span data-stu-id="1b5a3-129">PidTagReplyRecipientEntries Canonical Property</span></span>](pidtagreplyrecipiententries-canonical-property.md)
- [<span data-ttu-id="1b5a3-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="1b5a3-130">MAPI Structures</span></span>](mapi-structures.md)

