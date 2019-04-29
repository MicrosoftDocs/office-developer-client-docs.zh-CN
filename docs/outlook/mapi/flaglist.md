---
title: FLAGLIST
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.FLAGLIST
api_type:
- COM
ms.assetid: b4c0655c-1a3a-4f89-a977-0431db596512
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a5e508f5f7e6554a115517da87a8eac39f39aecf
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412973"
---
# <a name="flaglist"></a><span data-ttu-id="0073a-103">FLAGLIST</span><span class="sxs-lookup"><span data-stu-id="0073a-103">FLAGLIST</span></span>

  
  
<span data-ttu-id="0073a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0073a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0073a-105">包含用于指示名称解析过程中的地址条目状态的标志列表。</span><span class="sxs-lookup"><span data-stu-id="0073a-105">Contains a list of flags used to indicate the status of address entries during the name resolution process.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0073a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="0073a-106">Header file:</span></span>  <br/> |<span data-ttu-id="0073a-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="0073a-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG cFlags;
  ULONG ulFlags[MAPI_DIM];
} FlagList, FAR * LPFlagList;

```

## <a name="members"></a><span data-ttu-id="0073a-108">Members</span><span class="sxs-lookup"><span data-stu-id="0073a-108">Members</span></span>

 <span data-ttu-id="0073a-109">**cFlags**</span><span class="sxs-lookup"><span data-stu-id="0073a-109">**cFlags**</span></span>
  
> <span data-ttu-id="0073a-110">列表中 MAPI 定义的标志的计数。</span><span class="sxs-lookup"><span data-stu-id="0073a-110">Count of MAPI-defined flags in the list.</span></span>
    
 <span data-ttu-id="0073a-111">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="0073a-111">**ulFlags**</span></span>
  
> <span data-ttu-id="0073a-112">为收件人提供名称解析操作的状态的标志数组。</span><span class="sxs-lookup"><span data-stu-id="0073a-112">An array of flags that provides the status of the name resolution operation for a recipient.</span></span> <span data-ttu-id="0073a-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="0073a-113">The following flags can be set:</span></span>
    
<span data-ttu-id="0073a-114">MAPI_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="0073a-114">MAPI_AMBIGUOUS</span></span> 
  
> <span data-ttu-id="0073a-115">收件人已得到解决, 但不是唯一的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="0073a-115">The recipient has been resolved, but not to a unique entry identifier.</span></span> <span data-ttu-id="0073a-116">其他通讯簿容器不应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="0073a-116">Other address book containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="0073a-117">MAPI_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="0073a-117">MAPI_RESOLVED</span></span> 
  
> <span data-ttu-id="0073a-118">收件人已解析为唯一条目标识符。</span><span class="sxs-lookup"><span data-stu-id="0073a-118">The recipient has been resolved to a unique entry identifier.</span></span> <span data-ttu-id="0073a-119">其他通讯簿容器不应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="0073a-119">Other address book containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="0073a-120">MAPI_UNRESOLVED</span><span class="sxs-lookup"><span data-stu-id="0073a-120">MAPI_UNRESOLVED</span></span> 
  
> <span data-ttu-id="0073a-121">该条目尚未解决。</span><span class="sxs-lookup"><span data-stu-id="0073a-121">The entry has not been resolved.</span></span> <span data-ttu-id="0073a-122">其他通讯簿容器应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="0073a-122">Other address book containers should try to resolve this recipient.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="0073a-123">说明</span><span class="sxs-lookup"><span data-stu-id="0073a-123">Remarks</span></span>

<span data-ttu-id="0073a-124">**FLAGLIST**结构用作[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)的参数。</span><span class="sxs-lookup"><span data-stu-id="0073a-124">The **FLAGLIST** structure is used as a parameter to [IABContainer::ResolveNames](iabcontainer-resolvenames.md).</span></span> <span data-ttu-id="0073a-125">要解析的每个收件人都包含在[ADRLIST](adrlist.md)结构中。</span><span class="sxs-lookup"><span data-stu-id="0073a-125">Each of the recipients to be resolved is included in an [ADRLIST](adrlist.md) structure.</span></span> <span data-ttu-id="0073a-126">由于通讯簿容器尝试解析每个收件人, 因此它会在**FLAGLIST**结构中的相应条目中设置适当的标志。</span><span class="sxs-lookup"><span data-stu-id="0073a-126">As the address book container attempts to resolve each recipient, it sets the appropriate flag in the corresponding entry in the **FLAGLIST** structure.</span></span> <span data-ttu-id="0073a-127">**FLAGLIST**结构中的所有条目的顺序与**ADRLIST**结构中的条目的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="0073a-127">All of the entries in the **FLAGLIST** structure are in the same order as the entries in the **ADRLIST** structure.</span></span> <span data-ttu-id="0073a-128">这样便于将标志设置与收件人相关联。</span><span class="sxs-lookup"><span data-stu-id="0073a-128">This makes it easy to associate a flag setting with a recipient.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0073a-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0073a-129">See also</span></span>



[<span data-ttu-id="0073a-130">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="0073a-130">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="0073a-131">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="0073a-131">IABContainer::ResolveNames</span></span>](iabcontainer-resolvenames.md)


[<span data-ttu-id="0073a-132">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="0073a-132">MAPI Structures</span></span>](mapi-structures.md)

