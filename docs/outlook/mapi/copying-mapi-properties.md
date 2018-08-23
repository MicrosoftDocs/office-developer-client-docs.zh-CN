---
title: 复制的 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a52f4bcd-6e17-4623-a469-53be1f2758b1
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 556ea9faedf0d9a02b0cff1bb2f1750289cc4d1e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22565079"
---
# <a name="copying-mapi-properties"></a><span data-ttu-id="d2e03-103">复制的 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d2e03-103">Copying MAPI Properties</span></span>

  
  
<span data-ttu-id="d2e03-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d2e03-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d2e03-105">客户端和服务提供商可以复制一个或多个对象的属性，与以下**IMAPIProp**方法和 API 函数：</span><span class="sxs-lookup"><span data-stu-id="d2e03-105">Clients and service providers can copy one or more of an object's properties with the following **IMAPIProp** methods and API functions:</span></span> 
  
- <span data-ttu-id="d2e03-106">[IMAPIProp::CopyTo](imapiprop-copyto.md)方法将所有对象的属性复制到另一个对象，可选择不包括所选的属性。</span><span class="sxs-lookup"><span data-stu-id="d2e03-106">The [IMAPIProp::CopyTo](imapiprop-copyto.md) method copies all of an object's properties to another object, optionally excluding selected properties.</span></span> <span data-ttu-id="d2e03-107">**CopyTo**用于复制或移动任何类型的对象。</span><span class="sxs-lookup"><span data-stu-id="d2e03-107">**CopyTo** is used for copying or moving any type of object.</span></span> 
    
- <span data-ttu-id="d2e03-108">[IMAPIProp::CopyProps](imapiprop-copyprops.md)方法将复制所选的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="d2e03-108">The [IMAPIProp::CopyProps](imapiprop-copyprops.md) method copies selected properties of an object.</span></span> <span data-ttu-id="d2e03-109">**CopyProps**主要用于消息。</span><span class="sxs-lookup"><span data-stu-id="d2e03-109">**CopyProps** is used mainly with messages.</span></span> <span data-ttu-id="d2e03-110">当客户端创建一份转发的邮件或回复， **CopyProps**处理从原始邮件复制的相应属性。</span><span class="sxs-lookup"><span data-stu-id="d2e03-110">When a client creates a forwarded copy of a message or a reply, **CopyProps** handles copying the appropriate properties from the original message.</span></span> 
    
- <span data-ttu-id="d2e03-111">[PropCopyMore](propcopymore.md)函数将从一个位置的单个属性值复制到另一个。</span><span class="sxs-lookup"><span data-stu-id="d2e03-111">The [PropCopyMore](propcopymore.md) function copies a single property value from one location to another.</span></span> <span data-ttu-id="d2e03-112">请谨慎使用**PropCopyMore** 。</span><span class="sxs-lookup"><span data-stu-id="d2e03-112">Use **PropCopyMore** with caution.</span></span> <span data-ttu-id="d2e03-113">可能 — 一次复制的一个值时 — 分配内存的许多小型块，并导致内存片段。</span><span class="sxs-lookup"><span data-stu-id="d2e03-113">It is possible — when copying one value at a time — to allocate many small blocks of memory and cause memory to fragment.</span></span> 
    
- <span data-ttu-id="d2e03-114">[ScCopyProps](sccopyprops.md)函数批量复制属性值。</span><span class="sxs-lookup"><span data-stu-id="d2e03-114">The [ScCopyProps](sccopyprops.md) function copies property values in bulk.</span></span> <span data-ttu-id="d2e03-115">**ScCopyProps**可从内存脱节块复制已生成的属性值。</span><span class="sxs-lookup"><span data-stu-id="d2e03-115">**ScCopyProps** can copy property values that have been built from disjointed blocks of memory.</span></span> <span data-ttu-id="d2e03-116">它返回新的属性数组。</span><span class="sxs-lookup"><span data-stu-id="d2e03-116">It returns a new property array.</span></span> 
    
- <span data-ttu-id="d2e03-117">如果返回**ScCopyProps**属性数组是存储在磁盘上，使用[ScRelocProps](screlocprops.md)函数调整指针。</span><span class="sxs-lookup"><span data-stu-id="d2e03-117">If the property array returned by **ScCopyProps** is to be stored on disk, use the [ScRelocProps](screlocprops.md) function to adjust the pointers.</span></span> <span data-ttu-id="d2e03-118">应两次; 调用**ScRelocProps**一次在写入数据操作之前调整地址，然后再次期间读取操作。</span><span class="sxs-lookup"><span data-stu-id="d2e03-118">**ScRelocProps** should be called twice; once to adjust the addresses before writing the data operation and then again during the read operation.</span></span> <span data-ttu-id="d2e03-119">**ScRelocProps**函数假定属性值数组中的单个分配原来分配给。</span><span class="sxs-lookup"><span data-stu-id="d2e03-119">The **ScRelocProps** function assumes that the property value array was originally allocated in a single allocation.</span></span> 
    
<span data-ttu-id="d2e03-120">上述列表副本属性在内存中，而不是从另一个对象的一个对象中描述的 API 功能。</span><span class="sxs-lookup"><span data-stu-id="d2e03-120">The API functions described in the preceding list copy properties in memory rather than from one object to another object.</span></span> <span data-ttu-id="d2e03-121">这些函数目前支持，但可能不受支持的将来版本中。</span><span class="sxs-lookup"><span data-stu-id="d2e03-121">These functions are presently supported, but might not be supported in a future release.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2e03-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d2e03-122">See also</span></span>



[<span data-ttu-id="d2e03-123">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="d2e03-123">MAPI Property Overview</span></span>](mapi-property-overview.md)

