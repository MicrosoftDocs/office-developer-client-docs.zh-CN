---
title: 打开通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 017a62c0-49c6-47fb-acce-db58e6bb9cc5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6ebd6009700742e9b1159bc95ff0496c423e512c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422157"
---
# <a name="opening-address-book-entries"></a><span data-ttu-id="6c007-103">打开通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="6c007-103">Opening address book entries</span></span>

<span data-ttu-id="6c007-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6c007-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6c007-105">当客户端或提供程序请求打开某个对象时, MAPI 会调用您的提供程序的[IABLogon:: OpenEntry](iablogon-openentry.md)方法。</span><span class="sxs-lookup"><span data-stu-id="6c007-105">When a client or provider has requested that one of your objects be opened, MAPI calls your provider's [IABLogon::OpenEntry](iablogon-openentry.md) method.</span></span> <span data-ttu-id="6c007-106">MAPI 通过检查条目标识符的[MAPIUID](mapiuid.md)部分并将其与您的提供程序在调用\*\*\*\* **中注册的 MAPIUID 相匹配, 来确定表示目标对象是否属于您的提供程序的条目标识符。IMAPISupport:: SetProviderUID**。</span><span class="sxs-lookup"><span data-stu-id="6c007-106">MAPI determines that the entry identifier representing the target object belongs to your provider by examining the [MAPIUID](mapiuid.md) portion of the entry identifier and matching it to the **MAPIUID** that your provider registered in the call to **IMAPISupport::SetProviderUID**.</span></span> <span data-ttu-id="6c007-107">然后, MAPI 将调用您的**OpenEntry**方法。</span><span class="sxs-lookup"><span data-stu-id="6c007-107">MAPI then calls your **OpenEntry** method.</span></span> <span data-ttu-id="6c007-108">提供程序必须通过检索对应的对象 (容器、通讯组列表或邮件用户) 来做出响应。</span><span class="sxs-lookup"><span data-stu-id="6c007-108">Your provider must respond by retrieving the corresponding object — a container, distribution list, or messaging user.</span></span> 
  
<span data-ttu-id="6c007-109">空条目标识符指示打开通讯簿提供程序的根容器的请求。</span><span class="sxs-lookup"><span data-stu-id="6c007-109">A NULL entry identifier indicates a request to open the address book provider's root container.</span></span> <span data-ttu-id="6c007-110">客户端打开根容器以访问其层次结构表及其收件人。</span><span class="sxs-lookup"><span data-stu-id="6c007-110">Clients open the root container to access its hierarchy table and its recipients.</span></span> <span data-ttu-id="6c007-111">仅提供用于创建一次性收件人的模板的通讯簿提供程序不支持根容器的**OpenEntry**调用。</span><span class="sxs-lookup"><span data-stu-id="6c007-111">Address book providers that only supply templates for creating one-off recipients do not support the **OpenEntry** call for the root container.</span></span> 
  
### <a name="to-implement-iablogonopenentry"></a><span data-ttu-id="6c007-112">实现 IABLogon:: OpenEntry</span><span class="sxs-lookup"><span data-stu-id="6c007-112">To implement IABLogon::OpenEntry</span></span>
  
1. <span data-ttu-id="6c007-113">检查条目标识符是否为您的提供程序支持的有效标识符。</span><span class="sxs-lookup"><span data-stu-id="6c007-113">Check that the entry identifier is a valid identifier that your provider supports.</span></span> <span data-ttu-id="6c007-114">如果它不是有效的条目标识符, 则返回 MAPI_E_INVALID_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="6c007-114">If it is not a valid entry identifier, return MAPI_E_INVALID_ENTRYID.</span></span> 
    
2. <span data-ttu-id="6c007-115">检查使用_ulFlags_参数传入的标志。</span><span class="sxs-lookup"><span data-stu-id="6c007-115">Check the flag that is passed in with the  _ulFlags_ parameter.</span></span> <span data-ttu-id="6c007-116">如果 MAPI 已在 MAPI_MODIFY 中传递, 并且您的提供程序不允许对其对象进行修改, 则会失败并返回 MAPI_E_ACCESS_DENIED 错误值。</span><span class="sxs-lookup"><span data-stu-id="6c007-116">If MAPI has passed in MAPI_MODIFY and your provider does not allow its objects to be modified, fail and return the MAPI_E_ACCESS_DENIED error value.</span></span> 
    
3. <span data-ttu-id="6c007-117">检查_lpInterface_参数中请求的接口是否对您的提供程序要求打开的对象的类型有效。</span><span class="sxs-lookup"><span data-stu-id="6c007-117">Check that the interface requested in the  _lpInterface_ parameter is valid for the type of object your provider has been asked to open.</span></span> <span data-ttu-id="6c007-118">如果传入的参数无效, 则失败并返回 MAPI_E_INTERFACE_NOT_SUPPORTED 错误值。</span><span class="sxs-lookup"><span data-stu-id="6c007-118">If an invalid parameter has been passed in, fail and return the MAPI_E_INTERFACE_NOT_SUPPORTED error value.</span></span> 
    
4. <span data-ttu-id="6c007-119">如果_cbEntryID_参数为零, 则这是打开提供程序的根容器的请求。</span><span class="sxs-lookup"><span data-stu-id="6c007-119">If the  _cbEntryID_ parameter is zero, this is a request to open your provider's root container.</span></span> <span data-ttu-id="6c007-120">创建根容器, 并将指针返回到其**IABContainer**接口实现。</span><span class="sxs-lookup"><span data-stu-id="6c007-120">Create the root container and return a pointer to its **IABContainer** interface implementation.</span></span> 
    
5. <span data-ttu-id="6c007-121">如果提供程序实现了多个登录对象, 每个都有其自己的注册**MAPIUID**, 请使用相应的登录对象映射包含在条目标识符中的**MAPIUID** 。</span><span class="sxs-lookup"><span data-stu-id="6c007-121">If your provider implements several logon objects, each with its own registered **MAPIUID**, map the **MAPIUID** contained in the entry identifier with the appropriate logon object.</span></span> 
    
6. <span data-ttu-id="6c007-122">确定条目标识符表示的对象的类型: 邮件用户、通讯组列表或属于提供程序的容器或一个一次性邮件用户或通讯组列表, 以便可以为_lpulObjectType_设置适当的值。参数.</span><span class="sxs-lookup"><span data-stu-id="6c007-122">Determine which type of object the entry identifier represents: a messaging user, distribution list, or container belonging to your provider or a one-off messaging user or distribution list so that the appropriate value can be set for the  _lpulObjectType_ parameter.</span></span> 
    
7. <span data-ttu-id="6c007-123">创建适当类型的对象, 并设置以下基本属性:</span><span class="sxs-lookup"><span data-stu-id="6c007-123">Create the object of the appropriate type and set the following basic properties:</span></span>
    
    - <span data-ttu-id="6c007-124">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6c007-124">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    - <span data-ttu-id="6c007-125">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6c007-125">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    - <span data-ttu-id="6c007-126">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6c007-126">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    - <span data-ttu-id="6c007-127">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="6c007-127">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
8. <span data-ttu-id="6c007-128">从条目标识符中的信息计算**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 和**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6c007-128">Calculate **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) and **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) from information in the entry identifier.</span></span>
    
9. <span data-ttu-id="6c007-129">返回指向对象的接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="6c007-129">Return a pointer to the interface implementation for the object.</span></span> 
    

