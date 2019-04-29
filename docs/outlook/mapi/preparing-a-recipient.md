---
title: 准备收件人
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9573f10c-66e1-4e87-93f0-89687e906b8b
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: bb6bc8b8d0199ab07d5dad353dbc25da240593e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419875"
---
# <a name="preparing-a-recipient"></a><span data-ttu-id="30f0c-103">准备收件人</span><span class="sxs-lookup"><span data-stu-id="30f0c-103">Preparing a Recipient</span></span>

  
  
<span data-ttu-id="30f0c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="30f0c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="30f0c-105">客户端应用程序通过将短期条目标识符转换为长期条目标识符, 并可能添加、更改或重新排序属性来为收件人做准备。</span><span class="sxs-lookup"><span data-stu-id="30f0c-105">A client application prepares recipients by converting their short-term entry identifiers to long-term entry identifiers and possibly adding, changing, or reordering properties.</span></span> <span data-ttu-id="30f0c-106">您可以为与邮件无关的邮件或收件人准备收件人列表中的收件人。</span><span class="sxs-lookup"><span data-stu-id="30f0c-106">You can prepare recipients that are part of a recipient list for a message or recipients that are unrelated to a message.</span></span> <span data-ttu-id="30f0c-107">通常情况下, 客户端调用[IAddrBook::P reparerecips](iaddrbook-preparerecips.md)直接将短期条目标识符转换为公用地址对话框中包含的收件人的长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="30f0c-107">Typically, clients call [IAddrBook::PrepareRecips](iaddrbook-preparerecips.md) directly to translate short-term entry identifiers into long-term entry identifiers for recipients that are included in the common address dialog box.</span></span> <span data-ttu-id="30f0c-108">对于与传出邮件关联的收件人, 收件人准备将由名称解析过程处理。</span><span class="sxs-lookup"><span data-stu-id="30f0c-108">For recipients that are associated with an outgoing message, recipient preparation is handled by the name resolution process.</span></span> 
  
<span data-ttu-id="30f0c-109">若要准备收件人列表, 请调用**IAddrBook::P reparerecips**。</span><span class="sxs-lookup"><span data-stu-id="30f0c-109">To prepare a list of recipients, call **IAddrBook::PrepareRecips**.</span></span> <span data-ttu-id="30f0c-110">**PrepareRecips**接受[ADRLIST](adrlist.md)结构和属性标记的列表。</span><span class="sxs-lookup"><span data-stu-id="30f0c-110">**PrepareRecips** accepts an [ADRLIST](adrlist.md) structure and a list of property tags.</span></span> <span data-ttu-id="30f0c-111">**ADRLIST**结构包含要准备的收件人, 而属性标记列表表示每个收件人应支持的属性。</span><span class="sxs-lookup"><span data-stu-id="30f0c-111">The **ADRLIST** structure contains the recipients to be prepared while the property tag list represents properties that each recipient should support.</span></span> <span data-ttu-id="30f0c-112">**PrepareRecips**尝试将属性标记列表中包含的属性放在**ADRLIST**结构的开头。</span><span class="sxs-lookup"><span data-stu-id="30f0c-112">**PrepareRecips** attempts to place the properties that are included in the property tag list at the beginning of the **ADRLIST** structure.</span></span> <span data-ttu-id="30f0c-113">如果**ADRLIST**结构中缺少列表中的任何属性, 则 MAPI 会调用通讯簿提供程序来提供它们。</span><span class="sxs-lookup"><span data-stu-id="30f0c-113">If any of the properties in the list are missing from the **ADRLIST** structure, MAPI calls the address book provider to supply them.</span></span> <span data-ttu-id="30f0c-114">如果只需要检查长期条目标识符, 请为_lpSPropTagArray_参数传递 NULL。</span><span class="sxs-lookup"><span data-stu-id="30f0c-114">If you only need to check for long-term entry identifiers, pass NULL for the  _lpSPropTagArray_ parameter.</span></span> 
  
<span data-ttu-id="30f0c-115">例如, 假设您正在处理五个收件人。</span><span class="sxs-lookup"><span data-stu-id="30f0c-115">For example, suppose you are working with five recipients.</span></span> <span data-ttu-id="30f0c-116">所有五个收件人都按以下顺序显示在**ADRLIST**结构中, 其属性如下:</span><span class="sxs-lookup"><span data-stu-id="30f0c-116">All five recipients appear in the **ADRLIST** structure with the following properties in the following order:</span></span> 
  
1. <span data-ttu-id="30f0c-117">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="30f0c-117">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>
    
2. <span data-ttu-id="30f0c-118">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="30f0c-118">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>
    
3. <span data-ttu-id="30f0c-119">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="30f0c-119">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>
    
4. <span data-ttu-id="30f0c-120">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="30f0c-120">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>
    
5. <span data-ttu-id="30f0c-121">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="30f0c-121">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>
    
<span data-ttu-id="30f0c-122">前两个收件人的**ADRLIST**结构中包含了其他三个属性。</span><span class="sxs-lookup"><span data-stu-id="30f0c-122">Three other properties are included in the **ADRLIST** structure for the first two recipients.</span></span> 
  
1. <span data-ttu-id="30f0c-123">**PR_ACCOUNT**([PidTagAccount](pidtagaccount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="30f0c-123">**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))</span></span>
    
2. <span data-ttu-id="30f0c-124">**PR_GIVEN_NAME**([PidTagGivenName](pidtaggivenname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="30f0c-124">**PR_GIVEN_NAME** ([PidTagGivenName](pidtaggivenname-canonical-property.md))</span></span>
    
3. <span data-ttu-id="30f0c-125">**PR_SURNAME**([PidTagSurname](pidtagsurname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="30f0c-125">**PR_SURNAME** ([PidTagSurname](pidtagsurname-canonical-property.md))</span></span>
    
<span data-ttu-id="30f0c-126">由于所有收件人都需要将其作为前三个属性**PR_ADDRTYPE**、 **PR_ENTRYID**和**PR_HOME_TELEPHONE_NUMBER** ([PidTagHomeTelephoneNumber](pidtaghometelephonenumber-canonical-property.md)), 请使用这些属性创建一个 property 标记数组并传递将其和**ADRLIST**结构的**PrepareRecips**。</span><span class="sxs-lookup"><span data-stu-id="30f0c-126">Because all of the recipients need to have as their first three properties **PR_ADDRTYPE**, **PR_ENTRYID**, and **PR_HOME_TELEPHONE_NUMBER** ([PidTagHomeTelephoneNumber](pidtaghometelephonenumber-canonical-property.md)), create a property tag array with these properties and pass it and the **ADRLIST** structure to **PrepareRecips**.</span></span> <span data-ttu-id="30f0c-127">**PrepareRecips**调用每个收件人的**IMAPIProp:: GetProps**方法以检索**PR_HOME_TELEPHONE_NUMBER** , 因为它当前不是**ADRLIST**结构的一部分。</span><span class="sxs-lookup"><span data-stu-id="30f0c-127">**PrepareRecips** calls each recipient's **IMAPIProp::GetProps** method to retrieve **PR_HOME_TELEPHONE_NUMBER** because it is not currently part of the **ADRLIST** structure.</span></span> <span data-ttu-id="30f0c-128">当**PrepareRecips**返回时, 收件人列表表示收件人的合并列表, 其中包含在**ADRLIST**结构中包含在每个收件人的第一个显示的属性。</span><span class="sxs-lookup"><span data-stu-id="30f0c-128">When **PrepareRecips** returns, the recipient list represents a merged list of recipients with the properties included in the **ADRLIST** structure appearing first for each recipient.</span></span> 
  
<span data-ttu-id="30f0c-129">收件人1和组2的收件人列表包含按以下顺序排列的属性:</span><span class="sxs-lookup"><span data-stu-id="30f0c-129">The recipient list for recipients 1 and 2 includes properties in the following order:</span></span>
  
1. <span data-ttu-id="30f0c-130">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="30f0c-130">**PR_ADDRTYPE**</span></span>
    
2. <span data-ttu-id="30f0c-131">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="30f0c-131">**PR_ENTRYID**</span></span>
    
3. <span data-ttu-id="30f0c-132">**PR_HOME_TELEPHONE_NUMBER**</span><span class="sxs-lookup"><span data-stu-id="30f0c-132">**PR_HOME_TELEPHONE_NUMBER**</span></span>
    
4. <span data-ttu-id="30f0c-133">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="30f0c-133">**PR_DISPLAY_NAME**</span></span>
    
5. <span data-ttu-id="30f0c-134">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="30f0c-134">**PR_SEARCH_KEY**</span></span>
    
6. <span data-ttu-id="30f0c-135">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="30f0c-135">**PR_EMAIL_ADDRESS**</span></span>
    
7. <span data-ttu-id="30f0c-136">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="30f0c-136">**PR_ADDRTYPE**</span></span>
    
8. <span data-ttu-id="30f0c-137">**PR_ACCOUNT**</span><span class="sxs-lookup"><span data-stu-id="30f0c-137">**PR_ACCOUNT**</span></span>
    
9. <span data-ttu-id="30f0c-138">**PR_GIVEN_NAME**</span><span class="sxs-lookup"><span data-stu-id="30f0c-138">**PR_GIVEN_NAME**</span></span>
    
10. <span data-ttu-id="30f0c-139">**PR_SURNAME**</span><span class="sxs-lookup"><span data-stu-id="30f0c-139">**PR_SURNAME**</span></span>
    
<span data-ttu-id="30f0c-140">收件人3、4和5的收件人列表包括按以下顺序列出的属性:</span><span class="sxs-lookup"><span data-stu-id="30f0c-140">The recipient list for recipients 3, 4, and 5 includes properties in the following order:</span></span>
  
1. <span data-ttu-id="30f0c-141">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="30f0c-141">**PR_ADDRTYPE**</span></span>
    
2. <span data-ttu-id="30f0c-142">**PR_ENTRYID**</span><span class="sxs-lookup"><span data-stu-id="30f0c-142">**PR_ENTRYID**</span></span>
    
3. <span data-ttu-id="30f0c-143">**PR_HOME_TELEPHONE_NUMBER**</span><span class="sxs-lookup"><span data-stu-id="30f0c-143">**PR_HOME_TELEPHONE_NUMBER**</span></span>
    
4. <span data-ttu-id="30f0c-144">**PR_DISPLAY_NAME**</span><span class="sxs-lookup"><span data-stu-id="30f0c-144">**PR_DISPLAY_NAME**</span></span>
    
5. <span data-ttu-id="30f0c-145">**PR_SEARCH_KEY**</span><span class="sxs-lookup"><span data-stu-id="30f0c-145">**PR_SEARCH_KEY**</span></span>
    
6. <span data-ttu-id="30f0c-146">**PR_EMAIL_ADDRESS**</span><span class="sxs-lookup"><span data-stu-id="30f0c-146">**PR_EMAIL_ADDRESS**</span></span>
    
7. <span data-ttu-id="30f0c-147">**PR_ADDRTYPE**</span><span class="sxs-lookup"><span data-stu-id="30f0c-147">**PR_ADDRTYPE**</span></span>
    
<span data-ttu-id="30f0c-148">作为调用 IAddrBook 的替代方法 **::P reparerecips**若要使用属性, 请调用每个收件人的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法, 并在必要时调用其[IMAPIProp:: SetProps](imapiprop-setprops.md)方法。</span><span class="sxs-lookup"><span data-stu-id="30f0c-148">As an alternative to calling **IAddrBook::PrepareRecips** to work with properties, call each recipient's [IMAPIProp::GetProps](imapiprop-getprops.md) method and, if necessary, its [IMAPIProp::SetProps](imapiprop-setprops.md) method.</span></span> <span data-ttu-id="30f0c-149">当只涉及一个收件人时, 一种方法就是令人满意。</span><span class="sxs-lookup"><span data-stu-id="30f0c-149">When only one recipient is involved, either technique is satisfactory.</span></span> <span data-ttu-id="30f0c-150">但是, 当涉及多个收件人时, 调用**PrepareRecips**而不是**IMAPIProp**方法可节省时间, 并且, 如果您正在远程操作, 很多远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="30f0c-150">However, when multiple recipients are involved, calling **PrepareRecips** rather than the **IMAPIProp** methods saves time and, if you are operating remotely, many remote procedure calls.</span></span> <span data-ttu-id="30f0c-151">**PrepareRecips**处理单个呼叫中的所有收件人, 而**GetProps**和**SetProps**为每个收件人发出一个呼叫。</span><span class="sxs-lookup"><span data-stu-id="30f0c-151">**PrepareRecips** processes all recipients in a single call whereas **GetProps** and **SetProps** make one call for each recipient.</span></span> 
  

