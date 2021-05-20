---
title: IMailUser IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMailUser
api_type:
- COM
ms.assetid: 74c25870-62d9-484a-9a99-4dc35c52479e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a0e109fe95120483e700bab5b82f6d7cb75e2e28
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436592"
---
# <a name="imailuser--imapiprop"></a><span data-ttu-id="c538f-103">IMailUser : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="c538f-103">IMailUser : IMAPIProp</span></span>

  
  
<span data-ttu-id="c538f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c538f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c538f-105">提供对与邮件用户关联的许多属性的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c538f-105">Provides access to the many properties that are associated with messaging users.</span></span> <span data-ttu-id="c538f-106">**IMailUser** 接口由邮件用户对象实现。</span><span class="sxs-lookup"><span data-stu-id="c538f-106">The **IMailUser** interface is implemented by messaging user objects.</span></span> <span data-ttu-id="c538f-107">**IMailUser** 继承自 [IMAPIProp ： IUnknown](imapipropiunknown.md) 接口，并且没有其自己的唯一方法。</span><span class="sxs-lookup"><span data-stu-id="c538f-107">**IMailUser** inherits from the [IMAPIProp : IUnknown](imapipropiunknown.md) interface and has no unique methods of its own.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c538f-108">标头文件：</span><span class="sxs-lookup"><span data-stu-id="c538f-108">Header file:</span></span>  <br/> |<span data-ttu-id="c538f-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c538f-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="c538f-110">公开者：</span><span class="sxs-lookup"><span data-stu-id="c538f-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="c538f-111">邮件用户对象</span><span class="sxs-lookup"><span data-stu-id="c538f-111">Messaging user objects</span></span>  <br/> |
|<span data-ttu-id="c538f-112">实现者：</span><span class="sxs-lookup"><span data-stu-id="c538f-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="c538f-113">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="c538f-113">Address book providers</span></span>  <br/> |
|<span data-ttu-id="c538f-114">调用者：</span><span class="sxs-lookup"><span data-stu-id="c538f-114">Called by:</span></span>  <br/> |<span data-ttu-id="c538f-115">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="c538f-115">Client applications</span></span>  <br/> |
|<span data-ttu-id="c538f-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="c538f-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="c538f-117">IID_IMailUser</span><span class="sxs-lookup"><span data-stu-id="c538f-117">IID_IMailUser</span></span>  <br/> |
|<span data-ttu-id="c538f-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="c538f-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="c538f-119">LPMAILUSER</span><span class="sxs-lookup"><span data-stu-id="c538f-119">LPMAILUSER</span></span>  <br/> |
|<span data-ttu-id="c538f-120">事务模型：</span><span class="sxs-lookup"><span data-stu-id="c538f-120">Transaction model:</span></span>  <br/> |<span data-ttu-id="c538f-121">Transacted</span><span class="sxs-lookup"><span data-stu-id="c538f-121">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="c538f-122">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="c538f-122">Vtable order</span></span>

<span data-ttu-id="c538f-123">此接口没有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="c538f-123">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="c538f-124">**必需属性**</span><span class="sxs-lookup"><span data-stu-id="c538f-124">**Required properties**</span></span>|<span data-ttu-id="c538f-125">**Access**</span><span class="sxs-lookup"><span data-stu-id="c538f-125">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c538f-126">**PR_ADDRTYPE (** [PidTagAddressType](pidtagaddresstype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-126">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c538f-127">读/写</span><span class="sxs-lookup"><span data-stu-id="c538f-127">Read/write</span></span>  <br/> |
|<span data-ttu-id="c538f-128">**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-128">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c538f-129">读/写</span><span class="sxs-lookup"><span data-stu-id="c538f-129">Read/write</span></span>  <br/> |
|<span data-ttu-id="c538f-130">**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-130">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c538f-131">只读</span><span class="sxs-lookup"><span data-stu-id="c538f-131">Read-only</span></span>  <br/> |
|<span data-ttu-id="c538f-132">**PR_EMAIL_ADDRESS (** [PidTagEmailAddress)](pidtagemailaddress-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="c538f-132">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c538f-133">读/写</span><span class="sxs-lookup"><span data-stu-id="c538f-133">Read/write</span></span>  <br/> |
|<span data-ttu-id="c538f-134">**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-134">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c538f-135">只读</span><span class="sxs-lookup"><span data-stu-id="c538f-135">Read-only</span></span>  <br/> |
|<span data-ttu-id="c538f-136">**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-136">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c538f-137">只读</span><span class="sxs-lookup"><span data-stu-id="c538f-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="c538f-138">**PR_RECORD_KEY (** [PidTagRecordKey)](pidtagrecordkey-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="c538f-138">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c538f-139">只读</span><span class="sxs-lookup"><span data-stu-id="c538f-139">Read-only</span></span>  <br/> |
|<span data-ttu-id="c538f-140">**PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-140">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="c538f-141">只读</span><span class="sxs-lookup"><span data-stu-id="c538f-141">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c538f-142">备注</span><span class="sxs-lookup"><span data-stu-id="c538f-142">Remarks</span></span>

<span data-ttu-id="c538f-143">五个必需属性称为收件人的基地址属性：</span><span class="sxs-lookup"><span data-stu-id="c538f-143">Five of the required properties are known as the base address properties for recipients:</span></span>
  
- <span data-ttu-id="c538f-144">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="c538f-144">**PR_ADDRTYPE**</span></span>
    
- <span data-ttu-id="c538f-145">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="c538f-145">**PR_DISPLAY_NAME**</span></span>
    
- <span data-ttu-id="c538f-146">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="c538f-146">**PR_EMAIL_ADDRESS**</span></span>
    
- <span data-ttu-id="c538f-147">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="c538f-147">**PR_ENTRYID**</span></span>
    
- <span data-ttu-id="c538f-148">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="c538f-148">**PR_SEARCH_KEY**</span></span>
    
<span data-ttu-id="c538f-149">这些属性被视为特殊属性，因为许多其他类似属性组都基于此基组构建。</span><span class="sxs-lookup"><span data-stu-id="c538f-149">These properties are considered special because many other groups of similar properties are built upon this base group.</span></span> <span data-ttu-id="c538f-150">其他组用于描述各种角色中的收件人，如邮件的原始发件人或代理发件人。</span><span class="sxs-lookup"><span data-stu-id="c538f-150">The other groups are used to describe a recipient in various roles, such as a message's original or delegate sender.</span></span> <span data-ttu-id="c538f-151">有关这些属性以及如何使用这些属性的信息，请参阅 [MAPI 地址类型](mapi-address-types.md)。</span><span class="sxs-lookup"><span data-stu-id="c538f-151">For more information about these properties and how to use them, see [MAPI Address Types](mapi-address-types.md).</span></span>
  
<span data-ttu-id="c538f-152">邮件用户可以通过支持[PidTagDetailsTable](pidtagdetailstable-canonical-property.md)属性PR_DETAILS_TABLE (属性) 集合。</span><span class="sxs-lookup"><span data-stu-id="c538f-152">Messaging users can display a collection of their properties by supporting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property.</span></span> <span data-ttu-id="c538f-153">**PR_DETAILS_TABLE** 是一个显示表，用于描述详细信息对话框或显示收件人属性信息的选项卡式属性页的布局。</span><span class="sxs-lookup"><span data-stu-id="c538f-153">**PR_DETAILS_TABLE** is a display table that describes the layout of a details dialog box or a tabbed property page that displays recipient property information.</span></span> <span data-ttu-id="c538f-154">当客户端调用 [IAddrBook：:D etails](iaddrbook-details.md) 方法时，MAPI 将创建详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="c538f-154">MAPI creates details dialog boxes when a client calls the [IAddrBook::Details](iaddrbook-details.md) method.</span></span> 
  
<span data-ttu-id="c538f-155">邮件用户对象可以具有与其关联的其他可选属性。</span><span class="sxs-lookup"><span data-stu-id="c538f-155">Messaging user objects can have other optional properties associated with them.</span></span> <span data-ttu-id="c538f-156">MAPI 定义许多属性，这些属性提供有关邮件用户的其他寻址信息。</span><span class="sxs-lookup"><span data-stu-id="c538f-156">MAPI defines many properties that provide additional addressing information about a messaging user.</span></span> <span data-ttu-id="c538f-157">所有这些属性都是字符字符串。</span><span class="sxs-lookup"><span data-stu-id="c538f-157">All of these properties are character strings.</span></span> <span data-ttu-id="c538f-158">以下列表显示了更常用的属性：</span><span class="sxs-lookup"><span data-stu-id="c538f-158">The following list shows the more commonly used properties:</span></span>
  
- <span data-ttu-id="c538f-159">**PR_ACCOUNT (** [PidTagAccount)](pidtagaccount-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="c538f-159">**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))</span></span> 
    
- <span data-ttu-id="c538f-160">**PR_ASSISTANT (** [PidTagAssistant)](pidtagassistant-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="c538f-160">**PR_ASSISTANT** ([PidTagAssistant](pidtagassistant-canonical-property.md))</span></span> 
    
- <span data-ttu-id="c538f-161">**PR_BUSINESS_TELEPHONE_NUMBER (** [PidTagBusinessTelephoneNumber](pidtagbusinesstelephonenumber-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-161">**PR_BUSINESS_TELEPHONE_NUMBER** ([PidTagBusinessTelephoneNumber](pidtagbusinesstelephonenumber-canonical-property.md))</span></span> 
    
- <span data-ttu-id="c538f-162">**PR_GIVEN_NAME (** [PidTagGivenName](pidtaggivenname-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-162">**PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md))</span></span> 
    
- <span data-ttu-id="c538f-163">**PR_GOVERNMENT_ID_NUMBER (** [PidTagGovernmentIdNumber](pidtaggovernmentidnumber-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="c538f-163">**PR_GOVERNMENT_ID_NUMBER** ([PidTagGovernmentIdNumber](pidtaggovernmentidnumber-canonical-property.md))</span></span> 
    
- <span data-ttu-id="c538f-164">**PR_LOCALITY (** [PidTagLocality)](pidtaglocality-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="c538f-164">**PR_LOCALITY** ([PidTagLocality](pidtaglocality-canonical-property.md))</span></span> 
    
- <span data-ttu-id="c538f-165">**PR_POSTAL_ADDRESS (** [PidTagPostalAddress)](pidtagpostaladdress-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="c538f-165">**PR_POSTAL_ADDRESS** ([PidTagPostalAddress](pidtagpostaladdress-canonical-property.md))</span></span> 
    
<span data-ttu-id="c538f-166">有关属性的完整列表，请参阅Map [Mapping Canonical Property Names to MAPI Names。](mapping-canonical-property-names-to-mapi-names.md)</span><span class="sxs-lookup"><span data-stu-id="c538f-166">For a complete list of properties, see [Mapping Canonical Property Names to MAPI Names](mapping-canonical-property-names-to-mapi-names.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c538f-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c538f-167">See also</span></span>



[<span data-ttu-id="c538f-168">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="c538f-168">MAPI Interfaces</span></span>](mapi-interfaces.md)

