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
ms.openlocfilehash: 73475c5ee4e715796e06642756c05746b271d128
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778815"
---
# <a name="smapiformprop"></a><span data-ttu-id="d427d-103">SMAPIFormProp</span><span class="sxs-lookup"><span data-stu-id="d427d-103">SMAPIFormProp</span></span>

  
  
<span data-ttu-id="d427d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d427d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d427d-105">描述用于窗体的命名的属性。</span><span class="sxs-lookup"><span data-stu-id="d427d-105">Describes a named property used with a form.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d427d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="d427d-106">Header file:</span></span>  <br/> |<span data-ttu-id="d427d-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="d427d-107">Mapiform.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="d427d-108">Members</span><span class="sxs-lookup"><span data-stu-id="d427d-108">Members</span></span>

 <span data-ttu-id="d427d-109">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="d427d-109">**ulFlags**</span></span>
  
> <span data-ttu-id="d427d-110">用于区分**SMAPIFormProp**结构中的字符串格式的标志。</span><span class="sxs-lookup"><span data-stu-id="d427d-110">Flags used to distinguish the format of the strings in the **SMAPIFormProp** structure.</span></span> <span data-ttu-id="d427d-111">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="d427d-111">The following flag can be set:</span></span> 
    
<span data-ttu-id="d427d-112">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="d427d-112">MAPI_UNICODE</span></span> 
  
> <span data-ttu-id="d427d-113">返回的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="d427d-113">The strings returned are in Unicode format.</span></span> <span data-ttu-id="d427d-114">如果未设置 MAPI_UNICODE 的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="d427d-114">If MAPI_UNICODE is not set, the strings are in ANSI format.</span></span>
    
 <span data-ttu-id="d427d-115">**nPropType**</span><span class="sxs-lookup"><span data-stu-id="d427d-115">**nPropType**</span></span>
  
> <span data-ttu-id="d427d-116">命名属性，设置为零的最大单词的类型。</span><span class="sxs-lookup"><span data-stu-id="d427d-116">Type of the named property, with the most significant word set to zero.</span></span> 
    
 <span data-ttu-id="d427d-117">**nmid**</span><span class="sxs-lookup"><span data-stu-id="d427d-117">**nmid**</span></span>
  
> <span data-ttu-id="d427d-118">包含标识表示接口标识符和窗体名称的属性集和数字或字符串值的**GUID**结构的命名属性的名称。</span><span class="sxs-lookup"><span data-stu-id="d427d-118">Name for the named property, which includes a **GUID** structure identifying the property set and either a numeric or string value that represents an interface identifier and form name.</span></span> 
    
 <span data-ttu-id="d427d-119">**pszDisplayName**</span><span class="sxs-lookup"><span data-stu-id="d427d-119">**pszDisplayName**</span></span>
  
> <span data-ttu-id="d427d-120">指向的命名属性的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d427d-120">Pointer to the display name of the named property.</span></span>
    
 <span data-ttu-id="d427d-121">**nSpecialType**</span><span class="sxs-lookup"><span data-stu-id="d427d-121">**nSpecialType**</span></span>
  
> <span data-ttu-id="d427d-122">描述**u**成员中包含的数据类型的值。</span><span class="sxs-lookup"><span data-stu-id="d427d-122">Value describing the type of data included in the **u** member.</span></span> <span data-ttu-id="d427d-123">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="d427d-123">Possible values are as follows:</span></span> 
    
<span data-ttu-id="d427d-124">FPST_VANILLA</span><span class="sxs-lookup"><span data-stu-id="d427d-124">FPST_VANILLA</span></span> 
  
> <span data-ttu-id="d427d-125">**U**成员不包含枚举。</span><span class="sxs-lookup"><span data-stu-id="d427d-125">The **u** member does not contain an enumeration.</span></span> 
    
<span data-ttu-id="d427d-126">FPST_ENUM_PROP</span><span class="sxs-lookup"><span data-stu-id="d427d-126">FPST_ENUM_PROP</span></span> 
  
> <span data-ttu-id="d427d-127">**U**成员包含描述枚举的结构。</span><span class="sxs-lookup"><span data-stu-id="d427d-127">The **u** member contains a structure that describes an enumeration.</span></span> 
    
 <span data-ttu-id="d427d-128">**u**</span><span class="sxs-lookup"><span data-stu-id="d427d-128">**u**</span></span>
  
> <span data-ttu-id="d427d-129">联合描述的名称和数量的命名属性之间的关联。</span><span class="sxs-lookup"><span data-stu-id="d427d-129">Union describing the association between the name and number of the named property.</span></span> <span data-ttu-id="d427d-130">通过使用一些属性， **u**成员为空。</span><span class="sxs-lookup"><span data-stu-id="d427d-130">By using some properties, the **u** member is empty.</span></span> <span data-ttu-id="d427d-131">与其他属性，它表示在结构包含的以下成员：</span><span class="sxs-lookup"><span data-stu-id="d427d-131">With other properties, it is represented in a structure consisting of the following members:</span></span> 
    
 <span data-ttu-id="d427d-132">**nmidIdx**</span><span class="sxs-lookup"><span data-stu-id="d427d-132">**nmidIdx**</span></span>
  
> <span data-ttu-id="d427d-133">包含的属性集和命名属性标识符的[MAPINAMEID](mapinameid.md)结构。</span><span class="sxs-lookup"><span data-stu-id="d427d-133">The [MAPINAMEID](mapinameid.md) structure that contains the property set and identifier for the named property.</span></span> 
    
 <span data-ttu-id="d427d-134">**cfpevAvailable**</span><span class="sxs-lookup"><span data-stu-id="d427d-134">**cfpevAvailable**</span></span>
  
> <span data-ttu-id="d427d-135">由**pfpevAvailable**成员指向[SMAPIFormPropEnumVal](smapiformpropenumval.md)结构数组中的计数。</span><span class="sxs-lookup"><span data-stu-id="d427d-135">Count of [SMAPIFormPropEnumVal](smapiformpropenumval.md) structures in the array pointed to by the **pfpevAvailable** member.</span></span> 
    
 <span data-ttu-id="d427d-136">**pfpevAvailable**</span><span class="sxs-lookup"><span data-stu-id="d427d-136">**pfpevAvailable**</span></span>
  
> <span data-ttu-id="d427d-137">指向数组**SMAPIFormPropEnumVal**结构，其中每个保留的命名属性的值。</span><span class="sxs-lookup"><span data-stu-id="d427d-137">Pointer to an array of **SMAPIFormPropEnumVal** structures, each of which holds a value for the named property.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="d427d-138">说明</span><span class="sxs-lookup"><span data-stu-id="d427d-138">Remarks</span></span>

<span data-ttu-id="d427d-139">**SMAPIFormProp**结构包含有关用作[IMAPIFormInfo](imapiforminfoimapiprop.md)接口; 的定义的一部分的窗体属性的信息**nSpecialType**包含适用于**u**联合**SMAPIFormProp**的一部分的标记。</span><span class="sxs-lookup"><span data-stu-id="d427d-139">The **SMAPIFormProp** structure contains information about a form property used as part of the definitions of the [IMAPIFormInfo](imapiforminfoimapiprop.md) interface; **nSpecialType** contains a tag that applies to the **u** union that is part of **SMAPIFormProp**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d427d-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d427d-140">See also</span></span>



[<span data-ttu-id="d427d-141">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="d427d-141">MAPINAMEID</span></span>](mapinameid.md)
  
[<span data-ttu-id="d427d-142">SMAPIFormPropEnumVal</span><span class="sxs-lookup"><span data-stu-id="d427d-142">SMAPIFormPropEnumVal</span></span>](smapiformpropenumval.md)


[<span data-ttu-id="d427d-143">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="d427d-143">MAPI Structures</span></span>](mapi-structures.md)

