---
title: SBitMaskRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SBitMaskRestriction
api_type:
- COM
ms.assetid: ddd42180-6e4f-410c-9f78-d868a91452dc
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c9197201388530bd7755eb1987ecc863220e3847
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566605"
---
# <a name="sbitmaskrestriction"></a><span data-ttu-id="7ac4a-103">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="7ac4a-103">SBitMaskRestriction</span></span>

  
  
<span data-ttu-id="7ac4a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7ac4a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7ac4a-105">描述一个位掩码限制，用来执行按位**AND**操作和测试结果。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-105">Describes a bitmask restriction, which is used to perform a bitwise **AND** operation and test the result.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7ac4a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="7ac4a-106">Header file:</span></span>  <br/> |<span data-ttu-id="7ac4a-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7ac4a-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SBitMaskRestriction
{
  ULONG relBMR;
  PT_LONG ulPropTag;
  ULONG ulMask;
} SBitMaskRestriction;

```

## <a name="members"></a><span data-ttu-id="7ac4a-108">Members</span><span class="sxs-lookup"><span data-stu-id="7ac4a-108">Members</span></span>

 <span data-ttu-id="7ac4a-109">**relBMR**</span><span class="sxs-lookup"><span data-stu-id="7ac4a-109">**relBMR**</span></span>
  
> <span data-ttu-id="7ac4a-110">介绍如何在**ulMask**成员中指定的掩码应应用到属性标记的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-110">Relational operator that describes how the mask specified in the **ulMask** member should be applied to the property tag.</span></span> <span data-ttu-id="7ac4a-111">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="7ac4a-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="7ac4a-112">BMR_EQZ</span><span class="sxs-lookup"><span data-stu-id="7ac4a-112">BMR_EQZ</span></span> 
  
> <span data-ttu-id="7ac4a-113">使用由**ulPropTag**成员和检验值等于零的属性**ulMask**成员中执行按位**AND**运算的掩码。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-113">Perform a bitwise **AND** operation of the mask in the **ulMask** member with the property represented by the **ulPropTag** member and test for being equal to zero.</span></span> 
    
<span data-ttu-id="7ac4a-114">BMR_NEZ</span><span class="sxs-lookup"><span data-stu-id="7ac4a-114">BMR_NEZ</span></span> 
  
> <span data-ttu-id="7ac4a-115">使用由**ulPropTag**成员和测试的值不等于零的属性**ulMask**成员中执行按位**AND**运算的掩码。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-115">Perform a bitwise **AND** operation of the mask in the **ulMask** member with the property represented by the **ulPropTag** member and test for being not equal to zero.</span></span> 
    
 <span data-ttu-id="7ac4a-116">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="7ac4a-116">**ulPropTag**</span></span>
  
> <span data-ttu-id="7ac4a-117">属性标记的位掩码应用到的属性。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-117">Property tag of the property to which the bitmask is applied.</span></span>
    
 <span data-ttu-id="7ac4a-118">**ulMask**</span><span class="sxs-lookup"><span data-stu-id="7ac4a-118">**ulMask**</span></span>
  
> <span data-ttu-id="7ac4a-119">要应用于由**ulPropTag**标识属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-119">Bitmask to apply to the property identified by **ulPropTag**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="7ac4a-120">注解</span><span class="sxs-lookup"><span data-stu-id="7ac4a-120">Remarks</span></span>

<span data-ttu-id="7ac4a-121">**SBitMaskRestriction**结构执行按位**AND**操作使用**ulMask**成员和描述**ulPropTag**成员属性的值中所述的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-121">The **SBitMaskRestriction** structure performs a bitwise **AND** operation using the bitmask described in the **ulMask** member and the value of the property described by the **ulPropTag** member.</span></span> <span data-ttu-id="7ac4a-122">如果结果为零，则满足 BMR_EQZ。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-122">If the result is zero, BMR_EQZ is satisfied.</span></span> <span data-ttu-id="7ac4a-123">如果不为零，也就是说，如果该属性值有至少一个相同位设置为**ulMask**，然后 BMR_NEZ 被满足。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-123">If it is nonzero, that is, if the property value has at least one of the same bits set as **ulMask**, then BMR_NEZ is satisfied.</span></span>
  
<span data-ttu-id="7ac4a-124">有关**SBitMaskRestriction**结构和限制的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="7ac4a-124">For more information about the **SBitMaskRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ac4a-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ac4a-125">See also</span></span>



[<span data-ttu-id="7ac4a-126">SRestriction</span><span class="sxs-lookup"><span data-stu-id="7ac4a-126">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="7ac4a-127">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="7ac4a-127">MAPI Structures</span></span>](mapi-structures.md)

