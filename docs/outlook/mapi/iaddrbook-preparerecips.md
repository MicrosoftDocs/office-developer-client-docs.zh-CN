---
title: IAddrBookPrepareRecips
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAddrBook.PrepareRecips
api_type:
- COM
ms.assetid: d423f7b5-23b8-44dd-bca3-6590182dc42d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: db1c23f33e604d6aafdd8a046566c7390c281ad8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33414275"
---
# <a name="iaddrbookpreparerecips"></a><span data-ttu-id="03484-103">IAddrBook::PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="03484-103">IAddrBook::PrepareRecips</span></span>

  
  
<span data-ttu-id="03484-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="03484-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="03484-105">准备收件人列表, 以供邮件系统以后使用。</span><span class="sxs-lookup"><span data-stu-id="03484-105">Prepares a recipient list for later use by the messaging system.</span></span> 
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpSPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="03484-106">参数</span><span class="sxs-lookup"><span data-stu-id="03484-106">Parameters</span></span>

 <span data-ttu-id="03484-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="03484-107">_ulFlags_</span></span>
  
> <span data-ttu-id="03484-108">实时用于控制条目打开方式的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="03484-108">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="03484-109">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="03484-109">The following flag can be set:</span></span>
    
<span data-ttu-id="03484-110">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="03484-110">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="03484-111">仅使用脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="03484-111">Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="03484-112">例如, 可以使用此标志允许客户端应用程序在缓存 exchange 模式下打开全局地址列表 (GAL), 并从缓存中访问该通讯簿中的条目, 而无需在客户端和服务器之间创建流量。</span><span class="sxs-lookup"><span data-stu-id="03484-112">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and to access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="03484-113">仅 Exchange 通讯簿提供程序支持此标志。</span><span class="sxs-lookup"><span data-stu-id="03484-113">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
 <span data-ttu-id="03484-114">_lpSPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="03484-114">_lpSPropTagArray_</span></span>
  
> <span data-ttu-id="03484-115">实时一个指向[SPropTagArray](sproptagarray.md)结构的指针, 该结构包含一个指明属性 (如果有) 需要更新的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="03484-115">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags that indicate the properties, if any, that require updating.</span></span> <span data-ttu-id="03484-116">_lpSPropTagArray_参数可以为 NULL。</span><span class="sxs-lookup"><span data-stu-id="03484-116">The  _lpSPropTagArray_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="03484-117">_lpRecipList_</span><span class="sxs-lookup"><span data-stu-id="03484-117">_lpRecipList_</span></span>
  
> <span data-ttu-id="03484-118">实时指向包含收件人列表的[ADRLIST](adrlist.md)结构的指针。</span><span class="sxs-lookup"><span data-stu-id="03484-118">[in] A pointer to an [ADRLIST](adrlist.md) structure that contains the list of recipients.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="03484-119">返回值</span><span class="sxs-lookup"><span data-stu-id="03484-119">Return value</span></span>

<span data-ttu-id="03484-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="03484-120">S_OK</span></span> 
  
> <span data-ttu-id="03484-121">已成功准备收件人列表。</span><span class="sxs-lookup"><span data-stu-id="03484-121">The recipient list was successfully prepared.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="03484-122">说明</span><span class="sxs-lookup"><span data-stu-id="03484-122">Remarks</span></span>

<span data-ttu-id="03484-123">客户端和服务提供程序调用**PrepareRecips**方法以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="03484-123">Clients and service providers call the **PrepareRecips** method to do the following:</span></span> 
  
- <span data-ttu-id="03484-124">确保_lpRecipList_参数中的所有收件人都具有长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="03484-124">Ensure that all recipients in the  _lpRecipList_ parameter have long-term entry identifiers.</span></span> 
    
- <span data-ttu-id="03484-125">确保_lpRecipList_参数中的每个收件人都具有_lpSPropTagArray_参数中列出的属性, 并且这些属性将出现在收件人列表的开头。</span><span class="sxs-lookup"><span data-stu-id="03484-125">Ensure that each recipient in the  _lpRecipList_ parameter has the properties listed in the  _lpSPropTagArray_ parameter and that these properties appear at the start of the recipient list.</span></span> 
    
<span data-ttu-id="03484-126">MAPI 将每个收件人的短期条目标识符转换为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="03484-126">MAPI converts each recipient's short-term entry identifiers to long-term entry identifiers.</span></span> <span data-ttu-id="03484-127">如有必要, 将从相应的通讯簿提供程序中检索收件人的长期条目标识符, 并请求任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="03484-127">If necessary, recipients' long-term entry identifiers are retrieved from the appropriate address book provider and any additional properties are requested.</span></span>
  
<span data-ttu-id="03484-128">在单个收件人条目中, 首先对请求的属性进行排序, 然后对该条目的已有的所有属性进行排序。</span><span class="sxs-lookup"><span data-stu-id="03484-128">In an individual recipient entry, the requested properties are ordered first, followed by any properties that were already present for the entry.</span></span> <span data-ttu-id="03484-129">如果_lpSPropTagArray_参数中的一个或多个请求的属性不是由相应的通讯簿提供程序处理的, 则它们的属性类型将设置为 PT_ERROR。</span><span class="sxs-lookup"><span data-stu-id="03484-129">If one or more of the requested properties in the  _lpSPropTagArray_ parameter are not handled by the appropriate address book provider, their property types will be set to PT_ERROR.</span></span> <span data-ttu-id="03484-130">其属性值将设置为 MAPI_E_NOT_FOUND 或其他值, 以提供更具体的属性原因的原因。</span><span class="sxs-lookup"><span data-stu-id="03484-130">Their property values will be set to either to MAPI_E_NOT_FOUND or to another value that gives a more specific reason why the properties are not available.</span></span> <span data-ttu-id="03484-131">必须使用[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIAllocateMore](mapiallocatemore.md)函数分别分配_lpRecipList_参数中包含的每个[SPropValue](spropvalue.md)结构, 以便可以单独释放该结构。</span><span class="sxs-lookup"><span data-stu-id="03484-131">Each [SPropValue](spropvalue.md) structure included in the  _lpRecipList_ parameter must be separately allocated by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) and [MAPIAllocateMore](mapiallocatemore.md) functions so that it can be freed individually.</span></span> 
  
<span data-ttu-id="03484-132">有关 PT_ERROR 的信息, 请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="03484-132">For information about PT_ERROR, see [Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="03484-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03484-133">See also</span></span>



[<span data-ttu-id="03484-134">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="03484-134">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="03484-135">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="03484-135">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="03484-136">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="03484-136">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="03484-137">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="03484-137">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
  
[<span data-ttu-id="03484-138">SPropValue</span><span class="sxs-lookup"><span data-stu-id="03484-138">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="03484-139">SRowSet</span><span class="sxs-lookup"><span data-stu-id="03484-139">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="03484-140">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="03484-140">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

