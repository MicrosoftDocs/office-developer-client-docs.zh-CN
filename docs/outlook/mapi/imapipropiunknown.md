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
ms.openlocfilehash: 6b0a8923ee5efe22584170ce9853698885527ee8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407660"
---
# <a name="imapiprop--iunknown"></a><span data-ttu-id="78860-103">IMAPIProp : IUnknown</span><span class="sxs-lookup"><span data-stu-id="78860-103">IMAPIProp : IUnknown</span></span>

  
  
<span data-ttu-id="78860-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="78860-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="78860-105">使客户端、服务提供程序和 MAPI 能够使用属性。</span><span class="sxs-lookup"><span data-stu-id="78860-105">Enables clients, service providers, and MAPI to work with properties.</span></span> <span data-ttu-id="78860-106">所有支持属性的对象都实现此接口。</span><span class="sxs-lookup"><span data-stu-id="78860-106">All objects that support properties implement this interface.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="78860-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="78860-107">Header file:</span></span>  <br/> |<span data-ttu-id="78860-108">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="78860-108">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="78860-109">公开者:</span><span class="sxs-lookup"><span data-stu-id="78860-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="78860-110">无对象直接公开此接口。</span><span class="sxs-lookup"><span data-stu-id="78860-110">No object exposes this interface directly.</span></span>  <br/> |
|<span data-ttu-id="78860-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="78860-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="78860-112">服务提供商和 MAPI</span><span class="sxs-lookup"><span data-stu-id="78860-112">Service providers and MAPI</span></span>  <br/> |
|<span data-ttu-id="78860-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="78860-113">Called by:</span></span>  <br/> |<span data-ttu-id="78860-114">客户端应用程序、服务提供程序和 MAPI</span><span class="sxs-lookup"><span data-stu-id="78860-114">Client applications, service providers, and MAPI</span></span>  <br/> |
|<span data-ttu-id="78860-115">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="78860-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="78860-116">IID_IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="78860-116">IID_IMAPIProp</span></span>  <br/> |
|<span data-ttu-id="78860-117">指针类型:</span><span class="sxs-lookup"><span data-stu-id="78860-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="78860-118">LPMAPIPROP</span><span class="sxs-lookup"><span data-stu-id="78860-118">LPMAPIPROP</span></span>  <br/> |
|<span data-ttu-id="78860-119">事务模型:</span><span class="sxs-lookup"><span data-stu-id="78860-119">Transaction model:</span></span>  <br/> |<span data-ttu-id="78860-120">抽象类, 从未实现</span><span class="sxs-lookup"><span data-stu-id="78860-120">Abstract class, never implemented</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="78860-121">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="78860-121">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="78860-122">GetLastError</span><span class="sxs-lookup"><span data-stu-id="78860-122">GetLastError</span></span>](imapiprop-getlasterror.md) <br/> |<span data-ttu-id="78860-123">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="78860-123">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error.</span></span>  <br/> |
|[<span data-ttu-id="78860-124">SaveChanges</span><span class="sxs-lookup"><span data-stu-id="78860-124">SaveChanges</span></span>](imapiprop-savechanges.md) <br/> |<span data-ttu-id="78860-125">使自上次保存操作后对对象进行的任何更改成为永久性的。</span><span class="sxs-lookup"><span data-stu-id="78860-125">Makes permanent any changes that were made to an object since the last save operation.</span></span>  <br/> |
|[<span data-ttu-id="78860-126">GetProps</span><span class="sxs-lookup"><span data-stu-id="78860-126">GetProps</span></span>](imapiprop-getprops.md) <br/> |<span data-ttu-id="78860-127">检索对象的一个或多个属性的属性值。</span><span class="sxs-lookup"><span data-stu-id="78860-127">Retrieves the property value of one or more properties of an object.</span></span>  <br/> |
|[<span data-ttu-id="78860-128">GetPropList</span><span class="sxs-lookup"><span data-stu-id="78860-128">GetPropList</span></span>](imapiprop-getproplist.md) <br/> |<span data-ttu-id="78860-129">返回所有属性的属性标记。</span><span class="sxs-lookup"><span data-stu-id="78860-129">Returns property tags for all properties.</span></span>  <br/> |
|[<span data-ttu-id="78860-130">OpenProperty</span><span class="sxs-lookup"><span data-stu-id="78860-130">OpenProperty</span></span>](imapiprop-openproperty.md) <br/> |<span data-ttu-id="78860-131">返回指向可用于访问属性的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="78860-131">Returns a pointer to an interface that can be used to access a property.</span></span>  <br/> |
|[<span data-ttu-id="78860-132">SetProps</span><span class="sxs-lookup"><span data-stu-id="78860-132">SetProps</span></span>](imapiprop-setprops.md) <br/> |<span data-ttu-id="78860-133">更新一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="78860-133">Updates one or more properties.</span></span>  <br/> |
|[<span data-ttu-id="78860-134">DeleteProps</span><span class="sxs-lookup"><span data-stu-id="78860-134">DeleteProps</span></span>](imapiprop-deleteprops.md) <br/> |<span data-ttu-id="78860-135">从对象中删除一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="78860-135">Deletes one or more properties from an object.</span></span>  <br/> |
|[<span data-ttu-id="78860-136">CopyTo</span><span class="sxs-lookup"><span data-stu-id="78860-136">CopyTo</span></span>](imapiprop-copyto.md) <br/> |<span data-ttu-id="78860-137">复制或移动所有属性, 但特殊排除的属性除外。</span><span class="sxs-lookup"><span data-stu-id="78860-137">Copies or moves all properties, except for specifically excluded properties.</span></span>  <br/> |
|[<span data-ttu-id="78860-138">CopyProps</span><span class="sxs-lookup"><span data-stu-id="78860-138">CopyProps</span></span>](imapiprop-copyprops.md) <br/> |<span data-ttu-id="78860-139">复制或移动选定的属性。</span><span class="sxs-lookup"><span data-stu-id="78860-139">Copies or moves selected properties.</span></span>  <br/> |
|[<span data-ttu-id="78860-140">GetNamesFromIDs</span><span class="sxs-lookup"><span data-stu-id="78860-140">GetNamesFromIDs</span></span>](imapiprop-getnamesfromids.md) <br/> |<span data-ttu-id="78860-141">提供与一个或多个属性标识符相对应的属性名称。</span><span class="sxs-lookup"><span data-stu-id="78860-141">Provides the property names that correspond to one or more property identifiers.</span></span>  <br/> |
|[<span data-ttu-id="78860-142">GetIDsFromNames</span><span class="sxs-lookup"><span data-stu-id="78860-142">GetIDsFromNames</span></span>](imapiprop-getidsfromnames.md) <br/> |<span data-ttu-id="78860-143">提供与一个或多个属性名称对应的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="78860-143">Provides the property identifiers that correspond to one or more property names.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="78860-144">说明</span><span class="sxs-lookup"><span data-stu-id="78860-144">Remarks</span></span>

 <span data-ttu-id="78860-145">**IMAPIProp**是以下接口的基接口:</span><span class="sxs-lookup"><span data-stu-id="78860-145">**IMAPIProp** is the base interface for the following interfaces:</span></span> 
  
- [<span data-ttu-id="78860-146">IAttach</span><span class="sxs-lookup"><span data-stu-id="78860-146">IAttach</span></span>](iattachimapiprop.md)
    
- [<span data-ttu-id="78860-147">IMailUser</span><span class="sxs-lookup"><span data-stu-id="78860-147">IMailUser</span></span>](imailuserimapiprop.md)
    
- [<span data-ttu-id="78860-148">IMAPIContainer</span><span class="sxs-lookup"><span data-stu-id="78860-148">IMAPIContainer</span></span>](imapicontainerimapiprop.md)
    
- [<span data-ttu-id="78860-149">IMAPIFormInfo</span><span class="sxs-lookup"><span data-stu-id="78860-149">IMAPIFormInfo</span></span>](imapiforminfoimapiprop.md)
    
- [<span data-ttu-id="78860-150">IMAPIStatus</span><span class="sxs-lookup"><span data-stu-id="78860-150">IMAPIStatus</span></span>](imapistatusimapiprop.md)
    
- [<span data-ttu-id="78860-151">IMessage</span><span class="sxs-lookup"><span data-stu-id="78860-151">IMessage</span></span>](imessageimapiprop.md)
    
- [<span data-ttu-id="78860-152">IMsgStore</span><span class="sxs-lookup"><span data-stu-id="78860-152">IMsgStore</span></span>](imsgstoreimapiprop.md)
    
- [<span data-ttu-id="78860-153">IProfSect</span><span class="sxs-lookup"><span data-stu-id="78860-153">IProfSect</span></span>](iprofsectimapiprop.md)
    
- [<span data-ttu-id="78860-154">IPropData</span><span class="sxs-lookup"><span data-stu-id="78860-154">IPropData</span></span>](ipropdataimapiprop.md)
    
## <a name="see-also"></a><span data-ttu-id="78860-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78860-155">See also</span></span>



[<span data-ttu-id="78860-156">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="78860-156">MAPI Interfaces</span></span>](mapi-interfaces.md)

