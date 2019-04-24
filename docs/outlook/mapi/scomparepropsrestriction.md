---
title: SComparePropsRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SComparePropsRestriction
api_type:
- COM
ms.assetid: 3231a91a-1ef2-4dd8-9f3e-79ca56d2eae9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 513ec0db4e99e687d8aeb9e1d6acdef73df4d158
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351287"
---
# <a name="scomparepropsrestriction"></a><span data-ttu-id="0fa90-103">SComparePropsRestriction</span><span class="sxs-lookup"><span data-stu-id="0fa90-103">SComparePropsRestriction</span></span>

<span data-ttu-id="0fa90-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0fa90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0fa90-105">介绍 compare 属性限制, 该限制使用关系运算符测试两个属性。</span><span class="sxs-lookup"><span data-stu-id="0fa90-105">Describes a compare property restriction, which tests two properties using a relational operator.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0fa90-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0fa90-106">Header file:</span></span>  <br/> |<span data-ttu-id="0fa90-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0fa90-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SComparePropsRestriction
{
  ULONG relop;
  ULONG ulPropTag1;
  ULONG ulPropTag2;
} SComparePropsRestriction;

```

## <a name="members"></a><span data-ttu-id="0fa90-108">Members</span><span class="sxs-lookup"><span data-stu-id="0fa90-108">Members</span></span>

<span data-ttu-id="0fa90-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="0fa90-109">**relop**</span></span>
  
> <span data-ttu-id="0fa90-110">用于比较这两个属性的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="0fa90-110">Relational operator to use to compare the two properties.</span></span> <span data-ttu-id="0fa90-111">可能的值如下所示:</span><span class="sxs-lookup"><span data-stu-id="0fa90-111">Possible values are as follows:</span></span>
    
  - <span data-ttu-id="0fa90-112">RELOP_GE: 根据一个大于或等于的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0fa90-112">RELOP_GE: The comparison is made based on a greater or equal first value.</span></span>
      
  - <span data-ttu-id="0fa90-113">RELOP_GT: 根据更大的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0fa90-113">RELOP_GT: The comparison is made based on a greater first value.</span></span>
      
  - <span data-ttu-id="0fa90-114">RELOP_LE: 基于一个小于或等于的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0fa90-114">RELOP_LE: The comparison is made based on a lesser or equal first value.</span></span>
      
  - <span data-ttu-id="0fa90-115">RELOP_LT: 基于较小的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0fa90-115">RELOP_LT: The comparison is made based on a lesser first value.</span></span>
      
  - <span data-ttu-id="0fa90-116">RELOP_NE: 根据不相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0fa90-116">RELOP_NE: The comparison is made based on unequal values.</span></span>
      
  - <span data-ttu-id="0fa90-117">RELOP_RE: 根据 LIKE (正则表达式) 值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0fa90-117">RELOP_RE: The comparison is made based on LIKE (regular expression) values.</span></span>
      
  - <span data-ttu-id="0fa90-118">RELOP_EQ: 根据相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="0fa90-118">RELOP_EQ: The comparison is made based on equal values.</span></span>
    
<span data-ttu-id="0fa90-119">**ulPropTag1**</span><span class="sxs-lookup"><span data-stu-id="0fa90-119">**ulPropTag1**</span></span>
  
> <span data-ttu-id="0fa90-120">要比较的第一个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="0fa90-120">Property tag of the first property to be compared.</span></span> 
    
<span data-ttu-id="0fa90-121">**ulPropTag2**</span><span class="sxs-lookup"><span data-stu-id="0fa90-121">**ulPropTag2**</span></span>
  
> <span data-ttu-id="0fa90-122">要比较的第二个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="0fa90-122">Property tag of the second property to be compared.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0fa90-123">注解</span><span class="sxs-lookup"><span data-stu-id="0fa90-123">Remarks</span></span>

<span data-ttu-id="0fa90-124">比较顺序为 _(属性标记 1) (关系运算符) (属性标记 2)_。</span><span class="sxs-lookup"><span data-stu-id="0fa90-124">The comparison order is  _(property tag 1) (relational operator) (property tag 2)_.</span></span> <span data-ttu-id="0fa90-125">要进行比较的属性必须具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="0fa90-125">The properties to be compared must be of the same type.</span></span> <span data-ttu-id="0fa90-126">尝试比较不同类型的属性会导致 MAPI 或服务提供程序返回错误值 MAPI_E_TOO_COMPLEX 从将结构作为参数传递到的[IMAPITable](imapitableiunknown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0fa90-126">Attempting to compare properties of different types causes MAPI or the service provider to return the error value MAPI_E_TOO_COMPLEX from the [IMAPITable](imapitableiunknown.md) method to which the structure is passed as a parameter.</span></span> 
  
<span data-ttu-id="0fa90-127">如果一个或两个属性不存在, 则 compare 属性值限制的结果将未定义。</span><span class="sxs-lookup"><span data-stu-id="0fa90-127">The result of a compare property value restriction is undefined when one or both of the properties do not exist.</span></span> <span data-ttu-id="0fa90-128">当客户端需要此类限制的定义良好的行为且不确定该属性是否存在时 (例如, 它不是表中的必需列), 应创建**和**限制以将 compare 属性限制加入存在限制.</span><span class="sxs-lookup"><span data-stu-id="0fa90-128">When a client requires well-defined behavior for such a restriction and is not sure whether the property exists, (for example, it is not a required column of a table) it should create an **AND** restriction to join the compare property restriction with an exist restriction.</span></span> <span data-ttu-id="0fa90-129">使用[SExistRestriction](sexistrestriction.md)结构定义存在限制和[SAndRestriction](sandrestriction.md)结构以定义**和**限制。</span><span class="sxs-lookup"><span data-stu-id="0fa90-129">Use an [SExistRestriction](sexistrestriction.md) structure to define the exist restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="0fa90-130">如果服务提供程序支持, 在**ulPropTag1**和**ulPropTag2**成员中指定的属性可以是多值的。</span><span class="sxs-lookup"><span data-stu-id="0fa90-130">The properties specified in the **ulPropTag1** and **ulPropTag2** members can be multi-valued if the service provider supports it.</span></span> 
  
<span data-ttu-id="0fa90-131">有关**SComparePropsRestriction**结构和限制的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="0fa90-131">For more information about the **SComparePropsRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0fa90-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0fa90-132">See also</span></span>

- [<span data-ttu-id="0fa90-133">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="0fa90-133">SBitMaskRestriction</span></span>](sbitmaskrestriction.md)
- [<span data-ttu-id="0fa90-134">SRestriction</span><span class="sxs-lookup"><span data-stu-id="0fa90-134">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="0fa90-135">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="0fa90-135">MAPI Structures</span></span>](mapi-structures.md)

