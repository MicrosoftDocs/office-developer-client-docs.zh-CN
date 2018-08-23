---
title: SPropertyRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SPropertyRestriction
api_type:
- COM
ms.assetid: 2bbf13e9-05b3-4498-8e08-d9e07505190d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7d588380ccc84f51fe58bb0f092d5287b12b4270
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586534"
---
# <a name="spropertyrestriction"></a><span data-ttu-id="bb511-103">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="bb511-103">SPropertyRestriction</span></span>

<span data-ttu-id="bb511-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb511-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb511-105">介绍用于匹配属性的值的常量属性限制。</span><span class="sxs-lookup"><span data-stu-id="bb511-105">Describes a property restriction that is used to match a constant with the value of a property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="bb511-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="bb511-106">Header file:</span></span>  <br/> |<span data-ttu-id="bb511-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="bb511-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SPropertyRestriction
{
  ULONG relop;
  ULONG ulPropTag;
  LPSPropValue lpProp;
} SPropertyRestriction;

```

## <a name="members"></a><span data-ttu-id="bb511-108">Members</span><span class="sxs-lookup"><span data-stu-id="bb511-108">Members</span></span>

<span data-ttu-id="bb511-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="bb511-109">**relop**</span></span>
  
> <span data-ttu-id="bb511-110">将在搜索中使用的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="bb511-110">Relational operator that will be used in the search.</span></span> <span data-ttu-id="bb511-111">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="bb511-111">Possible values are as follows:</span></span>
    
  - <span data-ttu-id="bb511-112">RELOP_GE： 比较结果是根据大于或等于的第一个值。</span><span class="sxs-lookup"><span data-stu-id="bb511-112">RELOP_GE: The comparison is made based on a greater or equal first value.</span></span>
        
  - <span data-ttu-id="bb511-113">RELOP_GT： 比较结果是根据更高版本的第一个值。</span><span class="sxs-lookup"><span data-stu-id="bb511-113">RELOP_GT: The comparison is made based on a greater first value.</span></span>
        
  - <span data-ttu-id="bb511-114">RELOP_LE： 进行比较基于上第一个值小于或等于。</span><span class="sxs-lookup"><span data-stu-id="bb511-114">RELOP_LE: The comparison is made based on a lesser or equal first value.</span></span>
        
  - <span data-ttu-id="bb511-115">RELOP_LT： 比较结果是根据为较小的第一个值。</span><span class="sxs-lookup"><span data-stu-id="bb511-115">RELOP_LT: The comparison is made based on a lesser first value.</span></span>
        
  - <span data-ttu-id="bb511-116">RELOP_NE： 进行比较基于上不相等的值。</span><span class="sxs-lookup"><span data-stu-id="bb511-116">RELOP_NE: The comparison is made based on unequal values.</span></span>
        
  - <span data-ttu-id="bb511-117">RELOP_RE： 进行比较基于类似 （正则表达式） 值。</span><span class="sxs-lookup"><span data-stu-id="bb511-117">RELOP_RE: The comparison is made based on LIKE (regular expression) values.</span></span>
        
  - <span data-ttu-id="bb511-118">RELOP_EQ： 比较结果是根据相等的值。</span><span class="sxs-lookup"><span data-stu-id="bb511-118">RELOP_EQ: The comparison is made based on equal values.</span></span>
    
<span data-ttu-id="bb511-119">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="bb511-119">**ulPropTag**</span></span>
  
> <span data-ttu-id="bb511-120">属性标记标识要进行比较的属性。</span><span class="sxs-lookup"><span data-stu-id="bb511-120">Property tag identifying the property to be compared.</span></span> 
    
<span data-ttu-id="bb511-121">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="bb511-121">**lpProp**</span></span>
  
> <span data-ttu-id="bb511-122">指向[SPropValue](spropvalue.md)结构，其中包含将在比较中使用的常量值的指针。</span><span class="sxs-lookup"><span data-stu-id="bb511-122">Pointer to an [SPropValue](spropvalue.md) structure that contains the constant value that will be used in the comparison.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="bb511-123">注解</span><span class="sxs-lookup"><span data-stu-id="bb511-123">Remarks</span></span>

<span data-ttu-id="bb511-124">**SPropertyRestriction**结构中有两个属性标记。</span><span class="sxs-lookup"><span data-stu-id="bb511-124">There are two property tags in an **SPropertyRestriction** structure.</span></span> <span data-ttu-id="bb511-125">一个在**ulPropTag**成员中声明，另一个是在所指的**lpProp** **SPropValue**结构的**ulPropTag**成员。</span><span class="sxs-lookup"><span data-stu-id="bb511-125">One is in the **ulPropTag** member and the other is in the **ulPropTag** member of the **SPropValue** structure pointed to by **lpProp**.</span></span> <span data-ttu-id="bb511-126">MAPI 要求属性标识符字段和属性类型字段。</span><span class="sxs-lookup"><span data-stu-id="bb511-126">MAPI requires both the property identifier field and the property type field.</span></span> <span data-ttu-id="bb511-127">在**SPropertyRestriction** **ulPropTag**是要匹配的属性和**SPropertyRestriction**到**ulPropTag**的类型的**SPropValue** **lpProp**指针指示如何的成员值解释**lpProp**联合。</span><span class="sxs-lookup"><span data-stu-id="bb511-127">The **ulPropTag** in **SPropertyRestriction** is the property to be matched, and the **lpProp** pointer of the **SPropertyRestriction** to the **ulPropTag**'s type of the **SPropValue** indicates how the members value of the **lpProp** union are interpreted.</span></span> <span data-ttu-id="bb511-128">必须匹配的两个属性类型，否则 MAPI_E_TOO_COMPLEX 在调用[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)使用限制时则返回的错误值。</span><span class="sxs-lookup"><span data-stu-id="bb511-128">The two property types must match, or else the error value MAPI_E_TOO_COMPLEX is returned when the restriction is used in a call to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md).</span></span> 
  
<span data-ttu-id="bb511-129">比较顺序是 _（属性值） （关系运算符） （常量值）_。</span><span class="sxs-lookup"><span data-stu-id="bb511-129">The comparison order is  _(property value) (relational operator) (constant value)_.</span></span>
  
<span data-ttu-id="bb511-130">属性限制传递给**IMAPITable::Restrict**或**IMAPITable::FindRow**和目标属性不存在，当该限制的结果是未定义。</span><span class="sxs-lookup"><span data-stu-id="bb511-130">When a property restriction is passed to **IMAPITable::Restrict** or **IMAPITable::FindRow** and the target property does not exist, the results of the restriction are undefined.</span></span> <span data-ttu-id="bb511-131">通过创建加入带**存在**限制在属性限制**和**限制，呼叫者可以保证准确的结果。</span><span class="sxs-lookup"><span data-stu-id="bb511-131">By creating an **AND** restriction that joins the property restriction with an **EXIST** restriction, a caller can be guaranteed accurate results.</span></span> <span data-ttu-id="bb511-132">使用[SExistRestriction](sexistrestriction.md)结构以定义**存在**限制和[SAndRestriction](sandrestriction.md)结构，用于定义**和**限制。</span><span class="sxs-lookup"><span data-stu-id="bb511-132">Use an [SExistRestriction](sexistrestriction.md) structure to define the **EXIST** restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="bb511-133">可以在属性限制中使用多值的属性标记，如果服务提供商实现表支持。</span><span class="sxs-lookup"><span data-stu-id="bb511-133">Multi-valued property tags can be used in property restrictions if the service provider implementing the table supports them.</span></span> <span data-ttu-id="bb511-134">如果受支持，多值的属性标记可无处不在可以使用单值属性标记。</span><span class="sxs-lookup"><span data-stu-id="bb511-134">If supported, multi-valued property tags can be used anywhere single-valued property tags can be used.</span></span> 
  
<span data-ttu-id="bb511-135">多值的属性标记可以采用以下方法：</span><span class="sxs-lookup"><span data-stu-id="bb511-135">Multi-valued property tags can be used in the following methods:</span></span>
  
- [<span data-ttu-id="bb511-136">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="bb511-136">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
    
- [<span data-ttu-id="bb511-137">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="bb511-137">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
    
- [<span data-ttu-id="bb511-138">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="bb511-138">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
    
- [<span data-ttu-id="bb511-139">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="bb511-139">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
    
- [<span data-ttu-id="bb511-140">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="bb511-140">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
    
> [!IMPORTANT]
> <span data-ttu-id="bb511-141">对多值属性限制时值得注意的情况时两个属性标记不匹配。</span><span class="sxs-lookup"><span data-stu-id="bb511-141">A notable case when the two property tags won't match is if restricting on a multi-value property.</span></span> <span data-ttu-id="bb511-142">在此情况下必须满足以下条件。</span><span class="sxs-lookup"><span data-stu-id="bb511-142">In this case the following must be true.</span></span> <span data-ttu-id="bb511-143">> 如果**SPropertyRestriction** **ulPropTag**的属性类型包含多值属性类型的位标志 MV_FLAG (0x1000)， **SPropValue** **ulPropTag**的属性类型应匹配减去 MV_ 前者标志位标志，即，其反函数。</span><span class="sxs-lookup"><span data-stu-id="bb511-143">> If the property type of the **ulPropTag** of **SPropertyRestriction** contains the multi-value property type bit flag MV_FLAG (0x1000), the property type of the **ulPropTag** of **SPropValue** should match the former minus the MV_FLAG bit flag, that is, its inverse.</span></span> <span data-ttu-id="bb511-144">> 例如，若要限制使用属性标记属性 0x8012101f，即 PROP_TAG 一个多值自定义字符串属性，如类别 (MV_FLAG | PT_UNICODE，0x8012))，相应**SPropertyRestriction**将显示为如下所示。</span><span class="sxs-lookup"><span data-stu-id="bb511-144">> For example, to restrict using a multi-value custom string property such as a category with a property tag for the property 0x8012101f, that is, PROP_TAG(MV_FLAG|PT_UNICODE, 0x8012)), the corresponding **SPropertyRestriction** would appear as follows.</span></span><span data-ttu-id="bb511-145"> >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";`> 请注意，如果**SPropValue** **ulPropTag**的属性类型包含 MV_FLAG 位标志，可能返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="bb511-145"> >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";`> Note that if the property type of the **ulPropTag** of **SPropValue** contains the MV_FLAG bit flag, the likely return is MAPI_E_TOO_COMPLEX.</span></span> 
  
<span data-ttu-id="bb511-146">有关**SPropertyRestriction**结构的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="bb511-146">For more information about the **SPropertyRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bb511-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb511-147">See also</span></span>

- [<span data-ttu-id="bb511-148">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="bb511-148">SExistRestriction</span></span>](sexistrestriction.md)
- [<span data-ttu-id="bb511-149">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="bb511-149">SAndRestriction</span></span>](sandrestriction.md)
- [<span data-ttu-id="bb511-150">SPropValue</span><span class="sxs-lookup"><span data-stu-id="bb511-150">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="bb511-151">SRestriction</span><span class="sxs-lookup"><span data-stu-id="bb511-151">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="bb511-152">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="bb511-152">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
- [<span data-ttu-id="bb511-153">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="bb511-153">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
- [<span data-ttu-id="bb511-154">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="bb511-154">MAPI Structures</span></span>](mapi-structures.md)

