---
title: 复制 MAPI 属性
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a52f4bcd-6e17-4623-a469-53be1f2758b1
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ae8e553cf2e19ae1ba06ca09aad84eae9f7d1238
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415045"
---
# <a name="copying-mapi-properties"></a><span data-ttu-id="0b72d-103">复制 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0b72d-103">Copying MAPI Properties</span></span>

  
  
<span data-ttu-id="0b72d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0b72d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0b72d-105">客户端和服务提供商可以使用以下 **IMAPIProp** 方法和 API 函数复制对象的一个或多个属性：</span><span class="sxs-lookup"><span data-stu-id="0b72d-105">Clients and service providers can copy one or more of an object's properties with the following **IMAPIProp** methods and API functions:</span></span> 
  
- <span data-ttu-id="0b72d-106">[IMAPIProp：：CopyTo](imapiprop-copyto.md)方法将对象的所有属性复制到另一个对象，可以选择排除所选属性。</span><span class="sxs-lookup"><span data-stu-id="0b72d-106">The [IMAPIProp::CopyTo](imapiprop-copyto.md) method copies all of an object's properties to another object, optionally excluding selected properties.</span></span> <span data-ttu-id="0b72d-107">**CopyTo** 用于复制或移动任何类型的对象。</span><span class="sxs-lookup"><span data-stu-id="0b72d-107">**CopyTo** is used for copying or moving any type of object.</span></span> 
    
- <span data-ttu-id="0b72d-108">[IMAPIProp：：CopyProps](imapiprop-copyprops.md)方法复制对象的选定属性。</span><span class="sxs-lookup"><span data-stu-id="0b72d-108">The [IMAPIProp::CopyProps](imapiprop-copyprops.md) method copies selected properties of an object.</span></span> <span data-ttu-id="0b72d-109">**CopyProps** 主要用于邮件。</span><span class="sxs-lookup"><span data-stu-id="0b72d-109">**CopyProps** is used mainly with messages.</span></span> <span data-ttu-id="0b72d-110">当客户端创建邮件或回复的转发副本时 **，CopyProps** 处理从原始邮件复制相应属性。</span><span class="sxs-lookup"><span data-stu-id="0b72d-110">When a client creates a forwarded copy of a message or a reply, **CopyProps** handles copying the appropriate properties from the original message.</span></span> 
    
- <span data-ttu-id="0b72d-111">[PropCopyMore](propcopymore.md)函数将单个属性值从一个位置复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="0b72d-111">The [PropCopyMore](propcopymore.md) function copies a single property value from one location to another.</span></span> <span data-ttu-id="0b72d-112">请 **谨慎使用 PropCopyMore。**</span><span class="sxs-lookup"><span data-stu-id="0b72d-112">Use **PropCopyMore** with caution.</span></span> <span data-ttu-id="0b72d-113">在一次复制一个值时，可能会分配许多小的内存块，并会导致内存碎片化。</span><span class="sxs-lookup"><span data-stu-id="0b72d-113">It is possible — when copying one value at a time — to allocate many small blocks of memory and cause memory to fragment.</span></span> 
    
- <span data-ttu-id="0b72d-114">[ScCopyProps](sccopyprops.md)函数批量复制属性值。</span><span class="sxs-lookup"><span data-stu-id="0b72d-114">The [ScCopyProps](sccopyprops.md) function copies property values in bulk.</span></span> <span data-ttu-id="0b72d-115">**ScCopyProps** 可以复制从脱节的内存块构建的属性值。</span><span class="sxs-lookup"><span data-stu-id="0b72d-115">**ScCopyProps** can copy property values that have been built from disjointed blocks of memory.</span></span> <span data-ttu-id="0b72d-116">它返回一个新的属性数组。</span><span class="sxs-lookup"><span data-stu-id="0b72d-116">It returns a new property array.</span></span> 
    
- <span data-ttu-id="0b72d-117">如果 **ScCopyProps** 返回的属性数组要存储在磁盘上，请使用 [ScRelocProps](screlocprops.md) 函数调整指针。</span><span class="sxs-lookup"><span data-stu-id="0b72d-117">If the property array returned by **ScCopyProps** is to be stored on disk, use the [ScRelocProps](screlocprops.md) function to adjust the pointers.</span></span> <span data-ttu-id="0b72d-118">**应调用两次 ScRelocProps;** 一次，在写入数据操作之前调整地址，然后在读取操作期间再次调整。</span><span class="sxs-lookup"><span data-stu-id="0b72d-118">**ScRelocProps** should be called twice; once to adjust the addresses before writing the data operation and then again during the read operation.</span></span> <span data-ttu-id="0b72d-119">**ScRelocProps** 函数假定属性值数组最初在单个分配中分配。</span><span class="sxs-lookup"><span data-stu-id="0b72d-119">The **ScRelocProps** function assumes that the property value array was originally allocated in a single allocation.</span></span> 
    
<span data-ttu-id="0b72d-120">上述列表中描述的 API 函数将属性复制到内存中，而不是从一个对象复制到另一个对象。</span><span class="sxs-lookup"><span data-stu-id="0b72d-120">The API functions described in the preceding list copy properties in memory rather than from one object to another object.</span></span> <span data-ttu-id="0b72d-121">这些函数目前受支持，但可能在未来版本中不受支持。</span><span class="sxs-lookup"><span data-stu-id="0b72d-121">These functions are presently supported, but might not be supported in a future release.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b72d-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b72d-122">See also</span></span>



[<span data-ttu-id="0b72d-123">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="0b72d-123">MAPI Property Overview</span></span>](mapi-property-overview.md)

