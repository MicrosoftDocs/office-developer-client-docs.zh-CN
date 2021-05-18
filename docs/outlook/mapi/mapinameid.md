---
title: MAPINAMEID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPINAMEID
api_type:
- COM
ms.assetid: 9a92e9cd-8282-4cf0-93af-4089b3763594
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: baec750a460b3ba9becd2e1dddf967705424ac4e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411678"
---
# <a name="mapinameid"></a><span data-ttu-id="5968e-103">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="5968e-103">MAPINAMEID</span></span>

  
  
<span data-ttu-id="5968e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5968e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5968e-105">描述命名属性。</span><span class="sxs-lookup"><span data-stu-id="5968e-105">Describes a named property.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5968e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="5968e-106">Header file:</span></span>  <br/> |<span data-ttu-id="5968e-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5968e-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct _MAPINAMEID
{
  LPGUID lpguid;
  ULONG ulKind;
  union
  {
    LONG lID;
    LPWSTR lpwstrName;
  } Kind;
} MAPINAMEID, FAR *LPMAPINAMEID;

```

## <a name="members"></a><span data-ttu-id="5968e-108">Members</span><span class="sxs-lookup"><span data-stu-id="5968e-108">Members</span></span>

 <span data-ttu-id="5968e-109">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="5968e-109">**lpguid**</span></span>
  
> <span data-ttu-id="5968e-110">指向定义特定 [属性集的 GUID](guid.md) 结构的指针;此成员不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="5968e-110">Pointer to a [GUID](guid.md) structure defining a particular property set; this member cannot be NULL.</span></span> <span data-ttu-id="5968e-111">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="5968e-111">Valid values are as follows:</span></span> 
    
<span data-ttu-id="5968e-112">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="5968e-112">PS_PUBLIC_STRINGS</span></span>
  
> 
    
<span data-ttu-id="5968e-113">PS_MAPI</span><span class="sxs-lookup"><span data-stu-id="5968e-113">PS_MAPI</span></span>
  
> 
    
<span data-ttu-id="5968e-114">客户端定义的值</span><span class="sxs-lookup"><span data-stu-id="5968e-114">A client-defined value</span></span>
  
> 
    
 <span data-ttu-id="5968e-115">**ulKind**</span><span class="sxs-lookup"><span data-stu-id="5968e-115">**ulKind**</span></span>
  
> <span data-ttu-id="5968e-116">描述 Kind 成员中的值 **类型的** 值。</span><span class="sxs-lookup"><span data-stu-id="5968e-116">Value describing the type of value in the **Kind** member.</span></span> <span data-ttu-id="5968e-117">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="5968e-117">Valid values are as follows:</span></span> 
    
<span data-ttu-id="5968e-118">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="5968e-118">MNID_ID</span></span> 
  
> <span data-ttu-id="5968e-119">**Kind** 成员包含一个表示属性名称的整数值。</span><span class="sxs-lookup"><span data-stu-id="5968e-119">The **Kind** member contains an integer value that represents the property name.</span></span> 
    
<span data-ttu-id="5968e-120">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="5968e-120">MNID_STRING</span></span> 
  
> <span data-ttu-id="5968e-121">**Kind** 成员包含表示属性名称的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="5968e-121">The **Kind** member contains a Unicode character string representing the property name.</span></span> 
    
 <span data-ttu-id="5968e-122">**Kind**</span><span class="sxs-lookup"><span data-stu-id="5968e-122">**Kind**</span></span>
  
> <span data-ttu-id="5968e-123">用于描述命名属性的名称的 Union。</span><span class="sxs-lookup"><span data-stu-id="5968e-123">Union describing the name of the named property.</span></span> <span data-ttu-id="5968e-124">该名称可以是存储在 **lID** 中的整数值或存储在 **lpwstrName** 中的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="5968e-124">The name can be either an integer value, stored in **lID**, or a Unicode character string, stored in **lpwstrName**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="5968e-125">备注</span><span class="sxs-lookup"><span data-stu-id="5968e-125">Remarks</span></span>

<span data-ttu-id="5968e-126">**MAPINAMEID** 结构用于描述在属性类型中具有标识符的命名0x8000。</span><span class="sxs-lookup"><span data-stu-id="5968e-126">The **MAPINAMEID** structure is used to describe named properties properties that have identifiers over 0x8000.</span></span> <span data-ttu-id="5968e-127">属性集是命名属性的重要部分。</span><span class="sxs-lookup"><span data-stu-id="5968e-127">A property set is an important part a named property.</span></span> <span data-ttu-id="5968e-128">例如，PS_PUBLIC_STRINGS或PS_ROUTING_ADDRTYPE是 MAPI 定义的属性集。</span><span class="sxs-lookup"><span data-stu-id="5968e-128">For example PS_PUBLIC_STRINGS or PS_ROUTING_ADDRTYPE are property sets defined by MAPI.</span></span> 
  
<span data-ttu-id="5968e-129">命名属性使客户端能够定义比 MAPI 定义属性标识符范围中可用的更大命名空间中的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="5968e-129">Named properties enable clients to define custom properties in a larger namespace than is available in the MAPI-defined property identifier range.</span></span> <span data-ttu-id="5968e-130">属性名称不能用于直接获取属性值;它们必须先通过 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 方法映射到属性标识符。</span><span class="sxs-lookup"><span data-stu-id="5968e-130">Property names cannot be used to obtain property values directly; they must first be mapped to property identifiers through the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method.</span></span> <span data-ttu-id="5968e-131">对于邮件等特定对象，MAPI 保留自定义属性的属性标识符范围。</span><span class="sxs-lookup"><span data-stu-id="5968e-131">For particular objects such as messages, MAPI reserves a range of property identifiers for custom properties.</span></span> <span data-ttu-id="5968e-132">因此，对于这些对象，客户端不需要使用命名属性，并且可以节省关联的开销。</span><span class="sxs-lookup"><span data-stu-id="5968e-132">Therefore, for these objects, clients do not have to use named properties and can save the associated overhead.</span></span> 
  
<span data-ttu-id="5968e-133">有关命名属性详细信息，请参阅 [命名属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="5968e-133">For more information about named properties, see [Named Properties](mapi-named-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5968e-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5968e-134">See also</span></span>



[<span data-ttu-id="5968e-135">GUID</span><span class="sxs-lookup"><span data-stu-id="5968e-135">GUID</span></span>](guid.md)
  
[<span data-ttu-id="5968e-136">IMAPIProp::GetIDsFromNames</span><span class="sxs-lookup"><span data-stu-id="5968e-136">IMAPIProp::GetIDsFromNames</span></span>](imapiprop-getidsfromnames.md)


[<span data-ttu-id="5968e-137">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="5968e-137">MAPI Structures</span></span>](mapi-structures.md)

