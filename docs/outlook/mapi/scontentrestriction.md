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
ms.openlocfilehash: 34177aee48adad7eecb40836a247705fc22d2a32
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778709"
---
# <a name="scontentrestriction"></a><span data-ttu-id="b40b0-103">SContentRestriction</span><span class="sxs-lookup"><span data-stu-id="b40b0-103">SContentRestriction</span></span>
 
<span data-ttu-id="b40b0-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b40b0-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b40b0-105">介绍内容限制，用来限制为仅这些内容匹配搜索字符串中包含的列的行表视图。</span><span class="sxs-lookup"><span data-stu-id="b40b0-105">Describes a content restriction, which is used to limit a table view to only those rows that include a column with contents matching a search string.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b40b0-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b40b0-106">Header file:</span></span>  <br/> |<span data-ttu-id="b40b0-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b40b0-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _SContentRestriction
{
  ULONG        ulFuzzyLevel;
  ULONG        ulPropTag;
  LPSPropValue lpProp;
} SContentRestriction;

```

## <a name="members"></a><span data-ttu-id="b40b0-108">Members</span><span class="sxs-lookup"><span data-stu-id="b40b0-108">Members</span></span>

<span data-ttu-id="b40b0-109">**ulFuzzyLevel**</span><span class="sxs-lookup"><span data-stu-id="b40b0-109">**ulFuzzyLevel**</span></span>
  
> <span data-ttu-id="b40b0-110">定义的内容的限制时用于匹配验证应同时实施的 preciseness 级别选项设置。</span><span class="sxs-lookup"><span data-stu-id="b40b0-110">Option settings defining the level of preciseness that the content restriction should enforce when you verify for a match.</span></span>
    
   <span data-ttu-id="b40b0-111">**低 16 位**的**ulFuzzyLevel**成员 PT_BINARY 和 PT_STRING8 应用于类型的属性，并且必须设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="b40b0-111">The **lower 16 bits** of the **ulFuzzyLevel** member apply to properties of type PT_BINARY and PT_STRING8 and must be set to one of the following values:</span></span> 
    
   - <span data-ttu-id="b40b0-112">FL_FULLSTRING： 若要匹配， **lpProp**搜索字符串必须包含在由**ulPropTag**标识的属性。</span><span class="sxs-lookup"><span data-stu-id="b40b0-112">FL_FULLSTRING: To match, the **lpProp** search string must be contained in the property identified by **ulPropTag**.</span></span>
        
   - <span data-ttu-id="b40b0-113">FL_PREFIX： 若要匹配， **lpProp**搜索字符串必须显示由**ulPropTag**标识属性的开头。</span><span class="sxs-lookup"><span data-stu-id="b40b0-113">FL_PREFIX : To match, the **lpProp** search string must appear at the start of the property identified by **ulPropTag**.</span></span> <span data-ttu-id="b40b0-114">应仅最由**lpProp**搜索字符串的长度比较两个字符串。</span><span class="sxs-lookup"><span data-stu-id="b40b0-114">The two strings should be compared only up to the length of the search string indicated by **lpProp**.</span></span> 
        
   - <span data-ttu-id="b40b0-115">FL_SUBSTRING： 若要匹配， **lpProp**搜索字符串必须包含无处不在由**ulPropTag**标识的属性。</span><span class="sxs-lookup"><span data-stu-id="b40b0-115">FL_SUBSTRING: To match, the **lpProp** search string must be contained anywhere in the property identified by **ulPropTag**.</span></span> 
        
   <span data-ttu-id="b40b0-116">**UlFuzzyLevel**成员**高 16 位**的类型 PT_STRING8 属性仅应用于，并可以设置为下列值的任意组合：</span><span class="sxs-lookup"><span data-stu-id="b40b0-116">The **upper 16 bits** of the **ulFuzzyLevel** member apply only to properties of type PT_STRING8 and can be set to the following values in any combination:</span></span> 
        
   - <span data-ttu-id="b40b0-117">FL_IGNORECASE： 无需考虑用例，应进行比较。</span><span class="sxs-lookup"><span data-stu-id="b40b0-117">FL_IGNORECASE: The comparison should be made without considering case.</span></span> 
        
   - <span data-ttu-id="b40b0-118">FL_IGNORENONSPACE： 比较结果应忽略如音符 Unicode 定义不占位字符。</span><span class="sxs-lookup"><span data-stu-id="b40b0-118">FL_IGNORENONSPACE: The comparison should ignore Unicode-defined non-spacing characters such as diacritical marks.</span></span> 
        
   - <span data-ttu-id="b40b0-119">FL_LOOSE： 比较结果应为您提供忽略大小写和不占位字符匹配尽可能。</span><span class="sxs-lookup"><span data-stu-id="b40b0-119">FL_LOOSE: The comparison should give you a match whenever possible, ignoring case and non-spacing characters.</span></span> 
    
<span data-ttu-id="b40b0-120">**ulPropTag**</span><span class="sxs-lookup"><span data-stu-id="b40b0-120">**ulPropTag**</span></span>
  
> <span data-ttu-id="b40b0-121">标识要检查的搜索字符串匹配项的字符串属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="b40b0-121">Property tag identifying the string property to be checked for occurrence of the search string.</span></span> 
    
<span data-ttu-id="b40b0-122">**lpProp**</span><span class="sxs-lookup"><span data-stu-id="b40b0-122">**lpProp**</span></span>
  
> <span data-ttu-id="b40b0-123">指针指向包含要用作搜索字符串的字符串值的属性值结构。</span><span class="sxs-lookup"><span data-stu-id="b40b0-123">Pointer to a property value structure that contains the string value to use as the search string.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b40b0-124">说明</span><span class="sxs-lookup"><span data-stu-id="b40b0-124">Remarks</span></span>

<span data-ttu-id="b40b0-125">**SContentRestriction**结构中有两个属性标记： **ulPropTag**成员和在**SPropValue**结构的**ulPropTag**成员另一个指向**lpProp**。</span><span class="sxs-lookup"><span data-stu-id="b40b0-125">There are two property tags in an **SContentRestriction** structure: one in the **ulPropTag** member and the other in the **ulPropTag** member of the **SPropValue** structure pointed to by **lpProp**.</span></span> <span data-ttu-id="b40b0-126">在这两个标记，MAPI 需要属性的类型字段，并忽略属性标识符字段。</span><span class="sxs-lookup"><span data-stu-id="b40b0-126">In both tags, MAPI requires only the property type field and ignores the property identifier field.</span></span> <span data-ttu-id="b40b0-127">但是，必须匹配的两个属性类型，否则 MAPI_E_TOO_COMPLEX 在调用[IMAPITable::Restrict](imapitable-restrict.md)或[IMAPITable::FindRow](imapitable-findrow.md)使用限制时则返回的错误值。</span><span class="sxs-lookup"><span data-stu-id="b40b0-127">However, the two property types must match, or else the error value MAPI_E_TOO_COMPLEX is returned when the restriction is used in a call to [IMAPITable::Restrict](imapitable-restrict.md) or [IMAPITable::FindRow](imapitable-findrow.md).</span></span> 
  
<span data-ttu-id="b40b0-128">值 FL_FULLSTRING、 FL_PREFIX 和 FL_SUBSTRING 相互排斥。</span><span class="sxs-lookup"><span data-stu-id="b40b0-128">The values FL_FULLSTRING, FL_PREFIX, and FL_SUBSTRING are mutually exclusive.</span></span> <span data-ttu-id="b40b0-129">可以设置仅有一种，且两者之一必须设置。</span><span class="sxs-lookup"><span data-stu-id="b40b0-129">Only one of them can be set, and one of them must be set.</span></span> <span data-ttu-id="b40b0-130">及其含义固定的并提供程序必须完全按照定义方式实现它们。</span><span class="sxs-lookup"><span data-stu-id="b40b0-130">Their meanings are fixed, and the provider must implement them exactly as defined.</span></span> <span data-ttu-id="b40b0-131">如果无法支持这些值时，提供程序应返回 MAPI_E_TOO_COMPLEX。</span><span class="sxs-lookup"><span data-stu-id="b40b0-131">The provider should return MAPI_E_TOO_COMPLEX if it is unable to support these values.</span></span> 
  
<span data-ttu-id="b40b0-132">值 FL_IGNORECASE、 FL_IGNORENONSPACE 和 FL_LOOSE 无关。</span><span class="sxs-lookup"><span data-stu-id="b40b0-132">The values FL_IGNORECASE, FL_IGNORENONSPACE, and FL_LOOSE are independent.</span></span> <span data-ttu-id="b40b0-133">任意位置从零到所有这三个它们可以设置。</span><span class="sxs-lookup"><span data-stu-id="b40b0-133">Anywhere from zero to all three of them can be set.</span></span> <span data-ttu-id="b40b0-134">作为指导仅提供及其定义和提供程序是免费实现的每个标志自己特定含义。</span><span class="sxs-lookup"><span data-stu-id="b40b0-134">Their definitions are provided as a guideline only, and the provider is free to implement its own specific meaning of each flag.</span></span> <span data-ttu-id="b40b0-135">如果还没有指定的标志的实现，提供程序不应该返回任何错误的含义。</span><span class="sxs-lookup"><span data-stu-id="b40b0-135">The provider should not return any error indication if it has no implementation of a specified flag.</span></span> 
  
<span data-ttu-id="b40b0-136">属性不存在时未定义的属性对施加内容限制结果。</span><span class="sxs-lookup"><span data-stu-id="b40b0-136">The result of a content restriction imposed against a property is undefined when the property does not exist.</span></span> <span data-ttu-id="b40b0-137">当客户端定义完善的行为的需要这样的限制而不是确保是否属性存在，例如，它不是必需的表格列它应创建加入带存在限制内容的限制**和**限制。</span><span class="sxs-lookup"><span data-stu-id="b40b0-137">When a client requires well-defined behavior for such a restriction and is not sure whether the property exists for example, it is not a required column of a table it should create an **AND** restriction to join the content restriction with an exist restriction.</span></span> <span data-ttu-id="b40b0-138">使用[SExistRestriction](sexistrestriction.md)结构以定义存在限制和[SAndRestriction](sandrestriction.md)结构，用于定义**和**限制。</span><span class="sxs-lookup"><span data-stu-id="b40b0-138">Use an [SExistRestriction](sexistrestriction.md) structure to define the exist restriction and an [SAndRestriction](sandrestriction.md) structure to define the **AND** restriction.</span></span> 
  
<span data-ttu-id="b40b0-139">有关**SContentRestriction**结构和限制的详细信息，请参阅[有关限制](about-restrictions.md)。</span><span class="sxs-lookup"><span data-stu-id="b40b0-139">For more information about the **SContentRestriction** structure and restrictions in general, see [About Restrictions](about-restrictions.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b40b0-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b40b0-140">See also</span></span>

- [<span data-ttu-id="b40b0-141">SPropValue</span><span class="sxs-lookup"><span data-stu-id="b40b0-141">SPropValue</span></span>](spropvalue.md)
- [<span data-ttu-id="b40b0-142">SRestriction</span><span class="sxs-lookup"><span data-stu-id="b40b0-142">SRestriction</span></span>](srestriction.md)
- [<span data-ttu-id="b40b0-143">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="b40b0-143">MAPI Structures</span></span>](mapi-structures.md)

