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
ms.openlocfilehash: 7177b2f0f709939b7580fa7abb87490073bb00c4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588809"
---
# <a name="scomparepropsrestriction"></a><span data-ttu-id="3e270-103">SComparePropsRestriction</span><span class="sxs-lookup"><span data-stu-id="3e270-103">SComparePropsRestriction</span></span>

<span data-ttu-id="3e270-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3e270-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3e270-105">介绍比较属性限制，测试使用关系运算符的两个属性。</span><span class="sxs-lookup"><span data-stu-id="3e270-105">Describes a compare property restriction, which tests two properties using a relational operator.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3e270-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="3e270-106">Header file:</span></span>  <br/> |<span data-ttu-id="3e270-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3e270-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SComparePropsRestriction
{
  ULONG relop;
  ULONG ulPropTag1;
  ULONG ulPropTag2;
} SComparePropsRestriction;

```

## <a name="members"></a><span data-ttu-id="3e270-108">Members</span><span class="sxs-lookup"><span data-stu-id="3e270-108">Members</span></span>

<span data-ttu-id="3e270-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="3e270-109">**relop**</span></span>
  
> <span data-ttu-id="3e270-110">要用于比较两个属性的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="3e270-110">Relational operator to use to compare the two properties.</span></span> <span data-ttu-id="3e270-111">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="3e270-111">Possible values are as follows:</span></span>
    
  - <span data-ttu-id="3e270-112">RELOP_GE： 比较结果是根据大于或等于的第一个值。</span><span class="sxs-lookup"><span data-stu-id="3e270-112">RELOP_GE: The comparison is made based on a greater or equal first value.</span></span>
      
  - <span data-ttu-id="3e270-113">RELOP_GT： 比较结果是根据更高版本的第一个值。</span><span class="sxs-lookup"><span data-stu-id="3e270-113">RELOP_GT: The comparison is made based on a greater first value.</span></span>
      
  - <span data-ttu-id="3e270-114">RELOP_LE： 进行比较基于上第一个值小于或等于。</span><span class="sxs-lookup"><span data-stu-id="3e270-114">RELOP_LE: The comparison is made based on a lesser or equal first value.</span></span>
      
  - <span data-ttu-id="3e270-115">RELOP_LT： 比较结果是根据为较小的第一个值。</span><span class="sxs-lookup"><span data-stu-id="3e270-115">RELOP_LT: The comparison is made based on a lesser first value.</span></span>
      
  - <span data-ttu-id="3e270-116">RELOP_NE： 进行比较基于上不相等的值。</span><span class="sxs-lookup"><span data-stu-id="3e270-116">RELOP_NE: The comparison is made based on unequal values.</span></span>
      
  - <span data-ttu-id="3e270-117">RELOP_RE： 进行比较基于类似 （正则表达式） 值。</span><span class="sxs-lookup"><span data-stu-id="3e270-117">RELOP_RE: The comparison is made based on LIKE (regular expression) values.</span></span>
      
  - <span data-ttu-id="3e270-118">RELOP_EQ： 比较结果是根据相等的值。</span><span class="sxs-lookup"><span data-stu-id="3e270-118">RELOP_EQ: The comparison is made based on equal values.</span></span>
    
<span data-ttu-id="3e270-119">**ulPropTag1**</span><span class="sxs-lookup"><span data-stu-id="3e270-119">**ulPropTag1**</span></span>
  
> <span data-ttu-id="3e270-120">要比较的第一个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="3e270-120">Property tag of the first property to be compared.</span></span> 
    
<span data-ttu-id="3e270-121">**ulPropTag2**</span><span class="sxs-lookup"><span data-stu-id="3e270-121">**ulPropTag2**</span></span>
  
> <span data-ttu-id="3e270-122">要进行比较的第二个属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="3e270-122">Property tag of the second property to be compared.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3e270-123">注解</span><span class="sxs-lookup"><span data-stu-id="3e270-123">Remarks</span></span>

<span data-ttu-id="3e270-124">比较顺序是 _(1） （关系运算符） 中的属性标记 （属性标记 2）_。</span><span class="sxs-lookup"><span data-stu-id="3e270-124">The comparison order is  _(property tag 1) (relational operator) (property tag 2)_.</span></span> <span data-ttu-id="3e270-125">要比较的属性必须属于同一字段类型。</span><span class="sxs-lookup"><span data-stu-id="3e270-125">The properties to be compared must be of the same type.</span></span> <span data-ttu-id="3e270-126">试图比较不同类型的属性将导致从作为参数传递结构是指[IMAPITable](imapitableiunknown.md)方法返回错误值 MAPI_E_TOO_COMPLEX MAPI 或服务提供商。</span><span class="sxs-lookup"><span data-stu-id="3e270-126">Attempting to compare properties of different types causes MAPI or the service provider to return the error value MAPI_E_TOO_COMPLEX from the [IMAPITable](imapitableiunknown.md) method to which the structure is passed as a parameter.</span></span> 
  
<span data-ttu-id="3e270-127">一个或两个属性不存在时未定义的比较属性值限制结果。</span><span class="sxs-lookup"><span data-stu-id="3e270-127">The result of a compare property value restriction is undefined when one or both of the properties do not exist.</span></span> <span data-ttu-id="3e270-128">当客户端需要这样的限制定义完善的行为，并且不确保属性是否存在，（例如，不是必需的表格列） 它应创建加入存在比较属性限制**和**限制限制。</span><span class="sxs-lookup"><span data-stu-id="3e270-128">When a client requires well-defined behavior for such a restriction and is not sure whether the property exists, (for example, it is not a required column of a table) it should create an **AND** restriction to join the compare property restriction with an exist restriction.</span></span> <span data-ttu-id="3e270-129">使用[SExistRestriction](sexistrestriction.md)结构以定义存在限制和[SAndRestriction](sandrestriction.md)结构，用于定义**和**限制。</span><span class="sxs-lookup"><span data-stu-id="3e270-129">Use an [SExistRestriction](sexistrestriction.md) structure to define the exist restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="3e270-130">如果服务提供商支持，可以是多值的**ulPropTag1**和**ulPropTag2**成员中指定的属性。</span><span class="sxs-lookup"><span data-stu-id="3e270-130">The properties specified in the **ulPropTag1** and **ulPropTag2** members can be multi-valued if the service provider supports it.</span></span> 
  
<span data-ttu-id="3e270-131">有关**SComparePropsRestriction**结构和限制的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="3e270-131">For more information about the **SComparePropsRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e270-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e270-132">See also</span></span>

- [<span data-ttu-id="3e270-133">SBitMaskRestriction</span><span class="sxs-lookup"><span data-stu-id="3e270-133">SBitMaskRestriction</span></span>](sbitmaskrestriction.md)
- [<span data-ttu-id="3e270-134">SRestriction</span><span class="sxs-lookup"><span data-stu-id="3e270-134">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="3e270-135">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="3e270-135">MAPI Structures</span></span>](mapi-structures.md)

