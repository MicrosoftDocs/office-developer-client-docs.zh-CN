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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 0c70d16d294426d30f3ac5f00b6bc46992386a86
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775316"
---
# <a name="imailuser--imapiprop"></a><span data-ttu-id="d3026-103">IMailUser: IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="d3026-103">IMailUser : IMAPIProp</span></span>

  
  
<span data-ttu-id="d3026-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="d3026-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="d3026-105">提供了许多属性与邮件用户关联的访问权限。</span><span class="sxs-lookup"><span data-stu-id="d3026-105">Provides access to the many properties that are associated with messaging users.</span></span> <span data-ttu-id="d3026-106">**IMailUser**接口实现消息用户对象。</span><span class="sxs-lookup"><span data-stu-id="d3026-106">The **IMailUser** interface is implemented by messaging user objects.</span></span> <span data-ttu-id="d3026-107">继承自**IMailUser** [IMAPIProp: IUnknown](imapipropiunknown.md)接口，并具有其自己的方法都不唯一。</span><span class="sxs-lookup"><span data-stu-id="d3026-107">**IMailUser** inherits from the [IMAPIProp : IUnknown](imapipropiunknown.md) interface and has no unique methods of its own.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d3026-108">头文件：</span><span class="sxs-lookup"><span data-stu-id="d3026-108">Header file:</span></span>  <br/> |<span data-ttu-id="d3026-109">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d3026-109">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d3026-110">由公开：</span><span class="sxs-lookup"><span data-stu-id="d3026-110">Exposed by:</span></span>  <br/> |<span data-ttu-id="d3026-111">消息的用户对象</span><span class="sxs-lookup"><span data-stu-id="d3026-111">Messaging user objects</span></span>  <br/> |
|<span data-ttu-id="d3026-112">通过实现：</span><span class="sxs-lookup"><span data-stu-id="d3026-112">Implemented by:</span></span>  <br/> |<span data-ttu-id="d3026-113">通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="d3026-113">Address book providers</span></span>  <br/> |
|<span data-ttu-id="d3026-114">调用：</span><span class="sxs-lookup"><span data-stu-id="d3026-114">Called by:</span></span>  <br/> |<span data-ttu-id="d3026-115">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="d3026-115">Client applications</span></span>  <br/> |
|<span data-ttu-id="d3026-116">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="d3026-116">Interface identifier:</span></span>  <br/> |<span data-ttu-id="d3026-117">IID_IMailUser</span><span class="sxs-lookup"><span data-stu-id="d3026-117">IID_IMailUser</span></span>  <br/> |
|<span data-ttu-id="d3026-118">指针类型：</span><span class="sxs-lookup"><span data-stu-id="d3026-118">Pointer type:</span></span>  <br/> |<span data-ttu-id="d3026-119">LPMAILUSER</span><span class="sxs-lookup"><span data-stu-id="d3026-119">LPMAILUSER</span></span>  <br/> |
|<span data-ttu-id="d3026-120">事务模型：</span><span class="sxs-lookup"><span data-stu-id="d3026-120">Transaction model:</span></span>  <br/> |<span data-ttu-id="d3026-121">事务处理</span><span class="sxs-lookup"><span data-stu-id="d3026-121">Transacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="d3026-122">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="d3026-122">Vtable order</span></span>

<span data-ttu-id="d3026-123">此接口不具有任何唯一的方法。</span><span class="sxs-lookup"><span data-stu-id="d3026-123">This interface does not have any unique methods.</span></span>
  
|<span data-ttu-id="d3026-124">**必需的属性**</span><span class="sxs-lookup"><span data-stu-id="d3026-124">**Required properties**</span></span>|<span data-ttu-id="d3026-125">**访问**</span><span class="sxs-lookup"><span data-stu-id="d3026-125">**Access**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3026-126">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-126">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d3026-127">读/写</span><span class="sxs-lookup"><span data-stu-id="d3026-127">Read/write</span></span>  <br/> |
|<span data-ttu-id="d3026-128">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-128">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d3026-129">读/写</span><span class="sxs-lookup"><span data-stu-id="d3026-129">Read/write</span></span>  <br/> |
|<span data-ttu-id="d3026-130">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-130">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d3026-131">只读</span><span class="sxs-lookup"><span data-stu-id="d3026-131">Read-only</span></span>  <br/> |
|<span data-ttu-id="d3026-132">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-132">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d3026-133">读/写</span><span class="sxs-lookup"><span data-stu-id="d3026-133">Read/write</span></span>  <br/> |
|<span data-ttu-id="d3026-134">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-134">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d3026-135">只读</span><span class="sxs-lookup"><span data-stu-id="d3026-135">Read-only</span></span>  <br/> |
|<span data-ttu-id="d3026-136">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-136">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d3026-137">只读</span><span class="sxs-lookup"><span data-stu-id="d3026-137">Read-only</span></span>  <br/> |
|<span data-ttu-id="d3026-138">**PR_RECORD_KEY**([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-138">**PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d3026-139">只读</span><span class="sxs-lookup"><span data-stu-id="d3026-139">Read-only</span></span>  <br/> |
|<span data-ttu-id="d3026-140">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-140">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="d3026-141">只读</span><span class="sxs-lookup"><span data-stu-id="d3026-141">Read-only</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d3026-142">备注</span><span class="sxs-lookup"><span data-stu-id="d3026-142">Remarks</span></span>

<span data-ttu-id="d3026-143">必需的属性的第五个称为基址属性的收件人：</span><span class="sxs-lookup"><span data-stu-id="d3026-143">Five of the required properties are known as the base address properties for recipients:</span></span>
  
- <span data-ttu-id="d3026-144">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="d3026-144">**PR_ADDRTYPE**</span></span>
    
- <span data-ttu-id="d3026-145">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="d3026-145">**PR_DISPLAY_NAME**</span></span>
    
- <span data-ttu-id="d3026-146">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="d3026-146">**PR_EMAIL_ADDRESS**</span></span>
    
- <span data-ttu-id="d3026-147">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="d3026-147">**PR_ENTRYID**</span></span>
    
- <span data-ttu-id="d3026-148">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="d3026-148">**PR_SEARCH_KEY**</span></span>
    
<span data-ttu-id="d3026-149">因为相似属性的许多其他组建立在此基本组，这些属性被视为特殊。</span><span class="sxs-lookup"><span data-stu-id="d3026-149">These properties are considered special because many other groups of similar properties are built upon this base group.</span></span> <span data-ttu-id="d3026-150">其他组用于描述的收件人的各种角色，如一条消息的原始或委派发件人。</span><span class="sxs-lookup"><span data-stu-id="d3026-150">The other groups are used to describe a recipient in various roles, such as a message's original or delegate sender.</span></span> <span data-ttu-id="d3026-151">有关这些属性以及如何使用它们的详细信息，请参阅[MAPI 地址类型](mapi-address-types.md)。</span><span class="sxs-lookup"><span data-stu-id="d3026-151">For more information about these properties and how to use them, see [MAPI Address Types](mapi-address-types.md).</span></span>
  
<span data-ttu-id="d3026-152">消息用户可以通过支持**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性中显示其属性的集合。</span><span class="sxs-lookup"><span data-stu-id="d3026-152">Messaging users can display a collection of their properties by supporting the **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) property.</span></span> <span data-ttu-id="d3026-153">**PR_DETAILS_TABLE**是一个显示表，描述布局的详细信息对话框或选项卡式的属性页，显示收件人的属性信息。</span><span class="sxs-lookup"><span data-stu-id="d3026-153">**PR_DETAILS_TABLE** is a display table that describes the layout of a details dialog box or a tabbed property page that displays recipient property information.</span></span> <span data-ttu-id="d3026-154">客户端呼叫[IAddrBook::Details](iaddrbook-details.md)方法时，MAPI 创建详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="d3026-154">MAPI creates details dialog boxes when a client calls the [IAddrBook::Details](iaddrbook-details.md) method.</span></span> 
  
<span data-ttu-id="d3026-155">消息用户对象可以具有与其相关的其他可选属性。</span><span class="sxs-lookup"><span data-stu-id="d3026-155">Messaging user objects can have other optional properties associated with them.</span></span> <span data-ttu-id="d3026-156">MAPI 定义许多属性提供有关邮件用户的其他寻址信息。</span><span class="sxs-lookup"><span data-stu-id="d3026-156">MAPI defines many properties that provide additional addressing information about a messaging user.</span></span> <span data-ttu-id="d3026-157">所有这些属性是字符串。</span><span class="sxs-lookup"><span data-stu-id="d3026-157">All of these properties are character strings.</span></span> <span data-ttu-id="d3026-158">以下列表显示了多种常用的属性：</span><span class="sxs-lookup"><span data-stu-id="d3026-158">The following list shows the more commonly used properties:</span></span>
  
- <span data-ttu-id="d3026-159">**PR_ACCOUNT**([PidTagAccount](pidtagaccount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-159">**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d3026-160">**PR_ASSISTANT**([PidTagAssistant](pidtagassistant-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-160">**PR_ASSISTANT** ([PidTagAssistant](pidtagassistant-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d3026-161">**PR_BUSINESS_TELEPHONE_NUMBER**([PidTagBusinessTelephoneNumber](pidtagbusinesstelephonenumber-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-161">**PR_BUSINESS_TELEPHONE_NUMBER** ([PidTagBusinessTelephoneNumber](pidtagbusinesstelephonenumber-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d3026-162">**PR_GIVEN_NAME**([PidTagGivenName](pidtaggivenname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-162">**PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d3026-163">**PR_GOVERNMENT_ID_NUMBER**([PidTagGovernmentIdNumber](pidtaggovernmentidnumber-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-163">**PR_GOVERNMENT_ID_NUMBER** ([PidTagGovernmentIdNumber](pidtaggovernmentidnumber-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d3026-164">**PR_LOCALITY**([PidTagLocality](pidtaglocality-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-164">**PR_LOCALITY** ([PidTagLocality](pidtaglocality-canonical-property.md))</span></span> 
    
- <span data-ttu-id="d3026-165">**PR_POSTAL_ADDRESS**([PidTagPostalAddress](pidtagpostaladdress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="d3026-165">**PR_POSTAL_ADDRESS** ([PidTagPostalAddress](pidtagpostaladdress-canonical-property.md))</span></span> 
    
<span data-ttu-id="d3026-166">属性的完整列表，请参阅[到 MAPI 名称映射规范属性名称](mapping-canonical-property-names-to-mapi-names.md)。</span><span class="sxs-lookup"><span data-stu-id="d3026-166">For a complete list of properties, see [Mapping Canonical Property Names to MAPI Names](mapping-canonical-property-names-to-mapi-names.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d3026-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3026-167">See also</span></span>



[<span data-ttu-id="d3026-168">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="d3026-168">MAPI Interfaces</span></span>](mapi-interfaces.md)

