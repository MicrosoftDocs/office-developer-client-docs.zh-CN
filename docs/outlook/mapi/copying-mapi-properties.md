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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333073"
---
# <a name="copying-mapi-properties"></a><span data-ttu-id="1907b-103">复制 MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1907b-103">Copying MAPI Properties</span></span>

  
  
<span data-ttu-id="1907b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1907b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1907b-105">客户端和服务提供程序可以使用以下**IMAPIProp**方法和 API 函数复制一个或多个对象的属性:</span><span class="sxs-lookup"><span data-stu-id="1907b-105">Clients and service providers can copy one or more of an object's properties with the following **IMAPIProp** methods and API functions:</span></span> 
  
- <span data-ttu-id="1907b-106">[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将对象的所有属性复制到另一个对象, 也可以选择排除选定的属性。</span><span class="sxs-lookup"><span data-stu-id="1907b-106">The [IMAPIProp::CopyTo](imapiprop-copyto.md) method copies all of an object's properties to another object, optionally excluding selected properties.</span></span> <span data-ttu-id="1907b-107">**CopyTo**用于复制或移动任何类型的对象。</span><span class="sxs-lookup"><span data-stu-id="1907b-107">**CopyTo** is used for copying or moving any type of object.</span></span> 
    
- <span data-ttu-id="1907b-108">[IMAPIProp:: CopyProps](imapiprop-copyprops.md)方法复制对象的选定属性。</span><span class="sxs-lookup"><span data-stu-id="1907b-108">The [IMAPIProp::CopyProps](imapiprop-copyprops.md) method copies selected properties of an object.</span></span> <span data-ttu-id="1907b-109">**CopyProps**主要用于邮件。</span><span class="sxs-lookup"><span data-stu-id="1907b-109">**CopyProps** is used mainly with messages.</span></span> <span data-ttu-id="1907b-110">当客户端创建转发的邮件副本或答复时, **CopyProps**将处理原始邮件中的相应属性。</span><span class="sxs-lookup"><span data-stu-id="1907b-110">When a client creates a forwarded copy of a message or a reply, **CopyProps** handles copying the appropriate properties from the original message.</span></span> 
    
- <span data-ttu-id="1907b-111">[PropCopyMore](propcopymore.md)函数将单个属性值从一个位置复制到另一个位置。</span><span class="sxs-lookup"><span data-stu-id="1907b-111">The [PropCopyMore](propcopymore.md) function copies a single property value from one location to another.</span></span> <span data-ttu-id="1907b-112">使用**PropCopyMore**时要谨慎。</span><span class="sxs-lookup"><span data-stu-id="1907b-112">Use **PropCopyMore** with caution.</span></span> <span data-ttu-id="1907b-113">在一次复制一个值时, 可以分配多个小型内存块并导致内存分段。</span><span class="sxs-lookup"><span data-stu-id="1907b-113">It is possible — when copying one value at a time — to allocate many small blocks of memory and cause memory to fragment.</span></span> 
    
- <span data-ttu-id="1907b-114">[ScCopyProps](sccopyprops.md)函数批量复制属性值。</span><span class="sxs-lookup"><span data-stu-id="1907b-114">The [ScCopyProps](sccopyprops.md) function copies property values in bulk.</span></span> <span data-ttu-id="1907b-115">**ScCopyProps**可以从分离的内存块复制已生成的属性值。</span><span class="sxs-lookup"><span data-stu-id="1907b-115">**ScCopyProps** can copy property values that have been built from disjointed blocks of memory.</span></span> <span data-ttu-id="1907b-116">它返回一个新的属性数组。</span><span class="sxs-lookup"><span data-stu-id="1907b-116">It returns a new property array.</span></span> 
    
- <span data-ttu-id="1907b-117">如果**ScCopyProps**返回的属性数组要存储在磁盘上, 请使用[ScRelocProps](screlocprops.md)函数调整指针。</span><span class="sxs-lookup"><span data-stu-id="1907b-117">If the property array returned by **ScCopyProps** is to be stored on disk, use the [ScRelocProps](screlocprops.md) function to adjust the pointers.</span></span> <span data-ttu-id="1907b-118">应调用**ScRelocProps**两次;在写入数据操作之前调整地址, 然后在读取操作过程中再次进行。</span><span class="sxs-lookup"><span data-stu-id="1907b-118">**ScRelocProps** should be called twice; once to adjust the addresses before writing the data operation and then again during the read operation.</span></span> <span data-ttu-id="1907b-119">**ScRelocProps**函数假定属性值数组最初是在单个分配中分配的。</span><span class="sxs-lookup"><span data-stu-id="1907b-119">The **ScRelocProps** function assumes that the property value array was originally allocated in a single allocation.</span></span> 
    
<span data-ttu-id="1907b-120">上述列表中所述的 API 函数可复制内存中的属性, 而不是从一个对象复制到另一个对象。</span><span class="sxs-lookup"><span data-stu-id="1907b-120">The API functions described in the preceding list copy properties in memory rather than from one object to another object.</span></span> <span data-ttu-id="1907b-121">目前支持这些函数, 但在将来的版本中可能不支持这些函数。</span><span class="sxs-lookup"><span data-stu-id="1907b-121">These functions are presently supported, but might not be supported in a future release.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1907b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1907b-122">See also</span></span>



[<span data-ttu-id="1907b-123">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="1907b-123">MAPI Property Overview</span></span>](mapi-property-overview.md)

