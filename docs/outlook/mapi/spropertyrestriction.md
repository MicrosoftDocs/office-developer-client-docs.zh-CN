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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406085"
---
# <a name="spropertyrestriction"></a><span data-ttu-id="b49c5-103">SPropertyRestriction</span><span class="sxs-lookup"><span data-stu-id="b49c5-103">SPropertyRestriction</span></span>

<span data-ttu-id="b49c5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b49c5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b49c5-105">描述用于将常量与属性值相匹配的属性限制。</span><span class="sxs-lookup"><span data-stu-id="b49c5-105">Describes a property restriction that is used to match a constant with the value of a property.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b49c5-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b49c5-106">Header file:</span></span>  <br/> |<span data-ttu-id="b49c5-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b49c5-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SPropertyRestriction
{
  ULONG relop;
  ULONG ulPropTag;
  LPSPropValue lpProp;
} SPropertyRestriction;

```

## <a name="members"></a><span data-ttu-id="b49c5-108">Members</span><span class="sxs-lookup"><span data-stu-id="b49c5-108">Members</span></span>

<span data-ttu-id="b49c5-109">**relop**</span><span class="sxs-lookup"><span data-stu-id="b49c5-109">**relop**</span></span>
  
> <span data-ttu-id="b49c5-110">将在搜索中使用的关系运算符。</span><span class="sxs-lookup"><span data-stu-id="b49c5-110">Relational operator that will be used in the search.</span></span> <span data-ttu-id="b49c5-111">可能的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="b49c5-111">Possible values are as follows:</span></span>
    
  - <span data-ttu-id="b49c5-112">RELOP_GE：比较基于大于或等于第一个值。</span><span class="sxs-lookup"><span data-stu-id="b49c5-112">RELOP_GE: The comparison is made based on a greater or equal first value.</span></span>
        
  - <span data-ttu-id="b49c5-113">RELOP_GT：比较基于较大的第一个值。</span><span class="sxs-lookup"><span data-stu-id="b49c5-113">RELOP_GT: The comparison is made based on a greater first value.</span></span>
        
  - <span data-ttu-id="b49c5-114">RELOP_LE：比较基于小于或等于第一个值。</span><span class="sxs-lookup"><span data-stu-id="b49c5-114">RELOP_LE: The comparison is made based on a lesser or equal first value.</span></span>
        
  - <span data-ttu-id="b49c5-115">RELOP_LT：比较基于第一个值较小。</span><span class="sxs-lookup"><span data-stu-id="b49c5-115">RELOP_LT: The comparison is made based on a lesser first value.</span></span>
        
  - <span data-ttu-id="b49c5-116">RELOP_NE：基于数值进行比较。</span><span class="sxs-lookup"><span data-stu-id="b49c5-116">RELOP_NE: The comparison is made based on unequal values.</span></span>
        
  - <span data-ttu-id="b49c5-117">RELOP_RE：比较基于 LIKE (正则表达式) 值。</span><span class="sxs-lookup"><span data-stu-id="b49c5-117">RELOP_RE: The comparison is made based on LIKE (regular expression) values.</span></span>
        
  - <span data-ttu-id="b49c5-118">RELOP_EQ：基于相等的值进行比较。</span><span class="sxs-lookup"><span data-stu-id="b49c5-118">RELOP_EQ: The comparison is made based on equal values.</span></span>
    
<span data-ttu-id="b49c5-119">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="b49c5-119">**ulPropTag**</span></span>
  
> <span data-ttu-id="b49c5-120">标识要比较的属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="b49c5-120">Property tag identifying the property to be compared.</span></span> 
    
<span data-ttu-id="b49c5-121">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="b49c5-121">**lpProp**</span></span>
  
> <span data-ttu-id="b49c5-122">指向包含将在比较中使用的常量值的 [SPropValue](spropvalue.md) 结构的指针。</span><span class="sxs-lookup"><span data-stu-id="b49c5-122">Pointer to an [SPropValue](spropvalue.md) structure that contains the constant value that will be used in the comparison.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="b49c5-123">备注</span><span class="sxs-lookup"><span data-stu-id="b49c5-123">Remarks</span></span>

<span data-ttu-id="b49c5-124">**SPropertyRestriction 结构中有两个属性** 标记。</span><span class="sxs-lookup"><span data-stu-id="b49c5-124">There are two property tags in an **SPropertyRestriction** structure.</span></span> <span data-ttu-id="b49c5-125">一个位于 **ulPropTag** 成员中，另一个位于 **lpProp** 指向的 **SPropValue** 结构的 **ulPropTag** 成员中。</span><span class="sxs-lookup"><span data-stu-id="b49c5-125">One is in the **ulPropTag** member and the other is in the **ulPropTag** member of the **SPropValue** structure pointed to by **lpProp**.</span></span> <span data-ttu-id="b49c5-126">MAPI 需要属性标识符字段和属性类型字段。</span><span class="sxs-lookup"><span data-stu-id="b49c5-126">MAPI requires both the property identifier field and the property type field.</span></span> <span data-ttu-id="b49c5-127">**SPropertyRestriction** 中的 **ulPropTag** 是要匹配的属性 **，SPropertyRestriction** 到 **ulPropTag** 的 **SPropValue** 类型的 **lpProp** 指针指示如何解释 **lpProp** 联合的成员值。</span><span class="sxs-lookup"><span data-stu-id="b49c5-127">The **ulPropTag** in **SPropertyRestriction** is the property to be matched, and the **lpProp** pointer of the **SPropertyRestriction** to the **ulPropTag**'s type of the **SPropValue** indicates how the members value of the **lpProp** union are interpreted.</span></span> <span data-ttu-id="b49c5-128">这两个属性类型必须匹配，否则在调用 [IMAPITable：：Restrict](imapitable-restrict.md) 或 [IMAPITable：：FindRow](imapitable-findrow.md)MAPI_E_TOO_COMPLEX将返回错误值 。</span><span class="sxs-lookup"><span data-stu-id="b49c5-128">The two property types must match, or else the error value MAPI_E_TOO_COMPLEX is returned when the restriction is used in a call to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md).</span></span> 
  
<span data-ttu-id="b49c5-129">比较顺序是 (_运算符)  (运算符)  (常量) 。_</span><span class="sxs-lookup"><span data-stu-id="b49c5-129">The comparison order is  _(property value) (relational operator) (constant value)_.</span></span>
  
<span data-ttu-id="b49c5-130">当属性限制传递到 **IMAPITable：：Restrict** 或 **IMAPITable：：FindRow** 并且目标属性不存在时，限制的结果将不确定。</span><span class="sxs-lookup"><span data-stu-id="b49c5-130">When a property restriction is passed to **IMAPITable::Restrict** or **IMAPITable::FindRow** and the target property does not exist, the results of the restriction are undefined.</span></span> <span data-ttu-id="b49c5-131">通过创建 **将属性** 限制与 **EXIST** 限制联接在一起的 AND 限制，可以保证调用方得到准确的结果。</span><span class="sxs-lookup"><span data-stu-id="b49c5-131">By creating an **AND** restriction that joins the property restriction with an **EXIST** restriction, a caller can be guaranteed accurate results.</span></span> <span data-ttu-id="b49c5-132">使用 [SExistRestriction](sexistrestriction.md) 结构定义 **EXIST** 限制，使用 [SAndRestriction](sandrestriction.md) 结构定义 **AND** 限制。</span><span class="sxs-lookup"><span data-stu-id="b49c5-132">Use an [SExistRestriction](sexistrestriction.md) structure to define the **EXIST** restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="b49c5-133">如果实现表的服务提供商支持多值属性标记，可以在属性限制中使用它们。</span><span class="sxs-lookup"><span data-stu-id="b49c5-133">Multi-valued property tags can be used in property restrictions if the service provider implementing the table supports them.</span></span> <span data-ttu-id="b49c5-134">如果支持，可在可以使用单值属性标记的任何位置使用多值属性标记。</span><span class="sxs-lookup"><span data-stu-id="b49c5-134">If supported, multi-valued property tags can be used anywhere single-valued property tags can be used.</span></span> 
  
<span data-ttu-id="b49c5-135">多值属性标记可用于以下方法：</span><span class="sxs-lookup"><span data-stu-id="b49c5-135">Multi-valued property tags can be used in the following methods:</span></span>
  
- [<span data-ttu-id="b49c5-136">IMAPIProp::SetProps</span><span class="sxs-lookup"><span data-stu-id="b49c5-136">IMAPIProp::SetProps</span></span>](imapiprop-setprops.md)
    
- [<span data-ttu-id="b49c5-137">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="b49c5-137">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
    
- [<span data-ttu-id="b49c5-138">IMAPITable::SetColumns</span><span class="sxs-lookup"><span data-stu-id="b49c5-138">IMAPITable::SetColumns</span></span>](imapitable-setcolumns.md)
    
- [<span data-ttu-id="b49c5-139">IMAPITable::SortTable</span><span class="sxs-lookup"><span data-stu-id="b49c5-139">IMAPITable::SortTable</span></span>](imapitable-sorttable.md)
    
- [<span data-ttu-id="b49c5-140">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="b49c5-140">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
    
> [!IMPORTANT]
> <span data-ttu-id="b49c5-141">两个属性标记不匹配的一个值得注意的情况是限制多值属性。</span><span class="sxs-lookup"><span data-stu-id="b49c5-141">A notable case when the two property tags won't match is if restricting on a multi-value property.</span></span> <span data-ttu-id="b49c5-142">在这种情况下，必须为 true。</span><span class="sxs-lookup"><span data-stu-id="b49c5-142">In this case the following must be true.</span></span> <span data-ttu-id="b49c5-143">> 如果 **SPropertyRestriction** 的 **ulPropTag** 的属性类型包含多值属性类型位标志 MV_FLAG (0x1000) ，**则 SPropValue** 的 **ulPropTag** 的属性类型应匹配前者减去 MV_FLAG 位标志，即其反函数。</span><span class="sxs-lookup"><span data-stu-id="b49c5-143">> If the property type of the **ulPropTag** of **SPropertyRestriction** contains the multi-value property type bit flag MV_FLAG (0x1000), the property type of the **ulPropTag** of **SPropValue** should match the former minus the MV_FLAG bit flag, that is, its inverse.</span></span> <span data-ttu-id="b49c5-144">>例如，若要限制使用多值自定义字符串属性，例如属性 0x8012101f（即 PROP_TAG (MV_FLAG|PT_UNICODE、0x8012) ) ）具有属性标记的类别，对应的 **SPropertyRestriction** 将显示如下。</span><span class="sxs-lookup"><span data-stu-id="b49c5-144">> For example, to restrict using a multi-value custom string property such as a category with a property tag for the property 0x8012101f, that is, PROP_TAG(MV_FLAG|PT_UNICODE, 0x8012)), the corresponding **SPropertyRestriction** would appear as follows.</span></span><span data-ttu-id="b49c5-145"> >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";`>请注意，如果 **SPropValue** **的 ulPropTag** 的属性类型包含 MV_FLAG 位标志，则可能会返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="b49c5-145"> >  `SPropertyRestriction.ulPropTag = 0x8012101f; // attempt to restrict a MultiValue property`>  `SPropertyRestriction.lpProp->ulPropTag = 0x8012001f; // the lpszW member of the Value property is valid`>  `SPropertyRestriction.lpProp.Value->lpszW = L"My Category";`> Note that if the property type of the **ulPropTag** of **SPropValue** contains the MV_FLAG bit flag, the likely return is MAPI_E_TOO_COMPLEX.</span></span> 
  
<span data-ttu-id="b49c5-146">有关 **SPropertyRestriction** 结构详细信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="b49c5-146">For more information about the **SPropertyRestriction** structure, see [About Restrictions](about-restrictions.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b49c5-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b49c5-147">See also</span></span>

- [<span data-ttu-id="b49c5-148">SExistRestriction</span><span class="sxs-lookup"><span data-stu-id="b49c5-148">SExistRestriction</span></span>](sexistrestriction.md)
- [<span data-ttu-id="b49c5-149">SAndRestriction</span><span class="sxs-lookup"><span data-stu-id="b49c5-149">SAndRestriction</span></span>](sandrestriction.md)
- [<span data-ttu-id="b49c5-150">SPropValue</span><span class="sxs-lookup"><span data-stu-id="b49c5-150">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="b49c5-151">SRestriction</span><span class="sxs-lookup"><span data-stu-id="b49c5-151">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="b49c5-152">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="b49c5-152">IMAPITable::FindRow</span></span>](imapitable-findrow.md)
- [<span data-ttu-id="b49c5-153">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="b49c5-153">IMAPITable::Restrict</span></span>](imapitable-restrict.md)
- [<span data-ttu-id="b49c5-154">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b49c5-154">MAPI Structures</span></span>](mapi-structures.md)

