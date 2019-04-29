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
# <a name="ssizerestriction"></a><span data-ttu-id="4cc9e-103">SSizeRestriction</span><span class="sxs-lookup"><span data-stu-id="4cc9e-103">SSizeRestriction</span></span>

  
  
<span data-ttu-id="4cc9e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4cc9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4cc9e-105">介绍用于测试属性值大小的大小限制。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-105">Describes a size restriction which is used to test the size of a property value.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4cc9e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4cc9e-106">Header file:</span></span>  <br/> |<span data-ttu-id="4cc9e-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4cc9e-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SSizeRestriction
{
  ULONG relop;
  ULONG ulPropTag;
  ULONG cb;
} SSizeRestriction;

```

## <a name="members"></a><span data-ttu-id="4cc9e-108">Members</span><span class="sxs-lookup"><span data-stu-id="4cc9e-108">Members</span></span>

 <span data-ttu-id="4cc9e-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="4cc9e-109">**relop**</span></span>
  
> <span data-ttu-id="4cc9e-110">大小比较中使用的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-110">Relational operator that is used in the size comparison.</span></span> <span data-ttu-id="4cc9e-111">可能的值如下所示:</span><span class="sxs-lookup"><span data-stu-id="4cc9e-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="4cc9e-112">RELOP_GE</span><span class="sxs-lookup"><span data-stu-id="4cc9e-112">RELOP_GE</span></span> 
  
> <span data-ttu-id="4cc9e-113">根据大于或等于的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-113">The comparison is made based on a greater or equal first value.</span></span>
    
<span data-ttu-id="4cc9e-114">RELOP_GT</span><span class="sxs-lookup"><span data-stu-id="4cc9e-114">RELOP_GT</span></span> 
  
> <span data-ttu-id="4cc9e-115">根据更大的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-115">The comparison is made based on a greater first value.</span></span>
    
<span data-ttu-id="4cc9e-116">RELOP_LE</span><span class="sxs-lookup"><span data-stu-id="4cc9e-116">RELOP_LE</span></span> 
  
> <span data-ttu-id="4cc9e-117">根据值小于或等于的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-117">The comparison is made based on a lesser or equal first value.</span></span>
    
<span data-ttu-id="4cc9e-118">RELOP_LT</span><span class="sxs-lookup"><span data-stu-id="4cc9e-118">RELOP_LT</span></span> 
  
> <span data-ttu-id="4cc9e-119">根据较小的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-119">The comparison is made based on a lesser first value.</span></span>
    
<span data-ttu-id="4cc9e-120">RELOP_NE</span><span class="sxs-lookup"><span data-stu-id="4cc9e-120">RELOP_NE</span></span> 
  
> <span data-ttu-id="4cc9e-121">根据不相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-121">The comparison is made based on unequal values.</span></span>
    
<span data-ttu-id="4cc9e-122">RELOP_RE</span><span class="sxs-lookup"><span data-stu-id="4cc9e-122">RELOP_RE</span></span> 
  
> <span data-ttu-id="4cc9e-123">根据 LIKE (正则表达式) 值进行比较。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-123">The comparison is made based on LIKE (regular expression) values.</span></span>
    
<span data-ttu-id="4cc9e-124">RELOP_EQ</span><span class="sxs-lookup"><span data-stu-id="4cc9e-124">RELOP_EQ</span></span> 
  
> <span data-ttu-id="4cc9e-125">根据相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-125">The comparison is made based on equal values.</span></span>
    
 <span data-ttu-id="4cc9e-126">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="4cc9e-126">**ulPropTag**</span></span>
  
> <span data-ttu-id="4cc9e-127">标识要测试的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-127">Property tag identifying the property to test.</span></span>
    
 <span data-ttu-id="4cc9e-128">**cb**</span><span class="sxs-lookup"><span data-stu-id="4cc9e-128">**cb**</span></span>
  
> <span data-ttu-id="4cc9e-129">属性值中的字节数。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-129">Count of bytes in the property value.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4cc9e-130">说明</span><span class="sxs-lookup"><span data-stu-id="4cc9e-130">Remarks</span></span>

<span data-ttu-id="4cc9e-131">有关限制的工作原理的一般讨论, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="4cc9e-131">For a general discussion of how restrictions work, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4cc9e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cc9e-132">See also</span></span>



[<span data-ttu-id="4cc9e-133">SRestriction</span><span class="sxs-lookup"><span data-stu-id="4cc9e-133">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="4cc9e-134">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="4cc9e-134">MAPI Structures</span></span>](mapi-structures.md)

