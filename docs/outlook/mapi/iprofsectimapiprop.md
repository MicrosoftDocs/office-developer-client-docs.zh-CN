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
ms.openlocfilehash: 99ce944bec94a1e832f77fa8b0916ac1c76f6dc6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406596"
---
# <a name="iprofsect--imapiprop"></a><span data-ttu-id="4a145-103">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="4a145-103">IProfSect : IMAPIProp</span></span>

  
  
<span data-ttu-id="4a145-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a145-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a145-105">适用于 profile 节对象的属性。</span><span class="sxs-lookup"><span data-stu-id="4a145-105">Works with the properties of profile section objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4a145-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4a145-106">Header file:</span></span>  <br/> |<span data-ttu-id="4a145-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="4a145-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="4a145-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="4a145-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="4a145-109">Profile 部分对象</span><span class="sxs-lookup"><span data-stu-id="4a145-109">Profile section objects</span></span>  <br/> |
|<span data-ttu-id="4a145-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="4a145-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="4a145-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="4a145-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="4a145-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="4a145-112">Called by:</span></span>  <br/> |<span data-ttu-id="4a145-113">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="4a145-113">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="4a145-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="4a145-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4a145-115">IID_IProfSect</span><span class="sxs-lookup"><span data-stu-id="4a145-115">IID_IProfSect</span></span>  <br/> |
|<span data-ttu-id="4a145-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="4a145-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="4a145-117">LPPROFSECT</span><span class="sxs-lookup"><span data-stu-id="4a145-117">LPPROFSECT</span></span>  <br/> |
|<span data-ttu-id="4a145-118">事务模型:</span><span class="sxs-lookup"><span data-stu-id="4a145-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="4a145-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="4a145-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4a145-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="4a145-120">Vtable order</span></span>

<span data-ttu-id="4a145-121">此接口没有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="4a145-121">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="4a145-122">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="4a145-122">**Required properties**</span></span>|<span data-ttu-id="4a145-123">**访问**</span><span class="sxs-lookup"><span data-stu-id="4a145-123">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4a145-124">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="4a145-124">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="4a145-125">只读</span><span class="sxs-lookup"><span data-stu-id="4a145-125">Read-only</span></span>  <br/> |
|<span data-ttu-id="4a145-126">**PR_PROFILE_NAME**([PidTagProfileName](pidtagprofilename-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="4a145-126">**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="4a145-127">只读</span><span class="sxs-lookup"><span data-stu-id="4a145-127">Read-only</span></span>  <br/> |
   
## <a name="notes-to-callers"></a><span data-ttu-id="4a145-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="4a145-128">Notes to callers</span></span>

<span data-ttu-id="4a145-129">**IProfSect**接口没有自己的任何唯一方法, 但您可以调用 profile 节的[IMAPIProp](imapipropiunknown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4a145-129">The **IProfSect** interface does not have any unique methods of its own, but you can call the profile section's [IMAPIProp](imapipropiunknown.md) methods.</span></span> <span data-ttu-id="4a145-130">在**IProfSect**实现和**IMAPIProp**的其他实现之间存在一些差异:</span><span class="sxs-lookup"><span data-stu-id="4a145-130">There are some differences between the **IProfSect** implementation and other implementations of **IMAPIProp**:</span></span>
  
- <span data-ttu-id="4a145-131">**IProfSect**不支持事务模型。</span><span class="sxs-lookup"><span data-stu-id="4a145-131">**IProfSect** does not support a transaction model.</span></span> 
    
- <span data-ttu-id="4a145-132">**IProfSect**不支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="4a145-132">**IProfSect** does not support named properties.</span></span> 
    
- <span data-ttu-id="4a145-133">**IProfSect**保留用于安全属性的标识符范围0x67F0 到0x67ff。</span><span class="sxs-lookup"><span data-stu-id="4a145-133">**IProfSect** reserves the identifier range 0x67F0 to 0x67ff for secure properties.</span></span> 
    
<span data-ttu-id="4a145-134">不支持事务模型意味着在调用[IMAPIProp:: CopyProps](imapiprop-copyprops.md)和[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法后, 对配置文件节所做的所有更改都将立即发生。</span><span class="sxs-lookup"><span data-stu-id="4a145-134">Not supporting a transaction model means that all changes that were made to a profile section following calls to the [IMAPIProp::CopyProps](imapiprop-copyprops.md) and [IMAPIProp::CopyTo](imapiprop-copyto.md) methods occur immediately.</span></span> <span data-ttu-id="4a145-135">对[IMAPIProp:: SaveChanges](imapiprop-savechanges.md)方法的调用会成功, 但实际上并不会保存任何更改。</span><span class="sxs-lookup"><span data-stu-id="4a145-135">Calls to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method succeed but do not actually save any changes.</span></span> 
  
<span data-ttu-id="4a145-136">为了防止发生过早发生的更改, 服务提供商需要通过属性表向用户显示其配置文件节的副本。</span><span class="sxs-lookup"><span data-stu-id="4a145-136">To be protected from changes that occur prematurely, service providers need to make copies of their profile sections that are displayed to users through property sheets.</span></span> <span data-ttu-id="4a145-137">属性表应适用于副本, 而不是实际的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="4a145-137">The property sheets should work with the copy, instead of the real profile section.</span></span> <span data-ttu-id="4a145-138">当用户单击 **"确定"** 按钮以验证更改是否正确时, 可以将更改保存到 "实际配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="4a145-138">When the user clicks the **OK** button to verify that the changes are accurate, the changes can be saved to the real profile section.</span></span> 
  
<span data-ttu-id="4a145-139">若要使用已复制的 profile 节实现属性表, 请使用以下过程:</span><span class="sxs-lookup"><span data-stu-id="4a145-139">To implement a property sheet by using a copied profile section, use the following procedure:</span></span>
  
1. <span data-ttu-id="4a145-140">通过调用[IMAPISupport:: OpenProfileSection](imapisupport-openprofilesection.md)或[IProviderAdmin:: OpenProfileSection](iprovideradmin-openprofilesection.md)方法打开 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="4a145-140">Open the profile section by calling the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) or [IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) method.</span></span> 
    
2. <span data-ttu-id="4a145-141">调用[CreateIProp](createiprop.md)函数以检索属性数据对象, 即支持**IPropData**接口的对象。</span><span class="sxs-lookup"><span data-stu-id="4a145-141">Call the [CreateIProp](createiprop.md) function to retrieve a property data object — an object that supports the **IPropData** interface.</span></span> 
    
3. <span data-ttu-id="4a145-142">调用 profile 节的[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将属性表上显示的属性从配置文件部分复制到属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="4a145-142">Call the profile section's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the properties that will appear on the property sheet from the profile section to the property data object.</span></span> 
    
4. <span data-ttu-id="4a145-143">调用[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法, 以请求服务提供程序显示属性表, 并在_lpConfigData_参数中传递指向属性数据对象的指针。</span><span class="sxs-lookup"><span data-stu-id="4a145-143">Call the [IMAPISupport::DoConfigPropSheet](imapisupport-doconfigpropsheet.md) method to request that the service provider display a property sheet, and pass a pointer to the property data object in the  _lpConfigData_ parameter.</span></span> 
    
5. <span data-ttu-id="4a145-144">当用户在属性表中保存对配置属性所做的更改时, 调用[IMAPIProp:: CopyTo](imapiprop-copyto.md)方法将属性数据对象中的属性复制回 "配置文件" 部分。</span><span class="sxs-lookup"><span data-stu-id="4a145-144">When the user saves changes to configuration properties in the property sheet, call the [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the properties from the property data object back to the profile section.</span></span> 
    
<span data-ttu-id="4a145-145">与其他对象不同, 配置文件节不支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="4a145-145">Profile sections, unlike other objects, do not support named properties.</span></span> <span data-ttu-id="4a145-146">如果在 profile 节对象上调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)和[IMAPIProp:: GetNamesFromIDs](imapiprop-getnamesfromids.md)方法, 则将返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="4a145-146">The [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) and [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) methods return MAPI_E_NO_SUPPORT if they are called on a profile section object.</span></span> <span data-ttu-id="4a145-147">如果使用[IMAPIProp:: SetProps](imapiprop-setprops.md)方法在0x8000 上方的范围中设置属性标识符, 则将返回 PT_ERROR 属性类型。</span><span class="sxs-lookup"><span data-stu-id="4a145-147">If you use the [IMAPIProp::SetProps](imapiprop-setprops.md) method to set property identifiers in the range above 0x8000, the PT_ERROR property type will be returned.</span></span> 
  
<span data-ttu-id="4a145-148">配置文件节为安全属性保留0x67F0 到0x67FF 的标识符范围。</span><span class="sxs-lookup"><span data-stu-id="4a145-148">Profile sections reserve the identifier range 0x67F0 to 0x67FF for secure properties.</span></span> <span data-ttu-id="4a145-149">服务提供程序可以使用此范围来存储密码和其他特定于提供程序的凭据。</span><span class="sxs-lookup"><span data-stu-id="4a145-149">Service providers can use this range to store passwords and other provider-specific credentials.</span></span> <span data-ttu-id="4a145-150">如果在[IMAPIProp:: GetProps](imapiprop-getprops.md)方法的_lpPropTag_参数中传递 NULL 时, 不会在属性的完整列表中返回此范围中的属性, 也不会在该范围的_lppPropTagArray_参数[中返回这些属性。IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4a145-150">Properties in this range are not returned in the complete list of properties when NULL is passed in the  _lpPropTag_ parameter of the [IMAPIProp::GetProps](imapiprop-getprops.md) method, nor are they returned in the  _lppPropTagArray_ parameter of the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> <span data-ttu-id="4a145-151">安全属性必须由其标识符专门请求。</span><span class="sxs-lookup"><span data-stu-id="4a145-151">Secure properties must be requested specifically by their identifiers.</span></span> 
  
<span data-ttu-id="4a145-152">MAPI 提供使用硬编码常量 MUID_PROFILE_INSTANCE 作为其单个属性的标识符和**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 作为配置文件节。</span><span class="sxs-lookup"><span data-stu-id="4a145-152">MAPI furnishes a profile section with the hard-coded constant MUID_PROFILE_INSTANCE as its identifier and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) as its single property.</span></span> <span data-ttu-id="4a145-153">MAPI 可确保所有创建的配置文件中的**PR_SEARCH_KEY**属性值都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="4a145-153">MAPI ensures that the **PR_SEARCH_KEY** property value will be unique among all created profiles.</span></span> <span data-ttu-id="4a145-154">如果唯一性非常重要, 则使用**PR_SEARCH_KEY**而不是**PR_PROFILE_NAME** , 因为可能会有一个已删除的配置文件后跟另一个具有相同名称的配置文件。</span><span class="sxs-lookup"><span data-stu-id="4a145-154">Use **PR_SEARCH_KEY** instead of **PR_PROFILE_NAME** when uniqueness is important, because it is possible for a deleted profile to be followed by another profile with the same name.</span></span> 
  
<span data-ttu-id="4a145-155">有关如何使用配置文件节的详细信息, 请参阅[管理配置文件和邮件服务](administering-profiles-and-message-services.md)。</span><span class="sxs-lookup"><span data-stu-id="4a145-155">For more information about how to use profile sections, see [Administering Profiles and Message Services](administering-profiles-and-message-services.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4a145-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a145-156">See also</span></span>



[<span data-ttu-id="4a145-157">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="4a145-157">MAPI Interfaces</span></span>](mapi-interfaces.md)

