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
# <a name="scontentrestriction"></a><span data-ttu-id="e7407-103">SContentRestriction</span><span class="sxs-lookup"><span data-stu-id="e7407-103">SContentRestriction</span></span>
 
<span data-ttu-id="e7407-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e7407-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e7407-105">介绍内容限制, 用于将表视图限制为仅包含内容与搜索字符串匹配的列的那些行。</span><span class="sxs-lookup"><span data-stu-id="e7407-105">Describes a content restriction, which is used to limit a table view to only those rows that include a column with contents matching a search string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e7407-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e7407-106">Header file:</span></span>  <br/> |<span data-ttu-id="e7407-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e7407-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SContentRestriction
{
  ULONG        ulFuzzyLevel;
  ULONG        ulPropTag;
  LPSPropValue lpProp;
} SContentRestriction;

```

## <a name="members"></a><span data-ttu-id="e7407-108">Members</span><span class="sxs-lookup"><span data-stu-id="e7407-108">Members</span></span>

<span data-ttu-id="e7407-109">**ulFuzzyLevel**</span><span class="sxs-lookup"><span data-stu-id="e7407-109">**ulFuzzyLevel**</span></span>
  
> <span data-ttu-id="e7407-110">定义在验证匹配项时内容限制应强制实施的 preciseness 级别的选项设置。</span><span class="sxs-lookup"><span data-stu-id="e7407-110">Option settings defining the level of preciseness that the content restriction should enforce when you verify for a match.</span></span>
    
   <span data-ttu-id="e7407-111">**ulFuzzyLevel**成员的**低16位**应用于 PT_BINARY 和 PT_STRING8 类型的属性, 并且必须设置为以下值之一:</span><span class="sxs-lookup"><span data-stu-id="e7407-111">The **lower 16 bits** of the **ulFuzzyLevel** member apply to properties of type PT_BINARY and PT_STRING8 and must be set to one of the following values:</span></span> 
    
   - <span data-ttu-id="e7407-112">FL_FULLSTRING: 若要匹配, **lpProp**搜索字符串必须包含在由**ulPropTag**标识的属性中。</span><span class="sxs-lookup"><span data-stu-id="e7407-112">FL_FULLSTRING: To match, the **lpProp** search string must be contained in the property identified by **ulPropTag**.</span></span>
        
   - <span data-ttu-id="e7407-113">FL_PREFIX: 若要匹配, **lpProp**搜索字符串必须出现在由**ulPropTag**标识的属性的开头。</span><span class="sxs-lookup"><span data-stu-id="e7407-113">FL_PREFIX : To match, the **lpProp** search string must appear at the start of the property identified by **ulPropTag**.</span></span> <span data-ttu-id="e7407-114">这两个字符串只应与**lpProp**所指示的搜索字符串的长度进行比较。</span><span class="sxs-lookup"><span data-stu-id="e7407-114">The two strings should be compared only up to the length of the search string indicated by **lpProp**.</span></span> 
        
   - <span data-ttu-id="e7407-115">FL_SUBSTRING: 若要匹配, **lpProp**搜索字符串必须包含在**ulPropTag**标识的属性中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="e7407-115">FL_SUBSTRING: To match, the **lpProp** search string must be contained anywhere in the property identified by **ulPropTag**.</span></span> 
        
   <span data-ttu-id="e7407-116">**ulFuzzyLevel**成员的**高16位**仅适用于 PT_STRING8 类型的属性, 并且可以通过任意组合设置为以下值:</span><span class="sxs-lookup"><span data-stu-id="e7407-116">The **upper 16 bits** of the **ulFuzzyLevel** member apply only to properties of type PT_STRING8 and can be set to the following values in any combination:</span></span> 
        
   - <span data-ttu-id="e7407-117">FL_IGNORECASE: 应进行比较, 而不考虑大小写。</span><span class="sxs-lookup"><span data-stu-id="e7407-117">FL_IGNORECASE: The comparison should be made without considering case.</span></span> 
        
   - <span data-ttu-id="e7407-118">FL_IGNORENONSPACE: 比较操作应忽略 Unicode 定义的非空格字符, 如变音标记。</span><span class="sxs-lookup"><span data-stu-id="e7407-118">FL_IGNORENONSPACE: The comparison should ignore Unicode-defined non-spacing characters such as diacritical marks.</span></span> 
        
   - <span data-ttu-id="e7407-119">FL_LOOSE: 比较时应尽可能为您提供匹配项, 忽略大小写和非空格字符。</span><span class="sxs-lookup"><span data-stu-id="e7407-119">FL_LOOSE: The comparison should give you a match whenever possible, ignoring case and non-spacing characters.</span></span> 
    
<span data-ttu-id="e7407-120">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="e7407-120">**ulPropTag**</span></span>
  
> <span data-ttu-id="e7407-121">用于标识要检查搜索字符串的匹配项的字符串属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="e7407-121">Property tag identifying the string property to be checked for occurrence of the search string.</span></span> 
    
<span data-ttu-id="e7407-122">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="e7407-122">**lpProp**</span></span>
  
> <span data-ttu-id="e7407-123">指向属性值结构的指针, 该结构包含要用作搜索字符串的字符串值。</span><span class="sxs-lookup"><span data-stu-id="e7407-123">Pointer to a property value structure that contains the string value to use as the search string.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e7407-124">说明</span><span class="sxs-lookup"><span data-stu-id="e7407-124">Remarks</span></span>

<span data-ttu-id="e7407-125">**SContentRestriction**结构中有两个属性标记: 一个在**ulPropTag**成员中, 另一个位于**lpProp**指向的**SPropValue**结构的**ulPropTag**成员中。</span><span class="sxs-lookup"><span data-stu-id="e7407-125">There are two property tags in an **SContentRestriction** structure: one in the **ulPropTag** member and the other in the **ulPropTag** member of the **SPropValue** structure pointed to by **lpProp**.</span></span> <span data-ttu-id="e7407-126">在这两个标记中, MAPI 仅需要属性类型字段, 并且忽略属性标识符字段。</span><span class="sxs-lookup"><span data-stu-id="e7407-126">In both tags, MAPI requires only the property type field and ignores the property identifier field.</span></span> <span data-ttu-id="e7407-127">但是, 这两个属性类型必须匹配, 否则在对[IMAPITable:: Restrict](imapitable-restrict.md)或[imapitable:: FindRow](imapitable-findrow.md)的调用中使用限制时, 将返回错误值 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="e7407-127">However, the two property types must match, or else the error value MAPI_E_TOO_COMPLEX is returned when the restriction is used in a call to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md).</span></span> 
  
<span data-ttu-id="e7407-128">值 FL_FULLSTRING、FL_PREFIX 和 FL_SUBSTRING 是相互排斥的。</span><span class="sxs-lookup"><span data-stu-id="e7407-128">The values FL_FULLSTRING, FL_PREFIX, and FL_SUBSTRING are mutually exclusive.</span></span> <span data-ttu-id="e7407-129">只能设置其中一个, 并且必须设置其中一个。</span><span class="sxs-lookup"><span data-stu-id="e7407-129">Only one of them can be set, and one of them must be set.</span></span> <span data-ttu-id="e7407-130">它们的含义是固定的, 并且提供程序必须完全按照定义实现。</span><span class="sxs-lookup"><span data-stu-id="e7407-130">Their meanings are fixed, and the provider must implement them exactly as defined.</span></span> <span data-ttu-id="e7407-131">如果提供程序无法支持这些值, 则该提供程序应返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="e7407-131">The provider should return MAPI_E_TOO_COMPLEX if it is unable to support these values.</span></span> 
  
<span data-ttu-id="e7407-132">值 FL_IGNORECASE、FL_IGNORENONSPACE 和 FL_LOOSE 是独立的。</span><span class="sxs-lookup"><span data-stu-id="e7407-132">The values FL_IGNORECASE, FL_IGNORENONSPACE, and FL_LOOSE are independent.</span></span> <span data-ttu-id="e7407-133">可以设置从零到所有三项之间的任意位置。</span><span class="sxs-lookup"><span data-stu-id="e7407-133">Anywhere from zero to all three of them can be set.</span></span> <span data-ttu-id="e7407-134">它们的定义仅作为指导提供, 提供程序可自由实现每个标志的特定含义。</span><span class="sxs-lookup"><span data-stu-id="e7407-134">Their definitions are provided as a guideline only, and the provider is free to implement its own specific meaning of each flag.</span></span> <span data-ttu-id="e7407-135">如果提供程序不能实现指定的标志, 则该提供程序不应返回任何错误指示。</span><span class="sxs-lookup"><span data-stu-id="e7407-135">The provider should not return any error indication if it has no implementation of a specified flag.</span></span> 
  
<span data-ttu-id="e7407-136">如果属性不存在, 则针对属性施加的内容限制的结果将未定义。</span><span class="sxs-lookup"><span data-stu-id="e7407-136">The result of a content restriction imposed against a property is undefined when the property does not exist.</span></span> <span data-ttu-id="e7407-137">如果客户端需要此类限制的明确定义行为, 并且不确定该属性是否存在, 则它不是表的必需列。它应创建**并**限制, 以使用存在的限制加入内容限制。</span><span class="sxs-lookup"><span data-stu-id="e7407-137">When a client requires well-defined behavior for such a restriction and is not sure whether the property exists for example, it is not a required column of a table it should create an **AND** restriction to join the content restriction with an exist restriction.</span></span> <span data-ttu-id="e7407-138">使用[SExistRestriction](sexistrestriction.md)结构定义存在限制和[SAndRestriction](sandrestriction.md)结构以定义**和**限制。</span><span class="sxs-lookup"><span data-stu-id="e7407-138">Use an [SExistRestriction](sexistrestriction.md) structure to define the exist restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="e7407-139">有关**SContentRestriction**结构和限制的详细信息, 请参阅[关于限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="e7407-139">For more information about the **SContentRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7407-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7407-140">See also</span></span>

- [<span data-ttu-id="e7407-141">SPropValue</span><span class="sxs-lookup"><span data-stu-id="e7407-141">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="e7407-142">SRestriction</span><span class="sxs-lookup"><span data-stu-id="e7407-142">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="e7407-143">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="e7407-143">MAPI Structures</span></span>](mapi-structures.md)

