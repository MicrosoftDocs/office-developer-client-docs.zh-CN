---
title: SSizeRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SSizeRestriction
api_type:
- COM
ms.assetid: 4e7340d1-3cb9-4276-b83f-1c8f94acb909
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 24ceb7b5358447de3a240756227b86224d2c354c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439084"
---
# <a name="ssizerestriction"></a><span data-ttu-id="3349f-103">SSizeRestriction</span><span class="sxs-lookup"><span data-stu-id="3349f-103">SSizeRestriction</span></span>

  
  
<span data-ttu-id="3349f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3349f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3349f-105">描述用于测试属性值大小的大小限制。</span><span class="sxs-lookup"><span data-stu-id="3349f-105">Describes a size restriction which is used to test the size of a property value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3349f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="3349f-106">Header file:</span></span>  <br/> |<span data-ttu-id="3349f-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3349f-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SSizeRestriction
{
  ULONG relop;
  ULONG ulPropTag;
  ULONG cb;
} SSizeRestriction;

```

## <a name="members"></a><span data-ttu-id="3349f-108">Members</span><span class="sxs-lookup"><span data-stu-id="3349f-108">Members</span></span>

 <span data-ttu-id="3349f-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="3349f-109">**relop**</span></span>
  
> <span data-ttu-id="3349f-110">大小比较中使用的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="3349f-110">Relational operator that is used in the size comparison.</span></span> <span data-ttu-id="3349f-111">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="3349f-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="3349f-112">RELOP_GE</span><span class="sxs-lookup"><span data-stu-id="3349f-112">RELOP_GE</span></span> 
  
> <span data-ttu-id="3349f-113">比较基于大于或等于第一个值。</span><span class="sxs-lookup"><span data-stu-id="3349f-113">The comparison is made based on a greater or equal first value.</span></span>
    
<span data-ttu-id="3349f-114">RELOP_GT</span><span class="sxs-lookup"><span data-stu-id="3349f-114">RELOP_GT</span></span> 
  
> <span data-ttu-id="3349f-115">比较基于较大的第一个值。</span><span class="sxs-lookup"><span data-stu-id="3349f-115">The comparison is made based on a greater first value.</span></span>
    
<span data-ttu-id="3349f-116">RELOP_LE</span><span class="sxs-lookup"><span data-stu-id="3349f-116">RELOP_LE</span></span> 
  
> <span data-ttu-id="3349f-117">比较基于小于或等于第一个值。</span><span class="sxs-lookup"><span data-stu-id="3349f-117">The comparison is made based on a lesser or equal first value.</span></span>
    
<span data-ttu-id="3349f-118">RELOP_LT</span><span class="sxs-lookup"><span data-stu-id="3349f-118">RELOP_LT</span></span> 
  
> <span data-ttu-id="3349f-119">比较基于第一个值较小。</span><span class="sxs-lookup"><span data-stu-id="3349f-119">The comparison is made based on a lesser first value.</span></span>
    
<span data-ttu-id="3349f-120">RELOP_NE</span><span class="sxs-lookup"><span data-stu-id="3349f-120">RELOP_NE</span></span> 
  
> <span data-ttu-id="3349f-121">比较基于值。</span><span class="sxs-lookup"><span data-stu-id="3349f-121">The comparison is made based on unequal values.</span></span>
    
<span data-ttu-id="3349f-122">RELOP_RE</span><span class="sxs-lookup"><span data-stu-id="3349f-122">RELOP_RE</span></span> 
  
> <span data-ttu-id="3349f-123">比较基于 LIKE (正则表达式) 值。</span><span class="sxs-lookup"><span data-stu-id="3349f-123">The comparison is made based on LIKE (regular expression) values.</span></span>
    
<span data-ttu-id="3349f-124">RELOP_EQ</span><span class="sxs-lookup"><span data-stu-id="3349f-124">RELOP_EQ</span></span> 
  
> <span data-ttu-id="3349f-125">比较基于相等的值。</span><span class="sxs-lookup"><span data-stu-id="3349f-125">The comparison is made based on equal values.</span></span>
    
 <span data-ttu-id="3349f-126">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="3349f-126">**ulPropTag**</span></span>
  
> <span data-ttu-id="3349f-127">标识要测试的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="3349f-127">Property tag identifying the property to test.</span></span>
    
 <span data-ttu-id="3349f-128">**cb**</span><span class="sxs-lookup"><span data-stu-id="3349f-128">**cb**</span></span>
  
> <span data-ttu-id="3349f-129">属性值中的字节数。</span><span class="sxs-lookup"><span data-stu-id="3349f-129">Count of bytes in the property value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3349f-130">备注</span><span class="sxs-lookup"><span data-stu-id="3349f-130">Remarks</span></span>

<span data-ttu-id="3349f-131">有关限制如何工作的一般讨论，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="3349f-131">For a general discussion of how restrictions work, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3349f-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3349f-132">See also</span></span>



[<span data-ttu-id="3349f-133">SRestriction</span><span class="sxs-lookup"><span data-stu-id="3349f-133">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="3349f-134">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="3349f-134">MAPI Structures</span></span>](mapi-structures.md)

