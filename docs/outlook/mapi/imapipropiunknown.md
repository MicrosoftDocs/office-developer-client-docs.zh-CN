---
title: IMAPIProp IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProp
api_type:
- COM
ms.assetid: 3c9e4e05-cd3a-4b56-9dff-879e33ff6fd5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 02d2b136ed1437ba53ce1e54a202d70a48b2abe9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775542"
---
# <a name="imapiprop--iunknown"></a><span data-ttu-id="9550c-103">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="9550c-103">IMAPIProp : IUnknown</span></span>

  
  
<span data-ttu-id="9550c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9550c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9550c-105">使客户端、 服务提供商和 MAPI 处理属性。</span><span class="sxs-lookup"><span data-stu-id="9550c-105">Enables clients, service providers, and MAPI to work with properties.</span></span> <span data-ttu-id="9550c-106">支持属性的所有对象都实现此接口。</span><span class="sxs-lookup"><span data-stu-id="9550c-106">All objects that support properties implement this interface.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9550c-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="9550c-107">Header file:</span></span>  <br/> |<span data-ttu-id="9550c-108">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9550c-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="9550c-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="9550c-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="9550c-110">没有对象直接公开此接口。</span><span class="sxs-lookup"><span data-stu-id="9550c-110">No object exposes this interface directly.</span></span>  <br/> |
|<span data-ttu-id="9550c-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="9550c-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="9550c-112">服务提供商和 MAPI</span><span class="sxs-lookup"><span data-stu-id="9550c-112">Service providers and MAPI</span></span>  <br/> |
|<span data-ttu-id="9550c-113">调用：</span><span class="sxs-lookup"><span data-stu-id="9550c-113">Called by:</span></span>  <br/> |<span data-ttu-id="9550c-114">客户端应用程序、 服务提供商和 MAPI</span><span class="sxs-lookup"><span data-stu-id="9550c-114">Client applications, service providers, and MAPI</span></span>  <br/> |
|<span data-ttu-id="9550c-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="9550c-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="9550c-116">IID_IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="9550c-116">IID_IMAPIProp</span></span>  <br/> |
|<span data-ttu-id="9550c-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="9550c-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="9550c-118">LPMAPIPROP</span><span class="sxs-lookup"><span data-stu-id="9550c-118">LPMAPIPROP</span></span>  <br/> |
|<span data-ttu-id="9550c-119">事务模型：</span><span class="sxs-lookup"><span data-stu-id="9550c-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="9550c-120">从不实现抽象类</span><span class="sxs-lookup"><span data-stu-id="9550c-120">Abstract class, never implemented</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="9550c-121">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="9550c-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="9550c-122">时出错</span><span class="sxs-lookup"><span data-stu-id="9550c-122">GetLastError</span></span>](imapiprop-getlasterror.md) <br/> |<span data-ttu-id="9550c-123">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="9550c-123">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error.</span></span>  <br/> |
|[<span data-ttu-id="9550c-124">SaveChanges</span><span class="sxs-lookup"><span data-stu-id="9550c-124">SaveChanges</span></span>](imapiprop-savechanges.md) <br/> |<span data-ttu-id="9550c-125">使永久自上次保存操作对对象进行的任何更改。</span><span class="sxs-lookup"><span data-stu-id="9550c-125">Makes permanent any changes that were made to an object since the last save operation.</span></span>  <br/> |
|[<span data-ttu-id="9550c-126">GetProps</span><span class="sxs-lookup"><span data-stu-id="9550c-126">GetProps</span></span>](imapiprop-getprops.md) <br/> |<span data-ttu-id="9550c-127">检索一个或多个对象的属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="9550c-127">Retrieves the property value of one or more properties of an object.</span></span>  <br/> |
|[<span data-ttu-id="9550c-128">GetPropList</span><span class="sxs-lookup"><span data-stu-id="9550c-128">GetPropList</span></span>](imapiprop-getproplist.md) <br/> |<span data-ttu-id="9550c-129">返回所有属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="9550c-129">Returns property tags for all properties.</span></span>  <br/> |
|[<span data-ttu-id="9550c-130">OpenProperty</span><span class="sxs-lookup"><span data-stu-id="9550c-130">OpenProperty</span></span>](imapiprop-openproperty.md) <br/> |<span data-ttu-id="9550c-131">返回可用于访问属性的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="9550c-131">Returns a pointer to an interface that can be used to access a property.</span></span>  <br/> |
|[<span data-ttu-id="9550c-132">SetProps</span><span class="sxs-lookup"><span data-stu-id="9550c-132">SetProps</span></span>](imapiprop-setprops.md) <br/> |<span data-ttu-id="9550c-133">更新一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="9550c-133">Updates one or more properties.</span></span>  <br/> |
|[<span data-ttu-id="9550c-134">DeleteProps</span><span class="sxs-lookup"><span data-stu-id="9550c-134">DeleteProps</span></span>](imapiprop-deleteprops.md) <br/> |<span data-ttu-id="9550c-135">从对象中删除一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="9550c-135">Deletes one or more properties from an object.</span></span>  <br/> |
|[<span data-ttu-id="9550c-136">CopyTo</span><span class="sxs-lookup"><span data-stu-id="9550c-136">CopyTo</span></span>](imapiprop-copyto.md) <br/> |<span data-ttu-id="9550c-137">复制或移动的所有属性，特别是排除属性除外。</span><span class="sxs-lookup"><span data-stu-id="9550c-137">Copies or moves all properties, except for specifically excluded properties.</span></span>  <br/> |
|[<span data-ttu-id="9550c-138">CopyProps</span><span class="sxs-lookup"><span data-stu-id="9550c-138">CopyProps</span></span>](imapiprop-copyprops.md) <br/> |<span data-ttu-id="9550c-139">复制或移动所选的属性。</span><span class="sxs-lookup"><span data-stu-id="9550c-139">Copies or moves selected properties.</span></span>  <br/> |
|[<span data-ttu-id="9550c-140">GetNamesFromIDs</span><span class="sxs-lookup"><span data-stu-id="9550c-140">GetNamesFromIDs</span></span>](imapiprop-getnamesfromids.md) <br/> |<span data-ttu-id="9550c-141">提供对应于一个或多个属性标识符的属性名称。</span><span class="sxs-lookup"><span data-stu-id="9550c-141">Provides the property names that correspond to one or more property identifiers.</span></span>  <br/> |
|[<span data-ttu-id="9550c-142">GetIDsFromNames</span><span class="sxs-lookup"><span data-stu-id="9550c-142">GetIDsFromNames</span></span>](imapiprop-getidsfromnames.md) <br/> |<span data-ttu-id="9550c-143">提供属性的标识符的对应于一个或多个属性的名称。</span><span class="sxs-lookup"><span data-stu-id="9550c-143">Provides the property identifiers that correspond to one or more property names.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9550c-144">说明</span><span class="sxs-lookup"><span data-stu-id="9550c-144">Remarks</span></span>

 <span data-ttu-id="9550c-145">**IMAPIProp**是以下接口的基接口：</span><span class="sxs-lookup"><span data-stu-id="9550c-145">**IMAPIProp** is the base interface for the following interfaces:</span></span> 
  
- [<span data-ttu-id="9550c-146">IAttach</span><span class="sxs-lookup"><span data-stu-id="9550c-146">IAttach</span></span>](iattachimapiprop.md)
    
- [<span data-ttu-id="9550c-147">IMailUser</span><span class="sxs-lookup"><span data-stu-id="9550c-147">IMailUser</span></span>](imailuserimapiprop.md)
    
- [<span data-ttu-id="9550c-148">IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="9550c-148">IMAPIContainer</span></span>](imapicontainerimapiprop.md)
    
- [<span data-ttu-id="9550c-149">IMAPIFormInfo</span><span class="sxs-lookup"><span data-stu-id="9550c-149">IMAPIFormInfo</span></span>](imapiforminfoimapiprop.md)
    
- [<span data-ttu-id="9550c-150">IMAPIStatus</span><span class="sxs-lookup"><span data-stu-id="9550c-150">IMAPIStatus</span></span>](imapistatusimapiprop.md)
    
- [<span data-ttu-id="9550c-151">IMessage</span><span class="sxs-lookup"><span data-stu-id="9550c-151">IMessage</span></span>](imessageimapiprop.md)
    
- [<span data-ttu-id="9550c-152">IMsgStore</span><span class="sxs-lookup"><span data-stu-id="9550c-152">IMsgStore</span></span>](imsgstoreimapiprop.md)
    
- [<span data-ttu-id="9550c-153">IProfSect</span><span class="sxs-lookup"><span data-stu-id="9550c-153">IProfSect</span></span>](iprofsectimapiprop.md)
    
- [<span data-ttu-id="9550c-154">IPropData</span><span class="sxs-lookup"><span data-stu-id="9550c-154">IPropData</span></span>](ipropdataimapiprop.md)
    
## <a name="see-also"></a><span data-ttu-id="9550c-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9550c-155">See also</span></span>



[<span data-ttu-id="9550c-156">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="9550c-156">MAPI Interfaces</span></span>](mapi-interfaces.md)

