---
title: SMAPIFormProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SMAPIFormProp
api_type:
- COM
ms.assetid: 80f1c2e0-3567-4b16-86cb-d5e6ac95c2ee
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 968f9e1dad3a233b31f0ce29d3ce935b1257948c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32309497"
---
# <a name="smapiformprop"></a><span data-ttu-id="da6cd-103">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="da6cd-103">SMAPIFormProp</span></span>

  
  
<span data-ttu-id="da6cd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="da6cd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="da6cd-105">介绍用于窗体的命名属性。</span><span class="sxs-lookup"><span data-stu-id="da6cd-105">Describes a named property used with a form.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="da6cd-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="da6cd-106">Header file:</span></span>  <br/> |<span data-ttu-id="da6cd-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="da6cd-107">Mapiform.h</span></span>  <br/> |
   
```cpp
typedef struct _SMAPIFormProp
{
  ULONG ulFlags;
  ULONG nPropType;
  MAPINAMEID nmid;
  LPSTR pszDisplayName;
  FORMPROPSPECIALTYPE nSpecialType;
  union
  {
    struct
    {
      MAPINAMEID nmidIdx;
      ULONG cfpevAvailable;
      LPMAPIFORMPROPENUMVAL pfpevAvailable;
    } s1;
  } u;
} SMAPIFormProp, FAR * LPMAPIFORMPROP;

```

## <a name="members"></a><span data-ttu-id="da6cd-108">成员</span><span class="sxs-lookup"><span data-stu-id="da6cd-108">Members</span></span>

 <span data-ttu-id="da6cd-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="da6cd-109">**ulFlags**</span></span>
  
> <span data-ttu-id="da6cd-110">用于区分**SMAPIFormProp**结构中的字符串格式的标志。</span><span class="sxs-lookup"><span data-stu-id="da6cd-110">Flags used to distinguish the format of the strings in the **SMAPIFormProp** structure.</span></span> <span data-ttu-id="da6cd-111">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="da6cd-111">The following flag can be set:</span></span> 
    
<span data-ttu-id="da6cd-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="da6cd-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="da6cd-113">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="da6cd-113">The strings returned are in Unicode format.</span></span> <span data-ttu-id="da6cd-114">如果未设置 MAPI_UNICODE, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="da6cd-114">If MAPI_UNICODE is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="da6cd-115">**nPropType**</span><span class="sxs-lookup"><span data-stu-id="da6cd-115">**nPropType**</span></span>
  
> <span data-ttu-id="da6cd-116">命名属性的类型, 最重要的单词设置为零。</span><span class="sxs-lookup"><span data-stu-id="da6cd-116">Type of the named property, with the most significant word set to zero.</span></span> 
    
 <span data-ttu-id="da6cd-117">**nmid**</span><span class="sxs-lookup"><span data-stu-id="da6cd-117">**nmid**</span></span>
  
> <span data-ttu-id="da6cd-118">命名属性的名称, 其中包括标识属性集的**GUID**结构, 或者是表示接口标识符和表单名称的数值或字符串值。</span><span class="sxs-lookup"><span data-stu-id="da6cd-118">Name for the named property, which includes a **GUID** structure identifying the property set and either a numeric or string value that represents an interface identifier and form name.</span></span> 
    
 <span data-ttu-id="da6cd-119">**pszDisplayName**</span><span class="sxs-lookup"><span data-stu-id="da6cd-119">**pszDisplayName**</span></span>
  
> <span data-ttu-id="da6cd-120">指向命名属性的显示名称的指针。</span><span class="sxs-lookup"><span data-stu-id="da6cd-120">Pointer to the display name of the named property.</span></span>
    
 <span data-ttu-id="da6cd-121">**nSpecialType**</span><span class="sxs-lookup"><span data-stu-id="da6cd-121">**nSpecialType**</span></span>
  
> <span data-ttu-id="da6cd-122">描述**u**成员中包含的数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="da6cd-122">Value describing the type of data included in the **u** member.</span></span> <span data-ttu-id="da6cd-123">可能的值如下所示:</span><span class="sxs-lookup"><span data-stu-id="da6cd-123">Possible values are as follows:</span></span> 
    
<span data-ttu-id="da6cd-124">FPST_VANILLA</span><span class="sxs-lookup"><span data-stu-id="da6cd-124">FPST_VANILLA</span></span> 
  
> <span data-ttu-id="da6cd-125">**u**成员不包含枚举。</span><span class="sxs-lookup"><span data-stu-id="da6cd-125">The **u** member does not contain an enumeration.</span></span> 
    
<span data-ttu-id="da6cd-126">FPST_ENUM_PROP</span><span class="sxs-lookup"><span data-stu-id="da6cd-126">FPST_ENUM_PROP</span></span> 
  
> <span data-ttu-id="da6cd-127">**u**成员包含描述枚举的结构。</span><span class="sxs-lookup"><span data-stu-id="da6cd-127">The **u** member contains a structure that describes an enumeration.</span></span> 
    
 <span data-ttu-id="da6cd-128">**u**</span><span class="sxs-lookup"><span data-stu-id="da6cd-128">**u**</span></span>
  
> <span data-ttu-id="da6cd-129">描述命名属性的名称和编号之间的关联的联合。</span><span class="sxs-lookup"><span data-stu-id="da6cd-129">Union describing the association between the name and number of the named property.</span></span> <span data-ttu-id="da6cd-130">通过使用某些属性, **u**成员是空的。</span><span class="sxs-lookup"><span data-stu-id="da6cd-130">By using some properties, the **u** member is empty.</span></span> <span data-ttu-id="da6cd-131">使用其他属性, 它在由以下成员组成的结构中表示:</span><span class="sxs-lookup"><span data-stu-id="da6cd-131">With other properties, it is represented in a structure consisting of the following members:</span></span> 
    
 <span data-ttu-id="da6cd-132">**nmidIdx**</span><span class="sxs-lookup"><span data-stu-id="da6cd-132">**nmidIdx**</span></span>
  
> <span data-ttu-id="da6cd-133">包含命名属性的属性集和标识符的[MAPINAMEID](mapinameid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="da6cd-133">The [MAPINAMEID](mapinameid.md) structure that contains the property set and identifier for the named property.</span></span> 
    
 <span data-ttu-id="da6cd-134">**cfpevAvailable**</span><span class="sxs-lookup"><span data-stu-id="da6cd-134">**cfpevAvailable**</span></span>
  
> <span data-ttu-id="da6cd-135">由**pfpevAvailable**成员指向的数组中的[SMAPIFormPropEnumVal](smapiformpropenumval.md)结构的计数。</span><span class="sxs-lookup"><span data-stu-id="da6cd-135">Count of [SMAPIFormPropEnumVal](smapiformpropenumval.md) structures in the array pointed to by the **pfpevAvailable** member.</span></span> 
    
 <span data-ttu-id="da6cd-136">**pfpevAvailable**</span><span class="sxs-lookup"><span data-stu-id="da6cd-136">**pfpevAvailable**</span></span>
  
> <span data-ttu-id="da6cd-137">指向**SMAPIFormPropEnumVal**结构的数组的指针, 其中每个结构都保留命名属性的值。</span><span class="sxs-lookup"><span data-stu-id="da6cd-137">Pointer to an array of **SMAPIFormPropEnumVal** structures, each of which holds a value for the named property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="da6cd-138">注解</span><span class="sxs-lookup"><span data-stu-id="da6cd-138">Remarks</span></span>

<span data-ttu-id="da6cd-139">**SMAPIFormProp**结构包含有关用作[IMAPIFormInfo](imapiforminfoimapiprop.md)接口定义的一部分的窗体属性的信息;**nSpecialType**包含适用于**u** union 的标记, 该标记是**SMAPIFormProp**的一部分。</span><span class="sxs-lookup"><span data-stu-id="da6cd-139">The **SMAPIFormProp** structure contains information about a form property used as part of the definitions of the [IMAPIFormInfo](imapiforminfoimapiprop.md) interface; **nSpecialType** contains a tag that applies to the **u** union that is part of **SMAPIFormProp**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da6cd-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da6cd-140">See also</span></span>



[<span data-ttu-id="da6cd-141">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="da6cd-141">MAPINAMEID</span></span>](mapinameid.md)
  
[<span data-ttu-id="da6cd-142">SMAPIFormPropEnumVal</span><span class="sxs-lookup"><span data-stu-id="da6cd-142">SMAPIFormPropEnumVal</span></span>](smapiformpropenumval.md)


[<span data-ttu-id="da6cd-143">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="da6cd-143">MAPI Structures</span></span>](mapi-structures.md)

