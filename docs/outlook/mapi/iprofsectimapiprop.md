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
# <a name="iprofsect--imapiprop"></a><span data-ttu-id="b6ee1-103">IProfSect : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="b6ee1-103">IProfSect : IMAPIProp</span></span>

  
  
<span data-ttu-id="b6ee1-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6ee1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6ee1-105">使用配置文件节对象的属性。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-105">Works with the properties of profile section objects.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b6ee1-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-106">Header file:</span></span>  <br/> |<span data-ttu-id="b6ee1-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="b6ee1-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="b6ee1-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="b6ee1-109">配置文件节对象</span><span class="sxs-lookup"><span data-stu-id="b6ee1-109">Profile section objects</span></span>  <br/> |
|<span data-ttu-id="b6ee1-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="b6ee1-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="b6ee1-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="b6ee1-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-112">Called by:</span></span>  <br/> |<span data-ttu-id="b6ee1-113">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="b6ee1-113">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="b6ee1-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="b6ee1-115">IID_IProfSect</span><span class="sxs-lookup"><span data-stu-id="b6ee1-115">IID_IProfSect</span></span>  <br/> |
|<span data-ttu-id="b6ee1-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="b6ee1-117">LPPROFSECT</span><span class="sxs-lookup"><span data-stu-id="b6ee1-117">LPPROFSECT</span></span>  <br/> |
|<span data-ttu-id="b6ee1-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="b6ee1-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="b6ee1-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="b6ee1-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="b6ee1-120">Vtable order</span></span>

<span data-ttu-id="b6ee1-121">此接口没有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-121">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="b6ee1-122">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="b6ee1-122">**Required properties**</span></span>|<span data-ttu-id="b6ee1-123">**Access**</span><span class="sxs-lookup"><span data-stu-id="b6ee1-123">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6ee1-124">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b6ee1-124">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b6ee1-125">只读</span><span class="sxs-lookup"><span data-stu-id="b6ee1-125">Read-only</span></span>  <br/> |
|<span data-ttu-id="b6ee1-126">**PR_PROFILE_NAME (** [PidTagProfileName](pidtagprofilename-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b6ee1-126">**PR_PROFILE_NAME** ([PidTagProfileName](pidtagprofilename-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b6ee1-127">只读</span><span class="sxs-lookup"><span data-stu-id="b6ee1-127">Read-only</span></span>  <br/> |
   
## <a name="notes-to-callers"></a><span data-ttu-id="b6ee1-128">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="b6ee1-128">Notes to callers</span></span>

<span data-ttu-id="b6ee1-129">**IProfSect** 接口没有其自己的任何唯一方法，但您可以调用配置文件节的 [IMAPIProp](imapipropiunknown.md)方法。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-129">The **IProfSect** interface does not have any unique methods of its own, but you can call the profile section's [IMAPIProp](imapipropiunknown.md) methods.</span></span> <span data-ttu-id="b6ee1-130">**IProfSect** 实现与 **IMAPIProp** 的其他实现之间存在一些差异：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-130">There are some differences between the **IProfSect** implementation and other implementations of **IMAPIProp**:</span></span>
  
- <span data-ttu-id="b6ee1-131">**IProfSect** 不支持事务模型。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-131">**IProfSect** does not support a transaction model.</span></span> 
    
- <span data-ttu-id="b6ee1-132">**IProfSect** 不支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-132">**IProfSect** does not support named properties.</span></span> 
    
- <span data-ttu-id="b6ee1-133">**IProfSect** 保留标识符0x67F0 0x67ff安全属性。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-133">**IProfSect** reserves the identifier range 0x67F0 to 0x67ff for secure properties.</span></span> 
    
<span data-ttu-id="b6ee1-134">不支持事务模型意味着调用 [IMAPIProp：：CopyProps](imapiprop-copyprops.md) 和 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法后对配置文件节进行的所有更改会立即发生。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-134">Not supporting a transaction model means that all changes that were made to a profile section following calls to the [IMAPIProp::CopyProps](imapiprop-copyprops.md) and [IMAPIProp::CopyTo](imapiprop-copyto.md) methods occur immediately.</span></span> <span data-ttu-id="b6ee1-135">对 [IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法的调用成功，但实际上并未保存任何更改。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-135">Calls to the [IMAPIProp::SaveChanges](imapiprop-savechanges.md) method succeed but do not actually save any changes.</span></span> 
  
<span data-ttu-id="b6ee1-136">若要防止提前更改，服务提供商需要复制其配置文件部分，这些部分通过属性表显示给用户。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-136">To be protected from changes that occur prematurely, service providers need to make copies of their profile sections that are displayed to users through property sheets.</span></span> <span data-ttu-id="b6ee1-137">属性表应处理副本，而不是实际配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-137">The property sheets should work with the copy, instead of the real profile section.</span></span> <span data-ttu-id="b6ee1-138">当用户单击" **确定"** 按钮以验证更改是否准确时，可以将更改保存到真实的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-138">When the user clicks the **OK** button to verify that the changes are accurate, the changes can be saved to the real profile section.</span></span> 
  
<span data-ttu-id="b6ee1-139">若要使用属性表配置文件部分实现一个配置文件，请使用以下过程：</span><span class="sxs-lookup"><span data-stu-id="b6ee1-139">To implement a property sheet by using a copied profile section, use the following procedure:</span></span>
  
1. <span data-ttu-id="b6ee1-140">通过调用 [IMAPISupport：：OpenProfileSection](imapisupport-openprofilesection.md) 或 [IProviderAdmin：：OpenProfileSection](iprovideradmin-openprofilesection.md) 方法打开配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-140">Open the profile section by calling the [IMAPISupport::OpenProfileSection](imapisupport-openprofilesection.md) or [IProviderAdmin::OpenProfileSection](iprovideradmin-openprofilesection.md) method.</span></span> 
    
2. <span data-ttu-id="b6ee1-141">调用 [CreateIProp](createiprop.md) 函数以检索属性数据对象（支持 **IPropData 接口** 的对象）。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-141">Call the [CreateIProp](createiprop.md) function to retrieve a property data object — an object that supports the **IPropData** interface.</span></span> 
    
3. <span data-ttu-id="b6ee1-142">调用配置文件节的 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法，将出现在配置文件属性表上的属性复制到属性数据对象。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-142">Call the profile section's [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the properties that will appear on the property sheet from the profile section to the property data object.</span></span> 
    
4. <span data-ttu-id="b6ee1-143">调用 [IMAPISupport：:D oConfigPropSheet](imapisupport-doconfigpropsheet.md) 方法以请求服务提供商显示 属性表，并传递指向  _lpConfigData_ 参数中的属性数据对象的指针。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-143">Call the [IMAPISupport::DoConfigPropSheet](imapisupport-doconfigpropsheet.md) method to request that the service provider display a property sheet, and pass a pointer to the property data object in the  _lpConfigData_ parameter.</span></span> 
    
5. <span data-ttu-id="b6ee1-144">当用户在配置文件中保存对配置属性属性表，请调用 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 方法将属性从属性数据对象复制回配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-144">When the user saves changes to configuration properties in the property sheet, call the [IMAPIProp::CopyTo](imapiprop-copyto.md) method to copy the properties from the property data object back to the profile section.</span></span> 
    
<span data-ttu-id="b6ee1-145">配置文件节与其他对象不同，不支持命名属性。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-145">Profile sections, unlike other objects, do not support named properties.</span></span> <span data-ttu-id="b6ee1-146">如果对配置文件节对象调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 和 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md) 方法MAPI_E_NO_SUPPORT将返回值。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-146">The [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) and [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md) methods return MAPI_E_NO_SUPPORT if they are called on a profile section object.</span></span> <span data-ttu-id="b6ee1-147">如果使用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 方法设置上述 0x8000 范围中的属性标识符，PT_ERROR返回属性类型。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-147">If you use the [IMAPIProp::SetProps](imapiprop-setprops.md) method to set property identifiers in the range above 0x8000, the PT_ERROR property type will be returned.</span></span> 
  
<span data-ttu-id="b6ee1-148">配置文件部分保留标识符范围0x67F0 0x67FF安全属性。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-148">Profile sections reserve the identifier range 0x67F0 to 0x67FF for secure properties.</span></span> <span data-ttu-id="b6ee1-149">服务提供商可以使用此范围来存储密码和其他提供程序特定的凭据。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-149">Service providers can use this range to store passwords and other provider-specific credentials.</span></span> <span data-ttu-id="b6ee1-150">[在 IMAPIProp：：GetProps](imapiprop-getprops.md)方法的 _lpPropTag_ 参数中传递 NULL 时，不会在属性的完整列表中返回此范围中的属性，也不会在 [IMAPIProp：：GetPropList](imapiprop-getproplist.md)方法的 _lppPropTagArray_ 参数中返回这些属性。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-150">Properties in this range are not returned in the complete list of properties when NULL is passed in the  _lpPropTag_ parameter of the [IMAPIProp::GetProps](imapiprop-getprops.md) method, nor are they returned in the  _lppPropTagArray_ parameter of the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> <span data-ttu-id="b6ee1-151">安全属性必须由其标识符专门请求。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-151">Secure properties must be requested specifically by their identifiers.</span></span> 
  
<span data-ttu-id="b6ee1-152">MAPI 为配置文件节提供硬编码常量 MUID_PROFILE_INSTANCE 作为其标识符，PR_SEARCH_KEY ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 用作其单个属性。 </span><span class="sxs-lookup"><span data-stu-id="b6ee1-152">MAPI furnishes a profile section with the hard-coded constant MUID_PROFILE_INSTANCE as its identifier and **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) as its single property.</span></span> <span data-ttu-id="b6ee1-153">MAPI 确保PR_SEARCH_KEY **属性值在所有** 创建的配置文件中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-153">MAPI ensures that the **PR_SEARCH_KEY** property value will be unique among all created profiles.</span></span> <span data-ttu-id="b6ee1-154">如果 **PR_SEARCH_KEY** 唯 **一** PR_PROFILE_NAME，请使用"文件"，而不是"文件"，因为已删除的配置文件后面可以跟有同名的另一个配置文件。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-154">Use **PR_SEARCH_KEY** instead of **PR_PROFILE_NAME** when uniqueness is important, because it is possible for a deleted profile to be followed by another profile with the same name.</span></span> 
  
<span data-ttu-id="b6ee1-155">有关如何使用配置文件部分的信息，请参阅 [管理配置文件和邮件服务](administering-profiles-and-message-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b6ee1-155">For more information about how to use profile sections, see [Administering Profiles and Message Services](administering-profiles-and-message-services.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6ee1-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6ee1-156">See also</span></span>



[<span data-ttu-id="b6ee1-157">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="b6ee1-157">MAPI Interfaces</span></span>](mapi-interfaces.md)

