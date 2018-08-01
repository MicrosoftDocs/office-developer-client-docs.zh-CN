---
title: 准备收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9573f10c-66e1-4e87-93f0-89687e906b8b
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 51241009262471bf30f7d71e3108b896bbce8df7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778552"
---
# <a name="preparing-a-recipient"></a><span data-ttu-id="e04f3-103">准备收件人</span><span class="sxs-lookup"><span data-stu-id="e04f3-103">Preparing a Recipient</span></span>

  
  
<span data-ttu-id="e04f3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e04f3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e04f3-105">客户端应用程序通过将其短期条目标识符格式转换为长期条目标识符和可能添加、 更改或重新排序属性准备收件人。</span><span class="sxs-lookup"><span data-stu-id="e04f3-105">A client application prepares recipients by converting their short-term entry identifiers to long-term entry identifiers and possibly adding, changing, or reordering properties.</span></span> <span data-ttu-id="e04f3-106">您可以准备属于邮件的收件人列表的收件人或一条消息，与无关的收件人。</span><span class="sxs-lookup"><span data-stu-id="e04f3-106">You can prepare recipients that are part of a recipient list for a message or recipients that are unrelated to a message.</span></span> <span data-ttu-id="e04f3-107">通常情况下，客户端调用[IAddrBook::PrepareRecips](iaddrbook-preparerecips.md)直接要转换为长期条目标识符的短期条目标识符的通用的地址对话框中包含的收件人。</span><span class="sxs-lookup"><span data-stu-id="e04f3-107">Typically, clients call [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) directly to translate short-term entry identifiers into long-term entry identifiers for recipients that are included in the common address dialog box.</span></span> <span data-ttu-id="e04f3-108">对于与传出邮件的收件人，收件人准备进行处理的名称解析过程。</span><span class="sxs-lookup"><span data-stu-id="e04f3-108">For recipients that are associated with an outgoing message, recipient preparation is handled by the name resolution process.</span></span> 
  
<span data-ttu-id="e04f3-109">若要准备的收件人列表，请调用**IAddrBook::PrepareRecips**。</span><span class="sxs-lookup"><span data-stu-id="e04f3-109">To prepare a list of recipients, call **IAddrBook::PrepareRecips**.</span></span> <span data-ttu-id="e04f3-110">**PrepareRecips**接受[ADRLIST](adrlist.md)结构和属性标记的列表。</span><span class="sxs-lookup"><span data-stu-id="e04f3-110">**PrepareRecips** accepts an [ADRLIST](adrlist.md) structure and a list of property tags.</span></span> <span data-ttu-id="e04f3-111">**ADRLIST**结构包含属性标记列表代表应支持每个收件人的属性时要准备的收件人。</span><span class="sxs-lookup"><span data-stu-id="e04f3-111">The **ADRLIST** structure contains the recipients to be prepared while the property tag list represents properties that each recipient should support.</span></span> <span data-ttu-id="e04f3-112">**PrepareRecips**尝试将放置**ADRLIST**结构开头属性标记列表中包含的属性。</span><span class="sxs-lookup"><span data-stu-id="e04f3-112">**PrepareRecips** attempts to place the properties that are included in the property tag list at the beginning of the **ADRLIST** structure.</span></span> <span data-ttu-id="e04f3-113">如果有**ADRLIST**结构中缺少的属性列表中，MAPI 调用通讯簿提供程序提供它们。</span><span class="sxs-lookup"><span data-stu-id="e04f3-113">If any of the properties in the list are missing from the **ADRLIST** structure, MAPI calls the address book provider to supply them.</span></span> <span data-ttu-id="e04f3-114">如果您只需检查长期条目标识符， _lpSPropTagArray_参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="e04f3-114">If you only need to check for long-term entry identifiers, pass NULL for the  _lpSPropTagArray_ parameter.</span></span> 
  
<span data-ttu-id="e04f3-115">例如，假设您正在使用 5 个收件人。</span><span class="sxs-lookup"><span data-stu-id="e04f3-115">For example, suppose you are working with five recipients.</span></span> <span data-ttu-id="e04f3-116">所有五个收件人**ADRLIST**结构中出现与以下顺序中的以下属性：</span><span class="sxs-lookup"><span data-stu-id="e04f3-116">All five recipients appear in the **ADRLIST** structure with the following properties in the following order:</span></span> 
  
1. <span data-ttu-id="e04f3-117">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e04f3-117">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
2. <span data-ttu-id="e04f3-118">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e04f3-118">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
3. <span data-ttu-id="e04f3-119">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e04f3-119">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>
    
4. <span data-ttu-id="e04f3-120">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e04f3-120">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>
    
5. <span data-ttu-id="e04f3-121">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e04f3-121">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
<span data-ttu-id="e04f3-122">**ADRLIST**结构中的前两个收件人包含三个其他属性。</span><span class="sxs-lookup"><span data-stu-id="e04f3-122">Three other properties are included in the **ADRLIST** structure for the first two recipients.</span></span> 
  
1. <span data-ttu-id="e04f3-123">**PR_ACCOUNT**([PidTagAccount](pidtagaccount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e04f3-123">**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))</span></span>
    
2. <span data-ttu-id="e04f3-124">**PR_GIVEN_NAME**([PidTagGivenName](pidtaggivenname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e04f3-124">**PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md))</span></span>
    
3. <span data-ttu-id="e04f3-125">**PR_SURNAME**([PidTagSurname](pidtagsurname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="e04f3-125">**PR_SURNAME** ([PidTagSurname](pidtagsurname-canonical-property.md))</span></span>
    
<span data-ttu-id="e04f3-126">由于的所有收件人都需要具有**PR_ADDRTYPE**、 **PR_ENTRYID**和**PR_HOME_TELEPHONE_NUMBER** ([PidTagHomeTelephoneNumber](pidtaghometelephonenumber-canonical-property.md)) 及其前三个属性，这些属性与创建属性标记数组和传递它并**PrepareRecips** **ADRLIST**结构。</span><span class="sxs-lookup"><span data-stu-id="e04f3-126">Because all of the recipients need to have as their first three properties **PR_ADDRTYPE**, **PR_ENTRYID**, and **PR_HOME_TELEPHONE_NUMBER** ([PidTagHomeTelephoneNumber](pidtaghometelephonenumber-canonical-property.md)), create a property tag array with these properties and pass it and the **ADRLIST** structure to **PrepareRecips**.</span></span> <span data-ttu-id="e04f3-127">**PrepareRecips**调用每个收件人的**IMAPIProp::GetProps**方法来检索**PR_HOME_TELEPHONE_NUMBER** ，因为它不当前**ADRLIST**结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="e04f3-127">**PrepareRecips** calls each recipient's **IMAPIProp::GetProps** method to retrieve **PR_HOME_TELEPHONE_NUMBER** because it is not currently part of the **ADRLIST** structure.</span></span> <span data-ttu-id="e04f3-128">**PrepareRecips**返回时，收件人列表中的每个收件人显示第一个**ADRLIST**结构包括的属性表示合并的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="e04f3-128">When **PrepareRecips** returns, the recipient list represents a merged list of recipients with the properties included in the **ADRLIST** structure appearing first for each recipient.</span></span> 
  
<span data-ttu-id="e04f3-129">1 和 2 的收件人的收件人列表包括按以下顺序的属性：</span><span class="sxs-lookup"><span data-stu-id="e04f3-129">The recipient list for recipients 1 and 2 includes properties in the following order:</span></span>
  
1. <span data-ttu-id="e04f3-130">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="e04f3-130">**PR_ADDRTYPE**</span></span>
    
2. <span data-ttu-id="e04f3-131">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="e04f3-131">**PR_ENTRYID**</span></span>
    
3. <span data-ttu-id="e04f3-132">**PR_HOME_TELEPHONE_NUMBER**</span><span class="sxs-lookup"><span data-stu-id="e04f3-132">**PR_HOME_TELEPHONE_NUMBER**</span></span>
    
4. <span data-ttu-id="e04f3-133">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="e04f3-133">**PR_DISPLAY_NAME**</span></span>
    
5. <span data-ttu-id="e04f3-134">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="e04f3-134">**PR_SEARCH_KEY**</span></span>
    
6. <span data-ttu-id="e04f3-135">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="e04f3-135">**PR_EMAIL_ADDRESS**</span></span>
    
7. <span data-ttu-id="e04f3-136">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="e04f3-136">**PR_ADDRTYPE**</span></span>
    
8. <span data-ttu-id="e04f3-137">**PR_ACCOUNT**</span><span class="sxs-lookup"><span data-stu-id="e04f3-137">**PR_ACCOUNT**</span></span>
    
9. <span data-ttu-id="e04f3-138">**PR_GIVEN_NAME**</span><span class="sxs-lookup"><span data-stu-id="e04f3-138">**PR_GIVEN_NAME**</span></span>
    
10. <span data-ttu-id="e04f3-139">**PR_SURNAME**</span><span class="sxs-lookup"><span data-stu-id="e04f3-139">**PR_SURNAME**</span></span>
    
<span data-ttu-id="e04f3-140">收件人 3、 4 和 5 的收件人列表包括按以下顺序的属性：</span><span class="sxs-lookup"><span data-stu-id="e04f3-140">The recipient list for recipients 3, 4, and 5 includes properties in the following order:</span></span>
  
1. <span data-ttu-id="e04f3-141">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="e04f3-141">**PR_ADDRTYPE**</span></span>
    
2. <span data-ttu-id="e04f3-142">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="e04f3-142">**PR_ENTRYID**</span></span>
    
3. <span data-ttu-id="e04f3-143">**PR_HOME_TELEPHONE_NUMBER**</span><span class="sxs-lookup"><span data-stu-id="e04f3-143">**PR_HOME_TELEPHONE_NUMBER**</span></span>
    
4. <span data-ttu-id="e04f3-144">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="e04f3-144">**PR_DISPLAY_NAME**</span></span>
    
5. <span data-ttu-id="e04f3-145">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="e04f3-145">**PR_SEARCH_KEY**</span></span>
    
6. <span data-ttu-id="e04f3-146">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="e04f3-146">**PR_EMAIL_ADDRESS**</span></span>
    
7. <span data-ttu-id="e04f3-147">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="e04f3-147">**PR_ADDRTYPE**</span></span>
    
<span data-ttu-id="e04f3-148">作为调用**IAddrBook::PrepareRecips**用于属性的替代方法，调用每个收件人的[IMAPIProp::GetProps](imapiprop-getprops.md)方法，如有必要，其[IMAPIProp::SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="e04f3-148">As an alternative to calling **IAddrBook::PrepareRecips** to work with properties, call each recipient's [IMAPIProp::GetProps](imapiprop-getprops.md) method and, if necessary, its [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> <span data-ttu-id="e04f3-149">涉及仅有一个收件人时，令人满意上述任一方法。</span><span class="sxs-lookup"><span data-stu-id="e04f3-149">When only one recipient is involved, either technique is satisfactory.</span></span> <span data-ttu-id="e04f3-150">但是，涉及多个收件人时，调用**PrepareRecips** ，而不是**IMAPIProp**方法节省时间，如果您在远程运行多个远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="e04f3-150">However, when multiple recipients are involved, calling **PrepareRecips** rather than the **IMAPIProp** methods saves time and, if you are operating remotely, many remote procedure calls.</span></span> <span data-ttu-id="e04f3-151">**PrepareRecips**处理一次调用中的所有收件人，而**GetProps**和**SetProps**进行一次调用每个收件人。</span><span class="sxs-lookup"><span data-stu-id="e04f3-151">**PrepareRecips** processes all recipients in a single call whereas **GetProps** and **SetProps** make one call for each recipient.</span></span> 
  

