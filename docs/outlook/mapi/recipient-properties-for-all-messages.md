---
title: 所有邮件的收件人属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 18c96796-f38d-4058-9c51-9c5a14990846
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ceda6b1d551af973df08f8069d1eaf543085a375
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22574215"
---
# <a name="recipient-properties-for-all-messages"></a><span data-ttu-id="06d72-103">所有邮件的收件人属性</span><span class="sxs-lookup"><span data-stu-id="06d72-103">Recipient Properties for All Messages</span></span>

  
  
<span data-ttu-id="06d72-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="06d72-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="06d72-105">以下属性的所有邮件的收件人，通常有。</span><span class="sxs-lookup"><span data-stu-id="06d72-105">The following properties are typically present for all message recipients.</span></span> <span data-ttu-id="06d72-106">**PR_EMAIL_ADDRESS**和**PR_SEARCH_KEY**是可选的;所有其他属性都是必需的。</span><span class="sxs-lookup"><span data-stu-id="06d72-106">**PR_EMAIL_ADDRESS** and **PR_SEARCH_KEY** are optional; all of the other properties are required.</span></span> 
  
<span data-ttu-id="06d72-107">**表标题**</span><span class="sxs-lookup"><span data-stu-id="06d72-107">**Table Title**</span></span>

|<span data-ttu-id="06d72-108">**属性**</span><span class="sxs-lookup"><span data-stu-id="06d72-108">**Property**</span></span>|<span data-ttu-id="06d72-109">**说明**</span><span class="sxs-lookup"><span data-stu-id="06d72-109">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="06d72-110">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="06d72-110">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="06d72-111">包含消息的用户的电子邮件地址类型，如 SMTP。</span><span class="sxs-lookup"><span data-stu-id="06d72-111">Contains the messaging user's email address type, such as SMTP.</span></span>  <br/> |
|<span data-ttu-id="06d72-112">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="06d72-112">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="06d72-113">包含给定的 MAPI 对象的显示名称。</span><span class="sxs-lookup"><span data-stu-id="06d72-113">Contains the display name for a given MAPI object.</span></span>  <br/> |
|<span data-ttu-id="06d72-114">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="06d72-114">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="06d72-115">包含用于将图标与特定的表格行关联的值。</span><span class="sxs-lookup"><span data-stu-id="06d72-115">Contains a value used to associate an icon with a particular row of a table.</span></span>  <br/> |
|<span data-ttu-id="06d72-116">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="06d72-116">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="06d72-117">包含消息的用户的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="06d72-117">Contains the messaging user's email address.</span></span>  <br/> |
|<span data-ttu-id="06d72-118">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="06d72-118">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="06d72-119">包含用于打开和编辑特定的 MAPI 对象的属性的 MAPI 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="06d72-119">Contains a MAPI entry identifier used to open and edit properties of a particular MAPI object.</span></span>  <br/> |
|<span data-ttu-id="06d72-120">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="06d72-120">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="06d72-121">包含对象的类型。</span><span class="sxs-lookup"><span data-stu-id="06d72-121">Contains the type of an object.</span></span>  <br/> |
|<span data-ttu-id="06d72-122">**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="06d72-122">**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="06d72-123">包含一个标识用于搜索的相关的对象的二进制相当关键字。</span><span class="sxs-lookup"><span data-stu-id="06d72-123">Contains a binary-comparable key that identifies correlated objects for a search.</span></span>  <br/> |
   

