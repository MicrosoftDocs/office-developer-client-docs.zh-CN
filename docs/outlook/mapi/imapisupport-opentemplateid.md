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
# <a name="imapisupportopentemplateid"></a><span data-ttu-id="fe760-103">IMAPISupport::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="fe760-103">IMAPISupport::OpenTemplateID</span></span>

  
  
<span data-ttu-id="fe760-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fe760-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fe760-105">打开外部通讯簿提供程序中的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="fe760-105">Opens a recipient entry in a foreign address book provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="fe760-106">参数</span><span class="sxs-lookup"><span data-stu-id="fe760-106">Parameters</span></span>

 <span data-ttu-id="fe760-107">_cbTemplateID_</span><span class="sxs-lookup"><span data-stu-id="fe760-107">_cbTemplateID_</span></span>
  
> <span data-ttu-id="fe760-108">实时模板标识符中由_lpTemplateID_指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="fe760-108">[in] The byte count in the template identifier pointed to by  _lpTemplateID_.</span></span> 
    
 <span data-ttu-id="fe760-109">_lpTemplateID_</span><span class="sxs-lookup"><span data-stu-id="fe760-109">_lpTemplateID_</span></span>
  
> <span data-ttu-id="fe760-110">实时指向要打开的收件人条目的模板标识符**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的指针。</span><span class="sxs-lookup"><span data-stu-id="fe760-110">[in] A pointer to the template identifier **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property of the recipient entry to be opened.</span></span>
    
 <span data-ttu-id="fe760-111">_ulTemplateFlags_</span><span class="sxs-lookup"><span data-stu-id="fe760-111">_ulTemplateFlags_</span></span>
  
> <span data-ttu-id="fe760-112">实时用于描述如何打开条目的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="fe760-112">[in] A bitmask of flags used to describe how to open the entry.</span></span> <span data-ttu-id="fe760-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="fe760-113">The following flag can be set:</span></span>
    
<span data-ttu-id="fe760-114">FILL_ENTRY</span><span class="sxs-lookup"><span data-stu-id="fe760-114">FILL_ENTRY</span></span> 
  
> <span data-ttu-id="fe760-115">正在创建新条目。</span><span class="sxs-lookup"><span data-stu-id="fe760-115">A new entry is being created.</span></span> <span data-ttu-id="fe760-116">当外部提供程序接收到来自 MAPI 的后续[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)呼叫时, 它可以通过修改由_lpMAPIPropData_参数指向的属性或返回特定接口来控制创建条目的方式。_lppMAPIPropNew_中的实现来控制如何设置新条目的属性。</span><span class="sxs-lookup"><span data-stu-id="fe760-116">When the foreign provider receives the subsequent [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) call from MAPI, it can control how the entry is created by modifying properties pointed to by the  _lpMAPIPropData_ parameter or by returning a specific interface implementation in  _lppMAPIPropNew_ to control how properties for the new entry are set.</span></span> 
    
 <span data-ttu-id="fe760-117">_lpMAPIPropData_</span><span class="sxs-lookup"><span data-stu-id="fe760-117">_lpMAPIPropData_</span></span>
  
> <span data-ttu-id="fe760-118">实时指向调用方用来访问条目的接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="fe760-118">[in] A pointer to the interface implementation that the caller uses to access the entry.</span></span> <span data-ttu-id="fe760-119">这是外部提供程序可以使用其自己的实现进行包装并在_lppMAPIPropNew_参数中返回的实现。</span><span class="sxs-lookup"><span data-stu-id="fe760-119">This is the implementation that the foreign provider can wrap with its own implementation and return in the  _lppMAPIPropNew_ parameter.</span></span> <span data-ttu-id="fe760-120">_lpMAPIPropData_参数必须指向从[IMAPIProp: IUnknown](imapipropiunknown.md)派生并支持在_lpInterface_参数中请求的接口的读/写接口实现。</span><span class="sxs-lookup"><span data-stu-id="fe760-120">The  _lpMAPIPropData_ parameter must point to a read/write interface implementation that derives from [IMAPIProp : IUnknown](imapipropiunknown.md) and supports the interface being requested in the  _lpInterface_ parameter.</span></span> 
    
 <span data-ttu-id="fe760-121">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="fe760-121">_lpInterface_</span></span>
  
> <span data-ttu-id="fe760-122">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要用于访问该条目的接口。</span><span class="sxs-lookup"><span data-stu-id="fe760-122">[in] A pointer to the interface identifier (IID) that represents the interface to be used to access the entry.</span></span> <span data-ttu-id="fe760-123">_lppMAPIPropNew_参数指向_lpInterface_指定的类型的接口。</span><span class="sxs-lookup"><span data-stu-id="fe760-123">The  _lppMAPIPropNew_ parameter points to an interface of the type specified by  _lpInterface_.</span></span> <span data-ttu-id="fe760-124">传递 NULL 将返回邮件用户的标准接口 IID_IMailUser。</span><span class="sxs-lookup"><span data-stu-id="fe760-124">Passing NULL returns the standard interface for a messaging user, IID_IMailUser.</span></span> 
    
 <span data-ttu-id="fe760-125">_lppMAPIPropNew_</span><span class="sxs-lookup"><span data-stu-id="fe760-125">_lppMAPIPropNew_</span></span>
  
> <span data-ttu-id="fe760-126">排除指向外部提供程序用于访问条目的接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="fe760-126">[out] A pointer to the interface implementation that the foreign provider supplies for accessing the entry.</span></span>
    
 <span data-ttu-id="fe760-127">_lpMAPIPropSibling_</span><span class="sxs-lookup"><span data-stu-id="fe760-127">_lpMAPIPropSibling_</span></span>
  
> <span data-ttu-id="fe760-128">保留必须为 NULL。</span><span class="sxs-lookup"><span data-stu-id="fe760-128">Reserved; must be NULL.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="fe760-129">返回值</span><span class="sxs-lookup"><span data-stu-id="fe760-129">Return value</span></span>

<span data-ttu-id="fe760-130">S_OK</span><span class="sxs-lookup"><span data-stu-id="fe760-130">S_OK</span></span> 
  
> <span data-ttu-id="fe760-131">绑定过程已成功。</span><span class="sxs-lookup"><span data-stu-id="fe760-131">The binding process was successful.</span></span>
    
<span data-ttu-id="fe760-132">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="fe760-132">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="fe760-133">外部通讯簿提供程序不存在。</span><span class="sxs-lookup"><span data-stu-id="fe760-133">The foreign address book provider doesn't exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fe760-134">说明</span><span class="sxs-lookup"><span data-stu-id="fe760-134">Remarks</span></span>

<span data-ttu-id="fe760-135">仅对通讯簿提供程序支持对象实现**IMAPISupport:: OpenTemplateID**方法。</span><span class="sxs-lookup"><span data-stu-id="fe760-135">The **IMAPISupport::OpenTemplateID** method is implemented only for address book provider support objects.</span></span> <span data-ttu-id="fe760-136">**OpenTemplateID**只能由通讯簿提供程序调用, 该提供程序可充当属于其他通讯簿提供程序 (也称为外部提供程序) 的条目的主机。</span><span class="sxs-lookup"><span data-stu-id="fe760-136">**OpenTemplateID** is called only by address book providers that can act as hosts for entries that belong to other address book providers, also known as foreign providers.</span></span> <span data-ttu-id="fe760-137">主机提供程序调用**OpenTemplateID**以打开外接程序, 当主机提供程序中的数据绑定到外部提供程序中的代码时, 将发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="fe760-137">Host providers call **OpenTemplateID** to open a foreign entry, which occurs when data in the host provider is bound to code in the foreign provider.</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="fe760-138">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="fe760-138">Notes to callers</span></span>

<span data-ttu-id="fe760-139">仅当您支持通过外部通讯簿提供程序存储具有模板标识符的条目时, 才会调用**OpenTemplateID** 。</span><span class="sxs-lookup"><span data-stu-id="fe760-139">Call **OpenTemplateID** only if you support the storage of entries with template identifiers from foreign address book providers.</span></span> <span data-ttu-id="fe760-140">此类支持对[IABContainer:: CreateEntry](iabcontainer-createentry.md)和[IABLogon:: OpenEntry](iablogon-openentry.md)实现施加了其他要求。</span><span class="sxs-lookup"><span data-stu-id="fe760-140">Such support places additional requirements on your [IABContainer::CreateEntry](iabcontainer-createentry.md) and [IABLogon::OpenEntry](iablogon-openentry.md) implementations.</span></span> <span data-ttu-id="fe760-141">有关详细信息, 请参阅这些方法的说明和[充当主机通讯簿提供程序](acting-as-a-host-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="fe760-141">For more information, see the descriptions of these methods and [Acting as a Host Address Book Provider](acting-as-a-host-address-book-provider.md).</span></span>
  
<span data-ttu-id="fe760-142">如果**OpenTemplateID**调用作为绑定接口返回, 则表示您传递的属性对象实现相同, 您可以释放对属性对象的引用。</span><span class="sxs-lookup"><span data-stu-id="fe760-142">If the **OpenTemplateID** call returns as the bound interface the same property object implementation that you passed in, you can release your reference to your property object.</span></span> <span data-ttu-id="fe760-143">这是因为外部提供程序已调用对象的**AddRef**方法来保留自己的引用。</span><span class="sxs-lookup"><span data-stu-id="fe760-143">This is because the foreign provider has called the object's **AddRef** method to keep its own reference.</span></span> <span data-ttu-id="fe760-144">如果外部提供程序不需要保留对 property 对象的引用, 则**OpenTemplateID**将返回未绑定的属性对象。</span><span class="sxs-lookup"><span data-stu-id="fe760-144">If the foreign provider does not need to keep a reference to the property object, then **OpenTemplateID** will return the unbound property object.</span></span> 
  
<span data-ttu-id="fe760-145">如果**OpenTemplateID**在 MAPI_E_UNKNOWN_ENTRYID 中失败, 请尝试通过将该条目视为只读来继续。</span><span class="sxs-lookup"><span data-stu-id="fe760-145">If **OpenTemplateID** fails with MAPI_E_UNKNOWN_ENTRYID, try to continue by treating the entry as read-only.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fe760-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe760-146">See also</span></span>



[<span data-ttu-id="fe760-147">IABLogon::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="fe760-147">IABLogon::OpenTemplateID</span></span>](iablogon-opentemplateid.md)
  
[<span data-ttu-id="fe760-148">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="fe760-148">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)
  
[<span data-ttu-id="fe760-149">PidTagTemplateid 规范属性</span><span class="sxs-lookup"><span data-stu-id="fe760-149">PidTagTemplateid Canonical Property</span></span>](pidtagtemplateid-canonical-property.md)
  
[<span data-ttu-id="fe760-150">IMAPISupport : IUnknown</span><span class="sxs-lookup"><span data-stu-id="fe760-150">IMAPISupport : IUnknown</span></span>](imapisupportiunknown.md)

