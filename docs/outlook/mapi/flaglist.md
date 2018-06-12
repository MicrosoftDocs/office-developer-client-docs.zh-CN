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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 2cf5ff69e8453b2da26fd5044823ddf4f99a9f45
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774943"
---
# <a name="flaglist"></a><span data-ttu-id="dde21-103">FLAGLIST</span><span class="sxs-lookup"><span data-stu-id="dde21-103">FLAGLIST</span></span>

  
  
<span data-ttu-id="dde21-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="dde21-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="dde21-105">包含用于指示过程名称解析过程中的地址条目的状态标志的列表。</span><span class="sxs-lookup"><span data-stu-id="dde21-105">Contains a list of flags used to indicate the status of address entries during the name resolution process.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dde21-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="dde21-106">Header file:</span></span>  <br/> |<span data-ttu-id="dde21-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="dde21-107">Mapidefs.h</span></span>  <br/> |
   
```cpp
typedef struct
{
  ULONG cFlags;
  ULONG ulFlags[MAPI_DIM];
} FlagList, FAR * LPFlagList;

```

## <a name="members"></a><span data-ttu-id="dde21-108">成员</span><span class="sxs-lookup"><span data-stu-id="dde21-108">Members</span></span>

 <span data-ttu-id="dde21-109">**cFlags**</span><span class="sxs-lookup"><span data-stu-id="dde21-109">**cFlags**</span></span>
  
> <span data-ttu-id="dde21-110">MAPI 定义列表中的标志的计数。</span><span class="sxs-lookup"><span data-stu-id="dde21-110">Count of MAPI-defined flags in the list.</span></span>
    
 <span data-ttu-id="dde21-111">**ulFlags**</span><span class="sxs-lookup"><span data-stu-id="dde21-111">**ulFlags**</span></span>
  
> <span data-ttu-id="dde21-112">提供的收件人的名称解析操作的状态标志的数组。</span><span class="sxs-lookup"><span data-stu-id="dde21-112">An array of flags that provides the status of the name resolution operation for a recipient.</span></span> <span data-ttu-id="dde21-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="dde21-113">The following flags can be set:</span></span>
    
<span data-ttu-id="dde21-114">MAPI_AMBIGUOUS</span><span class="sxs-lookup"><span data-stu-id="dde21-114">MAPI_AMBIGUOUS</span></span> 
  
> <span data-ttu-id="dde21-115">收件人已得到解决，但不适用于唯一项标识符。</span><span class="sxs-lookup"><span data-stu-id="dde21-115">The recipient has been resolved, but not to a unique entry identifier.</span></span> <span data-ttu-id="dde21-116">其他地址簿容器不应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="dde21-116">Other address book containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="dde21-117">MAPI_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="dde21-117">MAPI_RESOLVED</span></span> 
  
> <span data-ttu-id="dde21-118">收件人已解析为唯一项标识符。</span><span class="sxs-lookup"><span data-stu-id="dde21-118">The recipient has been resolved to a unique entry identifier.</span></span> <span data-ttu-id="dde21-119">其他地址簿容器不应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="dde21-119">Other address book containers should not try to resolve this recipient.</span></span> 
    
<span data-ttu-id="dde21-120">MAPI_UNRESOLVED</span><span class="sxs-lookup"><span data-stu-id="dde21-120">MAPI_UNRESOLVED</span></span> 
  
> <span data-ttu-id="dde21-121">条目不已解决。</span><span class="sxs-lookup"><span data-stu-id="dde21-121">The entry has not been resolved.</span></span> <span data-ttu-id="dde21-122">其他地址簿容器应尝试解析该收件人。</span><span class="sxs-lookup"><span data-stu-id="dde21-122">Other address book containers should try to resolve this recipient.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="dde21-123">备注</span><span class="sxs-lookup"><span data-stu-id="dde21-123">Remarks</span></span>

<span data-ttu-id="dde21-124">**FLAGLIST**结构用作[IABContainer::ResolveNames](iabcontainer-resolvenames.md)参数。</span><span class="sxs-lookup"><span data-stu-id="dde21-124">The **FLAGLIST** structure is used as a parameter to [IABContainer::ResolveNames](iabcontainer-resolvenames.md).</span></span> <span data-ttu-id="dde21-125">[ADRLIST](adrlist.md)结构中包含每个要解析的收件人。</span><span class="sxs-lookup"><span data-stu-id="dde21-125">Each of the recipients to be resolved is included in an [ADRLIST](adrlist.md) structure.</span></span> <span data-ttu-id="dde21-126">通讯簿容器尝试解决每个收件人，如**FLAGLIST**结构中的相应条目中设置相应的标志。</span><span class="sxs-lookup"><span data-stu-id="dde21-126">As the address book container attempts to resolve each recipient, it sets the appropriate flag in the corresponding entry in the **FLAGLIST** structure.</span></span> <span data-ttu-id="dde21-127">所有**FLAGLIST**结构中的条目都**ADRLIST**结构中的项的顺序相同。</span><span class="sxs-lookup"><span data-stu-id="dde21-127">All of the entries in the **FLAGLIST** structure are in the same order as the entries in the **ADRLIST** structure.</span></span> <span data-ttu-id="dde21-128">这便于与收件人关联的标记设置。</span><span class="sxs-lookup"><span data-stu-id="dde21-128">This makes it easy to associate a flag setting with a recipient.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dde21-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dde21-129">See also</span></span>



[<span data-ttu-id="dde21-130">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="dde21-130">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="dde21-131">IABContainer::ResolveNames</span><span class="sxs-lookup"><span data-stu-id="dde21-131">IABContainer::ResolveNames</span></span>](iabcontainer-resolvenames.md)


[<span data-ttu-id="dde21-132">MAPI 结构</span><span class="sxs-lookup"><span data-stu-id="dde21-132">MAPI Structures</span></span>](mapi-structures.md)

