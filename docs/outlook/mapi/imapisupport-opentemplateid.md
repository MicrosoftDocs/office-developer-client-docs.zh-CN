---
title: IMAPISupportOpenTemplateID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.OpenTemplateID
api_type:
- COM
ms.assetid: 532f7af0-b2cc-49dd-b1de-e3ec1dc9a3e7
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 07aa508b473f4a87d5b4909f83771549c301a600
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418503"
---
# <a name="imapisupportopentemplateid"></a><span data-ttu-id="22ba1-103">IMAPISupport::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="22ba1-103">IMAPISupport::OpenTemplateID</span></span>

  
  
<span data-ttu-id="22ba1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22ba1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="22ba1-105">在外通讯簿提供程序中打开收件人条目。</span><span class="sxs-lookup"><span data-stu-id="22ba1-105">Opens a recipient entry in a foreign address book provider.</span></span>
  
```cpp
HRESULT OpenTemplateID(
ULONG cbTemplateID,
LPENTRYID lpTemplateID,
ULONG ulTemplateFlags,
LPMAPIPROP lpMAPIPropData,
LPCIID lpInterface,
LPMAPIPROP FAR * lppMAPIPropNew,
LPMAPIPROP lpMAPIPropSibling
);
```

## <a name="parameters"></a><span data-ttu-id="22ba1-106">参数</span><span class="sxs-lookup"><span data-stu-id="22ba1-106">Parameters</span></span>

 <span data-ttu-id="22ba1-107">_cbTemplateID_</span><span class="sxs-lookup"><span data-stu-id="22ba1-107">_cbTemplateID_</span></span>
  
> <span data-ttu-id="22ba1-108">[in]  _lpTemplateID_ 指向的模板标识符中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="22ba1-108">[in] The byte count in the template identifier pointed to by  _lpTemplateID_.</span></span> 
    
 <span data-ttu-id="22ba1-109">_lpTemplateID_</span><span class="sxs-lookup"><span data-stu-id="22ba1-109">_lpTemplateID_</span></span>
  
> <span data-ttu-id="22ba1-110">[in]指向要打开的收件人 **PR_TEMPLATEID (** [PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 模板标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="22ba1-110">[in] A pointer to the template identifier **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property of the recipient entry to be opened.</span></span>
    
 <span data-ttu-id="22ba1-111">_ulTemplateFlags_</span><span class="sxs-lookup"><span data-stu-id="22ba1-111">_ulTemplateFlags_</span></span>
  
> <span data-ttu-id="22ba1-112">[in]用于描述如何打开条目的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="22ba1-112">[in] A bitmask of flags used to describe how to open the entry.</span></span> <span data-ttu-id="22ba1-113">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="22ba1-113">The following flag can be set:</span></span>
    
<span data-ttu-id="22ba1-114">FILL_ENTRY</span><span class="sxs-lookup"><span data-stu-id="22ba1-114">FILL_ENTRY</span></span> 
  
> <span data-ttu-id="22ba1-115">正在创建一个新条目。</span><span class="sxs-lookup"><span data-stu-id="22ba1-115">A new entry is being created.</span></span> <span data-ttu-id="22ba1-116">当外提供程序收到来自 MAPI 的后续 [IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 调用时，它可以通过修改  _lpMAPIPropData_ 参数指向的属性或返回  _lppMAPIPropNew_ 中的特定接口实现来控制如何设置新条目的属性来控制条目的创建方式。</span><span class="sxs-lookup"><span data-stu-id="22ba1-116">When the foreign provider receives the subsequent [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) call from MAPI, it can control how the entry is created by modifying properties pointed to by the  _lpMAPIPropData_ parameter or by returning a specific interface implementation in  _lppMAPIPropNew_ to control how properties for the new entry are set.</span></span> 
    
 <span data-ttu-id="22ba1-117">_lpMAPIPropData_</span><span class="sxs-lookup"><span data-stu-id="22ba1-117">_lpMAPIPropData_</span></span>
  
> <span data-ttu-id="22ba1-118">[in]指向调用方用于访问条目的接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="22ba1-118">[in] A pointer to the interface implementation that the caller uses to access the entry.</span></span> <span data-ttu-id="22ba1-119">这是一个实现，该实现是外提供程序可以包装自己的实现，并返回到  _lppMAPIPropNew_ 参数中。</span><span class="sxs-lookup"><span data-stu-id="22ba1-119">This is the implementation that the foreign provider can wrap with its own implementation and return in the  _lppMAPIPropNew_ parameter.</span></span> <span data-ttu-id="22ba1-120">_lpMAPIPropData_ 参数必须指向从 [IMAPIProp ： IUnknown](imapipropiunknown.md)派生并支持 _在 lpInterface_ 参数中请求的接口的读/写接口实现。</span><span class="sxs-lookup"><span data-stu-id="22ba1-120">The  _lpMAPIPropData_ parameter must point to a read/write interface implementation that derives from [IMAPIProp : IUnknown](imapipropiunknown.md) and supports the interface being requested in the  _lpInterface_ parameter.</span></span> 
    
 <span data-ttu-id="22ba1-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="22ba1-121">_lpInterface_</span></span>
  
> <span data-ttu-id="22ba1-122">[in]指向接口标识符的指针 (IID) 表示用于访问条目的接口。</span><span class="sxs-lookup"><span data-stu-id="22ba1-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the entry.</span></span> <span data-ttu-id="22ba1-123">_lppMAPIPropNew_ 参数指向 _由 lpInterface_ 指定的类型的接口。</span><span class="sxs-lookup"><span data-stu-id="22ba1-123">The  _lppMAPIPropNew_ parameter points to an interface of the type specified by  _lpInterface_.</span></span> <span data-ttu-id="22ba1-124">传递 NULL 将返回消息传递用户的标准界面，IID_IMailUser。</span><span class="sxs-lookup"><span data-stu-id="22ba1-124">Passing NULL returns the standard interface for a messaging user, IID_IMailUser.</span></span> 
    
 <span data-ttu-id="22ba1-125">_lppMAPIPropNew_</span><span class="sxs-lookup"><span data-stu-id="22ba1-125">_lppMAPIPropNew_</span></span>
  
> <span data-ttu-id="22ba1-126">[out]指向外提供程序提供的用于访问条目的接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="22ba1-126">[out] A pointer to the interface implementation that the foreign provider supplies for accessing the entry.</span></span>
    
 <span data-ttu-id="22ba1-127">_lpMAPIPropSibling_</span><span class="sxs-lookup"><span data-stu-id="22ba1-127">_lpMAPIPropSibling_</span></span>
  
> <span data-ttu-id="22ba1-128">保留;必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="22ba1-128">Reserved; must be NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="22ba1-129">返回值</span><span class="sxs-lookup"><span data-stu-id="22ba1-129">Return value</span></span>

<span data-ttu-id="22ba1-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="22ba1-130">S_OK</span></span> 
  
> <span data-ttu-id="22ba1-131">绑定过程成功。</span><span class="sxs-lookup"><span data-stu-id="22ba1-131">The binding process was successful.</span></span>
    
<span data-ttu-id="22ba1-132">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="22ba1-132">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="22ba1-133">不存在外通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="22ba1-133">The foreign address book provider doesn't exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="22ba1-134">备注</span><span class="sxs-lookup"><span data-stu-id="22ba1-134">Remarks</span></span>

<span data-ttu-id="22ba1-135">**IMAPISupport：：OpenTemplateID** 方法仅为通讯簿提供程序支持对象实现。</span><span class="sxs-lookup"><span data-stu-id="22ba1-135">The **IMAPISupport::OpenTemplateID** method is implemented only for address book provider support objects.</span></span> <span data-ttu-id="22ba1-136">**OpenTemplateID** 仅由通讯簿提供程序调用，这些通讯簿提供程序可以充当属于其他通讯簿提供程序（也称为"外提供程序）"的条目的主机。</span><span class="sxs-lookup"><span data-stu-id="22ba1-136">**OpenTemplateID** is called only by address book providers that can act as hosts for entries that belong to other address book providers, also known as foreign providers.</span></span> <span data-ttu-id="22ba1-137">主机提供程序调用 **OpenTemplateID** 以打开一个外项，当主机提供程序中的数据绑定到该外提供程序中的代码时，将发生此情况。</span><span class="sxs-lookup"><span data-stu-id="22ba1-137">Host providers call **OpenTemplateID** to open a foreign entry, which occurs when data in the host provider is bound to code in the foreign provider.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="22ba1-138">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="22ba1-138">Notes to callers</span></span>

<span data-ttu-id="22ba1-139">仅在支持存储具有来自外通讯簿提供程序的模板标识符的条目时，才调用 **OpenTemplateID。**</span><span class="sxs-lookup"><span data-stu-id="22ba1-139">Call **OpenTemplateID** only if you support the storage of entries with template identifiers from foreign address book providers.</span></span> <span data-ttu-id="22ba1-140">此类支持对 [IABContainer：：CreateEntry](iabcontainer-createentry.md) 和 [IABLogon：：OpenEntry](iablogon-openentry.md) 实现提出了其他要求。</span><span class="sxs-lookup"><span data-stu-id="22ba1-140">Such support places additional requirements on your [IABContainer::CreateEntry](iabcontainer-createentry.md) and [IABLogon::OpenEntry](iablogon-openentry.md) implementations.</span></span> <span data-ttu-id="22ba1-141">有关详细信息，请参阅这些方法的说明和充当主机 [通讯簿提供程序](acting-as-a-host-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="22ba1-141">For more information, see the descriptions of these methods and [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>
  
<span data-ttu-id="22ba1-142">如果 **OpenTemplateID** 调用作为绑定接口返回传入的相同属性对象实现，可以释放对属性对象的引用。</span><span class="sxs-lookup"><span data-stu-id="22ba1-142">If the **OpenTemplateID** call returns as the bound interface the same property object implementation that you passed in, you can release your reference to your property object.</span></span> <span data-ttu-id="22ba1-143">这是因为外部提供程序已调用对象的 **AddRef** 方法来保留其自己的引用。</span><span class="sxs-lookup"><span data-stu-id="22ba1-143">This is because the foreign provider has called the object's **AddRef** method to keep its own reference.</span></span> <span data-ttu-id="22ba1-144">如果外提供程序不需要保留对属性对象的引用， **则 OpenTemplateID** 将返回未绑定的属性对象。</span><span class="sxs-lookup"><span data-stu-id="22ba1-144">If the foreign provider does not need to keep a reference to the property object, then **OpenTemplateID** will return the unbound property object.</span></span> 
  
<span data-ttu-id="22ba1-145">如果 **OpenTemplateID** 失败MAPI_E_UNKNOWN_ENTRYID，请尝试继续操作，将条目视为只读。</span><span class="sxs-lookup"><span data-stu-id="22ba1-145">If **OpenTemplateID** fails with MAPI_E_UNKNOWN_ENTRYID, try to continue by treating the entry as read-only.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="22ba1-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22ba1-146">See also</span></span>



[<span data-ttu-id="22ba1-147">IABLogon::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="22ba1-147">IABLogon::OpenTemplateID</span></span>](iablogon-opentemplateid.md)
  
[<span data-ttu-id="22ba1-148">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="22ba1-148">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)
  
[<span data-ttu-id="22ba1-149">PidTagTemplateid 规范属性</span><span class="sxs-lookup"><span data-stu-id="22ba1-149">PidTagTemplateid Canonical Property</span></span>](pidtagtemplateid-canonical-property.md)
  
[<span data-ttu-id="22ba1-150">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="22ba1-150">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

