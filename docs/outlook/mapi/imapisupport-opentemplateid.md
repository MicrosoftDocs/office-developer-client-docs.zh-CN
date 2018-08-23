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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 855810f7ac3bc1bd433ddd56aba3fe1f938b9559
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575383"
---
# <a name="imapisupportopentemplateid"></a><span data-ttu-id="69534-103">IMAPISupport::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="69534-103">IMAPISupport::OpenTemplateID</span></span>

  
  
<span data-ttu-id="69534-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="69534-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="69534-105">在外部地址簿提供程序中打开一个收件人的项。</span><span class="sxs-lookup"><span data-stu-id="69534-105">Opens a recipient entry in a foreign address book provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="69534-106">参数</span><span class="sxs-lookup"><span data-stu-id="69534-106">Parameters</span></span>

 <span data-ttu-id="69534-107">_cbTemplateID_</span><span class="sxs-lookup"><span data-stu-id="69534-107">_cbTemplateID_</span></span>
  
> <span data-ttu-id="69534-108">[in]由_lpTemplateID_指向该模板标识符中字节数。</span><span class="sxs-lookup"><span data-stu-id="69534-108">[in] The byte count in the template identifier pointed to by  _lpTemplateID_.</span></span> 
    
 <span data-ttu-id="69534-109">_lpTemplateID_</span><span class="sxs-lookup"><span data-stu-id="69534-109">_lpTemplateID_</span></span>
  
> <span data-ttu-id="69534-110">[in]一个指向模板标识符的收件人的条目，打开**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="69534-110">[in] A pointer to the template identifier **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property of the recipient entry to be opened.</span></span>
    
 <span data-ttu-id="69534-111">_ulTemplateFlags_</span><span class="sxs-lookup"><span data-stu-id="69534-111">_ulTemplateFlags_</span></span>
  
> <span data-ttu-id="69534-112">[in]用于介绍如何打开条目的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="69534-112">[in] A bitmask of flags used to describe how to open the entry.</span></span> <span data-ttu-id="69534-113">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="69534-113">The following flag can be set:</span></span>
    
<span data-ttu-id="69534-114">FILL_ENTRY</span><span class="sxs-lookup"><span data-stu-id="69534-114">FILL_ENTRY</span></span> 
  
> <span data-ttu-id="69534-115">正在创建一个新的条目。</span><span class="sxs-lookup"><span data-stu-id="69534-115">A new entry is being created.</span></span> <span data-ttu-id="69534-116">外的提供程序接收 MAPI 后续[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)调用，它可以控制如何通过修改属性指向通过_lpMAPIPropData_参数或返回特定的接口创建条目_lppMAPIPropNew_来控制如何设置新项的属性中的实现。</span><span class="sxs-lookup"><span data-stu-id="69534-116">When the foreign provider receives the subsequent [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) call from MAPI, it can control how the entry is created by modifying properties pointed to by the  _lpMAPIPropData_ parameter or by returning a specific interface implementation in  _lppMAPIPropNew_ to control how properties for the new entry are set.</span></span> 
    
 <span data-ttu-id="69534-117">_lpMAPIPropData_</span><span class="sxs-lookup"><span data-stu-id="69534-117">_lpMAPIPropData_</span></span>
  
> <span data-ttu-id="69534-118">[in]指向该接口实现用于访问该条目呼叫者的指针。</span><span class="sxs-lookup"><span data-stu-id="69534-118">[in] A pointer to the interface implementation that the caller uses to access the entry.</span></span> <span data-ttu-id="69534-119">这是外的提供程序可以使用它自己的实现包装并_lppMAPIPropNew_参数中返回的实现。</span><span class="sxs-lookup"><span data-stu-id="69534-119">This is the implementation that the foreign provider can wrap with its own implementation and return in the  _lppMAPIPropNew_ parameter.</span></span> <span data-ttu-id="69534-120">_LpMAPIPropData_参数必须指向派生的读/写接口实现[IMAPIProp: IUnknown](imapipropiunknown.md)和支持正在请求_lpInterface_参数中的接口。</span><span class="sxs-lookup"><span data-stu-id="69534-120">The  _lpMAPIPropData_ parameter must point to a read/write interface implementation that derives from [IMAPIProp : IUnknown](imapipropiunknown.md) and supports the interface being requested in the  _lpInterface_ parameter.</span></span> 
    
 <span data-ttu-id="69534-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="69534-121">_lpInterface_</span></span>
  
> <span data-ttu-id="69534-122">[in]指向接口标识 (IID) 值，该值代表要用于访问该条目的接口的指针。</span><span class="sxs-lookup"><span data-stu-id="69534-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the entry.</span></span> <span data-ttu-id="69534-123">_LppMAPIPropNew_参数指向_lpInterface_指定类型的接口。</span><span class="sxs-lookup"><span data-stu-id="69534-123">The  _lppMAPIPropNew_ parameter points to an interface of the type specified by  _lpInterface_.</span></span> <span data-ttu-id="69534-124">传递 NULL 返回的消息的用户，IID_IMailUser 标准的接口。</span><span class="sxs-lookup"><span data-stu-id="69534-124">Passing NULL returns the standard interface for a messaging user, IID_IMailUser.</span></span> 
    
 <span data-ttu-id="69534-125">_lppMAPIPropNew_</span><span class="sxs-lookup"><span data-stu-id="69534-125">_lppMAPIPropNew_</span></span>
  
> <span data-ttu-id="69534-126">[输出]一个指向外的提供程序提供用于访问该条目该接口实现。</span><span class="sxs-lookup"><span data-stu-id="69534-126">[out] A pointer to the interface implementation that the foreign provider supplies for accessing the entry.</span></span>
    
 <span data-ttu-id="69534-127">_lpMAPIPropSibling_</span><span class="sxs-lookup"><span data-stu-id="69534-127">_lpMAPIPropSibling_</span></span>
  
> <span data-ttu-id="69534-128">保留;必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="69534-128">Reserved; must be NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="69534-129">返回值</span><span class="sxs-lookup"><span data-stu-id="69534-129">Return value</span></span>

<span data-ttu-id="69534-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="69534-130">S_OK</span></span> 
  
> <span data-ttu-id="69534-131">绑定过程成功。</span><span class="sxs-lookup"><span data-stu-id="69534-131">The binding process was successful.</span></span>
    
<span data-ttu-id="69534-132">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="69534-132">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="69534-133">外部地址簿提供程序不存在。</span><span class="sxs-lookup"><span data-stu-id="69534-133">The foreign address book provider doesn't exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="69534-134">注解</span><span class="sxs-lookup"><span data-stu-id="69534-134">Remarks</span></span>

<span data-ttu-id="69534-135">只为通讯簿提供程序支持对象实现**IMAPISupport::OpenTemplateID**方法。</span><span class="sxs-lookup"><span data-stu-id="69534-135">The **IMAPISupport::OpenTemplateID** method is implemented only for address book provider support objects.</span></span> <span data-ttu-id="69534-136">仅可用作条目属于其他通讯簿提供程序，也称为外的提供程序承载的通讯簿提供程序调用**OpenTemplateID** 。</span><span class="sxs-lookup"><span data-stu-id="69534-136">**OpenTemplateID** is called only by address book providers that can act as hosts for entries that belong to other address book providers, also known as foreign providers.</span></span> <span data-ttu-id="69534-137">宿主提供程序调用**OpenTemplateID**打开一个外部项，宿主提供程序中的数据绑定到外的提供程序中的代码时，发生此事件。</span><span class="sxs-lookup"><span data-stu-id="69534-137">Host providers call **OpenTemplateID** to open a foreign entry, which occurs when data in the host provider is bound to code in the foreign provider.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="69534-138">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="69534-138">Notes to callers</span></span>

<span data-ttu-id="69534-139">调用**OpenTemplateID** ，才支持与外部地址簿提供程序的模板标识符的条目存储。</span><span class="sxs-lookup"><span data-stu-id="69534-139">Call **OpenTemplateID** only if you support the storage of entries with template identifiers from foreign address book providers.</span></span> <span data-ttu-id="69534-140">此类支持将放在[IABContainer::CreateEntry](iabcontainer-createentry.md)和[IABLogon::OpenEntry](iablogon-openentry.md)实现的其他要求。</span><span class="sxs-lookup"><span data-stu-id="69534-140">Such support places additional requirements on your [IABContainer::CreateEntry](iabcontainer-createentry.md) and [IABLogon::OpenEntry](iablogon-openentry.md) implementations.</span></span> <span data-ttu-id="69534-141">有关详细信息，请参阅这些方法和[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)的说明。</span><span class="sxs-lookup"><span data-stu-id="69534-141">For more information, see the descriptions of these methods and [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>
  
<span data-ttu-id="69534-142">如果**OpenTemplateID**调用与绑定接口返回相同的属性对象实现中传递，您可以释放您对 property 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="69534-142">If the **OpenTemplateID** call returns as the bound interface the same property object implementation that you passed in, you can release your reference to your property object.</span></span> <span data-ttu-id="69534-143">这是因为外的提供程序具有调用该对象的**AddRef**方法保留其自己的引用。</span><span class="sxs-lookup"><span data-stu-id="69534-143">This is because the foreign provider has called the object's **AddRef** method to keep its own reference.</span></span> <span data-ttu-id="69534-144">如果外的提供程序并不需要保存对 property object 的引用， **OpenTemplateID**将返回绑定的 property 对象。</span><span class="sxs-lookup"><span data-stu-id="69534-144">If the foreign provider does not need to keep a reference to the property object, then **OpenTemplateID** will return the unbound property object.</span></span> 
  
<span data-ttu-id="69534-145">如果操作失败， **OpenTemplateID** MAPI_E_UNKNOWN_ENTRYID，尝试继续通过将视为只读的条目。</span><span class="sxs-lookup"><span data-stu-id="69534-145">If **OpenTemplateID** fails with MAPI_E_UNKNOWN_ENTRYID, try to continue by treating the entry as read-only.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="69534-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69534-146">See also</span></span>



[<span data-ttu-id="69534-147">IABLogon::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="69534-147">IABLogon::OpenTemplateID</span></span>](iablogon-opentemplateid.md)
  
[<span data-ttu-id="69534-148">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="69534-148">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)
  
[<span data-ttu-id="69534-149">PidTagTemplateid 规范属性</span><span class="sxs-lookup"><span data-stu-id="69534-149">PidTagTemplateid Canonical Property</span></span>](pidtagtemplateid-canonical-property.md)
  
[<span data-ttu-id="69534-150">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="69534-150">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

