---
title: SMTP 地址
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 42015740-a94f-4628-bf32-b7fc2fdb9ff6
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 9bc77e3226066dc88bbaf4f4efc324825add8919
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778839"
---
# <a name="smtp-addresses"></a><span data-ttu-id="bef13-103">SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="bef13-103">SMTP Addresses</span></span>

  
  
<span data-ttu-id="bef13-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="bef13-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="bef13-105">RFC 822 中定义的 SMTP 电子邮件地址的格式。</span><span class="sxs-lookup"><span data-stu-id="bef13-105">The format of SMTP email addresses is defined in RFC 822.</span></span> <span data-ttu-id="bef13-106">MAPI 组件应处理任何符合该标准的地址。</span><span class="sxs-lookup"><span data-stu-id="bef13-106">MAPI components should handle any address that complies with that standard.</span></span> <span data-ttu-id="bef13-107">但是，没有特定窗体的最佳编码 MAPI 地址的 RFC 822 地址：</span><span class="sxs-lookup"><span data-stu-id="bef13-107">However, there is a particular form of RFC 822 address that best encodes MAPI addresses:</span></span>
  
 <span data-ttu-id="bef13-108">_显示名称_**\<** _电子邮件地址_**\>**</span><span class="sxs-lookup"><span data-stu-id="bef13-108">_display-name_ **\<** _email-address_ **\>**</span></span>
  
<span data-ttu-id="bef13-109">尖括号都作为包含文字。</span><span class="sxs-lookup"><span data-stu-id="bef13-109">The angle brackets are included as literals.</span></span> <span data-ttu-id="bef13-110">空值共有中的显示名称;他们不需要被引用。</span><span class="sxs-lookup"><span data-stu-id="bef13-110">Blanks are common in display names; they need not be quoted.</span></span> <span data-ttu-id="bef13-111">典型的地址可能类似于如下，其所属的 RFC 1521 coauthors 之一：</span><span class="sxs-lookup"><span data-stu-id="bef13-111">A typical address might look like this one, which belongs to one of the coauthors of RFC 1521:</span></span>
  
<span data-ttu-id="bef13-112">Nathaniel Borenstein \<nsb@bellcore.com\></span><span class="sxs-lookup"><span data-stu-id="bef13-112">Nathaniel Borenstein \<nsb@bellcore.com\></span></span>
  
<span data-ttu-id="bef13-113">如果显示名称包含字符具有特殊含义 SMTP 地址，如\<或 @，整个的显示名称应括在双引号中。</span><span class="sxs-lookup"><span data-stu-id="bef13-113">If the display name contains characters that have special meaning in SMTP addresses, such as \< or @, the entire display name should be enclosed in double quotes.</span></span> <span data-ttu-id="bef13-114">在出站邮件，如加号的电子邮件地址的总长度显示名称超过 255 个字符，应删除的显示名称。</span><span class="sxs-lookup"><span data-stu-id="bef13-114">On outbound mail, if the total length of the email address plus display name exceeds 255 characters, the display name should be dropped.</span></span>
  
<span data-ttu-id="bef13-115">SMTP 地址的部分映射到 MAPI 属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="bef13-115">The parts of an SMTP address map into MAPI properties as follows:</span></span>
  
|<span data-ttu-id="bef13-116">**SMTP 地址组件**</span><span class="sxs-lookup"><span data-stu-id="bef13-116">**SMTP address component**</span></span>|<span data-ttu-id="bef13-117">**MAPI 属性**</span><span class="sxs-lookup"><span data-stu-id="bef13-117">**MAPI property**</span></span>|
|:-----|:-----|
| <span data-ttu-id="bef13-118">所有收件人的的_显示名称_</span><span class="sxs-lookup"><span data-stu-id="bef13-118">_display-name_ for all recipients</span></span>  <br/> |<span data-ttu-id="bef13-119">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="bef13-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="bef13-120">_显示名称_的字段</span><span class="sxs-lookup"><span data-stu-id="bef13-120">_display-name_ for From field</span></span>  <br/> |<span data-ttu-id="bef13-121">**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="bef13-121">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="bef13-122">发件人字段的_显示名称_</span><span class="sxs-lookup"><span data-stu-id="bef13-122">_display-name_ for Sender field</span></span>  <br/> |<span data-ttu-id="bef13-123">**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="bef13-123">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="bef13-124">_电子邮件地址_</span><span class="sxs-lookup"><span data-stu-id="bef13-124">_email-address_</span></span> <br/> |<span data-ttu-id="bef13-125">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="bef13-125">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="bef13-126">隐式，始终"SMTP"</span><span class="sxs-lookup"><span data-stu-id="bef13-126">implicit, always "SMTP"</span></span>  <br/> |<span data-ttu-id="bef13-127">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="bef13-127">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |
   
<span data-ttu-id="bef13-128">如果没有显示名称的入站邮件上的地址，应使用的整个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="bef13-128">If there is no display name for an address on inbound mail, the entire email address should be used instead.</span></span> <span data-ttu-id="bef13-129">地址类型始终是 SMTP。</span><span class="sxs-lookup"><span data-stu-id="bef13-129">The address type is always SMTP.</span></span>
  
<span data-ttu-id="bef13-130">收件人属性均摘自的 MAPI 邮件收件人表;发件人属性来自消息本身。</span><span class="sxs-lookup"><span data-stu-id="bef13-130">Recipient properties are taken from the MAPI message's recipient table; sender properties are taken from the message itself.</span></span>
  

