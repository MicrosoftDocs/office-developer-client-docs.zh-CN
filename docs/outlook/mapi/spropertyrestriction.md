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
ms.openlocfilehash: 29d392eba530126e06a672c10044c5b4df0618c9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357853"
---
# <a name="spropertyrestriction"></a><span data-ttu-id="53cab-103">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="53cab-103">SPropertyRestriction</span></span>

<span data-ttu-id="53cab-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="53cab-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="53cab-105">介绍用于将常量与属性值相匹配的属性限制。</span><span class="sxs-lookup"><span data-stu-id="53cab-105">Describes a property restriction that is used to match a constant with the value of a property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="53cab-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="53cab-106">Header file:</span></span>  <br/> |<span data-ttu-id="53cab-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="53cab-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SPropertyRestriction
{
  ULONG relop;
  ULONG ulPropTag;
  LPSPropValue lpProp;
} SPropertyRestriction;

```

## <a name="members"></a><span data-ttu-id="53cab-108">Members</span><span class="sxs-lookup"><span data-stu-id="53cab-108">Members</span></span>

<span data-ttu-id="53cab-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="53cab-109">**relop**</span></span>
  
> <span data-ttu-id="53cab-110">将在搜索中使用的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="53cab-110">Relational operator that will be used in the search.</span></span> <span data-ttu-id="53cab-111">可能的值如下所示:</span><span class="sxs-lookup"><span data-stu-id="53cab-111">Possible values are as follows:</span></span>
    
  - <span data-ttu-id="53cab-112">RELOP_GE: 根据一个大于或等于的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="53cab-112">RELOP_GE: The comparison is made based on a greater or equal first value.</span></span>
        
  - <span data-ttu-id="53cab-113">RELOP_GT: 根据更大的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="53cab-113">RELOP_GT: The comparison is made based on a greater first value.</span></span>
        
  - <span data-ttu-id="53cab-114">RELOP_LE: 基于一个小于或等于的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="53cab-114">RELOP_LE: The comparison is made based on a lesser or equal first value.</span></span>
        
  - <span data-ttu-id="53cab-115">RELOP_LT: 基于较小的第一个值进行比较。</span><span class="sxs-lookup"><span data-stu-id="53cab-115">RELOP_LT: The comparison is made based on a lesser first value.</span></span>
        
  - <span data-ttu-id="53cab-116">RELOP_NE: 根据不相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="53cab-116">RELOP_NE: The comparison is made based on unequal values.</span></span>
        
  - <span data-ttu-id="53cab-117">RELOP_RE: 根据 LIKE (正则表达式) 值进行比较。</span><span class="sxs-lookup"><span data-stu-id="53cab-117">RELOP_RE: The comparison is made based on LIKE (regular expression) values.</span></span>
        
  - <span data-ttu-id="53cab-118">RELOP_EQ: 根据相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="53cab-118">RELOP_EQ: The comparison is made based on equal values.</span></span>
    
<span data-ttu-id="53cab-119">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="53cab-119">**ulPropTag**</span></span>
  
> <span data-ttu-id="53cab-120">标识要比较的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="53cab-120">Property tag identifying the property to be compared.</span></span> 
    
<span data-ttu-id="53cab-121">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="53cab-121">**lpProp**</span></span>
  
> <span data-ttu-id="53cab-122">指向包含将在比较中使用的常量值的[SPropValue](spropvalue.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="53cab-122">Pointer to an [SPropValue](spropvalue.md) structure that contains the constant value that will be used in the comparison.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="53cab-123">注解</span><span class="sxs-lookup"><span data-stu-id="53cab-123">Remarks</span></span>

<span data-ttu-id="53cab-124">**SPropertyRestriction**结构中有两个属性标记。</span><span class="sxs-lookup"><span data-stu-id="53cab-124">There are two property tags in an **SPropertyRestriction** structure.</span></span> <span data-ttu-id="53cab-125">一个位于**ulPropTag**成员中, 另一个位于**lpProp**指向的**SPropValue**结构的**ulPropTag**成员中。</span><span class="sxs-lookup"><span data-stu-id="53cab-125">One is in the **ulPropTag** member and the other is in the **ulPropTag** member of the **SPropValue** structure pointed to by **lpProp**.</span></span> <span data-ttu-id="53cab-126">MAPI 同时需要 "属性标识符" 字段和 "属性类型" 字段。</span><span class="sxs-lookup"><span data-stu-id="53cab-126">MAPI requires both the property identifier field and the property type field.</span></span> <span data-ttu-id="53cab-127">**SPropertyRestriction**中的**ulPropTag**是要匹配的属性, 而**SPropertyRestriction**的**lpProp**指针指示 ulPropTag 的 SPropValue 类型\*\*\*\* 的\*\*\*\* 的成员值解释**lpProp**联合。</span><span class="sxs-lookup"><span data-stu-id="53cab-127">The **ulPropTag** in **SPropertyRestriction** is the property to be matched, and the **lpProp** pointer of the **SPropertyRestriction** to the **ulPropTag**'s type of the **SPropValue** indicates how the members value of the **lpProp** union are interpreted.</span></span> <span data-ttu-id="53cab-128">这两个属性类型必须匹配, 否则在对[IMAPITable:: Restrict](imapitable-restrict.md)或[IMAPITable:: FindRow](imapitable-findrow.md)的调用中使用限制时, 将返回错误值 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="53cab-128">The two property types must match, or else the error value MAPI_E_TOO_COMPLEX is returned when the restriction is used in a call to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md).</span></span> 
  
<span data-ttu-id="53cab-129">比较顺序为 _(属性值) (关系运算符) (常量值_)。</span><span class="sxs-lookup"><span data-stu-id="53cab-129">The comparison order is  _(property value) (relational operator) (constant value)_.</span></span>
  
<span data-ttu-id="53cab-130">如果将属性限制传递给**IMAPITable:: Restrict**或**IMAPITable:: FindRow** , 且目标属性不存在, 则限制的结果将是不确定的。</span><span class="sxs-lookup"><span data-stu-id="53cab-130">When a property restriction is passed to **IMAPITable::Restrict** or **IMAPITable::FindRow** and the target property does not exist, the results of the restriction are undefined.</span></span> <span data-ttu-id="53cab-131">通过创建**和**限制将属性限制与**存在**的限制联接在一起, 可以保证正确结果的调用者。</span><span class="sxs-lookup"><span data-stu-id="53cab-131">By creating an **AND** restriction that joins the property restriction with an **EXIST** restriction, a caller can be guaranteed accurate results.</span></span> <span data-ttu-id="53cab-132">使用[SExistRestriction](sexistrestriction.md)结构定义**存在**限制和[SAndRestriction](sandrestriction.md)结构以定义**和**限制。</span><span class="sxs-lookup"><span data-stu-id="53cab-132">Use an [SExistRestriction](sexistrestriction.md) structure to define the **EXIST** restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="53cab-133">如果实现表的服务提供程序支持, 多值属性标记可在属性限制中使用。</span><span class="sxs-lookup"><span data-stu-id="53cab-133">Multi-valued property tags can be used in property restrictions if the service provider implementing the table supports them.</span></span> <span data-ttu-id="53cab-134">如果支持, 多值属性标记可用于任何可使用单值属性标记的地方。</span><span class="sxs-lookup"><span data-stu-id="53cab-134">If supported, multi-valued property tags can be used anywhere single-valued property tags can be used.</span></span> 
  
<span data-ttu-id="53cab-135">可以在以下方法中使用多值属性标记:</span><span class="sxs-lookup"><span data-stu-id="53cab-135">Multi-valued property tags can be used in the following methods:</span></span>
  
- [<span data-ttu-id="53cab-136">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="53cab-136">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
    
- [<span data-ttu-id="53cab-137">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="53cab-137">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
    
- [<span data-ttu-id="53cab-138">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="53cab-138">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
    
- [<span data-ttu-id="53cab-139">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="53cab-139">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
    
- [<span data-ttu-id="53cab-140">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="53cab-140">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
    
> [!IMPORTANT]
> <span data-ttu-id="53cab-141">这两个属性标记不匹配的一个显著情况是, 如果对多值属性进行限制。</span><span class="sxs-lookup"><span data-stu-id="53cab-141">A notable case when the two property tags won't match is if restricting on a multi-value property.</span></span> <span data-ttu-id="53cab-142">在这种情况下, 以下情况必须为 true。</span><span class="sxs-lookup"><span data-stu-id="53cab-142">In this case the following must be true.</span></span> <span data-ttu-id="53cab-143">> 如果**SPropertyRestriction**的**ulPropTag**的属性类型包含多值属性类型位标志 MV_FLAG (0x1000), 则**ulPropTag**的**SPropValue**的属性类型应与前减去 MV_ 的属性类型相匹配。标志位标志, 即它的反函数。</span><span class="sxs-lookup"><span data-stu-id="53cab-143">> If the property type of the **ulPropTag** of **SPropertyRestriction** contains the multi-value property type bit flag MV_FLAG (0x1000), the property type of the **ulPropTag** of **SPropValue** should match the former minus the MV_FLAG bit flag, that is, its inverse.</span></span> <span data-ttu-id="53cab-144">> 例如, 若要限制使用多值自定义字符串属性 (如具有属性标记的属性0x8012101f 的类别) (即 PROP_TAG (MV_FLAG | PT_UNICODE、0x8012)), 相应的**SPropertyRestriction**将显示为沿用.</span><span class="sxs-lookup"><span data-stu-id="53cab-144">> For example, to restrict using a multi-value custom string property such as a category with a property tag for the property 0x8012101f, that is, PROP_TAG(MV_FLAG|PT_UNICODE, 0x8012)), the corresponding **SPropertyRestriction** would appear as follows.</span></span><span data-ttu-id="53cab-145"> >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property\`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid\`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";\`> 请注意, 如果*\*SPropValue*\*的*\*ulPropTag*\*的属性类型包含 MV_FLAG 位标志, 则可能返回的是 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="53cab-145"> >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property\`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid\`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";\`> Note that if the property type of the *\*ulPropTag** of *\*SPropValue** contains the MV_FLAG bit flag, the likely return is MAPI_E_TOO_COMPLEX.</span></span> 
  
<span data-ttu-id="53cab-146">有关**SPropertyRestriction**结构的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="53cab-146">For more information about the **SPropertyRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="53cab-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="53cab-147">See also</span></span>

- [<span data-ttu-id="53cab-148">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="53cab-148">SExistRestriction</span></span>](sexistrestriction.md)
- [<span data-ttu-id="53cab-149">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="53cab-149">SAndRestriction</span></span>](sandrestriction.md)
- [<span data-ttu-id="53cab-150">SPropValue</span><span class="sxs-lookup"><span data-stu-id="53cab-150">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="53cab-151">SRestriction</span><span class="sxs-lookup"><span data-stu-id="53cab-151">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="53cab-152">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="53cab-152">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
- [<span data-ttu-id="53cab-153">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="53cab-153">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
- [<span data-ttu-id="53cab-154">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="53cab-154">MAPI Structures</span></span>](mapi-structures.md)

