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
ms.openlocfilehash: 990fe49d39a73c5bf80b9fdda96d2e5997869edf
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595417"
---
# <a name="ssizerestriction"></a><span data-ttu-id="9f4f6-103">SSizeRestriction</span><span class="sxs-lookup"><span data-stu-id="9f4f6-103">SSizeRestriction</span></span>

  
  
<span data-ttu-id="9f4f6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9f4f6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9f4f6-105">介绍了用于测试的属性值的大小的大小限制。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-105">Describes a size restriction which is used to test the size of a property value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="9f4f6-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="9f4f6-106">Header file:</span></span>  <br/> |<span data-ttu-id="9f4f6-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9f4f6-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SSizeRestriction
{
  ULONG relop;
  ULONG ulPropTag;
  ULONG cb;
} SSizeRestriction;

```

## <a name="members"></a><span data-ttu-id="9f4f6-108">Members</span><span class="sxs-lookup"><span data-stu-id="9f4f6-108">Members</span></span>

 <span data-ttu-id="9f4f6-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="9f4f6-109">**relop**</span></span>
  
> <span data-ttu-id="9f4f6-110">是用于大小比较关系运算符。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-110">Relational operator that is used in the size comparison.</span></span> <span data-ttu-id="9f4f6-111">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="9f4f6-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="9f4f6-112">RELOP_GE</span><span class="sxs-lookup"><span data-stu-id="9f4f6-112">RELOP_GE</span></span> 
  
> <span data-ttu-id="9f4f6-113">基于大于或等于的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-113">The comparison is made based on a greater or equal first value.</span></span>
    
<span data-ttu-id="9f4f6-114">RELOP_GT</span><span class="sxs-lookup"><span data-stu-id="9f4f6-114">RELOP_GT</span></span> 
  
> <span data-ttu-id="9f4f6-115">基于更高版本的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-115">The comparison is made based on a greater first value.</span></span>
    
<span data-ttu-id="9f4f6-116">RELOP_LE</span><span class="sxs-lookup"><span data-stu-id="9f4f6-116">RELOP_LE</span></span> 
  
> <span data-ttu-id="9f4f6-117">基于小于或等于的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-117">The comparison is made based on a lesser or equal first value.</span></span>
    
<span data-ttu-id="9f4f6-118">RELOP_LT</span><span class="sxs-lookup"><span data-stu-id="9f4f6-118">RELOP_LT</span></span> 
  
> <span data-ttu-id="9f4f6-119">在较小的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-119">The comparison is made based on a lesser first value.</span></span>
    
<span data-ttu-id="9f4f6-120">RELOP_NE</span><span class="sxs-lookup"><span data-stu-id="9f4f6-120">RELOP_NE</span></span> 
  
> <span data-ttu-id="9f4f6-121">基于不相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-121">The comparison is made based on unequal values.</span></span>
    
<span data-ttu-id="9f4f6-122">RELOP_RE</span><span class="sxs-lookup"><span data-stu-id="9f4f6-122">RELOP_RE</span></span> 
  
> <span data-ttu-id="9f4f6-123">基于类似 （正则表达式） 值进行比较。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-123">The comparison is made based on LIKE (regular expression) values.</span></span>
    
<span data-ttu-id="9f4f6-124">RELOP_EQ</span><span class="sxs-lookup"><span data-stu-id="9f4f6-124">RELOP_EQ</span></span> 
  
> <span data-ttu-id="9f4f6-125">基于相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-125">The comparison is made based on equal values.</span></span>
    
 <span data-ttu-id="9f4f6-126">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="9f4f6-126">**ulPropTag**</span></span>
  
> <span data-ttu-id="9f4f6-127">属性标记标识要测试的属性。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-127">Property tag identifying the property to test.</span></span>
    
 <span data-ttu-id="9f4f6-128">**cb**</span><span class="sxs-lookup"><span data-stu-id="9f4f6-128">**cb**</span></span>
  
> <span data-ttu-id="9f4f6-129">属性值中的字节数。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-129">Count of bytes in the property value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="9f4f6-130">注解</span><span class="sxs-lookup"><span data-stu-id="9f4f6-130">Remarks</span></span>

<span data-ttu-id="9f4f6-131">有关限制的工作方式的一般讨论，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="9f4f6-131">For a general discussion of how restrictions work, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9f4f6-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f4f6-132">See also</span></span>



[<span data-ttu-id="9f4f6-133">SRestriction</span><span class="sxs-lookup"><span data-stu-id="9f4f6-133">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="9f4f6-134">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="9f4f6-134">MAPI Structures</span></span>](mapi-structures.md)

