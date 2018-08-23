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
ms.openlocfilehash: 371d0305f8f00e66704bae03f93857c7275b6a10
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589817"
---
# <a name="flatentrylist"></a><span data-ttu-id="bfa10-103">FLATENTRYLIST</span><span class="sxs-lookup"><span data-stu-id="bfa10-103">FLATENTRYLIST</span></span>

<span data-ttu-id="bfa10-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bfa10-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bfa10-105">包含一个[FLATENTRY](flatentry.md)结构数组。</span><span class="sxs-lookup"><span data-stu-id="bfa10-105">Contains an array of [FLATENTRY](flatentry.md) structures.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bfa10-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="bfa10-106">Header file:</span></span>  <br/> |<span data-ttu-id="bfa10-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bfa10-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="bfa10-108">相关的宏：</span><span class="sxs-lookup"><span data-stu-id="bfa10-108">Related macros:</span></span>  <br/> |<span data-ttu-id="bfa10-109">[CbFLATENTRYLIST](cbflatentrylist.md) [CbNewFLATENTRYLIST](cbnewflatentrylist.md)</span><span class="sxs-lookup"><span data-stu-id="bfa10-109">[CbFLATENTRYLIST](cbflatentrylist.md), [CbNewFLATENTRYLIST](cbnewflatentrylist.md)</span></span> <br/> |
   
```cpp
typedef struct
{
  ULONG cEntries;
  ULONG cbEntries;
  BYTE abEntries[MAPI_DIM];
} FLATENTRYLIST, FAR *LPFLATENTRYLIST;

```

## <a name="members"></a><span data-ttu-id="bfa10-110">Members</span><span class="sxs-lookup"><span data-stu-id="bfa10-110">Members</span></span>

<span data-ttu-id="bfa10-111">**cEntries**</span><span class="sxs-lookup"><span data-stu-id="bfa10-111">**cEntries**</span></span>
  
> <span data-ttu-id="bfa10-112">**FLATENTRY**结构由**abEntries**成员描述该数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="bfa10-112">Count of **FLATENTRY** structures in the array described by the **abEntries** member.</span></span> 
    
<span data-ttu-id="bfa10-113">**cbEntries**</span><span class="sxs-lookup"><span data-stu-id="bfa10-113">**cbEntries**</span></span>
  
> <span data-ttu-id="bfa10-114">描述**abEntries**数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="bfa10-114">Count of bytes in the array described by **abEntries**.</span></span> 
    
<span data-ttu-id="bfa10-115">**abEntries**</span><span class="sxs-lookup"><span data-stu-id="bfa10-115">**abEntries**</span></span>
  
> <span data-ttu-id="bfa10-116">字节数组，其中包含一个或多个**FLATENTRY**结构排列的端到端。</span><span class="sxs-lookup"><span data-stu-id="bfa10-116">Byte array that contains one or more **FLATENTRY** structures, arranged end to end.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="bfa10-117">注解</span><span class="sxs-lookup"><span data-stu-id="bfa10-117">Remarks</span></span>

<span data-ttu-id="bfa10-118">在**abEntries**数组中，每个**FLATENTRY**结构自然地对齐边界上对齐。</span><span class="sxs-lookup"><span data-stu-id="bfa10-118">In the **abEntries** array, each **FLATENTRY** structure is aligned on a naturally aligned boundary.</span></span> <span data-ttu-id="bfa10-119">额外字节都作为包含填充使任意两个**FLATENTRY**结构之间的确保自然对齐。</span><span class="sxs-lookup"><span data-stu-id="bfa10-119">Extra bytes are included as padding to make sure natural alignment between any two **FLATENTRY** structures.</span></span> <span data-ttu-id="bfa10-120">该数组中的第一个**FLATENTRY**结构对齐始终正确，因为**abEntries**成员的偏移量为 8。</span><span class="sxs-lookup"><span data-stu-id="bfa10-120">The first **FLATENTRY** structure in the array is always aligned correctly because the offset of the **abEntries** member is 8.</span></span> <span data-ttu-id="bfa10-121">若要计算的偏移量的下一个结构，使用向上舍入到 4 的下一步的倍数的第一个条目的大小。</span><span class="sxs-lookup"><span data-stu-id="bfa10-121">To compute the offset of the next structure, use the size of the first entry rounded up to the next multiple of 4.</span></span> <span data-ttu-id="bfa10-122">使用[CbFLATENTRY](cbflatentry.md)宏来计算**FLATENTRY**结构的大小。</span><span class="sxs-lookup"><span data-stu-id="bfa10-122">Use the [CbFLATENTRY](cbflatentry.md) macro to compute the size of a **FLATENTRY** structure.</span></span> 
  
<span data-ttu-id="bfa10-123">例如，第二个**FLATENTRY**结构开始在偏移量为组成的第一个条目的偏移量以及舍入到下一步的四个字节的第一个条目的长度。</span><span class="sxs-lookup"><span data-stu-id="bfa10-123">For example, the second **FLATENTRY** structure starts at an offset that consists of the offset of the first entry plus the length of the first entry rounded to the next four bytes.</span></span> <span data-ttu-id="bfa10-124">第一个条目的长度是其**cb**成员长度加上其**abEntry**成员的长度。</span><span class="sxs-lookup"><span data-stu-id="bfa10-124">The length of the first entry is the length of its **cb** member plus the length of its **abEntry** member.</span></span> 
  
<span data-ttu-id="bfa10-125">下面的代码示例指示如何计算**FLATENTRYLIST**结构中的偏移量。</span><span class="sxs-lookup"><span data-stu-id="bfa10-125">The following code sample indicates how to compute offsets in a **FLATENTRYLIST** structure.</span></span> <span data-ttu-id="bfa10-126">假定该_lpFlatEntry_是指向列表中的第一个结构的指针。</span><span class="sxs-lookup"><span data-stu-id="bfa10-126">Assume that  _lpFlatEntry_ is a pointer to the first structure in the list.</span></span> 
  
```cpp
(offsetof(lpFlatEntry->ab) // for example, 4
+ lpFlatEntry->cb // size of lpFlatEntry->ab 
+ 4) & ~3 // round to next 4 byte boundary
```

## <a name="see-also"></a><span data-ttu-id="bfa10-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfa10-127">See also</span></span>

- [<span data-ttu-id="bfa10-128">FLATENTRY</span><span class="sxs-lookup"><span data-stu-id="bfa10-128">FLATENTRY</span></span>](flatentry.md)
- [<span data-ttu-id="bfa10-129">PidTagReplyRecipientEntries 规范属性</span><span class="sxs-lookup"><span data-stu-id="bfa10-129">PidTagReplyRecipientEntries Canonical Property</span></span>](pidtagreplyrecipiententries-canonical-property.md)
- [<span data-ttu-id="bfa10-130">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="bfa10-130">MAPI Structures</span></span>](mapi-structures.md)

