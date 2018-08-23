---
title: IABLogonOpenTemplateID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IABLogon.OpenTemplateID
api_type:
- COM
ms.assetid: 751c36d3-c39e-4357-a60a-88685a378de0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: a120fb1710bf2bd351d956e4d05eb0af346ef4c5
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583384"
---
# <a name="iablogonopentemplateid"></a><span data-ttu-id="7b6bc-103">IABLogon::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="7b6bc-103">IABLogon::OpenTemplateID</span></span>

  
  
<span data-ttu-id="7b6bc-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7b6bc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7b6bc-105">打开具有数据驻留在承载通讯簿提供程序中的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-105">Opens a recipient entry that has data residing in a host address book provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="7b6bc-106">参数</span><span class="sxs-lookup"><span data-stu-id="7b6bc-106">Parameters</span></span>

 <span data-ttu-id="7b6bc-107">_cbTemplateID_</span><span class="sxs-lookup"><span data-stu-id="7b6bc-107">_cbTemplateID_</span></span>
  
> <span data-ttu-id="7b6bc-108">[in]在模板标识符_lpTemplateID_参数指向字节数。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-108">[in] The byte count in the template identifier pointed to by the  _lpTemplateID_ parameter.</span></span> 
    
 <span data-ttu-id="7b6bc-109">_lpTemplateID_</span><span class="sxs-lookup"><span data-stu-id="7b6bc-109">_lpTemplateID_</span></span>
  
> <span data-ttu-id="7b6bc-110">[in]一个指向模板标识符或**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性，要打开的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-110">[in] A pointer to the template identifier, or **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property, of the recipient entry to be opened.</span></span>
    
 <span data-ttu-id="7b6bc-111">_ulTemplateFlags_</span><span class="sxs-lookup"><span data-stu-id="7b6bc-111">_ulTemplateFlags_</span></span>
  
> <span data-ttu-id="7b6bc-112">[in]用于指示如何打开由模板标识符的条目的标志位掩码。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-112">[in] A bitmask of flags used to indicate how to open the entry represented by the template identifier.</span></span> <span data-ttu-id="7b6bc-113">可以设置以下标记：</span><span class="sxs-lookup"><span data-stu-id="7b6bc-113">The following flag can be set:</span></span>
    
<span data-ttu-id="7b6bc-114">FILL_ENTRY</span><span class="sxs-lookup"><span data-stu-id="7b6bc-114">FILL_ENTRY</span></span> 
  
> <span data-ttu-id="7b6bc-115">宿主提供程序在基于由模板标识符项其容器中创建一个新的条目。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-115">The host provider is creating a new entry in its container based on the entry represented by the template identifier.</span></span> <span data-ttu-id="7b6bc-116">**IABLogon::OpenTemplateID**方法也应使用执行特定初始化宿主提供程序的条目的[IMAPIProp: IUnknown](imapipropiunknown.md) _lpMAPIPropData_参数或返回一个自定义**IMAPIProp 中的实现**接口_lppMAPIPropNew_参数中的实现。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-116">The **IABLogon::OpenTemplateID** method should either perform specific initialization of the host provider's entry by using the [IMAPIProp : IUnknown](imapipropiunknown.md) implementation in the  _lpMAPIPropData_ parameter, or return a custom **IMAPIProp** interface implementation in the  _lppMAPIPropNew_ parameter.</span></span> 
    
 <span data-ttu-id="7b6bc-117">_lpMAPIPropData_</span><span class="sxs-lookup"><span data-stu-id="7b6bc-117">_lpMAPIPropData_</span></span>
  
> <span data-ttu-id="7b6bc-118">[in]指向主机提供商的 property 对象和接口实现派生自**IMAPIProp**。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-118">[in] A pointer to the host provider's property object and implementation of an interface derived from **IMAPIProp**.</span></span>
    
 <span data-ttu-id="7b6bc-119">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="7b6bc-119">_lpInterface_</span></span>
  
> <span data-ttu-id="7b6bc-120">[in]一个指向代表类型的接口指针_lppMAPIPropNew_参数中要返回的接口标识符 (IID)。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-120">[in] A pointer to the interface identifier (IID) that represents the type of interface pointer to be returned in the  _lppMAPIPropNew_ parameter.</span></span> <span data-ttu-id="7b6bc-121">传递**null**返回消息用户界面的标准[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-121">Passing **null** returns the standard messaging user interface, [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span>
    
 <span data-ttu-id="7b6bc-122">_lppMAPIPropNew_</span><span class="sxs-lookup"><span data-stu-id="7b6bc-122">_lppMAPIPropNew_</span></span>
  
> <span data-ttu-id="7b6bc-123">[输出]一个指向绑定的 property 对象和接口派生自**IMAPIProp**的实现。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-123">[out] A pointer to the bound property object and an implementation of an interface derived from **IMAPIProp**.</span></span>
    
 <span data-ttu-id="7b6bc-124">_lpMAPIPropSibling_</span><span class="sxs-lookup"><span data-stu-id="7b6bc-124">_lpMAPIPropSibling_</span></span>
  
> <span data-ttu-id="7b6bc-125">[输出]保留;必须为**空**。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-125">[out] Reserved; must be **null**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="7b6bc-126">返回值</span><span class="sxs-lookup"><span data-stu-id="7b6bc-126">Return value</span></span>

<span data-ttu-id="7b6bc-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="7b6bc-127">S_OK</span></span> 
  
> <span data-ttu-id="7b6bc-128">相应的代码已成功绑定到宿主提供程序中的相关数据。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-128">The appropriate code was successfully bound to related data in the host provider.</span></span>
    
<span data-ttu-id="7b6bc-129">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="7b6bc-129">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="7b6bc-130">对象不支持模板 Id。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-130">The object does not support template IDs.</span></span>
    
<span data-ttu-id="7b6bc-131">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="7b6bc-131">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="7b6bc-132">通过通讯簿提供程序无法识别_lpTemplateID_参数中传递的模板标识符。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-132">The template identifier passed in the  _lpTemplateID_ parameter is not recognized by the address book provider.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="7b6bc-133">注解</span><span class="sxs-lookup"><span data-stu-id="7b6bc-133">Remarks</span></span>

<span data-ttu-id="7b6bc-134">仅由需要维护控制它们位于的宿主提供商的容器中的项的副本的通讯簿提供程序实现**IABLogon::OpenTemplateID**方法。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-134">The **IABLogon::OpenTemplateID** method is implemented only by address book providers that need to maintain control over copies of their entries that are located in the containers of host providers.</span></span> <span data-ttu-id="7b6bc-135">提供程序实现**OpenTemplateID**称为外的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-135">Providers that implement **OpenTemplateID** are known as foreign address book providers.</span></span> <span data-ttu-id="7b6bc-136">宿主提供程序调用[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)创建复制的条目或打开复制的条目，并在调用**IABLogon::OpenTemplateID**传递 MAPI。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-136">Host providers call [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) to create a copied entry or open the copied entry, and MAPI passes on the call to **IABLogon::OpenTemplateID**.</span></span> <span data-ttu-id="7b6bc-137">**IABLogon::OpenTemplateID**将打开条目，并将绑定控件到宿主提供程序中的数据的代码。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-137">**IABLogon::OpenTemplateID** opens the entry and binds the code that controls it to data in the host provider.</span></span> 
  
<span data-ttu-id="7b6bc-138">而不是使用的项标识符， **IABLogon::OpenTemplateID**使用另一个属性，该条目模板标识符， **PR_TEMPLATEID**。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-138">Rather than use an entry identifier, **IABLogon::OpenTemplateID** uses another property, the entry's template identifier, **PR_TEMPLATEID**.</span></span> <span data-ttu-id="7b6bc-139">模板标识符应支持其代码必须绑定到宿主提供程序中的数据的条目。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-139">Template identifiers should be supported for entries whose code must be bound to data in a host provider.</span></span>
  
<span data-ttu-id="7b6bc-140">某些的通讯簿提供程序应在何时实现**IABLogon::OpenTemplateID**示例如下所示：</span><span class="sxs-lookup"><span data-stu-id="7b6bc-140">Some examples of when an address book provider should implement **IABLogon::OpenTemplateID** are as follows:</span></span> 
  
- <span data-ttu-id="7b6bc-141">定期更新复制项的数据，使其保持同步与原始。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-141">To periodically update the data for a copied entry so that it stays synchronized with the original.</span></span>
    
- <span data-ttu-id="7b6bc-142">若要实现宿主提供程序无法实现，如动态填充列表项的详细信息表中显示从服务器上的数据的功能。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-142">To implement functionality that the host provider cannot implement, such as dynamically populating a list that appears in the entry's details table from data on a server.</span></span>
    
- <span data-ttu-id="7b6bc-143">若要控制宿主提供程序的条目中的属性和原始条目中，如计算**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 从包含不同的编辑控件中显示的详细信息的值之间的交互地址的组件。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-143">To control the interaction between properties in the host provider's entry and the original entry, such as computing the **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) from the values of the edit controls in the details display that contain different components of the address.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="7b6bc-144">针对实施者的注释</span><span class="sxs-lookup"><span data-stu-id="7b6bc-144">Notes to implementers</span></span>

<span data-ttu-id="7b6bc-145">当宿主提供程序复制或从您的提供商创建一个条目，并提供通过**IABLogon::OpenTemplateID**属性对象实现时，您处理大部分呼叫维护条目。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-145">When a host provider copies or creates an entry from your provider and you supply a property object implementation through **IABLogon::OpenTemplateID**, you handle most of the calls to maintain the entry.</span></span> <span data-ttu-id="7b6bc-146">但是，因为它是主机提供这些将呼叫转接到您，宿主提供程序可以截获任何呼叫，并执行自定义处理，然后转接呼叫。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-146">However, because it is up to the host provider to forward these calls to you, the host provider can intercept any call and perform custom processing before forwarding the call.</span></span>
  
<span data-ttu-id="7b6bc-147">您属性对象实现中，您应使用以下准则：</span><span class="sxs-lookup"><span data-stu-id="7b6bc-147">You should use the following guidelines in your property object implementations:</span></span>
  
- <span data-ttu-id="7b6bc-148">调用[IMAPIProp::GetProps](imapiprop-getprops.md)时，确定是否此请求所使用的计算属性，如果是，处理它。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-148">When [IMAPIProp::GetProps](imapiprop-getprops.md) is called, determine whether the request is for a computed property and, if it is, handle it.</span></span> <span data-ttu-id="7b6bc-149">将为未计算属性的所有请求都传送到宿主提供程序。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-149">Transfer all requests for noncomputed properties to the host provider.</span></span> 
    
- <span data-ttu-id="7b6bc-150">当[IMAPIProp::OpenProperty](imapiprop-openproperty.md)调用它以打开任何表格中的除详细信息显示表，处理请求。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-150">When [IMAPIProp::OpenProperty](imapiprop-openproperty.md) is called to open any table except the details display table, handle the request.</span></span> <span data-ttu-id="7b6bc-151">大多数表无法准确地复制到宿主提供程序。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-151">Most tables cannot be copied accurately to the host provider.</span></span> <span data-ttu-id="7b6bc-152">您必须生成这些请求表的**IMAPITable**实现。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-152">You must generate the **IMAPITable** implementation for these requested tables.</span></span> <span data-ttu-id="7b6bc-153">详细信息表**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性必须将复制到宿主提供程序。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-153">The details table **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property must be copied to the host provider.</span></span> <span data-ttu-id="7b6bc-154">这样，此提供程序可以生成本地表。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-154">This allows this provider to generate the table locally.</span></span> <span data-ttu-id="7b6bc-155">您可能希望换行显示表实现，以生成显示表通知。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-155">You might want to wrap the display table implementation to generate display table notifications.</span></span> 
    
- <span data-ttu-id="7b6bc-156">当调用[IMAPIProp::SetProps](imapiprop-setprops.md)时，宿主提供程序可以让您设置属性之前验证的数据。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-156">When [IMAPIProp::SetProps](imapiprop-setprops.md) is called, the host provider can validate the data before letting you set the properties.</span></span> <span data-ttu-id="7b6bc-157">您可以验证所有必要的属性已设置或计算。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-157">You can verify that all of the necessary properties were set or computed.</span></span> <span data-ttu-id="7b6bc-158">如果检测到错误时，返回相应的错误值，如果可能，通过[IMAPIProp::GetLastError](imapiprop-getlasterror.md)任何其他说明。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-158">If an error is detected, return the appropriate error value and, if you can, any additional explanation through [IMAPIProp::GetLastError](imapiprop-getlasterror.md).</span></span>
    
- <span data-ttu-id="7b6bc-159">当调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)时，宿主提供程序可能需要执行处理之前保存该条目。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-159">When [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called, the host provider might want to perform processing before you save the entry.</span></span> <span data-ttu-id="7b6bc-160">您应该保存受已更改的属性，如宿主提供程序的条目中的新地址的任何数据。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-160">You should save any data that is affected by the changed properties, such as a new address, in the host provider's entry.</span></span> 
    
<span data-ttu-id="7b6bc-161">一般情况下，返回对宿主提供程序进行传递的条目的实现 intercept 的所有方法执行的相关属性的上下文特定操作。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-161">In general, make your implementation of the entry that you pass back to the host provider intercept all of the methods to perform context-specific manipulation of the relevant properties.</span></span> <span data-ttu-id="7b6bc-162">如果_ulTemplateFlags_参数中传递 FILL_ENTRY 标志，则设置该条目的所有属性。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-162">If the FILL_ENTRY flag is passed in the  _ulTemplateFlags_ parameter, set all properties for the entry.</span></span> 
  
<span data-ttu-id="7b6bc-163">如果_lppMAPIPropNew_参数中返回新的 property 对象，请调用要维护的引用的宿主提供程序的属性对象的[IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-163">If you return a new property object in the  _lppMAPIPropNew_ parameter, call the [IUnknown::AddRef](http://msdn.microsoft.com/en-us/library/ms691379%28VS.85%29.aspx) method of the host provider's property object to maintain a reference.</span></span> <span data-ttu-id="7b6bc-164">通过**IMAPIProp**实现_lppMAPIPropNew_中返回的绑定对象的所有呼叫将都路由到其对应的方法中的主机属性对象处理绑定对象后。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-164">All calls through the bound object that the **IMAPIProp** implementation returned in  _lppMAPIPropNew_ should be routed to their corresponding method in the host property object after they are dealt with by the bound object.</span></span> 
  
<span data-ttu-id="7b6bc-165">通过绑定的属性对象传递任何命名属性的属性的标识符是提供程序的标识符命名空间中。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-165">The property identifiers of any named properties that are passed through your bound property object are in your provider's identifier namespace.</span></span> <span data-ttu-id="7b6bc-166">[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)方法的实现应确定属性的名称，以便它可以执行任何特定于模板的任务。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-166">Your implementation of the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) method should determine the names of the properties so that it can perform any template-specific tasks.</span></span> <span data-ttu-id="7b6bc-167">同样，您的提供商将传递给宿主提供程序的属性也必须在您的命名空间。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-167">Similarly, properties that your provider passes on to the host provider must also be in your namespace.</span></span> <span data-ttu-id="7b6bc-168">例如，如果**OpenTemplateID**中设置的命名的属性，您应使用您标识符之一的名称 — 通过调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)方法有必要，创建它。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-168">For example, if you set a named property in **OpenTemplateID**, you should use one of your identifiers for the name—creating it, if necessary, by calling the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method.</span></span> 
  
<span data-ttu-id="7b6bc-169">如果您不认识_lpTemplateID_中传递的项标识符，返回 MAPI_E_UNKNOWN_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-169">If you do not recognize the entry identifier passed in  _lpTemplateID_, return MAPI_E_UNKNOWN_ENTRYID.</span></span>
  
<span data-ttu-id="7b6bc-170">有关如何使用地址簿模板标识符的详细信息，请参阅[充当外的通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="7b6bc-170">For more information about how to work with address book template identifiers, see [Acting as a Foreign Address Book Provider](acting-as-a-foreign-address-book-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7b6bc-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b6bc-171">See also</span></span>



[<span data-ttu-id="7b6bc-172">IMAPISupport::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="7b6bc-172">IMAPISupport::OpenTemplateID</span></span>](imapisupport-opentemplateid.md)
  
[<span data-ttu-id="7b6bc-173">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="7b6bc-173">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)
  
[<span data-ttu-id="7b6bc-174">PidTagTemplateid 规范属性</span><span class="sxs-lookup"><span data-stu-id="7b6bc-174">PidTagTemplateid Canonical Property</span></span>](pidtagtemplateid-canonical-property.md)
  
[<span data-ttu-id="7b6bc-175">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="7b6bc-175">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

