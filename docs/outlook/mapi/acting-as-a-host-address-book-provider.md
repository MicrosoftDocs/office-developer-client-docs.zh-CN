---
title: 充当主机通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f06a1034-ee49-4a09-831e-9752713228a8
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: de0acb88eee6addc0347f5281e5fbe5070bad0a4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595404"
---
# <a name="acting-as-a-host-address-book-provider"></a><span data-ttu-id="0e433-103">充当主机通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="0e433-103">Acting as a Host Address Book Provider</span></span>

  
  
<span data-ttu-id="0e433-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0e433-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0e433-105">宿主提供程序是通讯簿提供程序，包括其容器中的其他提供程序的收件人，并依赖于由其他提供程序部分控制其维护的收件人的实现。</span><span class="sxs-lookup"><span data-stu-id="0e433-105">A host provider is an address book provider that includes recipients from other providers in its containers and relies on the implementation of the recipients by the other providers to partially control their maintenance.</span></span> <span data-ttu-id="0e433-106">宿主提供程序使用这些外的收件人的模板的标识符将这些收件人数据绑定到外的提供程序中的代码。</span><span class="sxs-lookup"><span data-stu-id="0e433-106">A host provider uses the template identifiers of these foreign recipients to bind the data for these recipients to code in the foreign provider.</span></span> <span data-ttu-id="0e433-107">您的提供商检索收件人的**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性，并将其传递[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)将调用时启动此绑定进程。</span><span class="sxs-lookup"><span data-stu-id="0e433-107">This binding process is initiated when your provider retrieves the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property of a recipient and passes it in a call to [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md).</span></span> 
  
<span data-ttu-id="0e433-108">当您提供程序调用**IMAPISupport::OpenTemplateID**，MAPI 匹配**MAPIUID**内时与**MAPIUID**模板标识符由提供程序注册，并调用提供程序的[IABLogon::OpenTemplateID](iablogon-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="0e433-108">When your provider calls **IMAPISupport::OpenTemplateID**, MAPI matches the **MAPIUID** within the template identifier with a **MAPIUID** registered by a provider and calls the provider's [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="0e433-109">外的提供程序可能会返回一个指针到提供程序的属性对象，它自己属性的对象实现，或实现的换行提供程序的对象。</span><span class="sxs-lookup"><span data-stu-id="0e433-109">The foreign provider might return a pointer to your provider's property object, to its own property object implementation, or to an implementation that wraps your provider's object.</span></span> <span data-ttu-id="0e433-110">返回的指针放在_lppMAPIPropNew_参数的内容。</span><span class="sxs-lookup"><span data-stu-id="0e433-110">The returned pointer is placed in the contents of the  _lppMAPIPropNew_ parameter.</span></span> 
  
<span data-ttu-id="0e433-111">您的提供商可以选择设置了 FILL_ENTRY 标志呼叫**IMAPISupport::OpenTemplateID** 。</span><span class="sxs-lookup"><span data-stu-id="0e433-111">Your provider can choose whether or not to call **IMAPISupport::OpenTemplateID** with the FILL_ENTRY flag set.</span></span> <span data-ttu-id="0e433-112">正在创建收件人或您的提供商已刷新收件人的属性以来已通过很长时间时，请设置此标志。</span><span class="sxs-lookup"><span data-stu-id="0e433-112">Set this flag when the recipient is being created or when a long time has passed since your provider has refreshed the recipient's properties.</span></span> <span data-ttu-id="0e433-113">常用 FILL_ENTRY 标志是保留与原始同步您提供程序中的收件人。</span><span class="sxs-lookup"><span data-stu-id="0e433-113">A common use of the FILL_ENTRY flag is to keep a recipient in your provider synchronized with the original.</span></span> <span data-ttu-id="0e433-114">实现此类型的同步计划增强了性能。</span><span class="sxs-lookup"><span data-stu-id="0e433-114">Implementing this type of synchronization schedule enhances performance.</span></span> 
  
 <span data-ttu-id="0e433-115">**若要保留外的收件人同步**</span><span class="sxs-lookup"><span data-stu-id="0e433-115">**To keep a foreign recipient synchronized**</span></span>
  
1. <span data-ttu-id="0e433-116">确定适当的时间间隔定期更新。</span><span class="sxs-lookup"><span data-stu-id="0e433-116">Determine an appropriate interval for periodic updates.</span></span> 
    
2. <span data-ttu-id="0e433-117">时间戳每个呼叫[IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md)。</span><span class="sxs-lookup"><span data-stu-id="0e433-117">Timestamp each call to [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md).</span></span> 
    
3. <span data-ttu-id="0e433-118">评估需要执行完全更新基于上次调用已过期的时间量。</span><span class="sxs-lookup"><span data-stu-id="0e433-118">Evaluate whether or not it is necessary to perform a full update based on the amount of time that has expired since the last call.</span></span> <span data-ttu-id="0e433-119">如果需要完全更新，则呼叫**IMAPISupport::OpenTemplateID** FILL_ENTRY 标志。</span><span class="sxs-lookup"><span data-stu-id="0e433-119">If a full update is necessary, call **IMAPISupport::OpenTemplateID** with the FILL_ENTRY flag.</span></span> <span data-ttu-id="0e433-120">如果不是必需的则不要在调用设置标志。</span><span class="sxs-lookup"><span data-stu-id="0e433-120">If it is not necessary, do not set the flag on the call.</span></span> 
    
<span data-ttu-id="0e433-121">当客户端请求复制的收件人的属性之一，您的提供商可以选择是否处理请求本身或使用外的提供商所提供的代码。</span><span class="sxs-lookup"><span data-stu-id="0e433-121">When a client makes a request for one of the copied recipient's properties, your provider can choose whether to handle the request itself or use the code supplied by the foreign provider.</span></span> <span data-ttu-id="0e433-122">您的提供商可以预期外的提供程序以截获最，如果不是所有，呼叫到**IMAPIProp** [IMAPIProp::OpenProperty](imapiprop-openproperty.md)除外。</span><span class="sxs-lookup"><span data-stu-id="0e433-122">Your provider can expect the foreign provider to intercept most, if not all, calls to **IMAPIProp** except for [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="0e433-123">调用**OpenProperty**请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性始终被转接到您的提供商。</span><span class="sxs-lookup"><span data-stu-id="0e433-123">A call to **OpenProperty** requesting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property is always forwarded to your provider.</span></span>
  
 <span data-ttu-id="0e433-124">**若要访问模板标识符代码**</span><span class="sxs-lookup"><span data-stu-id="0e433-124">**To access template identifier code**</span></span>
  
1. <span data-ttu-id="0e433-125">打开收件人，并调用其[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0e433-125">Open the recipient and call its [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property.</span></span> <span data-ttu-id="0e433-126">如果**GetProps**失败，因为**PR_TEMPLATEID**不可用外的提供程序不支持的模板标识符和相关的代码的此收件人。</span><span class="sxs-lookup"><span data-stu-id="0e433-126">If **GetProps** fails because **PR_TEMPLATEID** is unavailable, the foreign provider does not support a template identifier and related code for this recipient.</span></span> <span data-ttu-id="0e433-127">您的提供商需要收件人其实现用于所有维护。</span><span class="sxs-lookup"><span data-stu-id="0e433-127">Your provider will need to use its implementation of the recipient for all maintenance.</span></span> 
    
2. <span data-ttu-id="0e433-128">如果从**GetProps**返回模板标识符，将其和指针传递给**IMAPISupport::OpenTemplateID**方法调用中的收件人的**IMAPIProp**实现。</span><span class="sxs-lookup"><span data-stu-id="0e433-128">If the template identifier is returned from **GetProps**, pass it and a pointer to the recipient's **IMAPIProp** implementation in a call to the **IMAPISupport::OpenTemplateID** method.</span></span> <span data-ttu-id="0e433-129">如果需要最或所有收件人的属性设置 FILL_ENTRY 标志更新，例如，在创建时间或如果其尚未更新一段。</span><span class="sxs-lookup"><span data-stu-id="0e433-129">Set the FILL_ENTRY flag if most or all of the recipient's properties need to be updated, such as at creation time or if they have not been updated for a while.</span></span> 
    
3. <span data-ttu-id="0e433-130">如果**OpenTemplateID**返回外的提供程序**IMAPIProp**实现，返回到客户端指向此实现的指针。</span><span class="sxs-lookup"><span data-stu-id="0e433-130">If **OpenTemplateID** returns the foreign provider's **IMAPIProp** implementation, return to the client a pointer to this implementation.</span></span> 
    
4. <span data-ttu-id="0e433-131">如果**OpenTemplateID**不会返回实现，通常因为外的提供程序不在配置文件中，返回到客户端提供商的**IMAPIProp**实现的指针。</span><span class="sxs-lookup"><span data-stu-id="0e433-131">If **OpenTemplateID** does not return an implementation, typically because the foreign provider is not in the profile, return to the client a pointer to your provider's **IMAPIProp** implementation.</span></span> <span data-ttu-id="0e433-132">客户端应该能够处理使用任一接口的对象的属性。</span><span class="sxs-lookup"><span data-stu-id="0e433-132">The client should be able to work with the object's properties using either interface.</span></span> 
    

