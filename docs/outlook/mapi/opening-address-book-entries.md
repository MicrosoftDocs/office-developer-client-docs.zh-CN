---
title: 打开通讯簿条目
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 017a62c0-49c6-47fb-acce-db58e6bb9cc5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cd86b9cc86f30aac75b732b97208933de4d336e9
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566427"
---
# <a name="opening-address-book-entries"></a><span data-ttu-id="482f9-103">打开通讯簿条目</span><span class="sxs-lookup"><span data-stu-id="482f9-103">Opening address book entries</span></span>

<span data-ttu-id="482f9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="482f9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="482f9-105">在客户端或提供程序已请求您对象之一打开的 MAPI 调用您的提供商[IABLogon::OpenEntry](iablogon-openentry.md)方法。</span><span class="sxs-lookup"><span data-stu-id="482f9-105">When a client or provider has requested that one of your objects be opened, MAPI calls your provider's [IABLogon::OpenEntry](iablogon-openentry.md) method.</span></span> <span data-ttu-id="482f9-106">MAPI，表示目标对象的项标识符通过确定属于您的提供商检查的项标识符的[MAPIUID](mapiuid.md)部分并将它与提供程序注册**调用**MAPIUID**匹配IMAPISupport::SetProviderUID**。</span><span class="sxs-lookup"><span data-stu-id="482f9-106">MAPI determines that the entry identifier representing the target object belongs to your provider by examining the [MAPIUID](mapiuid.md) portion of the entry identifier and matching it to the **MAPIUID** that your provider registered in the call to **IMAPISupport::SetProviderUID**.</span></span> <span data-ttu-id="482f9-107">MAPI 然后调用**OpenEntry**方法。</span><span class="sxs-lookup"><span data-stu-id="482f9-107">MAPI then calls your **OpenEntry** method.</span></span> <span data-ttu-id="482f9-108">您的提供商必须响应通过检索相应对象 — 容器、 通讯组列表或消息用户。</span><span class="sxs-lookup"><span data-stu-id="482f9-108">Your provider must respond by retrieving the corresponding object — a container, distribution list, or messaging user.</span></span> 
  
<span data-ttu-id="482f9-109">NULL 条目标识符指示打开通讯簿提供程序的根容器的请求。</span><span class="sxs-lookup"><span data-stu-id="482f9-109">A NULL entry identifier indicates a request to open the address book provider's root container.</span></span> <span data-ttu-id="482f9-110">客户端打开根容器来访问其层次结构表和它的收件人。</span><span class="sxs-lookup"><span data-stu-id="482f9-110">Clients open the root container to access its hierarchy table and its recipients.</span></span> <span data-ttu-id="482f9-111">仅提供模板，用于创建一次性收件人的地址簿提供程序的根容器不支持**OpenEntry**呼叫。</span><span class="sxs-lookup"><span data-stu-id="482f9-111">Address book providers that only supply templates for creating one-off recipients do not support the **OpenEntry** call for the root container.</span></span> 
  
### <a name="to-implement-iablogonopenentry"></a><span data-ttu-id="482f9-112">若要实现 IABLogon::OpenEntry</span><span class="sxs-lookup"><span data-stu-id="482f9-112">To implement IABLogon::OpenEntry</span></span>
  
1. <span data-ttu-id="482f9-113">检查条目标识符为您提供商支持的有效标识符。</span><span class="sxs-lookup"><span data-stu-id="482f9-113">Check that the entry identifier is a valid identifier that your provider supports.</span></span> <span data-ttu-id="482f9-114">如果它不是有效的项标识符，返回 MAPI_E_INVALID_ENTRYID。</span><span class="sxs-lookup"><span data-stu-id="482f9-114">If it is not a valid entry identifier, return MAPI_E_INVALID_ENTRYID.</span></span> 
    
2. <span data-ttu-id="482f9-115">检查使用_ulFlags_参数传递的标志。</span><span class="sxs-lookup"><span data-stu-id="482f9-115">Check the flag that is passed in with the  _ulFlags_ parameter.</span></span> <span data-ttu-id="482f9-116">如果在 MAPI_MODIFY 已通过 MAPI 提供程序不允许要修改其对象，失败并返回 MAPI_E_ACCESS_DENIED 错误值。</span><span class="sxs-lookup"><span data-stu-id="482f9-116">If MAPI has passed in MAPI_MODIFY and your provider does not allow its objects to be modified, fail and return the MAPI_E_ACCESS_DENIED error value.</span></span> 
    
3. <span data-ttu-id="482f9-117">检查请求_lpInterface_参数中的接口有效的已要求您提供程序打开的对象的类型。</span><span class="sxs-lookup"><span data-stu-id="482f9-117">Check that the interface requested in the  _lpInterface_ parameter is valid for the type of object your provider has been asked to open.</span></span> <span data-ttu-id="482f9-118">如果传递中的参数无效，失败并返回 MAPI_E_INTERFACE_NOT_SUPPORTED 错误值。</span><span class="sxs-lookup"><span data-stu-id="482f9-118">If an invalid parameter has been passed in, fail and return the MAPI_E_INTERFACE_NOT_SUPPORTED error value.</span></span> 
    
4. <span data-ttu-id="482f9-119">如果_cbEntryID_参数为零，这是打开您的提供商根容器的请求。</span><span class="sxs-lookup"><span data-stu-id="482f9-119">If the  _cbEntryID_ parameter is zero, this is a request to open your provider's root container.</span></span> <span data-ttu-id="482f9-120">创建根容器，并返回到其**IABContainer**接口实现的指针。</span><span class="sxs-lookup"><span data-stu-id="482f9-120">Create the root container and return a pointer to its **IABContainer** interface implementation.</span></span> 
    
5. <span data-ttu-id="482f9-121">如果您的提供程序实现多个登录对象，每个都有自己注册**MAPIUID**， **MAPIUID**包含在与相应登录对象的项标识符的映射。</span><span class="sxs-lookup"><span data-stu-id="482f9-121">If your provider implements several logon objects, each with its own registered **MAPIUID**, map the **MAPIUID** contained in the entry identifier with the appropriate logon object.</span></span> 
    
6. <span data-ttu-id="482f9-122">确定哪种类型的对象的项标识符代表： 邮件用户、 通讯组列表或容器属于您的提供商或一次性的邮件用户或通讯组列表，以便可以为_lpulObjectType_设置适当的值参数。</span><span class="sxs-lookup"><span data-stu-id="482f9-122">Determine which type of object the entry identifier represents: a messaging user, distribution list, or container belonging to your provider or a one-off messaging user or distribution list so that the appropriate value can be set for the  _lpulObjectType_ parameter.</span></span> 
    
7. <span data-ttu-id="482f9-123">创建适当类型的对象，并设置以下基本属性：</span><span class="sxs-lookup"><span data-stu-id="482f9-123">Create the object of the appropriate type and set the following basic properties:</span></span>
    
    - <span data-ttu-id="482f9-124">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="482f9-124">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>
    - <span data-ttu-id="482f9-125">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="482f9-125">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    - <span data-ttu-id="482f9-126">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="482f9-126">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>
    - <span data-ttu-id="482f9-127">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="482f9-127">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
8. <span data-ttu-id="482f9-128">计算**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) 和**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 中的项标识符的信息。</span><span class="sxs-lookup"><span data-stu-id="482f9-128">Calculate **PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md)) and **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) from information in the entry identifier.</span></span>
    
9. <span data-ttu-id="482f9-129">返回到该接口实现对象的指针。</span><span class="sxs-lookup"><span data-stu-id="482f9-129">Return a pointer to the interface implementation for the object.</span></span> 
    

