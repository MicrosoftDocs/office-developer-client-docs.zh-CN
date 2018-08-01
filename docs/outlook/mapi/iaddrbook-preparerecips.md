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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fe3e098b2b70e77bd0c536002a4724810261bff3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/15/2018
ms.locfileid: "19775274"
---
# <a name="iaddrbookpreparerecips"></a><span data-ttu-id="63e26-103">IAddrBook::PrepareRecips</span><span class="sxs-lookup"><span data-stu-id="63e26-103">IAddrBook::PrepareRecips</span></span>

  
  
<span data-ttu-id="63e26-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="63e26-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="63e26-105">通过在邮件系统，以供以后使用准备收件人列表。</span><span class="sxs-lookup"><span data-stu-id="63e26-105">Prepares a recipient list for later use by the messaging system.</span></span> 
  
```cpp
HRESULT PrepareRecips(
  ULONG ulFlags,
  LPSPropTagArray lpSPropTagArray,
  LPADRLIST lpRecipList
);
```

## <a name="parameters"></a><span data-ttu-id="63e26-106">参数</span><span class="sxs-lookup"><span data-stu-id="63e26-106">Parameters</span></span>

 <span data-ttu-id="63e26-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="63e26-107">_ulFlags_</span></span>
  
> <span data-ttu-id="63e26-108">[in]位掩码的标志，控制如何打开该条目。</span><span class="sxs-lookup"><span data-stu-id="63e26-108">[in] A bitmask of flags that controls how the entry is opened.</span></span> <span data-ttu-id="63e26-109">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="63e26-109">The following flag can be set:</span></span>
    
<span data-ttu-id="63e26-110">MAPI_CACHE_ONLY</span><span class="sxs-lookup"><span data-stu-id="63e26-110">MAPI_CACHE_ONLY</span></span>
  
> <span data-ttu-id="63e26-111">使用仅脱机通讯簿执行名称解析。</span><span class="sxs-lookup"><span data-stu-id="63e26-111">Use only the offline address book to perform name resolution.</span></span> <span data-ttu-id="63e26-112">例如，可以使用此标志以允许在缓存的 exchange 模式下打开全局地址列表 (GAL) 和从缓存中访问该通讯簿中的条目，而不创建客户端和服务器之间的流量的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="63e26-112">For example, you can use this flag to allow a client application to open the global address list (GAL) in cached exchange mode and to access an entry in that address book from the cache without creating traffic between the client and the server.</span></span> <span data-ttu-id="63e26-113">此标志仅受 Exchange 通讯簿提供程序支持。</span><span class="sxs-lookup"><span data-stu-id="63e26-113">This flag is supported only by the Exchange Address Book Provider.</span></span>
    
 <span data-ttu-id="63e26-114">_lpSPropTagArray_</span><span class="sxs-lookup"><span data-stu-id="63e26-114">_lpSPropTagArray_</span></span>
  
> <span data-ttu-id="63e26-115">[in]指向包含属性标记指示属性，如果有一个数组[SPropTagArray](sproptagarray.md)结构的指针，需要更新。</span><span class="sxs-lookup"><span data-stu-id="63e26-115">[in] A pointer to an [SPropTagArray](sproptagarray.md) structure that contains an array of property tags that indicate the properties, if any, that require updating.</span></span> <span data-ttu-id="63e26-116">_LpSPropTagArray_参数可以是 NULL。</span><span class="sxs-lookup"><span data-stu-id="63e26-116">The  _lpSPropTagArray_ parameter can be NULL.</span></span> 
    
 <span data-ttu-id="63e26-117">_lpRecipList_</span><span class="sxs-lookup"><span data-stu-id="63e26-117">_lpRecipList_</span></span>
  
> <span data-ttu-id="63e26-118">[in]指向[ADRLIST](adrlist.md)结构，其中包含的收件人列表的指针。</span><span class="sxs-lookup"><span data-stu-id="63e26-118">[in] A pointer to an [ADRLIST](adrlist.md) structure that contains the list of recipients.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="63e26-119">返回值</span><span class="sxs-lookup"><span data-stu-id="63e26-119">Return value</span></span>

<span data-ttu-id="63e26-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="63e26-120">S_OK</span></span> 
  
> <span data-ttu-id="63e26-121">已成功准备好的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="63e26-121">The recipient list was successfully prepared.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="63e26-122">说明</span><span class="sxs-lookup"><span data-stu-id="63e26-122">Remarks</span></span>

<span data-ttu-id="63e26-123">客户端和服务提供商调用**PrepareRecips**方法以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="63e26-123">Clients and service providers call the **PrepareRecips** method to do the following:</span></span> 
  
- <span data-ttu-id="63e26-124">确保_lpRecipList_参数中的所有收件人都具有长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="63e26-124">Ensure that all recipients in the  _lpRecipList_ parameter have long-term entry identifiers.</span></span> 
    
- <span data-ttu-id="63e26-125">确保_lpRecipList_参数中的每个收件人有_lpSPropTagArray_参数中列出的属性，并且这些属性显示收件人列表的开头。</span><span class="sxs-lookup"><span data-stu-id="63e26-125">Ensure that each recipient in the  _lpRecipList_ parameter has the properties listed in the  _lpSPropTagArray_ parameter and that these properties appear at the start of the recipient list.</span></span> 
    
<span data-ttu-id="63e26-126">MAPI 将每个收件人的短期条目标识符转换为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="63e26-126">MAPI converts each recipient's short-term entry identifiers to long-term entry identifiers.</span></span> <span data-ttu-id="63e26-127">如有必要，收件人的长期条目标识符检索从相应地址簿提供程序和系统要求的任何其他属性。</span><span class="sxs-lookup"><span data-stu-id="63e26-127">If necessary, recipients' long-term entry identifiers are retrieved from the appropriate address book provider and any additional properties are requested.</span></span>
  
<span data-ttu-id="63e26-128">在单个收件人条目，请求的属性被排序首先，跟已存在的项的任何属性。</span><span class="sxs-lookup"><span data-stu-id="63e26-128">In an individual recipient entry, the requested properties are ordered first, followed by any properties that were already present for the entry.</span></span> <span data-ttu-id="63e26-129">如果一个或多个_lpSPropTagArray_参数中所请求属性不会处理相应地址簿提供程序，其属性类型将设置为 PT_ERROR。</span><span class="sxs-lookup"><span data-stu-id="63e26-129">If one or more of the requested properties in the  _lpSPropTagArray_ parameter are not handled by the appropriate address book provider, their property types will be set to PT_ERROR.</span></span> <span data-ttu-id="63e26-130">其属性值会设置为 MAPI_E_NOT_FOUND 或另一个值，该值提供更具体原因为什么属性不可用。</span><span class="sxs-lookup"><span data-stu-id="63e26-130">Their property values will be set to either to MAPI_E_NOT_FOUND or to another value that gives a more specific reason why the properties are not available.</span></span> <span data-ttu-id="63e26-131">_LpRecipList_参数中包含每个[SPropValue](spropvalue.md)结构必须单独分配使用的[MAPIAllocateBuffer](mapiallocatebuffer.md)和[MAPIAllocateMore](mapiallocatemore.md)函数，以便可以单独被释放。</span><span class="sxs-lookup"><span data-stu-id="63e26-131">Each [SPropValue](spropvalue.md) structure included in the  _lpRecipList_ parameter must be separately allocated by using the [MAPIAllocateBuffer](mapiallocatebuffer.md) and [MAPIAllocateMore](mapiallocatemore.md) functions so that it can be freed individually.</span></span> 
  
<span data-ttu-id="63e26-132">有关 PT_ERROR 的信息，请参阅[属性类型](property-types.md)。</span><span class="sxs-lookup"><span data-stu-id="63e26-132">For information about PT_ERROR, see [Property Types](property-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="63e26-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63e26-133">See also</span></span>



[<span data-ttu-id="63e26-134">ADRLIST</span><span class="sxs-lookup"><span data-stu-id="63e26-134">ADRLIST</span></span>](adrlist.md)
  
[<span data-ttu-id="63e26-135">IMAPIProp::GetProps</span><span class="sxs-lookup"><span data-stu-id="63e26-135">IMAPIProp::GetProps</span></span>](imapiprop-getprops.md)
  
[<span data-ttu-id="63e26-136">IMessage::ModifyRecipients</span><span class="sxs-lookup"><span data-stu-id="63e26-136">IMessage::ModifyRecipients</span></span>](imessage-modifyrecipients.md)
  
[<span data-ttu-id="63e26-137">PidTagEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="63e26-137">PidTagEntryId Canonical Property</span></span>](pidtagentryid-canonical-property.md)
  
[<span data-ttu-id="63e26-138">SPropValue</span><span class="sxs-lookup"><span data-stu-id="63e26-138">SPropValue</span></span>](spropvalue.md)
  
[<span data-ttu-id="63e26-139">SRowSet</span><span class="sxs-lookup"><span data-stu-id="63e26-139">SRowSet</span></span>](srowset.md)
  
[<span data-ttu-id="63e26-140">IAddrBook : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="63e26-140">IAddrBook : IMAPIProp</span></span>](iaddrbookimapiprop.md)

