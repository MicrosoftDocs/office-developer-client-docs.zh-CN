---
title: IProfSect IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfSect
api_type:
- COM
ms.assetid: 4e704044-5230-4521-a0d2-b7c2f981c954
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8152a9cad7623a077cd9df3f678a9ada56e3960
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577959"
---
# <a name="iprofsect--imapiprop"></a><span data-ttu-id="85417-103">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="85417-103">IProfSect : IMAPIProp</span></span>

  
  
<span data-ttu-id="85417-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85417-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="85417-105">适用于配置文件部分对象的属性。</span><span class="sxs-lookup"><span data-stu-id="85417-105">Works with the properties of profile section objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="85417-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="85417-106">Header file:</span></span>  <br/> |<span data-ttu-id="85417-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="85417-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="85417-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="85417-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="85417-109">配置文件部分对象</span><span class="sxs-lookup"><span data-stu-id="85417-109">Profile section objects</span></span>  <br/> |
|<span data-ttu-id="85417-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="85417-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="85417-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="85417-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="85417-112">调用：</span><span class="sxs-lookup"><span data-stu-id="85417-112">Called by:</span></span>  <br/> |<span data-ttu-id="85417-113">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="85417-113">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="85417-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="85417-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="85417-115">IID_IProfSect</span><span class="sxs-lookup"><span data-stu-id="85417-115">IID_IProfSect</span></span>  <br/> |
|<span data-ttu-id="85417-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="85417-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="85417-117">LPPROFSECT</span><span class="sxs-lookup"><span data-stu-id="85417-117">LPPROFSECT</span></span>  <br/> |
|<span data-ttu-id="85417-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="85417-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="85417-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="85417-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="85417-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="85417-120">Vtable order</span></span>

<span data-ttu-id="85417-121">此接口不具有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="85417-121">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="85417-122">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="85417-122">**Required properties**</span></span>|<span data-ttu-id="85417-123">**Access**</span><span class="sxs-lookup"><span data-stu-id="85417-123">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="85417-124">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="85417-124">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="85417-125">只读</span><span class="sxs-lookup"><span data-stu-id="85417-125">Read-only</span></span>  <br/> |
|<span data-ttu-id="85417-126">**PR_PROFILE_NAME**([PidTagProfileName](pidtagprofilename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="85417-126">**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="85417-127">只读</span><span class="sxs-lookup"><span data-stu-id="85417-127">Read-only</span></span>  <br/> |
   
## <a name="notes-to-callers"></a><span data-ttu-id="85417-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="85417-128">Notes to callers</span></span>

<span data-ttu-id="85417-129">**IProfSect**接口不具有其自己的任何唯一方法，但是您可以调用该配置文件节的[IMAPIProp](imapipropiunknown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="85417-129">The **IProfSect** interface does not have any unique methods of its own, but you can call the profile section's [IMAPIProp](imapipropiunknown.md) methods.</span></span> <span data-ttu-id="85417-130">有一些**IProfSect**实施和**IMAPIProp**其他实现之间的区别：</span><span class="sxs-lookup"><span data-stu-id="85417-130">There are some differences between the **IProfSect** implementation and other implementations of **IMAPIProp**:</span></span>
  
- <span data-ttu-id="85417-131">**IProfSect**不支持事务模型。</span><span class="sxs-lookup"><span data-stu-id="85417-131">**IProfSect** does not support a transaction model.</span></span> 
    
- <span data-ttu-id="85417-132">**IProfSect**不支持命名的属性。</span><span class="sxs-lookup"><span data-stu-id="85417-132">**IProfSect** does not support named properties.</span></span> 
    
- <span data-ttu-id="85417-133">**IProfSect**保留标识符的范围 0x67F0 到 0x67ff 安全属性。</span><span class="sxs-lookup"><span data-stu-id="85417-133">**IProfSect** reserves the identifier range 0x67F0 to 0x67ff for secure properties.</span></span> 
    
<span data-ttu-id="85417-134">不支持事务模型意味着，所做的所有更改配置文件部分以下都呼叫到[IMAPIProp::CopyProps](imapiprop-copyprops.md)和[IMAPIProp::CopyTo](imapiprop-copyto.md)方法立即发生。</span><span class="sxs-lookup"><span data-stu-id="85417-134">Not supporting a transaction model means that all changes that were made to a profile section following calls to the [IMAPIProp::CopyProps](imapiprop-copyprops.md) and [IMAPIProp::CopyTo](imapiprop-copyto.md) methods occur immediately.</span></span> <span data-ttu-id="85417-135">调用[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法成功，但实际不保存任何更改。</span><span class="sxs-lookup"><span data-stu-id="85417-135">Calls to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method succeed but do not actually save any changes.</span></span> 
  
<span data-ttu-id="85417-136">若要防止提前发生的更改，服务提供商需要进行的属性表通过向用户显示其配置文件部分副本。</span><span class="sxs-lookup"><span data-stu-id="85417-136">To be protected from changes that occur prematurely, service providers need to make copies of their profile sections that are displayed to users through property sheets.</span></span> <span data-ttu-id="85417-137">属性表应使用的副本，而不是实际的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="85417-137">The property sheets should work with the copy, instead of the real profile section.</span></span> <span data-ttu-id="85417-138">当用户单击**确定**按钮以验证所做的更改准确时，实际的配置文件一节可以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="85417-138">When the user clicks the **OK** button to verify that the changes are accurate, the changes can be saved to the real profile section.</span></span> 
  
<span data-ttu-id="85417-139">若要通过使用复制的配置文件部分实现属性表，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="85417-139">To implement a property sheet by using a copied profile section, use the following procedure:</span></span>
  
1. <span data-ttu-id="85417-140">通过调用[IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md)或[IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md)方法打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="85417-140">Open the profile section by calling the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) or [IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) method.</span></span> 
    
2. <span data-ttu-id="85417-141">调用[CreateIProp](createiprop.md)函数以检索属性数据对象 — 支持**IPropData**接口的对象。</span><span class="sxs-lookup"><span data-stu-id="85417-141">Call the [CreateIProp](createiprop.md) function to retrieve a property data object — an object that supports the **IPropData** interface.</span></span> 
    
3. <span data-ttu-id="85417-142">调用复制属性将出现在从配置文件部分对属性的数据对象的属性表上的配置文件部分的[IMAPIProp::CopyTo](imapiprop-copyto.md)方法。</span><span class="sxs-lookup"><span data-stu-id="85417-142">Call the profile section's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the properties that will appear on the property sheet from the profile section to the property data object.</span></span> 
    
4. <span data-ttu-id="85417-143">调用[IMAPISupport::DoConfigPropSheet](imapisupport-doconfigpropsheet.md)方法可以请求服务提供商显示属性表，并将指针传递给_lpConfigData_参数中的属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="85417-143">Call the [IMAPISupport::DoConfigPropSheet](imapisupport-doconfigpropsheet.md) method to request that the service provider display a property sheet, and pass a pointer to the property data object in the  _lpConfigData_ parameter.</span></span> 
    
5. <span data-ttu-id="85417-144">当用户将更改保存到属性表中的配置属性时，调用[IMAPIProp::CopyTo](imapiprop-copyto.md)方法以返回到配置文件部分，从属性数据对象复制属性。</span><span class="sxs-lookup"><span data-stu-id="85417-144">When the user saves changes to configuration properties in the property sheet, call the [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the properties from the property data object back to the profile section.</span></span> 
    
<span data-ttu-id="85417-145">配置文件节，与其他对象不同，不支持命名的属性。</span><span class="sxs-lookup"><span data-stu-id="85417-145">Profile sections, unlike other objects, do not support named properties.</span></span> <span data-ttu-id="85417-146">如果在配置文件部分对象上调用它们， [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)方法的返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="85417-146">The [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) and [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) methods return MAPI_E_NO_SUPPORT if they are called on a profile section object.</span></span> <span data-ttu-id="85417-147">如果您使用[IMAPIProp::SetProps](imapiprop-setprops.md)方法上方 0x8000 范围中设置属性标识符，将返回 PT_ERROR 属性类型。</span><span class="sxs-lookup"><span data-stu-id="85417-147">If you use the [IMAPIProp::SetProps](imapiprop-setprops.md) method to set property identifiers in the range above 0x8000, the PT_ERROR property type will be returned.</span></span> 
  
<span data-ttu-id="85417-148">配置文件部分保留标识符的范围 0x67F0 到 0x67FF 安全属性。</span><span class="sxs-lookup"><span data-stu-id="85417-148">Profile sections reserve the identifier range 0x67F0 to 0x67FF for secure properties.</span></span> <span data-ttu-id="85417-149">服务提供商可以使用此范围可存储密码和其他特定于提供程序的凭据。</span><span class="sxs-lookup"><span data-stu-id="85417-149">Service providers can use this range to store passwords and other provider-specific credentials.</span></span> <span data-ttu-id="85417-150">[IMAPIProp::GetProps](imapiprop-getprops.md)方法的_lpPropTag_参数中传递空值和它们以[的_lppPropTagArray_参数返回时，此范围中的属性不返回中属性的完整列表IMAPIProp::GetPropList](imapiprop-getproplist.md)方法。</span><span class="sxs-lookup"><span data-stu-id="85417-150">Properties in this range are not returned in the complete list of properties when NULL is passed in the  _lpPropTag_ parameter of the [IMAPIProp::GetProps](imapiprop-getprops.md) method, nor are they returned in the  _lppPropTagArray_ parameter of the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> <span data-ttu-id="85417-151">安全属性必须专门通过其标识符来请求。</span><span class="sxs-lookup"><span data-stu-id="85417-151">Secure properties must be requested specifically by their identifiers.</span></span> 
  
<span data-ttu-id="85417-152">MAPI 作为其单个属性与作为其标识符的硬编码常量 MUID_PROFILE_INSTANCE **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 提供配置文件一节。</span><span class="sxs-lookup"><span data-stu-id="85417-152">MAPI furnishes a profile section with the hard-coded constant MUID_PROFILE_INSTANCE as its identifier and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) as its single property.</span></span> <span data-ttu-id="85417-153">MAPI 确保**PR_SEARCH_KEY**属性值将是唯一的而创建的所有配置文件。</span><span class="sxs-lookup"><span data-stu-id="85417-153">MAPI ensures that the **PR_SEARCH_KEY** property value will be unique among all created profiles.</span></span> <span data-ttu-id="85417-154">唯一性很重要，因为这样跟具有相同名称的另一个配置文件的已删除配置文件时，请使用**PR_SEARCH_KEY**而不是**PR_PROFILE_NAME** 。</span><span class="sxs-lookup"><span data-stu-id="85417-154">Use **PR_SEARCH_KEY** instead of **PR_PROFILE_NAME** when uniqueness is important, because it is possible for a deleted profile to be followed by another profile with the same name.</span></span> 
  
<span data-ttu-id="85417-155">有关如何使用配置文件节，请参阅[管理配置文件和消息服务](administering-profiles-and-message-services.md)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="85417-155">For more information about how to use profile sections, see [Administering Profiles and Message Services](administering-profiles-and-message-services.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85417-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85417-156">See also</span></span>



[<span data-ttu-id="85417-157">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="85417-157">MAPI Interfaces</span></span>](mapi-interfaces.md)

