---
title: SMTP 地址
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 42015740-a94f-4628-bf32-b7fc2fdb9ff6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fb4402100891df8b27c8d26900a4acd05f4183e3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419623"
---
# <a name="smtp-addresses"></a><span data-ttu-id="f9dde-103">SMTP 地址</span><span class="sxs-lookup"><span data-stu-id="f9dde-103">SMTP Addresses</span></span>

  
  
<span data-ttu-id="f9dde-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f9dde-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f9dde-105">SMTP 电子邮件地址的格式是在 RFC 822 中定义的。</span><span class="sxs-lookup"><span data-stu-id="f9dde-105">The format of SMTP email addresses is defined in RFC 822.</span></span> <span data-ttu-id="f9dde-106">MAPI 组件应处理符合该标准的任何地址。</span><span class="sxs-lookup"><span data-stu-id="f9dde-106">MAPI components should handle any address that complies with that standard.</span></span> <span data-ttu-id="f9dde-107">但是, 有一种特定形式的 RFC 822 地址, 可以最大限度地编码 MAPI 地址:</span><span class="sxs-lookup"><span data-stu-id="f9dde-107">However, there is a particular form of RFC 822 address that best encodes MAPI addresses:</span></span>
  
 <span data-ttu-id="f9dde-108">_显示-名称_**\<** _电子邮件地址_**\>**</span><span class="sxs-lookup"><span data-stu-id="f9dde-108">_display-name_ **\<** _email-address_ **\>**</span></span>
  
<span data-ttu-id="f9dde-109">尖括号以文本形式包含。</span><span class="sxs-lookup"><span data-stu-id="f9dde-109">The angle brackets are included as literals.</span></span> <span data-ttu-id="f9dde-110">空白在显示名称中是通用的;不需要报价。</span><span class="sxs-lookup"><span data-stu-id="f9dde-110">Blanks are common in display names; they need not be quoted.</span></span> <span data-ttu-id="f9dde-111">典型的地址可能如下所示, 属于 RFC 1521 的合著者之一:</span><span class="sxs-lookup"><span data-stu-id="f9dde-111">A typical address might look like this one, which belongs to one of the coauthors of RFC 1521:</span></span>
  
<span data-ttu-id="f9dde-112">Nathaniel Borenstein \<nsb@bellcore.com\></span><span class="sxs-lookup"><span data-stu-id="f9dde-112">Nathaniel Borenstein \<nsb@bellcore.com\></span></span>
  
<span data-ttu-id="f9dde-113">如果显示名称包含在 SMTP 地址中有特殊含义的字符 (如\<或 @), 则应使用双引号将整个显示名称括起来。</span><span class="sxs-lookup"><span data-stu-id="f9dde-113">If the display name contains characters that have special meaning in SMTP addresses, such as \< or @, the entire display name should be enclosed in double quotes.</span></span> <span data-ttu-id="f9dde-114">在出站邮件中, 如果电子邮件地址的总长度加上显示名称超过255个字符, 则应删除显示名称。</span><span class="sxs-lookup"><span data-stu-id="f9dde-114">On outbound mail, if the total length of the email address plus display name exceeds 255 characters, the display name should be dropped.</span></span>
  
<span data-ttu-id="f9dde-115">SMTP 地址的各个部分映射到 MAPI 属性, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="f9dde-115">The parts of an SMTP address map into MAPI properties as follows:</span></span>
  
|<span data-ttu-id="f9dde-116">**SMTP 地址组件**</span><span class="sxs-lookup"><span data-stu-id="f9dde-116">**SMTP address component**</span></span>|<span data-ttu-id="f9dde-117">**MAPI 属性**</span><span class="sxs-lookup"><span data-stu-id="f9dde-117">**MAPI property**</span></span>|
|:-----|:-----|
| <span data-ttu-id="f9dde-118">_显示-_ 所有收件人的姓名</span><span class="sxs-lookup"><span data-stu-id="f9dde-118">_display-name_ for all recipients</span></span>  <br/> |<span data-ttu-id="f9dde-119">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f9dde-119">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="f9dde-120">"_显示-_ 源中的名称" 字段</span><span class="sxs-lookup"><span data-stu-id="f9dde-120">_display-name_ for From field</span></span>  <br/> |<span data-ttu-id="f9dde-121">**PR_SENDER_NAME**([PidTagSenderName](pidtagsendername-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f9dde-121">**PR_SENDER_NAME** ([PidTagSenderName](pidtagsendername-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="f9dde-122">"_显示-_ 发件人的名称" 字段</span><span class="sxs-lookup"><span data-stu-id="f9dde-122">_display-name_ for Sender field</span></span>  <br/> |<span data-ttu-id="f9dde-123">**PR_SENT_REPRESENTING_NAME**([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f9dde-123">**PR_SENT_REPRESENTING_NAME** ([PidTagSentRepresentingName](pidtagsentrepresentingname-canonical-property.md))</span></span>  <br/> |
| <span data-ttu-id="f9dde-124">_电子邮件地址_</span><span class="sxs-lookup"><span data-stu-id="f9dde-124">_email-address_</span></span> <br/> |<span data-ttu-id="f9dde-125">**PR_EMAIL_ADDRESS**([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f9dde-125">**PR_EMAIL_ADDRESS** ([PidTagEmailAddress](pidtagemailaddress-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="f9dde-126">隐式, 始终为 "SMTP"</span><span class="sxs-lookup"><span data-stu-id="f9dde-126">implicit, always "SMTP"</span></span>  <br/> |<span data-ttu-id="f9dde-127">**PR_ADDRTYPE**([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="f9dde-127">**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md))</span></span>  <br/> |
   
<span data-ttu-id="f9dde-128">如果入站邮件上的地址没有显示名称, 则应改为使用整个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="f9dde-128">If there is no display name for an address on inbound mail, the entire email address should be used instead.</span></span> <span data-ttu-id="f9dde-129">地址类型始终为 SMTP。</span><span class="sxs-lookup"><span data-stu-id="f9dde-129">The address type is always SMTP.</span></span>
  
<span data-ttu-id="f9dde-130">收件人属性是从 MAPI 邮件的收件人表中获取的;发件人属性是从邮件本身获取的。</span><span class="sxs-lookup"><span data-stu-id="f9dde-130">Recipient properties are taken from the MAPI message's recipient table; sender properties are taken from the message itself.</span></span>
  

