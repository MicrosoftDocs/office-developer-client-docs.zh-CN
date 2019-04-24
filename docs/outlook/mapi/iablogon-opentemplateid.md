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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bc68878a25873533162df7e1671e483c3bb77865
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32334746"
---
# <a name="iablogonopentemplateid"></a><span data-ttu-id="5f78f-103">IABLogon::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="5f78f-103">IABLogon::OpenTemplateID</span></span>

  
  
<span data-ttu-id="5f78f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5f78f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5f78f-105">打开包含驻留在主机通讯簿提供程序中的数据的收件人条目。</span><span class="sxs-lookup"><span data-stu-id="5f78f-105">Opens a recipient entry that has data residing in a host address book provider.</span></span>
  
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

## <a name="parameters"></a><span data-ttu-id="5f78f-106">参数</span><span class="sxs-lookup"><span data-stu-id="5f78f-106">Parameters</span></span>

 <span data-ttu-id="5f78f-107">_cbTemplateID_</span><span class="sxs-lookup"><span data-stu-id="5f78f-107">_cbTemplateID_</span></span>
  
> <span data-ttu-id="5f78f-108">实时模板标识符中由_lpTemplateID_参数指向的字节数。</span><span class="sxs-lookup"><span data-stu-id="5f78f-108">[in] The byte count in the template identifier pointed to by the  _lpTemplateID_ parameter.</span></span> 
    
 <span data-ttu-id="5f78f-109">_lpTemplateID_</span><span class="sxs-lookup"><span data-stu-id="5f78f-109">_lpTemplateID_</span></span>
  
> <span data-ttu-id="5f78f-110">实时指向要打开的收件人条目的模板标识符或**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性的指针。</span><span class="sxs-lookup"><span data-stu-id="5f78f-110">[in] A pointer to the template identifier, or **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property, of the recipient entry to be opened.</span></span>
    
 <span data-ttu-id="5f78f-111">_ulTemplateFlags_</span><span class="sxs-lookup"><span data-stu-id="5f78f-111">_ulTemplateFlags_</span></span>
  
> <span data-ttu-id="5f78f-112">实时标志的位掩码, 用于指示如何打开由模板标识符表示的条目。</span><span class="sxs-lookup"><span data-stu-id="5f78f-112">[in] A bitmask of flags used to indicate how to open the entry represented by the template identifier.</span></span> <span data-ttu-id="5f78f-113">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="5f78f-113">The following flag can be set:</span></span>
    
<span data-ttu-id="5f78f-114">FILL_ENTRY</span><span class="sxs-lookup"><span data-stu-id="5f78f-114">FILL_ENTRY</span></span> 
  
> <span data-ttu-id="5f78f-115">主机提供程序根据模板标识符所表示的条目, 在其容器中创建新条目。</span><span class="sxs-lookup"><span data-stu-id="5f78f-115">The host provider is creating a new entry in its container based on the entry represented by the template identifier.</span></span> <span data-ttu-id="5f78f-116">**IABLogon:: OpenTemplateID**方法应使用_lpMAPIPropData_参数中的[IMAPIProp: IUnknown](imapipropiunknown.md)实现来执行主机提供程序输入的特定初始化, 或返回自定义**IMAPIProp** _lppMAPIPropNew_参数中的接口实现。</span><span class="sxs-lookup"><span data-stu-id="5f78f-116">The **IABLogon::OpenTemplateID** method should either perform specific initialization of the host provider's entry by using the [IMAPIProp : IUnknown](imapipropiunknown.md) implementation in the  _lpMAPIPropData_ parameter, or return a custom **IMAPIProp** interface implementation in the  _lppMAPIPropNew_ parameter.</span></span> 
    
 <span data-ttu-id="5f78f-117">_lpMAPIPropData_</span><span class="sxs-lookup"><span data-stu-id="5f78f-117">_lpMAPIPropData_</span></span>
  
> <span data-ttu-id="5f78f-118">实时指向主机提供程序的 property 对象和实现的接口的指针, 该接口派生自**IMAPIProp**。</span><span class="sxs-lookup"><span data-stu-id="5f78f-118">[in] A pointer to the host provider's property object and implementation of an interface derived from **IMAPIProp**.</span></span>
    
 <span data-ttu-id="5f78f-119">_lpInterface_</span><span class="sxs-lookup"><span data-stu-id="5f78f-119">_lpInterface_</span></span>
  
> <span data-ttu-id="5f78f-120">实时指向接口标识符 (IID) 的指针, 该接口标识符表示要在_lppMAPIPropNew_参数中返回的接口指针的类型。</span><span class="sxs-lookup"><span data-stu-id="5f78f-120">[in] A pointer to the interface identifier (IID) that represents the type of interface pointer to be returned in the  _lppMAPIPropNew_ parameter.</span></span> <span data-ttu-id="5f78f-121">传递**null**将返回标准消息用户界面[IMailUser: IMAPIProp](imailuserimapiprop.md)。</span><span class="sxs-lookup"><span data-stu-id="5f78f-121">Passing **null** returns the standard messaging user interface, [IMailUser : IMAPIProp](imailuserimapiprop.md).</span></span>
    
 <span data-ttu-id="5f78f-122">_lppMAPIPropNew_</span><span class="sxs-lookup"><span data-stu-id="5f78f-122">_lppMAPIPropNew_</span></span>
  
> <span data-ttu-id="5f78f-123">排除指向绑定属性对象的指针, 以及从**IMAPIProp**派生的接口的实现。</span><span class="sxs-lookup"><span data-stu-id="5f78f-123">[out] A pointer to the bound property object and an implementation of an interface derived from **IMAPIProp**.</span></span>
    
 <span data-ttu-id="5f78f-124">_lpMAPIPropSibling_</span><span class="sxs-lookup"><span data-stu-id="5f78f-124">_lpMAPIPropSibling_</span></span>
  
> <span data-ttu-id="5f78f-125">排除保留必须为**null**。</span><span class="sxs-lookup"><span data-stu-id="5f78f-125">[out] Reserved; must be **null**.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="5f78f-126">返回值</span><span class="sxs-lookup"><span data-stu-id="5f78f-126">Return value</span></span>

<span data-ttu-id="5f78f-127">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f78f-127">S_OK</span></span> 
  
> <span data-ttu-id="5f78f-128">适当的代码已成功绑定到主机提供程序中的相关数据。</span><span class="sxs-lookup"><span data-stu-id="5f78f-128">The appropriate code was successfully bound to related data in the host provider.</span></span>
    
<span data-ttu-id="5f78f-129">MAPI_E_NO_SUPPORT</span><span class="sxs-lookup"><span data-stu-id="5f78f-129">MAPI_E_NO_SUPPORT</span></span> 
  
> <span data-ttu-id="5f78f-130">对象不支持模板 id。</span><span class="sxs-lookup"><span data-stu-id="5f78f-130">The object does not support template IDs.</span></span>
    
<span data-ttu-id="5f78f-131">MAPI_E_UNKNOWN_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="5f78f-131">MAPI_E_UNKNOWN_ENTRYID</span></span> 
  
> <span data-ttu-id="5f78f-132">通讯簿提供程序无法识别_lpTemplateID_参数中传递的模板标识符。</span><span class="sxs-lookup"><span data-stu-id="5f78f-132">The template identifier passed in the  _lpTemplateID_ parameter is not recognized by the address book provider.</span></span> 
    
## <a name="remarks"></a><span data-ttu-id="5f78f-133">注解</span><span class="sxs-lookup"><span data-stu-id="5f78f-133">Remarks</span></span>

<span data-ttu-id="5f78f-134">**IABLogon:: OpenTemplateID**方法仅由通讯簿提供程序实现, 这些提供程序需要保持对位于主机提供程序的容器中的项的副本的控制。</span><span class="sxs-lookup"><span data-stu-id="5f78f-134">The **IABLogon::OpenTemplateID** method is implemented only by address book providers that need to maintain control over copies of their entries that are located in the containers of host providers.</span></span> <span data-ttu-id="5f78f-135">实现**OpenTemplateID**的提供程序称为外部通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="5f78f-135">Providers that implement **OpenTemplateID** are known as foreign address book providers.</span></span> <span data-ttu-id="5f78f-136">主机提供程序调用[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)以创建复制的条目或打开复制的条目, 并在对**IABLogon:: OpenTemplateID**的调用中进行 MAPI 传递。</span><span class="sxs-lookup"><span data-stu-id="5f78f-136">Host providers call [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md) to create a copied entry or open the copied entry, and MAPI passes on the call to **IABLogon::OpenTemplateID**.</span></span> <span data-ttu-id="5f78f-137">**IABLogon:: OpenTemplateID**打开条目并将控制它的代码绑定到主机提供程序中的数据。</span><span class="sxs-lookup"><span data-stu-id="5f78f-137">**IABLogon::OpenTemplateID** opens the entry and binds the code that controls it to data in the host provider.</span></span> 
  
<span data-ttu-id="5f78f-138">而不是使用条目标识符, **IABLogon:: OpenTemplateID**使用其他属性, 即条目的模板标识符 ( **PR_TEMPLATEID**)。</span><span class="sxs-lookup"><span data-stu-id="5f78f-138">Rather than use an entry identifier, **IABLogon::OpenTemplateID** uses another property, the entry's template identifier, **PR_TEMPLATEID**.</span></span> <span data-ttu-id="5f78f-139">对于其代码必须绑定到主机提供程序中的数据的条目, 应支持模板标识符。</span><span class="sxs-lookup"><span data-stu-id="5f78f-139">Template identifiers should be supported for entries whose code must be bound to data in a host provider.</span></span>
  
<span data-ttu-id="5f78f-140">通讯簿提供商应实现 IABLogon 的一些示例 **:: OpenTemplateID**如下所示:</span><span class="sxs-lookup"><span data-stu-id="5f78f-140">Some examples of when an address book provider should implement **IABLogon::OpenTemplateID** are as follows:</span></span> 
  
- <span data-ttu-id="5f78f-141">定期更新复制的条目的数据, 以使其与原始条目保持同步。</span><span class="sxs-lookup"><span data-stu-id="5f78f-141">To periodically update the data for a copied entry so that it stays synchronized with the original.</span></span>
    
- <span data-ttu-id="5f78f-142">若要实现宿主提供程序无法实现的功能, 例如, 从服务器上的数据动态填充显示在项的详细信息表中的列表。</span><span class="sxs-lookup"><span data-stu-id="5f78f-142">To implement functionality that the host provider cannot implement, such as dynamically populating a list that appears in the entry's details table from data on a server.</span></span>
    
- <span data-ttu-id="5f78f-143">控制主机提供程序的条目中的属性与原始条目之间的交互, 例如, 从包含不同的详细信息显示中的编辑控件的值计算**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))地址的组件。</span><span class="sxs-lookup"><span data-stu-id="5f78f-143">To control the interaction between properties in the host provider's entry and the original entry, such as computing the **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) from the values of the edit controls in the details display that contain different components of the address.</span></span>
    
## <a name="notes-to-implementers"></a><span data-ttu-id="5f78f-144">针对实现者的说明</span><span class="sxs-lookup"><span data-stu-id="5f78f-144">Notes to implementers</span></span>

<span data-ttu-id="5f78f-145">当主机提供程序从提供程序中复制或创建一个条目, 并通过**IABLogon:: OpenTemplateID**提供 property 对象实现时, 您将处理大部分调用来维护该条目。</span><span class="sxs-lookup"><span data-stu-id="5f78f-145">When a host provider copies or creates an entry from your provider and you supply a property object implementation through **IABLogon::OpenTemplateID**, you handle most of the calls to maintain the entry.</span></span> <span data-ttu-id="5f78f-146">但是, 由于由主机提供程序将这些呼叫转发给您, 因此主机提供程序可以在转发呼叫之前拦截任何呼叫并执行自定义处理。</span><span class="sxs-lookup"><span data-stu-id="5f78f-146">However, because it is up to the host provider to forward these calls to you, the host provider can intercept any call and perform custom processing before forwarding the call.</span></span>
  
<span data-ttu-id="5f78f-147">您应在属性对象实现中使用以下准则:</span><span class="sxs-lookup"><span data-stu-id="5f78f-147">You should use the following guidelines in your property object implementations:</span></span>
  
- <span data-ttu-id="5f78f-148">调用[IMAPIProp:: GetProps](imapiprop-getprops.md)时, 确定该请求是否针对的是计算的属性, 如果是, 则处理它。</span><span class="sxs-lookup"><span data-stu-id="5f78f-148">When [IMAPIProp::GetProps](imapiprop-getprops.md) is called, determine whether the request is for a computed property and, if it is, handle it.</span></span> <span data-ttu-id="5f78f-149">将 noncomputed 属性的所有请求都转移到主机提供程序。</span><span class="sxs-lookup"><span data-stu-id="5f78f-149">Transfer all requests for noncomputed properties to the host provider.</span></span> 
    
- <span data-ttu-id="5f78f-150">如果调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)来打开除详细信息显示表之外的任何表, 请处理该请求。</span><span class="sxs-lookup"><span data-stu-id="5f78f-150">When [IMAPIProp::OpenProperty](imapiprop-openproperty.md) is called to open any table except the details display table, handle the request.</span></span> <span data-ttu-id="5f78f-151">大多数表无法精确复制到主机提供程序。</span><span class="sxs-lookup"><span data-stu-id="5f78f-151">Most tables cannot be copied accurately to the host provider.</span></span> <span data-ttu-id="5f78f-152">必须为这些请求的表生成**IMAPITable**实现。</span><span class="sxs-lookup"><span data-stu-id="5f78f-152">You must generate the **IMAPITable** implementation for these requested tables.</span></span> <span data-ttu-id="5f78f-153">必须将详细信息表**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性复制到主机提供程序。</span><span class="sxs-lookup"><span data-stu-id="5f78f-153">The details table **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property must be copied to the host provider.</span></span> <span data-ttu-id="5f78f-154">这将允许此提供程序在本地生成表。</span><span class="sxs-lookup"><span data-stu-id="5f78f-154">This allows this provider to generate the table locally.</span></span> <span data-ttu-id="5f78f-155">您可能想要包装显示表实现以生成显示表通知。</span><span class="sxs-lookup"><span data-stu-id="5f78f-155">You might want to wrap the display table implementation to generate display table notifications.</span></span> 
    
- <span data-ttu-id="5f78f-156">调用[IMAPIProp:: SetProps](imapiprop-setprops.md)时, 主机提供程序可以在允许您设置属性之前验证数据。</span><span class="sxs-lookup"><span data-stu-id="5f78f-156">When [IMAPIProp::SetProps](imapiprop-setprops.md) is called, the host provider can validate the data before letting you set the properties.</span></span> <span data-ttu-id="5f78f-157">您可以验证是否已设置或计算所有必需的属性。</span><span class="sxs-lookup"><span data-stu-id="5f78f-157">You can verify that all of the necessary properties were set or computed.</span></span> <span data-ttu-id="5f78f-158">如果检测到错误, 则返回相应的错误值, 如果可以, 还可以通过[IMAPIProp:: GetLastError](imapiprop-getlasterror.md)对任何其他说明进行说明。</span><span class="sxs-lookup"><span data-stu-id="5f78f-158">If an error is detected, return the appropriate error value and, if you can, any additional explanation through [IMAPIProp::GetLastError](imapiprop-getlasterror.md).</span></span>
    
- <span data-ttu-id="5f78f-159">当调用[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)时, 主机提供程序可能需要在保存条目之前执行处理。</span><span class="sxs-lookup"><span data-stu-id="5f78f-159">When [IMAPIProp::SaveChanges](imapiprop-savechanges.md) is called, the host provider might want to perform processing before you save the entry.</span></span> <span data-ttu-id="5f78f-160">应在主机提供程序的条目中保存受更改的属性 (如新地址) 影响的任何数据。</span><span class="sxs-lookup"><span data-stu-id="5f78f-160">You should save any data that is affected by the changed properties, such as a new address, in the host provider's entry.</span></span> 
    
<span data-ttu-id="5f78f-161">通常情况下, 您对传递回主机提供程序的项的实现将截获所有方法, 以执行相关属性的特定于上下文的操作。</span><span class="sxs-lookup"><span data-stu-id="5f78f-161">In general, make your implementation of the entry that you pass back to the host provider intercept all of the methods to perform context-specific manipulation of the relevant properties.</span></span> <span data-ttu-id="5f78f-162">如果在_ulTemplateFlags_参数中传递了 FILL_ENTRY 标志, 请设置该条目的所有属性。</span><span class="sxs-lookup"><span data-stu-id="5f78f-162">If the FILL_ENTRY flag is passed in the  _ulTemplateFlags_ parameter, set all properties for the entry.</span></span> 
  
<span data-ttu-id="5f78f-163">如果您在_lppMAPIPropNew_参数中返回新的 property 对象, 请调用主机提供程序的 property 对象的[IUnknown:: AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx)方法来维护引用。</span><span class="sxs-lookup"><span data-stu-id="5f78f-163">If you return a new property object in the  _lppMAPIPropNew_ parameter, call the [IUnknown::AddRef](https://msdn.microsoft.com/library/ms691379%28VS.85%29.aspx) method of the host provider's property object to maintain a reference.</span></span> <span data-ttu-id="5f78f-164">通过绑定对象在_lppMAPIPropNew_中返回的**IMAPIProp**实现的所有调用都应路由到主机 property 对象中其对应的方法, 然后由绑定的对象进行处理。</span><span class="sxs-lookup"><span data-stu-id="5f78f-164">All calls through the bound object that the **IMAPIProp** implementation returned in  _lppMAPIPropNew_ should be routed to their corresponding method in the host property object after they are dealt with by the bound object.</span></span> 
  
<span data-ttu-id="5f78f-165">通过绑定属性对象传递的任何命名属性的属性标识符都位于提供程序的标识符命名空间中。</span><span class="sxs-lookup"><span data-stu-id="5f78f-165">The property identifiers of any named properties that are passed through your bound property object are in your provider's identifier namespace.</span></span> <span data-ttu-id="5f78f-166">您的[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)方法的实现应确定属性的名称, 以便它可以执行任何特定于模板的任务。</span><span class="sxs-lookup"><span data-stu-id="5f78f-166">Your implementation of the [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) method should determine the names of the properties so that it can perform any template-specific tasks.</span></span> <span data-ttu-id="5f78f-167">同样, 您的提供程序传递给主机提供程序的属性也必须在您的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="5f78f-167">Similarly, properties that your provider passes on to the host provider must also be in your namespace.</span></span> <span data-ttu-id="5f78f-168">例如, 如果在**OpenTemplateID**中设置命名的属性, 则应使用您的名称的一个标识符 (如有必要, 可通过调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)方法来创建它)。</span><span class="sxs-lookup"><span data-stu-id="5f78f-168">For example, if you set a named property in **OpenTemplateID**, you should use one of your identifiers for the name—creating it, if necessary, by calling the [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) method.</span></span> 
  
<span data-ttu-id="5f78f-169">如果您不知道在_lpTemplateID_中传递的条目标识符, 则返回 MAPI_E_UNKNOWN_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="5f78f-169">If you do not recognize the entry identifier passed in  _lpTemplateID_, return MAPI_E_UNKNOWN_ENTRYID.</span></span>
  
<span data-ttu-id="5f78f-170">有关如何使用通讯簿模板标识符的详细信息, 请参阅[充当外部通讯簿提供程序](acting-as-a-foreign-address-book-provider.md)。</span><span class="sxs-lookup"><span data-stu-id="5f78f-170">For more information about how to work with address book template identifiers, see [Acting as a Foreign Address Book Provider](acting-as-a-foreign-address-book-provider.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5f78f-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f78f-171">See also</span></span>



[<span data-ttu-id="5f78f-172">IMAPISupport::OpenTemplateID</span><span class="sxs-lookup"><span data-stu-id="5f78f-172">IMAPISupport::OpenTemplateID</span></span>](imapisupport-opentemplateid.md)
  
[<span data-ttu-id="5f78f-173">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="5f78f-173">IPropData : IMAPIProp</span></span>](ipropdataimapiprop.md)
  
[<span data-ttu-id="5f78f-174">PidTagTemplateid 规范属性</span><span class="sxs-lookup"><span data-stu-id="5f78f-174">PidTagTemplateid Canonical Property</span></span>](pidtagtemplateid-canonical-property.md)
  
[<span data-ttu-id="5f78f-175">IABLogon : IUnknown</span><span class="sxs-lookup"><span data-stu-id="5f78f-175">IABLogon : IUnknown</span></span>](iablogoniunknown.md)

