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
ms.openlocfilehash: afac8c352ad0a07fcb1cd98683b6a5c87940ab4d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424474"
---
# <a name="sbitmaskrestriction"></a><span data-ttu-id="f90f9-103">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="f90f9-103">SBitMaskRestriction</span></span>

  
  
<span data-ttu-id="f90f9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f90f9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f90f9-105">描述位掩码限制，该限制用于执行位 **AND** 操作并测试结果。</span><span class="sxs-lookup"><span data-stu-id="f90f9-105">Describes a bitmask restriction, which is used to perform a bitwise **AND** operation and test the result.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f90f9-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="f90f9-106">Header file:</span></span>  <br/> |<span data-ttu-id="f90f9-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f90f9-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SBitMaskRestriction
{
  ULONG relBMR;
  PT_LONG ulPropTag;
  ULONG ulMask;
} SBitMaskRestriction;

```

## <a name="members"></a><span data-ttu-id="f90f9-108">Members</span><span class="sxs-lookup"><span data-stu-id="f90f9-108">Members</span></span>

 <span data-ttu-id="f90f9-109">**relBMR**</span><span class="sxs-lookup"><span data-stu-id="f90f9-109">**relBMR**</span></span>
  
> <span data-ttu-id="f90f9-110">描述如何将 **ulMask** 成员中指定的掩码应用于属性标记的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="f90f9-110">Relational operator that describes how the mask specified in the **ulMask** member should be applied to the property tag.</span></span> <span data-ttu-id="f90f9-111">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="f90f9-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="f90f9-112">BMR_EQZ</span><span class="sxs-lookup"><span data-stu-id="f90f9-112">BMR_EQZ</span></span> 
  
> <span data-ttu-id="f90f9-113">使用 **ulPropTag** 成员所代表的属性对 **ulMask** 成员中的掩码执行按位 **AND** 操作，并测试其等于零。</span><span class="sxs-lookup"><span data-stu-id="f90f9-113">Perform a bitwise **AND** operation of the mask in the **ulMask** member with the property represented by the **ulPropTag** member and test for being equal to zero.</span></span> 
    
<span data-ttu-id="f90f9-114">BMR_NEZ</span><span class="sxs-lookup"><span data-stu-id="f90f9-114">BMR_NEZ</span></span> 
  
> <span data-ttu-id="f90f9-115">使用 **ulPropTag** 成员所代表的属性对 **ulMask** 成员中的掩码执行按位 **AND** 操作，并测试其不等于零。</span><span class="sxs-lookup"><span data-stu-id="f90f9-115">Perform a bitwise **AND** operation of the mask in the **ulMask** member with the property represented by the **ulPropTag** member and test for being not equal to zero.</span></span> 
    
 <span data-ttu-id="f90f9-116">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="f90f9-116">**ulPropTag**</span></span>
  
> <span data-ttu-id="f90f9-117">应用位掩码的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="f90f9-117">Property tag of the property to which the bitmask is applied.</span></span>
    
 <span data-ttu-id="f90f9-118">**ulMask**</span><span class="sxs-lookup"><span data-stu-id="f90f9-118">**ulMask**</span></span>
  
> <span data-ttu-id="f90f9-119">要应用于由 **ulPropTag 标识的属性的位掩码**。</span><span class="sxs-lookup"><span data-stu-id="f90f9-119">Bitmask to apply to the property identified by **ulPropTag**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f90f9-120">备注</span><span class="sxs-lookup"><span data-stu-id="f90f9-120">Remarks</span></span>

<span data-ttu-id="f90f9-121">**SBitMaskRestriction** 结构使用 **ulMask** 成员中描述的位掩码和 **ulPropTag** 成员描述的属性值执行按位 **AND** 操作。</span><span class="sxs-lookup"><span data-stu-id="f90f9-121">The **SBitMaskRestriction** structure performs a bitwise **AND** operation using the bitmask described in the **ulMask** member and the value of the property described by the **ulPropTag** member.</span></span> <span data-ttu-id="f90f9-122">如果结果为零，则BMR_EQZ结果。</span><span class="sxs-lookup"><span data-stu-id="f90f9-122">If the result is zero, BMR_EQZ is satisfied.</span></span> <span data-ttu-id="f90f9-123">如果不是零，即，如果属性值至少具有一个设置为 **ulMask** 的相同位，则BMR_NEZ满足。</span><span class="sxs-lookup"><span data-stu-id="f90f9-123">If it is nonzero, that is, if the property value has at least one of the same bits set as **ulMask**, then BMR_NEZ is satisfied.</span></span>
  
<span data-ttu-id="f90f9-124">有关 **SBitMaskRestriction** 结构和限制的一般详细信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="f90f9-124">For more information about the **SBitMaskRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f90f9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f90f9-125">See also</span></span>



[<span data-ttu-id="f90f9-126">SRestriction</span><span class="sxs-lookup"><span data-stu-id="f90f9-126">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="f90f9-127">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="f90f9-127">MAPI Structures</span></span>](mapi-structures.md)

