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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32331267"
---
# <a name="acting-as-a-host-address-book-provider"></a><span data-ttu-id="931da-103">充当主机通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="931da-103">Acting as a Host Address Book Provider</span></span>

  
  
<span data-ttu-id="931da-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="931da-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="931da-105">主机提供程序是一个通讯簿提供程序, 其中包含来自其容器中的其他提供程序的收件人, 并依赖其他提供程序的收件人实现以部分控制其维护。</span><span class="sxs-lookup"><span data-stu-id="931da-105">A host provider is an address book provider that includes recipients from other providers in its containers and relies on the implementation of the recipients by the other providers to partially control their maintenance.</span></span> <span data-ttu-id="931da-106">主机提供程序使用这些外部收件人的模板标识符将这些收件人的数据绑定到外部提供程序中的代码。</span><span class="sxs-lookup"><span data-stu-id="931da-106">A host provider uses the template identifiers of these foreign recipients to bind the data for these recipients to code in the foreign provider.</span></span> <span data-ttu-id="931da-107">当提供程序检索收件人的**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性并将其传递到[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)的调用中时, 将启动此绑定过程。</span><span class="sxs-lookup"><span data-stu-id="931da-107">This binding process is initiated when your provider retrieves the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property of a recipient and passes it in a call to [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md).</span></span> 
  
<span data-ttu-id="931da-108">当提供程序调用**IMAPISupport:: OpenTemplateID**时, MAPI 会将模板标识符中的**MAPIUID**与提供程序注册的**MAPIUID**进行匹配, 并调用提供程序的[IABLogon:: OpenTemplateID](iablogon-opentemplateid.md)方法。</span><span class="sxs-lookup"><span data-stu-id="931da-108">When your provider calls **IMAPISupport::OpenTemplateID**, MAPI matches the **MAPIUID** within the template identifier with a **MAPIUID** registered by a provider and calls the provider's [IABLogon::OpenTemplateID](iablogon-opentemplateid.md) method.</span></span> <span data-ttu-id="931da-109">外部提供程序可能返回指向提供程序的 property 对象的指针、其自己的 property 对象实现或包装提供程序对象的实现。</span><span class="sxs-lookup"><span data-stu-id="931da-109">The foreign provider might return a pointer to your provider's property object, to its own property object implementation, or to an implementation that wraps your provider's object.</span></span> <span data-ttu-id="931da-110">返回的指针放置在_lppMAPIPropNew_参数的内容中。</span><span class="sxs-lookup"><span data-stu-id="931da-110">The returned pointer is placed in the contents of the  _lppMAPIPropNew_ parameter.</span></span> 
  
<span data-ttu-id="931da-111">提供程序可以选择是否调用**IMAPISupport:: OpenTemplateID**和 FILL_ENTRY 标志集。</span><span class="sxs-lookup"><span data-stu-id="931da-111">Your provider can choose whether or not to call **IMAPISupport::OpenTemplateID** with the FILL_ENTRY flag set.</span></span> <span data-ttu-id="931da-112">在创建收件人时或在你的提供程序刷新收件人的属性后经过较长时间时, 请设置此标志。</span><span class="sxs-lookup"><span data-stu-id="931da-112">Set this flag when the recipient is being created or when a long time has passed since your provider has refreshed the recipient's properties.</span></span> <span data-ttu-id="931da-113">FILL_ENTRY 标志的常见用途是使提供程序中的收件人与原始的同步。</span><span class="sxs-lookup"><span data-stu-id="931da-113">A common use of the FILL_ENTRY flag is to keep a recipient in your provider synchronized with the original.</span></span> <span data-ttu-id="931da-114">实现此类型的同步计划可提高性能。</span><span class="sxs-lookup"><span data-stu-id="931da-114">Implementing this type of synchronization schedule enhances performance.</span></span> 
  
 <span data-ttu-id="931da-115">**保持外部收件人同步**</span><span class="sxs-lookup"><span data-stu-id="931da-115">**To keep a foreign recipient synchronized**</span></span>
  
1. <span data-ttu-id="931da-116">确定定期更新的适当时间间隔。</span><span class="sxs-lookup"><span data-stu-id="931da-116">Determine an appropriate interval for periodic updates.</span></span> 
    
2. <span data-ttu-id="931da-117">对[IMAPISupport:: OpenTemplateID](imapisupport-opentemplateid.md)的每个调用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="931da-117">Timestamp each call to [IMAPISupport::OpenTemplateID](imapisupport-opentemplateid.md).</span></span> 
    
3. <span data-ttu-id="931da-118">评估是否有必要根据自上次呼叫后过期的时间量来执行完全更新。</span><span class="sxs-lookup"><span data-stu-id="931da-118">Evaluate whether or not it is necessary to perform a full update based on the amount of time that has expired since the last call.</span></span> <span data-ttu-id="931da-119">如果需要进行完全更新, 请使用 FILL_ENTRY 标志调用**IMAPISupport:: OpenTemplateID** 。</span><span class="sxs-lookup"><span data-stu-id="931da-119">If a full update is necessary, call **IMAPISupport::OpenTemplateID** with the FILL_ENTRY flag.</span></span> <span data-ttu-id="931da-120">如果不需要, 请不要在呼叫中设置标志。</span><span class="sxs-lookup"><span data-stu-id="931da-120">If it is not necessary, do not set the flag on the call.</span></span> 
    
<span data-ttu-id="931da-121">当客户端发出请求复制的收件人的属性之一时, 提供程序可以选择是处理请求本身还是使用外部提供程序提供的代码。</span><span class="sxs-lookup"><span data-stu-id="931da-121">When a client makes a request for one of the copied recipient's properties, your provider can choose whether to handle the request itself or use the code supplied by the foreign provider.</span></span> <span data-ttu-id="931da-122">提供程序可以预期外部提供程序截获对**IMAPIProp**的大部分 (如果不是) 调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)除外。</span><span class="sxs-lookup"><span data-stu-id="931da-122">Your provider can expect the foreign provider to intercept most, if not all, calls to **IMAPIProp** except for [IMAPIProp::OpenProperty](imapiprop-openproperty.md).</span></span> <span data-ttu-id="931da-123">对**OpenProperty**请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性的调用将始终转发给提供程序。</span><span class="sxs-lookup"><span data-stu-id="931da-123">A call to **OpenProperty** requesting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property is always forwarded to your provider.</span></span>
  
 <span data-ttu-id="931da-124">**访问模板标识符代码**</span><span class="sxs-lookup"><span data-stu-id="931da-124">**To access template identifier code**</span></span>
  
1. <span data-ttu-id="931da-125">打开收件人并调用其[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索**PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="931da-125">Open the recipient and call its [IMAPIProp::GetProps](imapiprop-getprops.md) method to retrieve the **PR_TEMPLATEID** ([PidTagTemplateid](pidtagtemplateid-canonical-property.md)) property.</span></span> <span data-ttu-id="931da-126">如果**GetProps**因**PR_TEMPLATEID**不可用而失败, 则外部提供程序不支持此收件人的模板标识符和相关代码。</span><span class="sxs-lookup"><span data-stu-id="931da-126">If **GetProps** fails because **PR_TEMPLATEID** is unavailable, the foreign provider does not support a template identifier and related code for this recipient.</span></span> <span data-ttu-id="931da-127">提供程序将需要对所有维护使用其收件人实现。</span><span class="sxs-lookup"><span data-stu-id="931da-127">Your provider will need to use its implementation of the recipient for all maintenance.</span></span> 
    
2. <span data-ttu-id="931da-128">如果从**GetProps**返回模板标识符, 则将其传递, 并在调用**IMAPISupport:: OpenTemplateID**方法时, 将指针传递给收件人的**IMAPIProp**实现。</span><span class="sxs-lookup"><span data-stu-id="931da-128">If the template identifier is returned from **GetProps**, pass it and a pointer to the recipient's **IMAPIProp** implementation in a call to the **IMAPISupport::OpenTemplateID** method.</span></span> <span data-ttu-id="931da-129">如果大多数或所有收件人的属性需要更新, 如创建时或尚未更新一段时间, 则设置 FILL_ENTRY 标志。</span><span class="sxs-lookup"><span data-stu-id="931da-129">Set the FILL_ENTRY flag if most or all of the recipient's properties need to be updated, such as at creation time or if they have not been updated for a while.</span></span> 
    
3. <span data-ttu-id="931da-130">如果**OpenTemplateID**返回外部提供程序的**IMAPIProp**实现, 则向客户端返回指向此实现的指针。</span><span class="sxs-lookup"><span data-stu-id="931da-130">If **OpenTemplateID** returns the foreign provider's **IMAPIProp** implementation, return to the client a pointer to this implementation.</span></span> 
    
4. <span data-ttu-id="931da-131">如果**OpenTemplateID**不返回实现, 通常是因为外部提供程序不在配置文件中, 请将指向提供程序的**IMAPIProp**实现的指针返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="931da-131">If **OpenTemplateID** does not return an implementation, typically because the foreign provider is not in the profile, return to the client a pointer to your provider's **IMAPIProp** implementation.</span></span> <span data-ttu-id="931da-132">客户端应能够使用任意一个接口处理对象的属性。</span><span class="sxs-lookup"><span data-stu-id="931da-132">The client should be able to work with the object's properties using either interface.</span></span> 
    

