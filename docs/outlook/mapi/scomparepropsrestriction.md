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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33440001"
---
# <a name="scomparepropsrestriction"></a><span data-ttu-id="12849-103">SComparePropsRestriction</span><span class="sxs-lookup"><span data-stu-id="12849-103">SComparePropsRestriction</span></span>

<span data-ttu-id="12849-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="12849-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="12849-105">描述比较属性限制，该限制使用关系运算符测试两个属性。</span><span class="sxs-lookup"><span data-stu-id="12849-105">Describes a compare property restriction, which tests two properties using a relational operator.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="12849-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="12849-106">Header file:</span></span>  <br/> |<span data-ttu-id="12849-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="12849-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SComparePropsRestriction
{
  ULONG relop;
  ULONG ulPropTag1;
  ULONG ulPropTag2;
} SComparePropsRestriction;

```

## <a name="members"></a><span data-ttu-id="12849-108">Members</span><span class="sxs-lookup"><span data-stu-id="12849-108">Members</span></span>

<span data-ttu-id="12849-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="12849-109">**relop**</span></span>
  
> <span data-ttu-id="12849-110">用于比较这两个属性的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="12849-110">Relational operator to use to compare the two properties.</span></span> <span data-ttu-id="12849-111">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="12849-111">Possible values are as follows:</span></span>
    
  - <span data-ttu-id="12849-112">RELOP_GE：比较基于大于或等于第一个值。</span><span class="sxs-lookup"><span data-stu-id="12849-112">RELOP_GE: The comparison is made based on a greater or equal first value.</span></span>
      
  - <span data-ttu-id="12849-113">RELOP_GT：比较基于较大的第一个值。</span><span class="sxs-lookup"><span data-stu-id="12849-113">RELOP_GT: The comparison is made based on a greater first value.</span></span>
      
  - <span data-ttu-id="12849-114">RELOP_LE：比较基于小于或等于第一个值。</span><span class="sxs-lookup"><span data-stu-id="12849-114">RELOP_LE: The comparison is made based on a lesser or equal first value.</span></span>
      
  - <span data-ttu-id="12849-115">RELOP_LT：比较基于第一个值较小。</span><span class="sxs-lookup"><span data-stu-id="12849-115">RELOP_LT: The comparison is made based on a lesser first value.</span></span>
      
  - <span data-ttu-id="12849-116">RELOP_NE：基于数值进行比较。</span><span class="sxs-lookup"><span data-stu-id="12849-116">RELOP_NE: The comparison is made based on unequal values.</span></span>
      
  - <span data-ttu-id="12849-117">RELOP_RE：比较基于 LIKE (正则表达式) 值。</span><span class="sxs-lookup"><span data-stu-id="12849-117">RELOP_RE: The comparison is made based on LIKE (regular expression) values.</span></span>
      
  - <span data-ttu-id="12849-118">RELOP_EQ：基于相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="12849-118">RELOP_EQ: The comparison is made based on equal values.</span></span>
    
<span data-ttu-id="12849-119">**ulPropTag1**</span><span class="sxs-lookup"><span data-stu-id="12849-119">**ulPropTag1**</span></span>
  
> <span data-ttu-id="12849-120">要比较的第一个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="12849-120">Property tag of the first property to be compared.</span></span> 
    
<span data-ttu-id="12849-121">**ulPropTag2**</span><span class="sxs-lookup"><span data-stu-id="12849-121">**ulPropTag2**</span></span>
  
> <span data-ttu-id="12849-122">要比较的第二个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="12849-122">Property tag of the second property to be compared.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="12849-123">备注</span><span class="sxs-lookup"><span data-stu-id="12849-123">Remarks</span></span>

<span data-ttu-id="12849-124">比较顺序为属性 ( _标记 1，)  (关系运算符)  (标记 2)_。</span><span class="sxs-lookup"><span data-stu-id="12849-124">The comparison order is  _(property tag 1) (relational operator) (property tag 2)_.</span></span> <span data-ttu-id="12849-125">要比较的属性必须相同类型。</span><span class="sxs-lookup"><span data-stu-id="12849-125">The properties to be compared must be of the same type.</span></span> <span data-ttu-id="12849-126">尝试比较不同类型的属性会导致 MAPI 或服务提供商从作为参数MAPI_E_TOO_COMPLEX [IMAPITable](imapitableiunknown.md) 方法返回错误值。</span><span class="sxs-lookup"><span data-stu-id="12849-126">Attempting to compare properties of different types causes MAPI or the service provider to return the error value MAPI_E_TOO_COMPLEX from the [IMAPITable](imapitableiunknown.md) method to which the structure is passed as a parameter.</span></span> 
  
<span data-ttu-id="12849-127">比较属性值限制的结果在一个或两个属性不存在时未定义。</span><span class="sxs-lookup"><span data-stu-id="12849-127">The result of a compare property value restriction is undefined when one or both of the properties do not exist.</span></span> <span data-ttu-id="12849-128">当客户端需要针对此类限制进行明确定义的行为，并且不确定属性是否存在时（例如 (不是表) 的必需列）时，它应创建 **AND** 限制以将比较属性限制与存在限制联接。</span><span class="sxs-lookup"><span data-stu-id="12849-128">When a client requires well-defined behavior for such a restriction and is not sure whether the property exists, (for example, it is not a required column of a table) it should create an **AND** restriction to join the compare property restriction with an exist restriction.</span></span> <span data-ttu-id="12849-129">使用 [SExistRestriction](sexistrestriction.md) 结构定义存在限制，使用 [SAndRestriction](sandrestriction.md) 结构定义 **AND** 限制。</span><span class="sxs-lookup"><span data-stu-id="12849-129">Use an [SExistRestriction](sexistrestriction.md) structure to define the exist restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="12849-130">如果服务提供商支持 **，则 ulPropTag1** 和 **ulPropTag2** 成员中指定的属性可以是多值属性。</span><span class="sxs-lookup"><span data-stu-id="12849-130">The properties specified in the **ulPropTag1** and **ulPropTag2** members can be multi-valued if the service provider supports it.</span></span> 
  
<span data-ttu-id="12849-131">有关 **SComparePropsRestriction** 结构和限制的一般详细信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="12849-131">For more information about the **SComparePropsRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="12849-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12849-132">See also</span></span>

- [<span data-ttu-id="12849-133">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="12849-133">SBitMaskRestriction</span></span>](sbitmaskrestriction.md)
- [<span data-ttu-id="12849-134">SRestriction</span><span class="sxs-lookup"><span data-stu-id="12849-134">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="12849-135">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="12849-135">MAPI Structures</span></span>](mapi-structures.md)

