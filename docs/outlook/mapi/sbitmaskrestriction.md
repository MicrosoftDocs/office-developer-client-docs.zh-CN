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
# <a name="sbitmaskrestriction"></a><span data-ttu-id="6411d-103">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="6411d-103">SBitMaskRestriction</span></span>

  
  
<span data-ttu-id="6411d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6411d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6411d-105">介绍用于执行按位**and**运算并测试结果的位掩码限制。</span><span class="sxs-lookup"><span data-stu-id="6411d-105">Describes a bitmask restriction, which is used to perform a bitwise **AND** operation and test the result.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="6411d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="6411d-106">Header file:</span></span>  <br/> |<span data-ttu-id="6411d-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="6411d-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SBitMaskRestriction
{
  ULONG relBMR;
  PT_LONG ulPropTag;
  ULONG ulMask;
} SBitMaskRestriction;

```

## <a name="members"></a><span data-ttu-id="6411d-108">Members</span><span class="sxs-lookup"><span data-stu-id="6411d-108">Members</span></span>

 <span data-ttu-id="6411d-109">**relBMR**</span><span class="sxs-lookup"><span data-stu-id="6411d-109">**relBMR**</span></span>
  
> <span data-ttu-id="6411d-110">描述**ulMask**成员中指定的掩码应如何应用于属性标记的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="6411d-110">Relational operator that describes how the mask specified in the **ulMask** member should be applied to the property tag.</span></span> <span data-ttu-id="6411d-111">可能的值如下所示:</span><span class="sxs-lookup"><span data-stu-id="6411d-111">Possible values are as follows:</span></span> 
    
<span data-ttu-id="6411d-112">BMR_EQZ</span><span class="sxs-lookup"><span data-stu-id="6411d-112">BMR_EQZ</span></span> 
  
> <span data-ttu-id="6411d-113">使用**ulPropTag**成员表示的属性对**ulMask**成员中的掩码执行按位 "**与**" 运算, 并测试是否等于零。</span><span class="sxs-lookup"><span data-stu-id="6411d-113">Perform a bitwise **AND** operation of the mask in the **ulMask** member with the property represented by the **ulPropTag** member and test for being equal to zero.</span></span> 
    
<span data-ttu-id="6411d-114">BMR_NEZ</span><span class="sxs-lookup"><span data-stu-id="6411d-114">BMR_NEZ</span></span> 
  
> <span data-ttu-id="6411d-115">对**ulMask**成员中的掩码执行按位**and**运算, 该属性由**ulPropTag**成员表示, 并测试为不等于零。</span><span class="sxs-lookup"><span data-stu-id="6411d-115">Perform a bitwise **AND** operation of the mask in the **ulMask** member with the property represented by the **ulPropTag** member and test for being not equal to zero.</span></span> 
    
 <span data-ttu-id="6411d-116">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="6411d-116">**ulPropTag**</span></span>
  
> <span data-ttu-id="6411d-117">要应用位掩码的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="6411d-117">Property tag of the property to which the bitmask is applied.</span></span>
    
 <span data-ttu-id="6411d-118">**ulMask**</span><span class="sxs-lookup"><span data-stu-id="6411d-118">**ulMask**</span></span>
  
> <span data-ttu-id="6411d-119">应用于由**ulPropTag**标识的属性的位掩码。</span><span class="sxs-lookup"><span data-stu-id="6411d-119">Bitmask to apply to the property identified by **ulPropTag**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6411d-120">说明</span><span class="sxs-lookup"><span data-stu-id="6411d-120">Remarks</span></span>

<span data-ttu-id="6411d-121">**SBitMaskRestriction**结构使用**ulMask**成员中描述的位掩码和**ulPropTag**成员描述的属性值执行按位**and**运算。</span><span class="sxs-lookup"><span data-stu-id="6411d-121">The **SBitMaskRestriction** structure performs a bitwise **AND** operation using the bitmask described in the **ulMask** member and the value of the property described by the **ulPropTag** member.</span></span> <span data-ttu-id="6411d-122">如果结果为零, 则表示已满足 BMR_EQZ。</span><span class="sxs-lookup"><span data-stu-id="6411d-122">If the result is zero, BMR_EQZ is satisfied.</span></span> <span data-ttu-id="6411d-123">如果该属性值为非零, 即如果属性值至少有一个相同的位设置为**ulMask**, 则满足 BMR_NEZ。</span><span class="sxs-lookup"><span data-stu-id="6411d-123">If it is nonzero, that is, if the property value has at least one of the same bits set as **ulMask**, then BMR_NEZ is satisfied.</span></span>
  
<span data-ttu-id="6411d-124">有关**SBitMaskRestriction**结构和限制的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="6411d-124">For more information about the **SBitMaskRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6411d-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6411d-125">See also</span></span>



[<span data-ttu-id="6411d-126">SRestriction</span><span class="sxs-lookup"><span data-stu-id="6411d-126">SRestriction</span></span>](srestriction.md)


[<span data-ttu-id="6411d-127">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="6411d-127">MAPI Structures</span></span>](mapi-structures.md)

