---
title: 充当主机通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f06a1034-ee49-4a09-831e-9752713228a8
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 202d4b4391de7553e39e50dc527df5502ebcefb3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406463"
---
# <a name="acting-as-a-host-address-book-provider"></a><span data-ttu-id="d707e-103">充当主机通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="d707e-103">Acting as a Host Address Book Provider</span></span>

  
  
<span data-ttu-id="d707e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d707e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d707e-105">宿主提供程序是一个通讯簿提供程序，其中包含来自其容器中的其他提供程序的收件人，并且依靠其他提供程序的收件人实现来部分控制其维护。</span><span class="sxs-lookup"><span data-stu-id="d707e-105">A host provider is an address book provider that includes recipients from other providers in its containers and relies on the implementation of the recipients by the other providers to partially control their maintenance.</span></span> <span data-ttu-id="d707e-106">宿主提供商使用这些外收件人的模板标识符，将这些收件人的数据绑定到该外提供程序中的代码。</span><span class="sxs-lookup"><span data-stu-id="d707e-106">A host provider uses the template identifiers of these foreign recipients to bind the data for these recipients to code in the foreign provider.</span></span> <span data-ttu-id="d707e-107">当提供程序检索收件人的 **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性，并传递给 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md)的调用时，将启动此绑定过程。</span><span class="sxs-lookup"><span data-stu-id="d707e-107">This binding process is initiated when your provider retrieves the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property of a recipient and passes it in a call to [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md).</span></span> 
  
<span data-ttu-id="d707e-108">当提供程序调用 **IMAPISupport：：OpenTemplateID** 时，MAPI 与模板标识符中的 **MAPIUID** 与提供程序注册的 **MAPIUID** 匹配，并调用提供程序的 [IABLogon：：OpenTemplateID](iablogon-opentemplateid.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="d707e-108">When your provider calls **IMAPISupport::OpenTemplateID**, MAPI matches the **MAPIUID** within the template identifier with a **MAPIUID** registered by a provider and calls the provider's [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="d707e-109">该外提供程序可能会返回一个指针，指向提供程序的属性对象、它自己的属性对象实现或包装提供程序对象的实现。</span><span class="sxs-lookup"><span data-stu-id="d707e-109">The foreign provider might return a pointer to your provider's property object, to its own property object implementation, or to an implementation that wraps your provider's object.</span></span> <span data-ttu-id="d707e-110">返回的指针放置在  _lppMAPIPropNew_ 参数的内容中。</span><span class="sxs-lookup"><span data-stu-id="d707e-110">The returned pointer is placed in the contents of the  _lppMAPIPropNew_ parameter.</span></span> 
  
<span data-ttu-id="d707e-111">您的提供程序可以选择是否调用 **IMAPISupport：：OpenTemplateID，FILL_ENTRY** 设置。</span><span class="sxs-lookup"><span data-stu-id="d707e-111">Your provider can choose whether or not to call **IMAPISupport::OpenTemplateID** with the FILL_ENTRY flag set.</span></span> <span data-ttu-id="d707e-112">创建收件人时或在提供程序刷新收件人属性后经过很长时间后设置此标志。</span><span class="sxs-lookup"><span data-stu-id="d707e-112">Set this flag when the recipient is being created or when a long time has passed since your provider has refreshed the recipient's properties.</span></span> <span data-ttu-id="d707e-113">该标志的FILL_ENTRY是使提供程序中的收件人与原始收件人保持同步。</span><span class="sxs-lookup"><span data-stu-id="d707e-113">A common use of the FILL_ENTRY flag is to keep a recipient in your provider synchronized with the original.</span></span> <span data-ttu-id="d707e-114">实现此类型的同步计划可提高性能。</span><span class="sxs-lookup"><span data-stu-id="d707e-114">Implementing this type of synchronization schedule enhances performance.</span></span> 
  
 <span data-ttu-id="d707e-115">**保持外收件人同步**</span><span class="sxs-lookup"><span data-stu-id="d707e-115">**To keep a foreign recipient synchronized**</span></span>
  
1. <span data-ttu-id="d707e-116">确定定期更新的适当间隔。</span><span class="sxs-lookup"><span data-stu-id="d707e-116">Determine an appropriate interval for periodic updates.</span></span> 
    
2. <span data-ttu-id="d707e-117">每次调用 [IMAPISupport：：OpenTemplateID](imapisupport-opentemplateid.md)的时间戳。</span><span class="sxs-lookup"><span data-stu-id="d707e-117">Timestamp each call to [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md).</span></span> 
    
3. <span data-ttu-id="d707e-118">根据自上次调用以来的到期时间，评估是否需要执行完整更新。</span><span class="sxs-lookup"><span data-stu-id="d707e-118">Evaluate whether or not it is necessary to perform a full update based on the amount of time that has expired since the last call.</span></span> <span data-ttu-id="d707e-119">如果需要完整更新，请调用具有 FILL_ENTRY 标志的 **IMAPISupport：：OpenTemplateID。**</span><span class="sxs-lookup"><span data-stu-id="d707e-119">If a full update is necessary, call **IMAPISupport::OpenTemplateID** with the FILL_ENTRY flag.</span></span> <span data-ttu-id="d707e-120">如果没有必要，请不要在调用上设置 标志。</span><span class="sxs-lookup"><span data-stu-id="d707e-120">If it is not necessary, do not set the flag on the call.</span></span> 
    
<span data-ttu-id="d707e-121">当客户端对复制的收件人的属性之一提出请求时，您的提供商可以选择是处理请求本身，还是使用由外提供程序提供的代码。</span><span class="sxs-lookup"><span data-stu-id="d707e-121">When a client makes a request for one of the copied recipient's properties, your provider can choose whether to handle the request itself or use the code supplied by the foreign provider.</span></span> <span data-ttu-id="d707e-122">除了 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md)之外，你的提供程序可以预期外提供商会截取大部分（如果不是全部 **）IMAPIProp** 调用。</span><span class="sxs-lookup"><span data-stu-id="d707e-122">Your provider can expect the foreign provider to intercept most, if not all, calls to **IMAPIProp** except for [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="d707e-123">始终将调用 **OpenProperty** PR_DETAILS_TABLE ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性转发到提供程序。 </span><span class="sxs-lookup"><span data-stu-id="d707e-123">A call to **OpenProperty** requesting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property is always forwarded to your provider.</span></span>
  
 <span data-ttu-id="d707e-124">**访问模板标识符代码**</span><span class="sxs-lookup"><span data-stu-id="d707e-124">**To access template identifier code**</span></span>
  
1. <span data-ttu-id="d707e-125">打开收件人并调用其[IMAPIProp：：GetProps](imapiprop-getprops.md)方法来检索PR_TEMPLATEID ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d707e-125">Open the recipient and call its [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property.</span></span> <span data-ttu-id="d707e-126">如果 **GetProps** 因PR_TEMPLATEID不可用而失败，则外提供程序不支持此收件人的模板标识符和相关代码。</span><span class="sxs-lookup"><span data-stu-id="d707e-126">If **GetProps** fails because **PR_TEMPLATEID** is unavailable, the foreign provider does not support a template identifier and related code for this recipient.</span></span> <span data-ttu-id="d707e-127">您的提供商将需要使用其收件人实现进行所有维护。</span><span class="sxs-lookup"><span data-stu-id="d707e-127">Your provider will need to use its implementation of the recipient for all maintenance.</span></span> 
    
2. <span data-ttu-id="d707e-128">如果从 **GetProps** 返回模板标识符，请传递该标识符，并通过调用 **IMAPISupport：：OpenTemplateID** 方法，将指针传递给收件人的 **IMAPIProp** 实现。</span><span class="sxs-lookup"><span data-stu-id="d707e-128">If the template identifier is returned from **GetProps**, pass it and a pointer to the recipient's **IMAPIProp** implementation in a call to the **IMAPISupport::OpenTemplateID** method.</span></span> <span data-ttu-id="d707e-129">如果FILL_ENTRY或所有收件人的属性需要更新（例如创建时或一段时间尚未更新这些属性）时，请设置此标志。</span><span class="sxs-lookup"><span data-stu-id="d707e-129">Set the FILL_ENTRY flag if most or all of the recipient's properties need to be updated, such as at creation time or if they have not been updated for a while.</span></span> 
    
3. <span data-ttu-id="d707e-130">如果 **OpenTemplateID** 返回了外提供程序的 **IMAPIProp** 实现，则向客户端返回指向此实现的指针。</span><span class="sxs-lookup"><span data-stu-id="d707e-130">If **OpenTemplateID** returns the foreign provider's **IMAPIProp** implementation, return to the client a pointer to this implementation.</span></span> 
    
4. <span data-ttu-id="d707e-131">如果 **OpenTemplateID** 不返回实现（通常是因为外提供程序不在配置文件中）则向客户端返回指向提供程序 **的 IMAPIProp** 实现指针。</span><span class="sxs-lookup"><span data-stu-id="d707e-131">If **OpenTemplateID** does not return an implementation, typically because the foreign provider is not in the profile, return to the client a pointer to your provider's **IMAPIProp** implementation.</span></span> <span data-ttu-id="d707e-132">客户端应该能够使用任一接口处理对象的属性。</span><span class="sxs-lookup"><span data-stu-id="d707e-132">The client should be able to work with the object's properties using either interface.</span></span> 
    

