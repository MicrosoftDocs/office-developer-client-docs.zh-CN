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
ms.openlocfilehash: c3a21e8a6e69cae9d8b757a60fe56d63e079b3ea
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776367"
---
# <a name="mapinameid"></a><span data-ttu-id="69991-103">MAPINAMEID</span><span class="sxs-lookup"><span data-stu-id="69991-103">MAPINAMEID</span></span>

  
  
<span data-ttu-id="69991-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="69991-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="69991-105">描述的命名的属性。</span><span class="sxs-lookup"><span data-stu-id="69991-105">Describes a named property.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="69991-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="69991-106">Header file:</span></span>  <br/> |<span data-ttu-id="69991-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="69991-107">Mapidefs.h</span></span>  <br/> |
   
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

## <a name="members"></a><span data-ttu-id="69991-108">Members</span><span class="sxs-lookup"><span data-stu-id="69991-108">Members</span></span>

 <span data-ttu-id="69991-109">**lpguid**</span><span class="sxs-lookup"><span data-stu-id="69991-109">**lpguid**</span></span>
  
> <span data-ttu-id="69991-110">指向定义特定属性的[GUID](guid.md)结构设置;此成员不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="69991-110">Pointer to a [GUID](guid.md) structure defining a particular property set; this member cannot be NULL.</span></span> <span data-ttu-id="69991-111">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="69991-111">Valid values are as follows:</span></span> 
    
<span data-ttu-id="69991-112">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="69991-112">PS_PUBLIC_STRINGS</span></span>
  
> 
    
<span data-ttu-id="69991-113">PS_MAPI</span><span class="sxs-lookup"><span data-stu-id="69991-113">PS_MAPI</span></span>
  
> 
    
<span data-ttu-id="69991-114">客户端定义的值</span><span class="sxs-lookup"><span data-stu-id="69991-114">A client-defined value</span></span>
  
> 
    
 <span data-ttu-id="69991-115">**ulKind**</span><span class="sxs-lookup"><span data-stu-id="69991-115">**ulKind**</span></span>
  
> <span data-ttu-id="69991-116">描述**类型**成员中的值的类型的值。</span><span class="sxs-lookup"><span data-stu-id="69991-116">Value describing the type of value in the **Kind** member.</span></span> <span data-ttu-id="69991-117">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="69991-117">Valid values are as follows:</span></span> 
    
<span data-ttu-id="69991-118">MNID_ID</span><span class="sxs-lookup"><span data-stu-id="69991-118">MNID_ID</span></span> 
  
> <span data-ttu-id="69991-119">**类型**成员包含一个整数值，表示的属性名称。</span><span class="sxs-lookup"><span data-stu-id="69991-119">The **Kind** member contains an integer value that represents the property name.</span></span> 
    
<span data-ttu-id="69991-120">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="69991-120">MNID_STRING</span></span> 
  
> <span data-ttu-id="69991-121">**类型**成员包含表示的属性名称的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="69991-121">The **Kind** member contains a Unicode character string representing the property name.</span></span> 
    
 <span data-ttu-id="69991-122">**种类**</span><span class="sxs-lookup"><span data-stu-id="69991-122">**Kind**</span></span>
  
> <span data-ttu-id="69991-123">联合描述的命名属性的名称。</span><span class="sxs-lookup"><span data-stu-id="69991-123">Union describing the name of the named property.</span></span> <span data-ttu-id="69991-124">名称可以存储在**盖**，整数值或**lpwstrName**中存储的 Unicode 字符字符串。</span><span class="sxs-lookup"><span data-stu-id="69991-124">The name can be either an integer value, stored in **lID**, or a Unicode character string, stored in **lpwstrName**.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="69991-125">说明</span><span class="sxs-lookup"><span data-stu-id="69991-125">Remarks</span></span>

<span data-ttu-id="69991-126">**MAPINAMEID**结构用于描述具有超过 0x8000 标识符的命名的属性属性。</span><span class="sxs-lookup"><span data-stu-id="69991-126">The **MAPINAMEID** structure is used to describe named properties properties that have identifiers over 0x8000.</span></span> <span data-ttu-id="69991-127">属性集是一个重要组成部分的命名属性。</span><span class="sxs-lookup"><span data-stu-id="69991-127">A property set is an important part a named property.</span></span> <span data-ttu-id="69991-128">例如 PS_PUBLIC_STRINGS 或 PS_ROUTING_ADDRTYPE 是由 MAPI 的属性集。</span><span class="sxs-lookup"><span data-stu-id="69991-128">For example PS_PUBLIC_STRINGS or PS_ROUTING_ADDRTYPE are property sets defined by MAPI.</span></span> 
  
<span data-ttu-id="69991-129">命名的属性允许客户端比可用 MAPI 定义属性标识符的范围中的较大命名空间中定义自定义属性。</span><span class="sxs-lookup"><span data-stu-id="69991-129">Named properties enable clients to define custom properties in a larger namespace than is available in the MAPI-defined property identifier range.</span></span> <span data-ttu-id="69991-130">属性名称不能用于直接调用获取属性值他们必须首先将映射到属性标识符通过[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法。</span><span class="sxs-lookup"><span data-stu-id="69991-130">Property names cannot be used to obtain property values directly; they must first be mapped to property identifiers through the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method.</span></span> <span data-ttu-id="69991-131">例如，消息的特定对象，MAPI 保留自定义属性的属性标识符的范围。</span><span class="sxs-lookup"><span data-stu-id="69991-131">For particular objects such as messages, MAPI reserves a range of property identifiers for custom properties.</span></span> <span data-ttu-id="69991-132">因此，对于这些对象，客户端没有以使用命名的属性，可以保存关联开销。</span><span class="sxs-lookup"><span data-stu-id="69991-132">Therefore, for these objects, clients do not have to use named properties and can save the associated overhead.</span></span> 
  
<span data-ttu-id="69991-133">有关命名属性的详细信息，请参阅[名为属性](mapi-named-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="69991-133">For more information about named properties, see [Named Properties](mapi-named-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="69991-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69991-134">See also</span></span>



[<span data-ttu-id="69991-135">GUID</span><span class="sxs-lookup"><span data-stu-id="69991-135">GUID</span></span>](guid.md)
  
[<span data-ttu-id="69991-136">IMAPIProp::GetIDsFromNames</span><span class="sxs-lookup"><span data-stu-id="69991-136">IMAPIProp::GetIDsFromNames</span></span>](imapiprop-getidsfromnames.md)


[<span data-ttu-id="69991-137">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="69991-137">MAPI Structures</span></span>](mapi-structures.md)

