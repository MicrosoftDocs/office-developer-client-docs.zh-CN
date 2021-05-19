---
title: SContentRestriction
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SContentRestriction
api_type:
- COM
ms.assetid: 784c8a5a-493e-48e6-8784-ba8122c76e3d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 87be6df27a3e6729cb514118438521d76a66b30c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423662"
---
# <a name="scontentrestriction"></a><span data-ttu-id="d480c-103">SContentRestriction</span><span class="sxs-lookup"><span data-stu-id="d480c-103">SContentRestriction</span></span>
 
<span data-ttu-id="d480c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d480c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d480c-105">描述内容限制，该限制用于将表视图限制为仅包含内容与搜索字符串匹配的列的行。</span><span class="sxs-lookup"><span data-stu-id="d480c-105">Describes a content restriction, which is used to limit a table view to only those rows that include a column with contents matching a search string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d480c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d480c-106">Header file:</span></span>  <br/> |<span data-ttu-id="d480c-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d480c-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SContentRestriction
{
  ULONG        ulFuzzyLevel;
  ULONG        ulPropTag;
  LPSPropValue lpProp;
} SContentRestriction;

```

## <a name="members"></a><span data-ttu-id="d480c-108">Members</span><span class="sxs-lookup"><span data-stu-id="d480c-108">Members</span></span>

<span data-ttu-id="d480c-109">**ulFuzzyLevel**</span><span class="sxs-lookup"><span data-stu-id="d480c-109">**ulFuzzyLevel**</span></span>
  
> <span data-ttu-id="d480c-110">选项设置，用于定义验证匹配项时内容限制应强制实施的精度级别。</span><span class="sxs-lookup"><span data-stu-id="d480c-110">Option settings defining the level of preciseness that the content restriction should enforce when you verify for a match.</span></span>
    
   <span data-ttu-id="d480c-111">**ulFuzzyLevel** 成员较低的 **16** 位适用于 PT_BINARY 和 PT_STRING8 类型的属性，并且必须设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="d480c-111">The **lower 16 bits** of the **ulFuzzyLevel** member apply to properties of type PT_BINARY and PT_STRING8 and must be set to one of the following values:</span></span> 
    
   - <span data-ttu-id="d480c-112">FL_FULLSTRING：若要匹配 **，lpProp** 搜索字符串必须包含在 **ulPropTag 标识的属性中**。</span><span class="sxs-lookup"><span data-stu-id="d480c-112">FL_FULLSTRING: To match, the **lpProp** search string must be contained in the property identified by **ulPropTag**.</span></span>
        
   - <span data-ttu-id="d480c-113">FL_PREFIX：若要匹配 **，lpProp** 搜索字符串必须出现在 **ulPropTag 标识的属性的开头**。</span><span class="sxs-lookup"><span data-stu-id="d480c-113">FL_PREFIX : To match, the **lpProp** search string must appear at the start of the property identified by **ulPropTag**.</span></span> <span data-ttu-id="d480c-114">这两个字符串应仅与 **lpProp** 指示的搜索字符串的长度进行比较。</span><span class="sxs-lookup"><span data-stu-id="d480c-114">The two strings should be compared only up to the length of the search string indicated by **lpProp**.</span></span> 
        
   - <span data-ttu-id="d480c-115">FL_SUBSTRING：若要匹配 **，lpProp** 搜索字符串必须包含在 **ulPropTag** 标识的属性中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="d480c-115">FL_SUBSTRING: To match, the **lpProp** search string must be contained anywhere in the property identified by **ulPropTag**.</span></span> 
        
   <span data-ttu-id="d480c-116">**ulFuzzyLevel** 成员上面的 **16** 位仅适用于 PT_STRING8 类型的属性，可以任意组合设置为以下值：</span><span class="sxs-lookup"><span data-stu-id="d480c-116">The **upper 16 bits** of the **ulFuzzyLevel** member apply only to properties of type PT_STRING8 and can be set to the following values in any combination:</span></span> 
        
   - <span data-ttu-id="d480c-117">FL_IGNORECASE：应在不考虑大小写的情况下进行比较。</span><span class="sxs-lookup"><span data-stu-id="d480c-117">FL_IGNORECASE: The comparison should be made without considering case.</span></span> 
        
   - <span data-ttu-id="d480c-118">FL_IGNORENONSPACE：比较应忽略 Unicode 定义的非空格字符，如音调符号。</span><span class="sxs-lookup"><span data-stu-id="d480c-118">FL_IGNORENONSPACE: The comparison should ignore Unicode-defined non-spacing characters such as diacritical marks.</span></span> 
        
   - <span data-ttu-id="d480c-119">FL_LOOSE：比较应尽可能为您提供匹配，忽略大小写字符和非空格字符。</span><span class="sxs-lookup"><span data-stu-id="d480c-119">FL_LOOSE: The comparison should give you a match whenever possible, ignoring case and non-spacing characters.</span></span> 
    
<span data-ttu-id="d480c-120">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="d480c-120">**ulPropTag**</span></span>
  
> <span data-ttu-id="d480c-121">属性标记，用于标识要检查搜索字符串是否出现的字符串属性。</span><span class="sxs-lookup"><span data-stu-id="d480c-121">Property tag identifying the string property to be checked for occurrence of the search string.</span></span> 
    
<span data-ttu-id="d480c-122">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="d480c-122">**lpProp**</span></span>
  
> <span data-ttu-id="d480c-123">指向包含要用作搜索字符串的字符串值的属性值结构的指针。</span><span class="sxs-lookup"><span data-stu-id="d480c-123">Pointer to a property value structure that contains the string value to use as the search string.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d480c-124">备注</span><span class="sxs-lookup"><span data-stu-id="d480c-124">Remarks</span></span>

<span data-ttu-id="d480c-125">**SContentRestriction** 结构中有两个属性标记：一个在 **ulPropTag** 成员中，另一个在 **lpProp** 指向 **的 SPropValue 结构的 ulPropTag** 成员中。 </span><span class="sxs-lookup"><span data-stu-id="d480c-125">There are two property tags in an **SContentRestriction** structure: one in the **ulPropTag** member and the other in the **ulPropTag** member of the **SPropValue** structure pointed to by **lpProp**.</span></span> <span data-ttu-id="d480c-126">在这两个标记中，MAPI 仅需要属性类型字段并忽略属性标识符字段。</span><span class="sxs-lookup"><span data-stu-id="d480c-126">In both tags, MAPI requires only the property type field and ignores the property identifier field.</span></span> <span data-ttu-id="d480c-127">但是，这两个属性类型必须匹配，否则在调用 [IMAPITable：：Restrict](imapitable-restrict.md) 或 [IMAPITable：：FindRow](imapitable-findrow.md)时，将返回错误值 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="d480c-127">However, the two property types must match, or else the error value MAPI_E_TOO_COMPLEX is returned when the restriction is used in a call to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md).</span></span> 
  
<span data-ttu-id="d480c-128">值FL_FULLSTRING、FL_PREFIX和FL_SUBSTRING是互斥的。</span><span class="sxs-lookup"><span data-stu-id="d480c-128">The values FL_FULLSTRING, FL_PREFIX, and FL_SUBSTRING are mutually exclusive.</span></span> <span data-ttu-id="d480c-129">只能设置其中一个，并且必须设置其中一个。</span><span class="sxs-lookup"><span data-stu-id="d480c-129">Only one of them can be set, and one of them must be set.</span></span> <span data-ttu-id="d480c-130">它们的含义是固定的，提供程序必须完全按照定义实现它们。</span><span class="sxs-lookup"><span data-stu-id="d480c-130">Their meanings are fixed, and the provider must implement them exactly as defined.</span></span> <span data-ttu-id="d480c-131">如果提供程序无法MAPI_E_TOO_COMPLEX这些值，则提供程序应返回值。</span><span class="sxs-lookup"><span data-stu-id="d480c-131">The provider should return MAPI_E_TOO_COMPLEX if it is unable to support these values.</span></span> 
  
<span data-ttu-id="d480c-132">值FL_IGNORECASE、FL_IGNORENONSPACE和FL_LOOSE是独立的。</span><span class="sxs-lookup"><span data-stu-id="d480c-132">The values FL_IGNORECASE, FL_IGNORENONSPACE, and FL_LOOSE are independent.</span></span> <span data-ttu-id="d480c-133">Anywhere from zero to all three them can be set.</span><span class="sxs-lookup"><span data-stu-id="d480c-133">Anywhere from zero to all three of them can be set.</span></span> <span data-ttu-id="d480c-134">它们的定义仅作为指南提供，并且提供程序可以自由实现每个标志自己的特定含义。</span><span class="sxs-lookup"><span data-stu-id="d480c-134">Their definitions are provided as a guideline only, and the provider is free to implement its own specific meaning of each flag.</span></span> <span data-ttu-id="d480c-135">如果提供程序没有实现指定标志，则不应返回任何错误指示。</span><span class="sxs-lookup"><span data-stu-id="d480c-135">The provider should not return any error indication if it has no implementation of a specified flag.</span></span> 
  
<span data-ttu-id="d480c-136">当属性不存在时，未定义对属性施加的内容限制的结果。</span><span class="sxs-lookup"><span data-stu-id="d480c-136">The result of a content restriction imposed against a property is undefined when the property does not exist.</span></span> <span data-ttu-id="d480c-137">当客户端需要针对此类限制进行明确定义的行为，并且不确定属性是否存在（例如，该属性不是表的必需列）时，它应创建 **AND** 限制以使用存在限制加入内容限制。</span><span class="sxs-lookup"><span data-stu-id="d480c-137">When a client requires well-defined behavior for such a restriction and is not sure whether the property exists for example, it is not a required column of a table it should create an **AND** restriction to join the content restriction with an exist restriction.</span></span> <span data-ttu-id="d480c-138">使用 [SExistRestriction](sexistrestriction.md) 结构定义存在限制，使用 [SAndRestriction](sandrestriction.md) 结构定义 **AND** 限制。</span><span class="sxs-lookup"><span data-stu-id="d480c-138">Use an [SExistRestriction](sexistrestriction.md) structure to define the exist restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="d480c-139">有关 **SContentRestriction** 结构和限制的一般详细信息，请参阅关于 [限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="d480c-139">For more information about the **SContentRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d480c-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d480c-140">See also</span></span>

- [<span data-ttu-id="d480c-141">SPropValue</span><span class="sxs-lookup"><span data-stu-id="d480c-141">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="d480c-142">SRestriction</span><span class="sxs-lookup"><span data-stu-id="d480c-142">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="d480c-143">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="d480c-143">MAPI Structures</span></span>](mapi-structures.md)

